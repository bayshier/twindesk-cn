<p align="center">
  <img src=".github/assets/icon.png" width="112" alt="TwinDesk 图标">
</p>

<h1 align="center"><a href="https://twin-desk.vercel.app">TwinDesk</a></h1>

<p align="center">
  <b>你的所有电脑和手机，共用一张桌面。</b><br>
  屏幕、应用、文件、剪贴板、摄像头、通话、短信、通知、鼠标和键盘，在 Mac、Windows、Linux 与 Android 之间共享。<br>
  免费开源。无需账号，不走云端，甚至不需要共用网络。
</p>

<p align="center">
  <a href="#download"><b>⬇️ 下载 2.4</b></a> ·
  <a href="https://twin-desk.vercel.app"><b>官网</b></a> ·
  <a href="#-new-in-23"><b>新功能</b></a> ·
  <a href="#-get-started"><b>开始使用</b></a> ·
  <a href="#how-it-works"><b>工作原理</b></a>
</p>

<p align="center">
  <img alt="版本" src="https://img.shields.io/github/v/release/InukaAsith/TwinDesk?label=version&color=4b8bff">
  <img alt="macOS 13+" src="https://img.shields.io/badge/macOS-13%2B-black">
  <img alt="Windows 10/11" src="https://img.shields.io/badge/Windows-10%20%7C%2011-0078d4">
  <img alt="Linux X11 与 Wayland" src="https://img.shields.io/badge/Linux-X11%20%7C%20Wayland-f0a30a">
  <img alt="Android 10+" src="https://img.shields.io/badge/Android-10%2B-3ddc84">
  <img alt="许可证：GPL-3.0" src="https://img.shields.io/badge/license-GPL--3.0-blue">
  <a href="https://github.com/inukaasith/twindesk/releases"><img src="https://img.shields.io/github/downloads/inukaasith/twindesk/total" alt="下载量"></a>
</p>

> [!NOTE]
> 本仓库是 [InukaAsith/TwinDesk](https://github.com/InukaAsith/TwinDesk) 的中文汉化版：README、贡献指南与 NixOS 使用文档已翻译为中文，代码与上游保持同步。下载链接、版本号以[官方仓库](https://github.com/InukaAsith/TwinDesk/releases)为准。英文版入口见 [README.en.md](README.en.md)。
>
> `docs/` 下四份工程设计文档（`mesh.md`、`screen-mesh.md`、`multi-device.md`、`rezume.md`）保留英文原文：它们面向参与开发的读者，逐条引用源码文件与通信协议细节，保留原文便于与上游对照。

<p align="center">
  <img src=".github/assets/hero.jpg" alt="一台 Mac 的扩展屏显示在另一台 Mac 的窗口里，Mac 桌面扩展到平板，手机上运行着 TwinDesk" width="100%">
</p>

你的设备各自干活都挺好，凑到一起就一团糟。TwinDesk 就是来解决这个问题的。
把 **Mac 和 Windows PC** 并排一放，用一套鼠标键盘同时操作。在 Mac 上打开 PC 的应用。把旧笔记本或你的 **Android 平板**变成第二块屏幕。在电脑上接听**手机来电、回短信**，视频通话里用手机的**摄像头**，在一台设备上复制、到另一台直接粘贴。

- **任意组合。** Mac ↔ Windows、Mac ↔ Mac、PC ↔ PC、Linux ↔ 任何设备、Android ↔ 任何电脑。或者用 [TwinDesk Mesh](#-twindesk-mesh-every-device-at-once) 把它们全部连成一个整体。
- **任何环境。** 同一个 Wi-Fi、一根 USB 线，或者干脆没有共用网络：蓝牙加自建的直连 Wi-Fi。
- **无账号、无云端。** 设备之间只在加密链路里互相通信。
- **只开你要的。** 每个功能默认关闭，没打开之前连加载都不会加载。

<table>
<tr>
<td width="33%" valign="top">

### 💻 [电脑互联](#-computer-to-computer)
一套鼠标键盘 · 第二块屏 · 对方电脑的应用开在独立窗口 · 文件 · 剪贴板 · **摄像头** · 声音 · 终端

</td>
<td width="33%" valign="top">

### 📱 [手机与平板](#-phone-and-tablet)
通话 · 短信 · 照片 · 文件 · **摄像头** · **遥控与手柄** · 屏幕和应用开在窗口里 · 平板当第二屏

</td>
<td width="33%" valign="top">

### 📡 [连接方式](#-connections)
同一 Wi-Fi · USB 线 · **蓝牙** · 按需建立的 **Wi-Fi Direct** 与**热点**链路 · 自动选择、自动切换

</td>
</tr>
<tr>
<td width="33%" valign="top">

### 🚀 [开始使用](#-get-started)
下载 · 两端打开 · 输一次配对码 · 打开你要的功能 · [隐私](#隐私)：无账号、无遥测

</td>
<td width="33%" valign="top">

### 🐧 [Linux](#linux) 与 🤖 [Android](#android-in-detail) 细节
X11 与 Wayland · 通过 Samba 共享文件夹 · 手机应用逐页说明 · [无线调试](#wireless-debugging)只配一次

</td>
<td width="33%" valign="top">

### 🛠 [技术细节](#how-it-works)
[工作原理](#how-it-works) · 在 macOS、Windows、Linux、NixOS 与 Android 上[构建运行](#build-and-run) · [GitHub Actions](#github-actions)

</td>
</tr>
</table>

<a name="download"></a>

## ⬇️ 下载

<table>
<tr>
<td width="25%" align="center" valign="top">

**🍎 macOS**<br><sub>13 Ventura 或更高</sub>

<a href="https://github.com/InukaAsith/TwinDesk/releases/download/v2.4.0/TwinDesk-2.4.0-arm64.dmg"><img src="https://img.shields.io/badge/Apple_Silicon-.dmg-000000?style=for-the-badge" alt="macOS, Apple Silicon"></a><br>
<a href="https://github.com/InukaAsith/TwinDesk/releases/download/v2.4.0/TwinDesk-2.4.0-x64_Intel.dmg"><img src="https://img.shields.io/badge/Intel-.dmg-555555?style=for-the-badge" alt="macOS, Intel"></a>

</td>
<td width="25%" align="center" valign="top">

**🪟 Windows**<br><sub>10 与 11</sub>

<a href="https://github.com/InukaAsith/TwinDesk/releases/download/v2.4.0/TwinDesk-Setup-2.4.0.exe"><img src="https://img.shields.io/badge/x64-Installer-0078d4?style=for-the-badge" alt="Windows, x64"></a><br>
<a href="https://github.com/InukaAsith/TwinDesk/releases/download/v2.4.0/TwinDesk-Setup-2.4.0-arm64.exe"><img src="https://img.shields.io/badge/ARM64-Installer-005a9e?style=for-the-badge" alt="Windows on ARM"></a>

</td>
<td width="25%" align="center" valign="top">

**🐧 Linux**<br><sub>X11 与 Wayland，x86_64</sub>

<a href="https://github.com/InukaAsith/TwinDesk/releases/download/v2.4.0/TwinDesk-2.4.0-amd64.deb"><img src="https://img.shields.io/badge/Debian_·_Ubuntu-.deb-d70a53?style=for-the-badge" alt="Linux, .deb"></a><br>
<a href="https://github.com/InukaAsith/TwinDesk/releases/download/v2.4.0/TwinDesk-2.4.0-x86_64.AppImage"><img src="https://img.shields.io/badge/Any_distro-AppImage-f0a30a?style=for-the-badge" alt="Linux, AppImage"></a><br>
<a href="https://github.com/InukaAsith/TwinDesk/releases/download/v2.4.0/twindesk-bin-2.4.0-1-x86_64.pkg.tar.zst"><img src="https://img.shields.io/badge/Arch-pkg.tar.zst-1793d1?style=for-the-badge" alt="Linux, Arch 包"></a><br>
<sub>NixOS：<code>nix run github:InukaAsith/TwinDesk</code>（<a href="#nixos--nix-flakes">详见</a>）</sub>

</td>
<td width="25%" align="center" valign="top">

**🤖 Android**<br><sub>10 或更高，手机与平板</sub>

<a href="https://github.com/InukaAsith/TwinDesk/releases/download/v2.4.0/TwinDesk-2.4.0.apk"><img src="https://img.shields.io/badge/Phone_app-.apk-3ddc84?style=for-the-badge" alt="Android 应用"></a><br>
<a href="https://github.com/InukaAsith/TwinDesk/releases/download/v2.4.0/TwinDesk-2.4.0-full.apk"><img src="https://img.shields.io/badge/Full_app-.apk-1b8a4c?style=for-the-badge" alt="Android 完整版应用"></a><br>
<sub>完整版包含通知、短信与无障碍服务；电脑可以通过无线调试帮你装</sub>

</td>
</tr>
</table>

<p align="center">🍺 macOS 上也可用 <b>Homebrew</b>：<code>brew install --cask inukaasith/twindesk/twindesk</code><br>
<sub>用 <code>brew upgrade --cask twindesk</code> 升级：如果 TwinDesk 正在运行，升级后它会自己重新打开——这样只用它来操作的那台 Mac 就能把鼠标拿回来。<a href="https://github.com/InukaAsith/homebrew-twindesk">tap</a> 会跟随每次发布更新。</sub></p>

<a name="first-launch"></a>

<details>
<summary><b>⚠️ 首次启动：应用没有代码签名</b> <sub>在 macOS、Windows 和 Android 上如何放行</sub></summary>

TwinDesk 是免费的，没有购买 Apple Developer ID 或 Windows 代码签名证书，所以
macOS 和 Windows 不知道它是谁做的，打开前会询问一次。源码都在这里。

**🍎 macOS**

最省事的办法是用 **Homebrew**，装完就能直接打开：
`brew install --cask inukaasith/twindesk/twindesk`

从 .dmg 安装的话：

1. 把 TwinDesk 拖进「应用程序」并打开。macOS 提示无法验证 TwinDesk：点 **完成**
   （不要点「移到废纸篓」）。
2. 打开 **系统设置 › 隐私与安全性**，向下滚动到「安全性」，在"已阻止 TwinDesk"旁边
   点 **仍要打开**。输入密码，再点一次 **仍要打开**。

只需做一次，之后更新可以正常打开。如果 macOS 说 TwinDesk **已损坏，无法打开**，其实并没有：
在终端里执行下面的命令，然后重新打开：

```sh
xattr -dr com.apple.quarantine /Applications/TwinDesk.app
```

**🪟 Windows**

1. 如果浏览器提示该文件不常被下载，选择 **保留**（Edge 中：**⋯ › 保留 › 显示更多 › 仍然保留**）。
2. 安装器显示 **Windows 已保护你的电脑**（SmartScreen）时，点 **更多信息**，再点
   **仍要运行**。

Windows 11 如果开启了 **智能应用控制**，未签名的应用会被直接拦截，连"仍要运行"都没有。
唯一的办法是关掉它（Windows 安全中心 › 应用和浏览器控制 › 智能应用控制设置），而在很多
Windows 11 版本上，关掉之后不重装系统就再也开不回来。

**🤖 Android**

1. 打开下载好的 .apk。Android 会询问是否允许你的浏览器或「文件」应用 **安装未知应用**：
   点 **设置**，打开 **允许来自此来源**，返回后点 **安装**。
2. 如果 Play Protect 提示开发者未知，点 **更多详情 › 仍然安装**。

**完整版应用**（通知、短信与无障碍）最省事的安装方式是让电脑通过[无线调试](#wireless-debugging)
安装（手机页面 › 来自手机的通知）：这样 Android 才允许你打开那些权限。手动安装的话，
Play Protect 可能会拦截；而且 Android 13 及更高版本会把通知使用权和无障碍服务置灰为
**受限设置**：打开 **设置 › 应用 › TwinDesk**，点 **⋮ › 允许受限设置**，再打开它们。

</details>

<p align="center"><sub>所有文件和旧版本都在 <a href="https://github.com/InukaAsith/TwinDesk/releases">Releases 页面</a>。</sub></p>

---

<a name="-new-in-23"></a>
# ✨ 2.3 版新功能

<p align="center">
  <img src=".github/assets/v23-whats-new.jpg" alt="TwinDesk 2.3：手机现在是你的摄像头、遥控器和游戏手柄" width="100%">
</p>

你的手机现在可以是**摄像头、遥控器和游戏手柄**。在任何视频通话里用它的摄像头，窝在沙发上
操控电脑，或者把它当手柄玩游戏。图片和截图可以在所有屏幕之间复制，还能用快捷键把指针锁定在
一台电脑上。

| | 新功能 | |
|---|---|---|
| 📷 | **摄像头。** 手机的摄像头（或另一台电脑的），可以显示在窗口里，也可以作为 Zoom、Teams、Meet 的摄像头 | [详情](#-phone-camera) |
| 🎮 | **遥控与手柄。** 给电脑用的触控板和键盘，以及电脑识别为真实手柄的虚拟手柄 | [详情](#-remote-and-gamepad) |
| 🖼 | **剪贴板里的图片。** 在 PC 上截屏，粘到 Mac 或手机上 | [详情](#-shared-clipboard) |
| 🔒 | **指针锁定。** 按 Scroll Lock 把指针留在当前电脑上 | [详情](#-one-mouse-and-keyboard) |
| 🎵 | **媒体控制。** 看手机上在放什么，在电脑上播放、暂停、切歌 | [详情](#-media-controls-and-phone-sound) |
| 🪶 | **更轻了。** 所有功能默认关闭，驻留托盘时内存占用约减少一半 | [详情](#-also-new-in-23) |

<a name="-also-new-in-23"></a>
## ➕ 2.3 版的其他更新

- **全新安装时所有功能都关闭**，在打开之前不会加载任何相关模块。升级会保留你的设置。
- **收进托盘或菜单栏时，窗口也会彻底释放：** 一台 Windows PC 的内存占用从约 240 MB 降到约 125 MB。
- **<kbd>Ctrl+Alt+V</kbd> / <kbd>⌃⌥V</kbd> 可以直接把文件粘贴到前台应用**，比如聊天窗口或邮件，而不只是粘贴到文件夹。
- **可以选择接收文件的保存位置**（通用 › 接收的文件），Windows 和 Linux 现在和 Mac 一样。
- **手机窗口：** 在 WhatsApp、Instagram 和 Telegram 里按 Enter 直接发送；Windows 上控制按钮收进侧边栏，并带有旋转和截图按钮。
- **把手机自己的屏幕显示在电脑上**，从手机的「屏幕」页面启动。
- **触控板模式：** 电脑屏幕在手机上显示时，滑动移动指针，轻点即点击。
- **手机电量：** 锁屏的手机不会再自己亮屏，设备发现也不会再让它保持唤醒。
- **无线调试可以在电脑离开时自动关闭**（通用 › 在手机上允许）。
- **手机上的指针**在通知栏下拉和设置页面上也会显示。
- **与手机之间的蓝牙和 Wi-Fi Direct 更稳定**：会优先使用 Android Studio 或 scrcpy 自带的 adb，而不是内置的 adb，两者不再互相踢掉对方。
- **单独的 Intel Mac 版本下载**，以及可以用 Developer ID 签名和公证的构建。

感谢所有为这个版本提交 pull request 的人：见[致谢](#thanks)。

<sub>更早的版本：2.2 带来了 [TwinDesk Mesh](#-twindesk-mesh-every-device-at-once)，2.1 带来了
[蓝牙与 Wi-Fi Direct](#-connections) 以及手机的[通话、短信、照片和文件](#-calls-and-messages)。
每个版本的说明都在 [Releases 页面](https://github.com/InukaAsith/TwinDesk/releases)。</sub>

---

<a name="-computer-to-computer"></a>
# 💻 电脑与电脑

<p align="center">
  <img src=".github/assets/mac-windows.jpg" alt="一台 Mac 连接到 Windows PC，Mac 上列出了 PC 的应用" width="100%">
</p>

每个平台都是同一个应用，所以 Mac 和 PC 配对，跟两台 Mac 配对完全一样。

<a name="-one-mouse-and-keyboard"></a>
## 🖱 一套鼠标键盘

把指针推出屏幕边缘，就能**接着在另一台电脑上操作**，就像它们本来就是一台。键盘跟着指针走。
触控板手势（切换空间、双指缩放、显示桌面）也能用，双击热键可以让一切回到原位。还可以设置
对方电脑在哪个方向、边缘阻力和指针速度。

**指针锁定**（2.3 新增）把指针固定在它所在的电脑上，即使鼠标没插在这台电脑上也一样：按
**Scroll Lock**（Mac 上是 F14），或使用「指针」标签页、托盘 / 菜单栏里的开关。

<a name="-extended-display-and-remote-screen"></a>
## 🖥 扩展屏与远程屏幕

用**真正的虚拟显示器**把 Mac 扩展到 PC 或另一台 Mac 上，也可以镜像。或者把对方电脑的屏幕
放进一个窗口里，在窗口内操作。低延迟 H.264，提供*极速*和*流畅*两种画质，可选帧生成。

<p align="center">
  <img src=".github/assets/mac-screen-window.jpg" alt="MacBook Pro 的扩展屏显示在 Studio Mac 的窗口里，右侧是接收屏幕设置" width="100%">
</p>

<a name="-the-other-computers-apps"></a>
## 🪟 对方电脑的应用，开在自己的窗口里

在 **Mac 上打开 Windows 应用**（或在 PC 上打开 Mac 应用），它会得到**自己的窗口**，
有自己的 Dock 图标或开始菜单固定项。不是整个远程桌面，只是你需要的那一个应用，和本机的
应用并排。

<p align="center">
  <img src=".github/assets/mac-apps.jpg" alt="一台 Mac 上的国际象棋、时钟和计算器，在另一台 Mac 上以独立窗口运行" width="100%">
</p>

<a name="-camera-sharing"></a>
## 📷 摄像头共享

把对方电脑的摄像头显示在窗口里，或作为**所有应用都能选到的摄像头**：在 Zoom、Teams、Meet
或浏览器里选择 **TwinDesk Camera**。只有你在一台电脑上打开*允许 … 使用此摄像头*，它才会
共享摄像头，并且会弹窗告诉你谁在看。手机摄像头同理，见[手机摄像头](#-phone-camera)。

虚拟摄像头在第一次打开时安装：Windows 11 使用系统摄像头（一次管理员授权），Linux 使用
v4l2loopback（一次密码授权），Mac 上装入 **OBS Virtual Camera**（或 TwinDesk 自有的摄像头
扩展，需签名版本）。

<a name="-files-shared-folders-and-terminal"></a>
## 📁 文件、共享文件夹与终端

**把文件拖过屏幕边缘**，在任意位置放下；或者用 <kbd>⌃⌥C</kbd> 复制、<kbd>⌃⌥V</kbd> 粘贴
（Windows 和 Linux 上是 <kbd>Ctrl+Alt+C/V</kbd>），可以粘到文件夹，也可以直接粘进前台应用。
还可以从 macOS 的共享菜单或资源管理器的*发送到*发送，或**共享一个文件夹**，在对面显示为
网络驱动器。传输中的文件会显示**实时进度**。需要 shell？`ssh twindesk` 就能在对方电脑上
开一个，无需密码。

<p align="center">
  <img src=".github/assets/computers-files.jpg" alt="文件页面和终端页面" width="100%">
</p>

<a name="-shared-clipboard"></a>
## 📋 共享剪贴板

在一台电脑上复制，在另一台上粘贴，可以即时同步，也可以切过去时再同步。**图片**也能传
（2.3 新增），上限 10 MB：在 PC 上按 <kbd>Win+Shift+S</kbd> 截图，粘到 Mac 上。
来自密码管理器的内容会被跳过，「最近」列表保留你最近复制的几项，图片带预览。

<p align="center">
  <img src=".github/assets/computers-clipboard.jpg" alt="两台 Mac 的剪贴板历史里是同一段复制的文字" width="100%">
</p>

<a name="-notifications-sound-and-wake-on-lan"></a>
## 🔔 通知、声音与网络唤醒

在一台电脑上看到另一台电脑的通知（以系统原生通知显示），在一台电脑上听到另一台的声音。
用网络唤醒（Wake-on-LAN）唤醒睡眠中的电脑，你拨动的每个开关都由两端共享，并按设备对记住。

<a name="-more-than-two-devices"></a>
## 🔀 两台以上设备

想配多少台电脑和手机就配多少。**切换**把会话转移到附近另一台已配对设备，**接管**抢占一台
正被他人使用的设备，**断开**则放手。都可以在概览、菜单栏或托盘里操作。

<a name="-twindesk-mesh-every-device-at-once"></a>
## 🕸 TwinDesk Mesh：所有设备同时互联

<p align="center">
  <img src=".github/assets/v22-mesh-desk.jpg" alt="指针从 Windows PC 依次越过 MacBook 和 Linux 笔记本到达手机，下方是桌面地图" width="100%">
</p>

你的笔记本、台式机、角落里的 Linux 主机和你的手机，**同时连在一起**，彼此直连，中间没有
中心节点。

- **一套鼠标，所有屏幕。** 在地图上把设备排一次，指针就能从 PC 走到 Mac，再到 Linux 笔记本，最后到手机。
- **一个剪贴板。** 在任意一台复制，在任意另一台粘贴。最新的复制生效。
- **一个通知池。** 手机响了，所有电脑都会显示。
- **配对一次，加入全部。** 与其中一台电脑配对的新设备，会自动认识其余设备。

Mesh 在 Windows、Mac 和 Linux 上处于 **beta**：在**多设备**标签页里打开，随时可以关闭，
一切保持原样。只连两台设备的话用不上它。Mesh 还差这些：摄像头、剪贴板图片，以及把文件
一次拖给多台设备；手机一次只连一台电脑，Linux 只能通过同一 Wi-Fi 加入。

---

<a name="-phone-and-tablet"></a>
# 📱 手机与平板

大多数手机联动止步于通知和丢文件。在 TwinDesk 里，你的 Android 手机或平板是**完整的对等
设备**：它像电脑一样配对，享受同样的功能，外加自己的通话、短信、照片、文件和摄像头。

<a name="-calls-and-messages"></a>
## 📞 通话与短信

在电脑上接听、拒接和拨打电话。来电时，一个小窗口显示来电人，带**接听**和**拒接**。配合
蓝牙，电脑就变成**手机耳机**，你直接在电脑上说和听。**通话**页面有拨号盘、联系人和通话记录。

在**短信**里阅读和回复：每个会话都在，包含图片，侧边栏显示未读数。

<p align="center">
  <img src=".github/assets/v21-calls-messages.jpg" alt="通话页面显示来电和通话记录，短信页面显示一个会话" width="100%">
</p>

<a name="-photos-and-phone-files"></a>
## 🖼 照片与手机文件

在**照片**里浏览手机的照片和视频，可以打开看大图，也可以保存一张或多张到电脑。
**手机文件**浏览手机的全部存储：保存、上传、重命名、删除，或直接把文件拖到页面上。
**共享文件夹双向可用**：手机共享的文件夹在 Finder、资源管理器或 Linux 文件管理器里打开，
电脑共享的文件夹出现在手机的文件应用里。

<p align="center">
  <img src=".github/assets/v21-photos-files.jpg" alt="照片页面显示手机相册，手机文件页面显示共享文件夹和手机存储" width="100%">
</p>

<a name="-phone-camera"></a>
## 📷 手机摄像头

手机的**后置或前置摄像头**，可以显示在电脑的窗口里，也可以作为 **TwinDesk Camera** 摄像头
用于任何视频通话。在「摄像头」标签页切换镜头、旋转画面，或者从手机自己的「摄像头」页面启动。

<a name="-remote-and-gamepad"></a>
## 🎮 遥控与手柄

<p align="center">
  <img src=".github/assets/v23-remote.jpg" alt="手机的遥控页面：带一排按键的触控板，以及按 Xbox 手柄布局的游戏手柄" width="100%">
</p>

手机的**遥控**页面把它变成电脑的遥控器，适合窝沙发或做演示：

- **触控板与键盘。** 滑动移动、轻点点击、双指滚动，还有手机键盘缺少的键（Esc、Tab、Ctrl、
  Alt、方向键、媒体键和音量键）。旋转后进入横屏。
- **游戏手柄**，按 Xbox 手柄布局。它的按键输出你指定的键，或者打开**真实手柄**，电脑就会
  看到真正的手柄：Windows 上是 Xbox 360 手柄，Linux 上是普通游戏手柄。
- **给任何电脑用的蓝牙手柄**，包括 Mac，对面不需要装 TwinDesk，也不需要驱动：在电脑的
  蓝牙设置里和手机配对一次即可。

在电脑上打开**遥控**，才允许手机操控它。

<a name="-media-controls-and-phone-sound"></a>
## 🎵 媒体控制与手机声音

手机上正在播放的内容会显示在概览的卡片里，带封面、**上一首、播放/暂停、下一首**和一个进度条。
在 Windows 和 Linux 上，**在此播放手机声音**会让电脑变成手机蓝牙音箱。

<a name="-phone-screen-and-apps-on-the-computer"></a>
## 📲 手机屏幕与应用显示在电脑上

在窗口里看到手机屏幕，并用鼠标、触控板和键盘操控它。更进一步，可以**把单个 Android 应用
开在自己的窗口里**，和你的桌面应用并排。把它们固定到 Dock 或开始菜单，像普通应用一样使用。
在 WhatsApp、Instagram 和 Telegram 里，按 Enter 直接发送。

<p align="center">
  <img src=".github/assets/phone-on-mac.jpg" alt="平板的桌面显示在 Mac 窗口里，计算器、日历和时钟作为独立的 Mac 窗口打开" width="100%">
</p>

<a name="-tablet-as-a-second-screen"></a>
## 🖥 平板当第二屏

把平板或手机变成**额外的显示器**。用**扩展**增加桌面空间，或**镜像**显示你屏幕上的内容。
可以用触摸当鼠标，也可以打开触控板模式。

<p align="center">
  <img src=".github/assets/second-screen.jpg" alt="Mac 上的共享屏幕设置，以及平板上显示的扩展 Mac 桌面" width="100%">
</p>

<a name="-files-clipboard-notifications-mouse-and-keyboard"></a>
## 📤 文件、剪贴板、通知、鼠标与键盘

- **文件。** 在任意 Android 应用的分享菜单里选*发送到电脑*或*复制到电脑*；从电脑发送可以用
  共享菜单、*发送到*、拖过屏幕边缘，或 <kbd>⌃⌥C</kbd> / <kbd>Ctrl+Alt+C</kbd>。
- **剪贴板。** 文字和图片双向同步，包括手机的截图；还有一个快捷设置磁贴可以发送。
- **通知。** 手机的通知在电脑上以原生通知显示，反向也一样。可以隐藏内容或静音单个应用。
- **鼠标与键盘。** 把指针推出屏幕边缘，它就会**接着跑到手机上**；用真实键盘在任意 Android 应用里打字。

<p align="center">
  <img src=".github/assets/share-files.jpg" alt="Mac 的文件页面、带发送到电脑和复制到电脑的 Android 分享菜单，以及平板上收到的文件通知" width="100%">
</p>

<a name="-the-android-app"></a>
## 📱 Android 应用

Android 应用会随设备调整布局：手机上标签栏在底部，平板上用完整侧边栏。每个页面都会标明
当前连接的电脑，并显示每个方向上共享了什么。

<p align="center">
  <img src=".github/assets/android-phone.jpg" alt="手机上的 Android 应用：概览、屏幕、文件、剪贴板和更多" width="100%">
</p>

---

<a name="-connections"></a>
# 📡 连接方式

<p align="center">
  <img src=".github/assets/v21-connections.jpg" alt="同一 Wi-Fi、蓝牙 LE、Wi-Fi Direct、手机热点和 USB 线" width="100%">
</p>

你永远不用自己选。有网络时 TwinDesk 就用同一个网络，插上手机就切到 **USB 线**，Wi-Fi 断
了就退回**蓝牙**：在火车上，或者在访客 Wi-Fi 禁止设备互访的咖啡馆。链路和延迟始终显示在
应用顶部（*38 ms · 蓝牙*）。

蓝牙适合维持会话，但传屏幕或大文件太慢。所以当你开始这类操作时，TwinDesk 会在两台设备之间
**临时建立一条直连 Wi-Fi 链路**，用完再退回蓝牙。想保留就点 **用 Wi-Fi Direct 连接**，或者
让电脑加入手机的**热点**。

| | 同一 Wi-Fi | USB 线 | 蓝牙 | + Wi-Fi Direct 或热点 |
|---|:-:|:-:|:-:|:-:|
| 会话、剪贴板文字、通知 | ✅ | ✅ | ✅ | ✅ |
| 鼠标键盘、遥控 | ✅ | ✅ | ✅ | ✅ |
| 通话与短信 | ✅ | ✅ | ✅ | ✅ |
| 屏幕、应用、摄像头、文件、照片、剪贴板图片 | ✅ | ✅ | 切换到 Wi-Fi Direct | ✅ |
| 电脑之间的终端（`ssh twindesk`） | ✅ | — | 走 Wi-Fi Direct | ✅ |

谁能通过蓝牙连进来由你决定：**与手机的蓝牙**（默认开）和**与电脑的蓝牙**（默认关，需要时再开），
在概览和通用设置里都有。

---

<a name="-get-started"></a>
# 🚀 开始使用

<p align="center">
  <img src=".github/assets/tour.gif" alt="TwinDesk 窗口导览" width="820">
</p>

1. **下载**每台电脑和手机上对应的 TwinDesk（[见上文](#download)，或从 [Releases](https://github.com/InukaAsith/TwinDesk/releases/latest) 下载）。
2. **两端都打开。** 它们会在同一网络、蓝牙或手机的 USB 连接上互相发现。
3. **配对一次**，核对验证码（USB 连接只需点允许）。之后它们会自动连接。
4. **打开你要的功能。** 每个功能有一个带开关的标签页，在你打开之前会说明它的作用。

要用手机的屏幕、应用和摄像头窗口，TwinDesk 会引导你打开一次 Android 的无线调试
（[详情](#wireless-debugging)）。文件、剪贴板、通话和照片不需要它。手机的通知、短信、媒体
控制，以及通过无障碍实现的鼠标键盘，需要完整版应用，由电脑通过无线调试安装一次。

| 配对组合 | 你能得到 |
|---|---|
| Mac ↔ Windows PC、Mac ↔ Mac、PC ↔ PC | 全部电脑功能 |
| Linux ↔ Mac、PC 或 Linux | 全部电脑功能（[少量差异](#linux)） |
| Android ↔ Mac、Windows 或 Linux | 全部手机与平板功能（真实手柄限 Windows 和 Linux） |
| 全部同时连接 | [TwinDesk Mesh](#-twindesk-mesh-every-device-at-once)（beta） |

## 隐私

TwinDesk 只与你配对过的设备通信，直接走你自己的网络、蓝牙、直连 Wi-Fi 或线缆。没有账号，
没有遥测，没有云端中继。你的通话、短信、照片和摄像头画面直接从手机到你的电脑，不经过别处。
唯一的联网请求是向 GitHub 公开的 releases 检查更新，可以关闭。

<br>

---


以下内容面向好奇的读者和自行构建 TwinDesk 的人。

<a name="linux"></a>
<details>
<summary><h2>🐧 Linux</h2> <sub>X11 与 Wayland、共享文件夹、扩展屏、虚拟摄像头与手柄</sub></summary>

在 Linux 上，TwinDesk 同时支持 X11 和 Wayland。Wayland 下鼠标键盘通过 evdev 和 uinput 工作
（安装设置页授权一次），屏幕通过桌面门户捕获。有几处行为略有不同：

- **共享文件夹。** 共享使用 Samba。第一次使用时，如果没装会弹出一次密码提示安装，并添加一个
  仅限网络的账户。对方电脑的文件夹通过 GVFS 挂载，显示在文件管理器侧边栏。
- **复制粘贴文件。** <kbd>Ctrl+Alt+C</kbd> 复制前台文件管理器中选中的内容（或你已复制的文件），
  <kbd>Ctrl+Alt+V</kbd> 粘贴到前台文件管理器窗口（否则是「下载」）。右键 › *发送到* 在
  Nautilus、Nemo、Caja、Dolphin 和 Thunar 中可用。
- **跨边缘拖拽文件。** 从对方电脑拖来的文件会放到指针所在的文件夹，或桌面上。Wayland 下会放到
  前台文件管理器窗口。从 Linux 拖出文件需要 Xorg 会话。
- **扩展屏。** 在 GNOME（Wayland）上使用 Mutter 自带的虚拟显示器；桌面询问共享哪块屏幕时选择
  "Virtual remote monitor"。X11 下会打开显卡驱动的一个空闲输出（NVIDIA 驱动不支持）。这需要
  一个小助手，.deb 会安装它；使用 AppImage 时在 共享屏幕 › *TwinDesk virtual display* › 安装
  中输入一次密码即可装好。
- **应用。** 在对面打开本机应用需要 Xorg 会话。
- **虚拟摄像头与手柄。** TwinDesk Camera 是一个 v4l2loopback 设备，真实手柄是一个 uinput 控制器
  （"TwinDesk Gamepad"）；各自在第一次打开时询问一次密码。
- **蓝牙与 Wi-Fi Direct。** 蓝牙 LE 走 BlueZ，直连 Wi-Fi 走 NetworkManager，在网卡允许的情况下
  与电脑自身的 Wi-Fi 并存（与手机连接时使用 2.4 GHz）。
- **Android 手机。** [Android](#android-in-detail) 的所有功能在 Linux 上同样可用：手机屏幕与应用
  窗口、跨边缘的鼠标键盘、文件、剪贴板、通知和声音。安装包自带 adb；设置页的防火墙修复会放开
  mDNS（5353/udp），以便发现手机的无线调试。

</details>

<a name="android-in-detail"></a>
<details>
<summary><h2>🤖 Android 细节</h2> <sub>手机应用逐页说明，以及无线调试</sub></summary>

在手机上安装 TwinDesk，与电脑上的 TwinDesk 并排打开，从 概览 › 附近 配对。手机需要 Android 10，
所有经过无线调试的功能需要 Android 11。

### 手机应用

应用的布局与电脑端类似（平板用侧边栏，手机用底部标签栏），每个页面都会标明当前连接的电脑：

| 页面 | 作用 |
|---|---|
| **概览** | 当前连接的电脑、连接与断开、附近可配对的电脑，以及无线调试未配置前的引导卡片 |
| **屏幕** | 把手机当作电脑的屏幕：镜像，或把桌面扩展到手机上。触摸当鼠标用（轻点点击、长按右键、拖动选择或移动窗口、双指滚动），支持电脑声音和流畅画质 |
| **指针** | 电脑的鼠标跨屏幕边缘到手机上，可设置这里的指针速度、反向滚动、右键与中键 |
| **键盘** | 电脑的键盘在手机上打字，每个键都是真实的键，所以任何布局都能用，软键盘不会挡路。手机上的键盘也能在电脑上打字 |
| **遥控** | 手机作为电脑的触控板和键盘，或作为手柄：自定义按键、真实手柄（Windows、Linux），或给任何电脑用的蓝牙手柄 |
| **摄像头** | 手机后置或前置摄像头显示在电脑上，以及虚拟摄像头是否使用它 |
| **剪贴板** | 一端复制、另一端粘贴，两个方向各有独立开关，可即时同步或发送时同步 |
| **通知** | 手机通知显示在电脑上（可选择隐藏内容），电脑通知也显示在手机上 |
| **文件** | 发送文件、复制到电脑以便粘贴，并查看电脑端的文件落到哪里 |
| **声音** | 手机声音输出到电脑，电脑声音输出到手机 |
| **通用** | 手机名称、后台运行，以及 TwinDesk 使用的权限，各有开关 |
| **关于** | 源码、发布版本、许可证，以及哪些数据经过无线调试和网络 |

应用之外还有：

- **分享菜单：** 每个应用的分享菜单里都有*发送到电脑*和*复制到电脑*。
- **快捷设置磁贴：** *发送剪贴板*和*无线调试*。
- **主屏幕快捷方式：** 一键打开电脑屏幕，或一键开启无线调试。
- **常驻通知**显示当前连接状态，并可退出。

### 无线调试

文件、剪贴板和通知立刻就能用。手机屏幕、应用窗口、触摸、在手机上使用你的鼠标键盘以及手机
声音，都走**无线调试**，TwinDesk 会与它配对一次：

<p align="center">
  <img src=".github/assets/ui-phone-pair.jpg" alt="概览：已连接电脑下方的无线调试卡片，带配对码" width="820">
</p>

- 配对之前，概览里已连接电脑下方会有一张卡片（电脑和手机上都有）引导你完成。在手机上打开
  *开发者选项 › 无线调试 › 使用配对码配对设备*，在电脑上输入 6 位配对码，或在手机上 TwinDesk
  的通知里输入（设置对话框保持打开）。手机会把配对码发送给它当前连接的电脑：Mac、PC 或 Linux。
- 之后 TwinDesk 会在需要时自己打开无线调试，每次重启后跟到新端口，并保持配对不过期
  （Android 通常会在 7 天未使用后忘记一台电脑）。有些手机（MIUI、HyperOS）每次切换 Wi-Fi 或
  锁屏都会关闭无线调试，TwinDesk 会在解锁后尽快重新打开；如果被拒绝则给出提示。
  无线调试只有在 **USB 调试**也开启时才能运行，所以 TwinDesk 会同时打开两者。
- **小米、Redmi 和 POCO** 还需要 *开发者选项 › USB 调试（安全设置）* 才能使用触摸、鼠标和键盘
  （需要登录小米账号）。不开的话屏幕能显示但输入被拒绝；电脑的「手机」页面会显示"触摸被阻止"，
  直到你打开它。
- **在 Mac 上通过 Finder 访问手机。** 在「挂载」标签页打开并点挂载：手机会像网络服务器一样显示在
  位置栏。在此之前 TwinDesk 从不查看手机的文件。允许 USB 调试时走线缆，否则走无线调试。
  Finder 的 `.DS_Store` 和 `._` 文件永远不会写入手机。

</details>

<a name="how-it-works"></a>
<details>
<summary><h2>⚙️ 工作原理</h2> <sub>Electron 应用、原生助手，以及设备之间的链路</sub></summary>

<p align="center">
  <img src=".github/assets/how-it-works.svg" alt="架构：每台电脑上各有一个 Electron 应用和原生助手，通过 TLS 控制通道、WebRTC 媒体和系统服务连接" width="100%">
</p>

每台电脑运行一个 **Electron 应用**，负责窗口、配对、链路和状态机。它旁边运行一个小的
**原生助手**，处理操作系统独占的能力：输入捕获与注入、虚拟显示器、手势、窗口捕获和原生拖放。

| 目录 | 内容 |
|---|---|
| `mac/` | macOS 应用（Electron） |
| `mac-helper/` | macOS 助手（Swift）：虚拟显示器、事件监听、输入注入、音频、应用、SMB |
| `windows/` | Windows 应用（Electron）与安装器 |
| `windows-helper/` | Windows 助手（C#）：钩子、SendInput、Raw Input 触控板、窗口捕获、原生拖拽 |
| `linux/` | Linux 应用（Electron） |
| `linux-helper/` | Linux 助手（C）：X11 上的 XInput2 / XTest，Wayland 上的 evdev / uinput，XRandR、窗口列表、XDND 边缘条 |
| `android/` | Android 应用（Kotlin、Jetpack Compose）；电脑通过 adb 和 [scrcpy](https://github.com/Genymobile/scrcpy) 的服务端驱动手机 |
| `shared/` | 所有平台共用：通信协议、蓝牙管道与 Wi-Fi Direct 链路、手机中枢（通话、短信、照片、手机文件）、共享文件夹、帧生成与图标 |

两台设备之间的链路始终是一个 TLS 会话，无论跑在哪里：局域网、手机的 USB 线（adb），还是
**蓝牙 LE**（TwinDesk 自己的 GATT 管道，`shared/blepipe.js`）。当蓝牙上的会话需要带宽时，
`shared/netlink.js` 会建立一个 **Wi-Fi Direct** 组或加入手机热点，把会话迁移过去，不再需要时
再撤掉。通话、短信、照片和手机文件在电脑端是 `shared/phonehub.js`，由手机上的 TwinDesk 应答。

网络上或线缆连接的两台电脑之间，文件通过同一端口上的 HTTPS 流式传输，与控制链路并存，最多
支持四路并发（`shared/fastfile.js`），所以鼠标键盘永远不会排在大文件后面。走蓝牙、Wi-Fi
Direct、热点，或者对方是旧版 TwinDesk 时，文件仍按原方式传输：在控制链路上分片发送。

端口：局域网上的 TCP **47800**（控制链路与文件）和 UDP **47801**（发现）。

</details>

<a name="build-and-run"></a>
<details>
<summary><h2>🛠 构建与运行</h2> <sub>macOS、Windows、Linux、NixOS、Android 与 GitHub Actions</sub></summary>

每个平台都需要 [Node.js](https://nodejs.org) 18+。

### macOS（13 Ventura 或更高）

```sh
xcode-select --install          # 助手需要的 Swift 编译器
cd mac
npm install
npm run build:helper
npm start                       # 从源码运行
npm run dist && npm run dmg     # 在 mac/dist/ 中生成 TwinDesk.app 和 TwinDesk-<version>-<arch>.dmg
```

磁盘映像的名称由其中的应用决定：Apple Silicon 上是 `TwinDesk-2.4.0-arm64.dmg`，Intel 上是
`TwinDesk-2.4.0-x64.dmg`。发布时请保持这些命名：应用内更新器靠它们为每台 Mac 选择正确的版本。

默认情况下，`npm run dist` 针对当前 Mac 的架构构建。要在 Apple Silicon Mac 上构建 Intel 包：

```sh
npm run dist:x64 && npm run dmg
```

一步完成 Intel 应用及其映像的构建，运行 `npm run dmg:intel`；它会生成
`mac/dist/TwinDesk-<version>-x64.dmg`。

明确构建 Apple Silicon 版本用 `npm run dist:arm64 && npm run dmg`。x64 构建会交叉编译 Swift
助手并打包 x64 版 Electron 运行时，因此不需要 Intel Mac。

首次启动时，TwinDesk 会请求**屏幕录制**、**辅助功能**和**输入监控**权限（只需一次；之后
「通用」标签页会显示各权限状态）。

`npm run dist` 会用自签名证书签署应用，证书首次生成于 `~/.twindesk-signing`（请备份）。macOS
按签名保留权限，所以使用同一证书时，把更新拖进「应用程序」后权限会延续。没有证书构建的应用
是 ad-hoc 签名的，macOS 会把每次更新都当作新应用；此时 TwinDesk 会清除过期的权限记录，让
「允许」重新生效。

### Windows 10 / 11

```bat
cd windows
npm install
npm run build:helper            :: 使用 Windows 自带的 .NET Framework C# 编译器
npm start
npm run dist                    :: windows\dist\ 中的 NSIS 安装器
npm run dist -- arm64           :: Windows on ARM 安装器（或 `x64 arm64` 同时构建两者）
```

`npm run dist` 在 Mac 或 Linux 上也能用：它会跳过助手构建，直接打包 `windows-helper\bin\`
中已有的 `macshare-winhelper.exe`（例如从发布版中取得的）。

安装器会添加防火墙规则（对所有网络配置文件生效，这样在"公用"网络上的标准账户之后就不需要
管理员权限）。只显示一次的设置页会提供修复防火墙（需要管理员权限）和安装扩展屏所需的可选
虚拟显示器驱动的选项。

### Linux（X11 或 Wayland）

```sh
sudo apt install build-essential libx11-dev libxi-dev libxtst-dev libxext-dev libxrandr-dev libxfixes-dev
cd linux
npm install
npm run build:helper
npm start
npm run dist                    # linux/dist/ 中的 AppImage 和 .deb
```

设置页会引导你完成剩下的步骤。Wayland 下需要输入权限（一次管理员授权，然后注销再登录一次）。
它还可以为终端安装 OpenSSH。GNOME Wayland 上的扩展屏使用 Python 3 配合 GObject 和 GStreamer
的 PipeWire 插件（`python3-gi`、`gstreamer1.0-pipewire`），GNOME 桌面通常已经自带。

<a name="nixos--nix-flakes"></a>

#### NixOS 与 Nix Flakes

TwinDesk 附带 `flake.nix`，支持打包、开发环境和 NixOS 模块：

```sh
# 直接用 flakes 运行
nix run github:InukaAsith/TwinDesk

# 或进入开发环境
nix develop
```

在 NixOS 上，在系统配置中启用模块：

```nix
{
  programs.twindesk = {
    enable = true;
    user = "yourusername"; # 加入 input/uinput 组，供 Wayland 下的键鼠共享使用
  };
}
```

完整选项（防火墙、Wi-Fi Direct 能力包装、虚拟显示器等）见 [docs/nixos.md](docs/nixos.md)。


#### 在 Mac 上测试 Linux 版

`linux/scripts/vm-test.sh` 会在 [Parallels Desktop](https://www.parallels.com) 的 Linux 虚拟机
（装有上述依赖和 Node.js 的 Ubuntu）中运行它：把当前检出复制进虚拟机、构建助手、在虚拟机桌面
会话中启动 TwinDesk，并从 Mac 上驱动它。

```sh
linux/scripts/vm-test.sh start            # 同步、构建并在虚拟机中（重新）启动
linux/scripts/vm-test.sh shot linux.png   # 截取其窗口
linux/scripts/vm-test.sh eval "UI.go('cursor')"
linux/scripts/vm-test.sh log
```

在虚拟机的共享网络中，它能发现 Mac 上的 TwinDesk，并像任何 Linux 电脑一样配对。

### Android

```sh
cd android
./gradlew assembleRelease        # JDK 17+；输出到 app/build/outputs/apk/{standard,full}/release/
```

`standard` 是大家下载的版本。`full` 增加了通知使用权、短信权限（短信）和无障碍服务（不依赖
无线调试的鼠标键盘），Play Protect 会拦截下载到的这类应用；电脑会通过无线调试安装它（手机
页面 › 来自手机的通知），所以每个平台上的 `npm run dist` 都会打包最新的
`android/dist/*-full.apk`。

<a name="github-actions"></a>

### GitHub Actions

**Build Android**、**Build Linux** 和 **Build Windows**（Actions 标签页 › Run workflow）会生成
标准版和完整版 APK、AppImage 与 .deb，以及 x64 和 arm64 安装器，包含各平台的助手。
设置 `ANDROID_KEYSTORE` secret 为 Android 应用签名所用的密钥
（`base64 -i ~/.android/debug.keystore`）：这样 APK 可以覆盖安装现有版本，Linux 和 Windows
构建也会带上完整版 Android 应用。没有设置时，APK 使用 runner 自己的密钥，电脑端构建则不含
Android 应用。

要为 Windows 安装器做 Authenticode 签名，设置 `WIN_CSC_LINK` secret 为 base64 编码的 Windows
代码签名 `.pfx` 证书，`WIN_CSC_KEY_PASSWORD` 为其密码。请勿将证书和密码提交到仓库。设置了
`WIN_CSC_LINK` 后，如果签名无法完成，Windows 构建会直接失败，而不是悄悄发布未签名的安装器。
签名会给用户一个可验证的发布者，也有助于随时间积累 SmartScreen 信誉；但它并不保证杀毒软件
不再拦截文件。

</details>

<a name="thanks"></a>
## 致谢

TwinDesk 因这些提交 pull request 的人而更好：

- [@DevPsycho-07](https://github.com/DevPsycho-07)：手机遥控（[#44](https://github.com/InukaAsith/TwinDesk/pull/44)）、跨设备剪贴板截图（[#45](https://github.com/InukaAsith/TwinDesk/pull/45)）、手机窗口控制（[#46](https://github.com/InukaAsith/TwinDesk/pull/46)）及手机端修复（[#43](https://github.com/InukaAsith/TwinDesk/pull/43)）
- [@benzntech](https://github.com/benzntech)：手机摄像头（[#48](https://github.com/InukaAsith/TwinDesk/pull/48)）、Developer ID 签名与公证（[#40](https://github.com/InukaAsith/TwinDesk/pull/40)）以及 Mac 端下载（[#39](https://github.com/InukaAsith/TwinDesk/pull/39)）
- [@atse25029-collab](https://github.com/atse25029-collab)：手机窗口中的 WhatsApp 和 Instagram（[#42](https://github.com/InukaAsith/TwinDesk/pull/42)）
- [@philopaterwaheed](https://github.com/philopaterwaheed)：指针锁定（[#49](https://github.com/InukaAsith/TwinDesk/pull/49)）
- [@ghustanov](https://github.com/ghustanov)：无线调试自动关闭（[#31](https://github.com/InukaAsith/TwinDesk/pull/31)）以及 Mac 助手的 Info.plist（[#30](https://github.com/InukaAsith/TwinDesk/pull/30)）
- [@m-uvex](https://github.com/m-uvex)：Nix flake 与 NixOS 模块（[#37](https://github.com/InukaAsith/TwinDesk/pull/37)）
- Erdoğan Yeşil（[@erdodo](https://github.com/erdodo)）：TwinDesk Mesh 所基于的 mesh（[#29](https://github.com/InukaAsith/TwinDesk/pull/29)），以及 [#8](https://github.com/InukaAsith/TwinDesk/pull/8) 和 [#9](https://github.com/InukaAsith/TwinDesk/pull/9)
- [@Jay-Prajapati01](https://github.com/Jay-Prajapati01)：Windows 安装器签名（[#13](https://github.com/InukaAsith/TwinDesk/pull/13)）

同样感谢所有在 [issues](https://github.com/InukaAsith/TwinDesk/issues) 里报告问题和分享想法的人。

## 许可证

TwinDesk 是自由软件，采用 [GNU 通用公共许可证第 3 版](LICENSE)授权。
Copyright © 2026 inukaasith。

部分内容改编自 [DeskPad](https://github.com/Stengo/DeskPad)（MIT）。详见 [THIRD_PARTY_NOTICES](THIRD_PARTY_NOTICES)。