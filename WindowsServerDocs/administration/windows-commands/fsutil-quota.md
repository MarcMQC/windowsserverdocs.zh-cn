---
title: fsutil quota
description: Fsutil quota 命令的参考主题，它管理 NTFS 卷上的磁盘配额，以便更精确地控制基于网络的存储。
ms.prod: windows-server
manager: dmoss
ms.author: toklima
author: toklima
ms.technology: storage
ms.assetid: 21225c11-7c72-4ea2-96bd-e63d4beb3be5
ms.topic: article
ms.date: 10/16/2017
ms.openlocfilehash: 54c4f6fe5fd5ae7a43d5057cd5837374f1b94ecd
ms.sourcegitcommit: bf887504703337f8ad685d778124f65fe8c3dc13
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "83435808"
---
# <a name="fsutil-quota"></a>fsutil quota

> 适用于： Windows Server （半年频道），Windows Server 2019，Windows Server 2016，Windows 10，Windows Server 2012 R2，Windows 8.1，Windows Server 2012，Windows 8

管理 NTFS 卷上的磁盘配额，以便更精确地控制基于网络的存储。

## <a name="syntax"></a>语法

```
fsutil quota [disable] <volumepath>
fsutil quota [enforce] <volumepath>
fsutil quota [modify] <volumepath> <threshold> <limit> <username>
fsutil quota [query] <volumepath>
fsutil quota [track] <volumepath>
fsutil quota [violations]
```

### <a name="parameters"></a>参数

| 参数 | 说明 |
| --------- | ----------- |
| disable | 在指定卷上禁用配额跟踪和强制。 |
| 实行 | 在指定卷上强制实施配额。 |
| modify | 修改现有磁盘配额，或创建新配额。 |
| 查询 | 列出现有磁盘配额。 |
| 跟踪 | 跟踪指定卷上的磁盘使用情况。 |
| 多次 | 搜索系统和应用程序日志，并显示一条消息，指示已检测到配额冲突，或者用户已达到配额阈值或配额限制。 |
| `<volumepath>` | 必需。 指定驱动器名称后跟冒号或 GUID （格式为） `volume{GUID}` 。 |
| `<threshold>`  | 设置发出警告的限制（以字节为单位）。 此参数对于命令是必需的 `fsutil quota modify` 。 |
| `<limit>` | 设置允许的最大磁盘使用量（以字节为单位）。 此参数对于命令是必需的 `fsutil quota modify` 。 |
| `<username>` | 指定域或用户名。 此参数对于命令是必需的 `fsutil quota modify` 。 |

#### <a name="remarks"></a>备注

- 磁盘配额是根据每个卷实现的，它们启用了基于每个用户的硬和软存储限制。

- 你可以使用在每次添加新用户或自动跟踪配额限制、将其编译为报表以及自动通过电子邮件将其发送给系统管理员时使用**fsutil 配额**的编写脚本设置配额限制。

### <a name="examples"></a>示例

若要列出使用 GUID "{928842df-5a01-11de-a85c-806e6f6e6963}" 指定的磁盘卷的现有磁盘配额，请键入：

```
fsutil quota query volume{928842df-5a01-11de-a85c-806e6f6e6963}
```

若要列出使用驱动器号（ **C：**）指定的磁盘卷的现有磁盘配额，请键入：

```
fsutil quota query C:
```

## <a name="additional-references"></a>其他参考

- [命令行语法项](command-line-syntax-key.md)

- [fsutil](fsutil.md)
