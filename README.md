<div align="center">
  <img src="docs/icon.png" width="120" alt="GameWindow logo"/>
  <h1 align="center">GameWindow</h1>

  <p>
    置顶小浏览器 · 跟攻略视频不再切窗口
    <br/>
    <i>在游戏上方浮一个始终置顶的小窗口放攻略 / 直播，三条栏自动收起让网页铺满窗口，鼠标移上去再展开</i>
  </p>

  <p>
    基于 .NET WinForms + Microsoft Edge WebView2 原生窗口，<b>无 Python 运行环境依赖</b>，绿色版解压即用。
  </p>
</div>

<div align="center">

![平台](https://img.shields.io/badge/platform-Windows%2010%2F11%20x64-blue)
![.NET](https://img.shields.io/badge/.NET%20Desktop%20Runtime-6.0%2B-512BD4)
![WebView2](https://img.shields.io/badge/WebView2-Runtime-0078D7)
[![最新版本](https://img.shields.io/github/v/release/suinianya/GameWindow?label=%E6%9C%80%E6%96%B0%E7%89%88%E6%9C%AC&color=brightgreen)](https://github.com/suinianya/GameWindow/releases/latest)
![免费](https://img.shields.io/badge/%E5%85%8D%E8%B4%B9-%E7%BB%BF%E8%89%B2%E7%89%88-brightgreen)

</div>

![界面截图](docs/screenshot.png)

---

## 这是什么

一边打游戏一边看攻略视频，最烦的是频繁切窗口：切出去游戏声音没了、切回来视频又卡。**GameWindow** 就是在游戏画面上开一个「始终置顶」的小浏览器窗口，攻略、直播、B 站、任意网页都能放，窗口搁在游戏画面旁边，点一下就能看。

它不是一个新浏览器内核，而是把系统自带的 **Microsoft Edge WebView2** 做成了一个能吸附、能隐藏、能挖孔的小窗口外壳：性能好、网页兼容性好、不占额外内存。

## ✨ 主要功能

*   **置顶小窗**：始终浮在游戏上方，不挡视野，可一键取消置顶
*   **三条栏自动隐藏**：标题栏、地址栏、标签栏平时自动收起，**网页铺满整个窗口**；鼠标移到窗口最上方自动展开，移开自动收起
*   **沉浸模式**：按 `0` 收起全部界面只留画面；鼠标移上去会在指针处挖一个跟随圆孔，孔里能直接看到并点击下面的游戏，实现「视频盖着、游戏照玩」
*   **多标签**：网页里的新窗口（`target=_blank`、`window.open`）都在程序内开成标签，不跳系统浏览器
*   **全局播放热键**：`~` 播放/暂停、`5`/`6` 快退快进 3 秒、`7`/`8` 上下集、`9` 隐藏窗口、`0` 沉浸，游戏里也能直接按，不用切窗口
*   **标题栏提示**：标题栏直接显示软件名和热键说明，第一次用也能看懂怎么操作
*   **边缘吸附**：窗口拖到屏幕边缘 18 像素以内自动贴边，四边四角都支持，多显示器按所在屏幕吸附
*   **无边框窗口**：拖动标题栏移动窗口，拖动窗口边缘 6 像素以内缩放，双击标题栏最大化 / 还原
*   **记忆**：窗口位置、大小、置顶 / 沉浸状态、上次观看的网页，下次启动自动恢复
*   **环境自检**：启动自动检测 .NET 桌面运行时和 WebView2 运行时，缺了弹窗一键下载安装
*   **绿色版**：解压即用，配置和缓存都在程序目录 `data\` 下，不写注册表、不装系统服务

## 📥 下载与安装

前往 **[Releases 页面](https://github.com/suinianya/GameWindow/releases/latest)** 下载最新的 `GameWindow-x.x.x-win64.zip`。

| 步骤 | 说明 |
| --- | --- |
| 1 | 下载 zip 后**完整解压**到任意目录（不要在压缩包里直接双击运行） |
| 2 | 双击 `GameWindow.exe` |
| 3 | 首次启动会检查运行环境，缺组件会弹中文提示，点「是」自动下载安装；装好后自动继续启动 |
| 4 | 用地址栏或 `Ctrl+L` 打开你想看的页面，开始用 |

### 运行环境要求

不用装 Python，但系统需要这两个运行库（Windows 11 一般已自带，Windows 10 多数机器也有）：

| 项目 | 要求 |
| --- | --- |
| 操作系统 | Windows 10 1809 及以上 / Windows 11，**64 位（x64）** |
| .NET 桌面运行时 | .NET Desktop Runtime **6.0 或更高**（推荐 10.0） |
| WebView2 运行时 | Microsoft Edge WebView2 Runtime（随新版 Edge 自动安装） |
| 磁盘空间 | 程序约 25 MB；网页缓存另计；缺运行库时启动会自动下载（.NET 约 60 MB / WebView2 约 205 MB） |

缺了不用自己找：每次启动都会自动检测，也可以在托盘菜单点「环境检测…」重新检查。检测和安装日志在程序目录 `data\env_check.log`。

## 🚀 使用步骤

1. 解压后双击 `GameWindow.exe`，等窗口出现（首次初始化 WebView2 需要一两秒）
2. 把窗口拖到你想要的位置 —— 靠近屏幕边缘会自动吸附，拖动标题栏移动，拖边缘缩放
3. 鼠标移到窗口最上方，三条栏滑出，在地址栏输入网址；回车后三条栏自动收起、网页铺满
4. 打游戏时用全局热键控制视频：`~` 播放暂停、`5`/`6` 快退快进、`7`/`8` 上下集
5. 按 `9` 临时隐藏窗口，按 `0` 进入沉浸模式（挖孔）；托盘的「热键键位绑定…」可以把这些键改成你习惯的

## ⌨️ 快捷键

| 按键 | 作用 |
| --- | --- |
| `` ` ``（反引号） | 播放 / 暂停 |
| `5` / `6` | 快退 / 快进 3 秒 |
| `7` / `8` | 上一集 / 下一集 |
| `9` | 隐藏 / 显示窗口 |
| `0` | 沉浸模式（挖孔 + 指针穿透）开关 |
| `Ctrl+L` | 展开三条栏并聚焦地址栏 |
| `Ctrl+T` / `Ctrl+W` | 新建标签 / 关闭当前标签 |
| `F5` | 刷新页面 |
| 托盘图标双击 | 显示 / 隐藏窗口 |

热键默认**全局生效**（游戏窗口在前台时也能用），可以在托盘菜单「热键键位绑定…」里改；如果刚在地址栏打过字，等 3 秒让热键恢复接管。

## 🔧 疑难解答

如果遇到问题，先按顺序排查：

1.  **杀毒软件**：把程序目录加到杀毒软件（包括 Windows Defender、360、火绒）的信任区，避免 `_internal` 里的 DLL 被误删。
2.  **SmartScreen 提示**：未签名程序首次运行会被拦，点「更多信息 → 仍要运行」。
3.  **打不开 / 白屏**：确认 WebView2 Runtime 已安装（托盘「环境检测…」）；或退出程序后删掉 `data\WebView2` 目录重试。
4.  **独占全屏时看不到小窗**：游戏请用「无边框窗口 / 窗口化」模式，独占全屏会盖住所有窗口。
5.  **热键没反应**：确认程序在运行；如果别的软件占用了同样的全局热键，到托盘「热键键位绑定…」换一个键。
6.  **提示缺少 .NET / WebView2 但明明装过**：大概率装成了 x86 版，确认装的是 **x64**；刚装完仍提示就重启电脑（.NET 安装返回 3010 即要求重启）；还不行看 `data\env_check.log`。
7.  **公司电脑不让装软件**：.NET 桌面运行时需要管理员权限，WebView2 一般当前用户即可安装；装不了就找 IT，或把整个程序目录拷到已装好运行库的电脑上直接用（绿色版本身不用安装）。
8.  **点击程序没反应**：先看任务管理器里有没有 `GameWindow.exe` 进程；再看程序目录下有没有 `error.log` 和 `data\env_check.log`，把这两个文件发给作者。

排查时可以带参数 `--skip-env-check`（或设环境变量 `GAMEWINDOW_SKIP_ENV_CHECK=1`）跳过启动环境检测。

## ⚠️ 免责声明

本项目只是一个**浏览器外壳**：不提供、不存储、不分发任何视频、直播或网页内容，播放的内容全部来自你访问的网站。使用本软件访问第三方网站时，请遵守对应网站的服务条款；因访问第三方内容产生的任何问题与本项目无关。

本软件开源免费、仅供个人学习与日常使用，禁止用于任何商业用途。请勿移除版权标识后二次打包分发。

## ❤️ 致谢

*   [Microsoft Edge WebView2](https://developer.microsoft.com/microsoft-edge/webview2/) —— 网页渲染内核
*   [.NET Desktop Runtime](https://dotnet.microsoft.com/) —— WinForms 窗口与运行时
*   [pythonnet](https://github.com/pythonnet/pythonnet) / [PyInstaller](https://pyinstaller.org/) —— 让 Python 写的逻辑打包成单目录可执行程序

## 💬 反馈

*   Bug、建议欢迎提 [Issue](https://github.com/suinianya/GameWindow/issues)，请附上系统版本和 `data\env_check.log`、`error.log`
*   功能更新记录见 [Releases](https://github.com/suinianya/GameWindow/releases)

## 📄 许可证

Copyright (c) 2026 GameWindow. 保留所有权利。

本软件为免费软件，允许原样分发；**禁止反编译、反汇编、修改后再分发**，禁止移除版权标识后二次打包销售。详见 [LICENSE](LICENSE)。
