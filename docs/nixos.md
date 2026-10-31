# 在 NixOS 与 Nix 上使用 TwinDesk

TwinDesk 通过 `flake.nix` 为 NixOS 和 Nix 提供一等支持。

---

## 🚀 用 Nix Flakes 直接运行

无需全系统安装即可运行 TwinDesk：

```sh
nix run github:InukaAsith/TwinDesk
# 或在本地克隆目录中：
nix run .
```

进入包含所有所需 C 库、Node.js、Electron 与 Python GStreamer typelib 的开发环境：

```sh
nix develop
```

---

## ❄️ NixOS 系统配置

把 TwinDesk 加入系统 flake 输入并启用 NixOS 模块：

### `flake.nix`
```nix
{
  inputs = {
    nixpkgs.url = "github:NixOS/nixpkgs/nixos-unstable";
    twindesk.url = "github:InukaAsith/TwinDesk"; # 或本地检出
  };

  outputs = { self, nixpkgs, twindesk, ... }: {
    nixosConfigurations.myhostname = nixpkgs.lib.nixosSystem {
      system = "x86_64-linux";
      modules = [
        twindesk.nixosModules.default
        {
          # 启用 TwinDesk
          programs.twindesk = {
            enable = true;
            user = "yourusername"; # 自动把你的用户加入 input 与 uinput 组
          };
        }
      ];
    };
  };
}
```

> **注意：** 模块同时接受 `programs.twindesk` 与 `services.twindesk` 两种写法。

---

## ⚙️ 模块选项

| 选项 | 类型 | 默认值 | 说明 |
|---|---|---|---|
| `programs.twindesk.enable` | `bool` | `false` | 启用 TwinDesk 应用及系统集成。 |
| `programs.twindesk.package` | `package` | `twindesk` | 使用的 TwinDesk 包 derivation。 |
| `programs.twindesk.user` | `nullOr str` | `null` | 你的用户名。指定后会把该用户加入 `input` 和 `uinput` 组。 |
| `programs.twindesk.openFirewall` | `bool` | `true` | 自动放行 TCP `47800`（设备间通信）与 UDP `47801`（发现）、`5353`（mDNS）。 |
| `programs.twindesk.uinput` | `bool` | `true` | 启用 `hardware.uinput.enable`，并为 Wayland 下的输入捕获与注入配置 udev 规则。 |
| `programs.twindesk.enableWifiDirect` | `bool` | `true` | 创建带 `CAP_NET_ADMIN` 的 `/run/wrappers/bin/twindesk-wifiap`，使 Wi-Fi Direct 接口管理无需 root 密码即可工作。 |

---

## 🛠️ 功能在 NixOS 上的实现方式

### 1. Wayland 鼠标与键盘（KVM）
Wayland 下，输入捕获与注入通过 `/dev/input/event*` 和 `/dev/uinput` 工作。
- NixOS 模块会自动启用 `hardware.uinput.enable = true;` 并配置 uinput 的 `/etc/udev/rules.d`。
- 确保你的用户同时属于 `input` 和 `uinput` 组（设置 `programs.twindesk.user = "yourusername";` 时会自动配置）。
- 如果用户刚被加入这些组，记得注销再登录。

### 2. Wi-Fi Direct 与热点链路
在支持的无线网卡上创建辅助接入点接口需要 `CAP_NET_ADMIN`。
- NixOS 模块会自动配置安全能力包装：
  ```nix
  security.wrappers.twindesk-wifiap = {
    source = "${pkg}/libexec/twindesk-wifiap";
    capabilities = "cap_net_admin+ep";
    owner = "root";
    group = "root";
  };
  ```
- TwinDesk 会自动检测 `/run/wrappers/bin/twindesk-wifiap`，连接时无需 `pkexec` 提示。

### 3. 扩展屏（虚拟显示器）
- **GNOME on Wayland**：使用 Mutter 的虚拟显示器门户。包包装会自动捆绑并配置带 `pygobject` 和 `gst-python` 的 Python 3，包含全部 GStreamer PipeWire 插件与 GI typelib。
- **X11**：模块会自动把 Polkit 策略（`org.twindesk.linux.connector.policy`）和连接器脚本（`twindesk-connector`）安装到 `/run/current-system/sw`，输出切换开箱即用。

### 4. 文件共享与远程终端
- **OpenSSH（终端）**：在 NixOS 配置中启用 `services.openssh.enable = true;`。
- **Samba（文件夹共享）**：在 NixOS 配置中启用 `services.samba.enable = true;`。