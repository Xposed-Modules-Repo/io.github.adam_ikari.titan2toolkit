# Titan2 Toolkit

适用于 **Unihertz Titan 2 国际版**（TEE / EEA 固件，Android 15 / 16）的 Xposed 模块，兼容 **Vector**（LSPosed 2.0）与较新的 LSPosed。

## 功能

| 功能 | 说明 |
| --- | --- |
| 桌面 6 列布局 | 工作区、Dock、应用抽屉统一改为 6 列；可开关，修改后需重启桌面 |
| 桌面布局保护 | 随 6 列开关自动生效，模块停用期间不丢第 6 列图标 |
| 字母键全局快捷启动 | 除输入法弹出外，任意应用内按字母键启动对应应用；可开关 |
| 实验性：更多应用克隆 | 放开“设置 → 应用 → 克隆应用”的原厂白名单，已安装第三方应用均可克隆；默认关闭 |

## 环境要求

- Unihertz Titan 2 国际版，Android 15 或 16
- 已解锁 Bootloader 并 root（Magisk / KernelSU + Zygisk）
- 已安装 [Vector](https://github.com/JingMatrix/Vector) 或较新的 LSPosed

模块使用现代 libxposed API（`minApiVersion=101`、`targetApiVersion=101`）。

## 安装与启用

1. 安装本仓库 Release 中的 APK。
2. 在 Vector / LSPosed 管理器中启用 **Titan2 Toolkit**。
3. 作用域勾选 **系统框架**（`android`）、**桌面**（`com.android.launcher3`）、**设置**（`com.android.settings`）。
4. 重启手机，让 system_server、桌面与设置进程重新加载模块。

## 功能开关

- **桌面 6 列布局**：默认开启。关闭后恢复系统默认 5 列，布局保护一并关闭。
- **字母键快捷启动全局生效**：默认开启。关闭后仅在桌面或按住 Magic Key 时触发。
- **实验性：支持更多应用克隆**：默认关闭。开启后在“设置 → 应用 → 克隆应用”列出全部已安装第三方应用；克隆仍走原厂 clone profile 流程。个别应用克隆后可能异常，关闭开关即恢复原厂白名单。

## 源码与反馈

源码与问题反馈：<https://github.com/adam-ikari/Titan2Toolkit>

## 更新日志

### 0.5.0
- 新增实验性“更多应用克隆”：放开克隆应用白名单
- 发布包名调整为 `io.github.adam_ikari.titan2toolkit`

### 0.4.0
- 桌面 6 列布局改为单一开关，布局保护随之自动生效
- 字母键快捷启动支持全局生效
