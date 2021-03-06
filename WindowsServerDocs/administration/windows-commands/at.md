---
title: at
description: At 命令的参考主题，它计划在指定的时间和日期在计算机上运行命令和程序。
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: ff18fd16-9437-4c53-8794-bfc67f5256b3
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 3aafcf4cbc4a6626a3390fe5ad6a305b90dfaec0
ms.sourcegitcommit: ab64dc83fca28039416c26226815502d0193500c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "82718922"
---
# <a name="at"></a>at

> 适用于： Windows Server （半年频道），Windows Server 2019，Windows Server 2016，Windows Server 2012 R2，Windows Server 2012

计划在指定的时间和日期在计算机上运行的命令和程序。 仅当计划服务正在运行**时，才**可以使用。 在不使用参数的情况下，**在**列出计划的命令。 您必须是本地管理员组的成员才能运行此命令。

## <a name="syntax"></a>语法

```
at [\computername] [[id] [/delete] | /delete [/yes]]
at [\computername] <time> [/interactive] [/every:date[,...] | /next:date[,...]] <command>
```

### <a name="parameters"></a>参数

| 参数 | 描述 |
| --------- | ----------- |
| `\<computername\>` | 指定远程计算机。 如果省略此参数，则会**在**本地计算机上计划命令和程序。 |
| `<id>` | 指定分配给计划命令的标识号。 |
| /delete | 取消计划的命令。 如果省略*ID*，计算机上的所有计划命令都将被取消。 |
| /yes | 删除计划事件时，会对系统中的所有查询回答 "是"。 |
| `<time>` | 指定要运行命令的时间。 时间以小时为单位表示，以24小时表示法表示（即，00:00 （午夜）到23:59）。 |
| 交互式 | 允许*命令*与在运行*命令*时登录的用户的桌面进行交互。 |
| 各个 | 在每周或每月的某一天或几天（例如，每个星期四或每月的第三天）运行*命令*。 |
| `<date>` | 指定要运行命令的日期。 可以指定一周中的一天或多天（即，键入**M**、**T**、**W**、**Th**、**F**、**S**、**Su**）或一个或多个月的某一天（即，键入1到31）。 用逗号分隔多个日期项。 如果省略*date*，则**在**使用当月的当前日期。 |
| 一个 | 在一天的下一次出现时运行*命令*（例如，下个星期四）。 |
| `<command>` | 指定要运行的 Windows 命令、程序（即 .exe 或 .com 文件）或批处理程序（即 .bat 或 .cmd 文件）。 当命令需要路径作为参数时，请使用绝对路径（即，以驱动器号开头的完整路径）。 如果命令在远程计算机上，请为服务器和共享名称指定通用命名约定（UNC）表示法，而不是远程驱动器号。 |
| /? | 在命令提示符下显示帮助。 |

### <a name="remarks"></a>备注

- 在运行命令之前，此命令不会自动加载 cmd.exe。 如果未运行可执行（.exe）文件，则必须在命令开头显式加载 cmd.exe，如下所示：

    ```
    cmd /c dir > c:\test.out
    ```

- 如果在不使用命令行选项的情况下使用此命令，则计划任务将显示在类似于以下格式的表中：

    ```
    Status  ID   Day        time        Command Line
    OK      1    Each F     4:30 PM     net send group leads status due
    OK      2    Each M     12:00 AM    chkstor > check.file
    OK      3    Each F     11:59 PM    backup2.bat
    ```

- 如果在此命令中包含标识号（*ID*），则只有单个条目的信息以如下格式显示：  

    ```
    Task ID: 1
    Status: OK
    Schedule: Each  F
    Time of Day: 4:30 PM
    Command: net send group leads status due
    ```

- 在计划命令（特别是具有命令行选项的命令）后，请通过**在**不使用任何命令行选项的情况下键入来检查命令语法是否正确。 如果 "**命令行**" 列中的信息错误，请删除并重新键入该命令。 如果仍然不正确，请使用更少的命令行选项重新键入命令。

- **在**运行时以后台进程的形式计划的命令。 计算机屏幕上不显示输出。 若要将输出重定向到文件，请使用`>`重定向符号。 如果将输出重定向到文件，则需要使用重定向符号前面`^`的转义符号，无论是在命令行中还是在批处理文件**中使用。** 例如，要将输出重定向到*输出 .txt*，请键入：

    ```
    at 14:45 c:\test.bat ^>c:\output.txt
    ```

    执行命令的当前目录为 systemroot 文件夹。

- 如果在计划命令运行后更改系统时间，请通过**在**不使用命令行选项的情况下键入，将**at**计划程序与修改后的系统时间同步。

- 计划的命令存储在注册表中。 因此，如果重新启动计划服务，则不会丢失计划任务。

- 不要将重定向的驱动器用于访问网络的计划作业。 计划服务可能无法访问重定向的驱动器，或者，如果在计划任务运行时有其他用户登录，则可能不会出现重定向的驱动器。 相反，请为计划作业使用 UNC 路径。 例如：  

    ```
    at 1:00pm my_backup \\server\share
    ```

    不要使用以下语法，其中**x：** 是用户建立的连接：  

    ```
    at 1:00pm my_backup x:
    ```

    如果计划使用驱动器号连接到共享目录的**at**命令，请在使用完该驱动器后，包含**at**命令以断开驱动器连接。 如果驱动器未断开连接，则在命令提示符下将不会提供已分配的驱动器号。

- 默认情况下，使用此命令计划的任务将在72小时后停止。 您可以修改注册表以更改此默认值。

    **修改注册表**

    > [!Caution]
    > 不正确地编辑注册表可能会对系统造成严重损坏。 在更改注册表之前，应备份计算机上任何有价值的数据。

    1. 启动注册表编辑器（regedit.exe）。

    2. 在注册表中找到并单击以下项：`HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Schedule`

    3. 在 "**编辑**" 菜单上，单击 "**添加值**"，然后添加以下注册表值：

        - **值名称。** atTaskMaxHours

        - **数据类型。** reg_DWOrd 

        - **基数.** Decimal

        - **值数据：** 0. **值数据**字段中的值为**0** ，表示没有限制，也不会停止。 介于1到99之间的值表示小时数。

- 您可以使用 "计划任务" 文件夹来查看或修改通过使用此命令创建的任务的设置。 使用此命令计划任务时，该任务将在 "计划任务" 文件夹中列出，其名称如下：**at3478**。 但是，如果通过 "计划任务" 文件夹修改任务，则会将其升级到正常的计划任务。 任务在**at**命令中不再可见，且 at 帐户设置不再适用于该任务。 必须为任务显式输入用户帐户和密码。

## <a name="examples"></a>示例

若要显示在市场营销服务器上计划的命令列表，请键入：

```
at \\marketing
```

若要详细了解 Corp 服务器上的标识号为3的命令，请键入：

```
at \\corp 3
```

计划在凌晨8:00 的 Corp 服务器上运行 net share 命令。 然后，将列表重定向到维护服务器，在 "报告" 共享目录中，键入 Corp .txt 文件，键入：

```
at \\corp 08:00 cmd /c net share reports=d:\marketing\reports >> \\maintenance\reports\corp.txt
```

若要将营销服务器的硬盘驱动器每隔五天午夜备份到磁带驱动器，请创建名为 Archive 的批处理程序，其中包含备份命令，然后计划要运行的批处理程序，键入：

```
at \\marketing 00:00 /every:5,10,15,20,25,30 archive
```

若要取消当前服务器上计划的所有命令，请按如下所示清除**at**计划信息：

```
at /delete
```

若要运行不是可执行（.exe）文件的命令，请在命令前面加上**cmd/c** ，按如下所示加载 cmd.exe：

```
cmd /c dir > c:\test.out
```

## <a name="additional-references"></a>其他参考

- [命令行语法项](command-line-syntax-key.md)

- [schtasks](schtasks.md)。 另一个命令行计划工具。
