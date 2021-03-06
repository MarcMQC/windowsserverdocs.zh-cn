---
title: iOS 客户端中的新增功能
description: 了解适用于 iOS 的远程桌面客户端的最新更改
ms.prod: windows-server
ms.technology: remote-desktop-services
ms.topic: article
author: heidilohr
manager: lizross
ms.author: helohr
ms.date: 05/06/2020
ms.localizationpriority: medium
ms.openlocfilehash: 0943379b8f251d1548a0aa920a95931dc39a0624
ms.sourcegitcommit: 67116322915066b85decb4261d47cedec2cfe12f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82903452"
---
# <a name="whats-new-in-the-ios-client"></a>iOS 客户端中的新增功能

我们会定期更新[适用于 iOS 的远程桌面客户端](remote-desktop-ios.md)，添加新功能并修复问题。 可在此页上找到最新更新。

## <a name="how-to-report-issues"></a>如何报告问题

我们致力于将适用于 iOS 的远程桌面客户端打造成最好的，因此我们非常重视你的反馈。 你可以通过“帮助” > “报告问题”来报告任何问题。

## <a name="updates-for-version-1007"></a>版本 10.0.7 的更新

发布日期：2020 年 4 月 29 日

此更新中新增了按名称或上次连接时间对（iPhone 上提供的）电脑列表视图进行排序的功能。

## <a name="updates-for-version-1006"></a>版本 10.0.6 的更新

发布日期：2020 年 3 月 31 日

现在是时候进行快速更新（包含一些缺陷修复）了。 下面是此版本的新变化：

- 修复了许多 VoiceOver 辅助功能问题。
- 修复了用户无法使用土耳其语凭据进行连接的问题。
- 切换器 UI 中显示的会话现在按启动时间排序。
- 现在，选择 Connection Center 中的“返回”按钮会返回到上一个活动会话。
- 现在，在从客户端切换到另一个应用时，Swiftpoint 鼠标就会释放。
- 提高了与 Windows 虚拟桌面服务的互操作性。
- 修复了错误报告中显示的故障。

非常感谢通过 App Store、应用内反馈和电子邮件发送给我们的所有意见。 另外，特别感谢与我们一同诊断问题的每个人。

## <a name="updates-for-version-1005"></a>针对版本 10.0.5 的更新

*发布日期：2020/03/09*

我们汇总了针对此 10.0.5 版本的一些 Bug 修复和功能更新。 下面是新增功能：

- 现在会自动导入已启动的 RDP 文件（在“常规”设置中查找开关）。
- 你现在可以启动尚未在“文件”应用中下载的基于 iCloud 的 RDP 文件。
- 远程会话现在可以扩展到 iPhone 上的 Home 指示器下方（在“显示”设置中查找开关）。
- 增加了对通过多个击键键入复合字符（例如 é）的支持。
- 增加了对 iPad 屏幕浮动键盘的支持。
- 增加了对从远程会话调整重定向相机的属性的支持。
- 修复了手势识别器中的一个 bug，当已连接到远程会话时，该 bug 会导致客户端停止响应。
- 你现在只需向上轻扫一次即可进入“应用切换”模式（除非你在“触控”模式下且会话扩展到了 Home 指示器区域）。
- 当已连接到远程会话时，Home 指示器将自动隐藏，在你点击屏幕时将重新出现。
- 增加了键盘快捷方式（**Command + ,** ），用于访问连接中心内的应用设置。
- 增加了键盘快捷方式（**Command + R**），用于刷新连接中心内的所有工作区。
- 挂接了已连接到远程会话时用于退出的系统键盘快捷方式（**Command +.** ）。
- 修复了远程会话中的 Windows 屏幕键盘太小的情况。
- 在整个连接中心实现了自动键盘聚焦，使数据输入更加顺畅。
- 现在，在凭据提示下按 **Enter** 会导致提示消失，当前流程继续进行。
- 针对以下情况进行了修复：按 Shift + Option + 向左、向上或向下箭头键时，客户端将发生故障。
- 针对移除 SwiftPoint 设备时发生故障的情况进行了修复。
- 修复了自上次发布以来，用户报告给我们的其他故障。

我们要感谢所有报告了 Bug 并与我们一起诊断问题的所有人。

## <a name="updates-for-version-1004"></a>针对版本 10.0.4 的更新

*发布日期：2020/03/02*

是时候再次更新了！ 我们要感谢所有报告了 Bug 并与我们一起诊断问题的所有人。 下面是此版本中的新增功能：

- 删除用户帐户和网关时，现在会显示确认 UI。
- 连接中心内的搜索 UI 做了轻微的修改。
- 现在，如果存在用户名提示，则当从 RDP 文件或 URI 启动时，它将显示在凭据提示 UI 中。
- 修复了扩展的屏幕键盘将扩展到 iPhone 槽口下方的问题。
- 修复了外部键盘在断开并重新连接后将停止工作的 Bug。
- 增加了对外部键盘上的 Esc 键的支持。
- 修复了在输入中文字符时出现英文字符的 Bug。
- 修复了某些中文输入在删除后将保留在远程会话中的 Bug。
- 修复了自上次发布以来，用户报告给我们的其他故障。

我们非常感谢你通过 App Store、应用内反馈和电子邮件发送给我们的所有意见。 我们将继续专注于在每一个版本中使此应用变得更好。

## <a name="updates-for-version-1003"></a>针对版本 10.0.3 的更新

*发布日期：2020/01/16*

现在是 2020 年，是时候推出我们今年的第一个版本了，这意味着将增加新功能并修复一些 bug。 下面是此更新中包括的内容：

- 支持从 RDP 文件和 RDP URI 启动连接。
- 工作区页眉现在可以折叠。
- 鼠标指针模式现在支持同时缩放和平移。
- 鼠标指针模式下的按住手势现在会触发远程会话中的右键单击。
- 删除了鼠标指针模式下用于右键单击的强制触控手势。
- 即使未连接任何应用，会话中切换器屏幕现在也支持断开连接。
- 会话中切换器屏幕现在支持轻型消除。
- 在会话中切换器屏幕中，电脑和应用不再自动重新排序。
- 扩大了电脑缩略图视图省略号菜单的命中测试区域。
- “输入设备设置”页现在包含指向受支持设备的链接。
- 修复了一个 Bug，该 Bug 导致在启动时对于某些用户不断显示蓝牙权限 UI。
- 修复了自上次发布以来，用户报告给我们的其他故障。

## <a name="updates-for-version-1002"></a>针对版本 10.0.2 的更新

*发布日期：2019/12/20*

我们一直在努力修复 Bug 并增加有用功能。 下面是此版本中的新增功能：

- 支持在硬件键盘上输入日语和中文。
- 现在，电脑列表视图会显示关联用户帐户的友好名称（如果存在）。
- 首次运行体验中的权限 UI 在轻型模式下现在会正确呈现。
- 修复了当有人在硬件键盘上同时按 Option 和向上或向下箭头键时发生的故障。
- 更新了密码提示 UI 中使用的屏幕键盘布局，使查找反斜杠键更为容易。
- 修复了自上次发布以来，用户报告给我们的其他故障。

## <a name="updates-for-version-1001"></a>针对版本 10.0.1 的更新

*发布日期：2019/12/15*

下面是此版本中的新增功能：

- 支持 Windows 虚拟桌面服务。
- 更新了连接中心 UI。
- 更新了会话中 UI。

## <a name="updates-for-version-1000"></a>针对版本 10.0.0 的更新

*发布日期：2019/12/13*

自我们上次更新适用于 iOS 的远程桌面客户端以来已经过去了一年多的时间。 不过，这次回归我们带来了激动人心的新更新，并且从现在开始，我们还将定期发布更多更新。下面是版本 10.0.0 中的新增功能：

- 支持 Windows 虚拟桌面服务。
- 新的连接中心 UI。
- 新的会话内 UI，可在已连接的电脑和应用之间切换。
- 辅助屏幕键盘的全新布局。
- 改进的外部键盘支持。
- 支持 SwiftPoint 蓝牙鼠标。
- 支持麦克风重定向。
- 支持本地存储重定向。
- 支持相机重定向（仅适用于 Windows 10 版本 1809 或更高版本）。
- 支持新的 iPhone 和 iPad 设备。
- 深色和浅色主题支持。
- 控制在连接到远程电脑或应用时电话是否会锁定。
- 现在可以通过长按远程桌面徽标按钮来折叠会话内的连接栏。

## <a name="updates-for-version-8142"></a>针对版本 8.1.42 的更新

*发布日期：2018 年 6 月 20 日*

- Bug 修复和性能改进。

## <a name="updates-for-version-8141"></a>针对版本 8.1.41 的更新

*发布日期：2018 年 3 月 28 日*

- 用于解决 CVE-2018-0886 中所述的 CredSSP 加密 Oracle 修正的更新。

## <a name="how-to-report-issues"></a>如何报告问题

我们致力于尽全力地打造好此应用，因此我们非常重视你的反馈。 你可以通过在客户端中导航到“设置” > “报告问题”将问题报告给我们 。
