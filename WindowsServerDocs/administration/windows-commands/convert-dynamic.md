---
title: convert dynamic
description: 转换动态命令的参考主题，将基本磁盘转换为动态磁盘。
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 7b8fa4b1-850f-4e48-b05f-871c883ea33c
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 05d507fb5a1f8ac3ca8d8899249a26dee496ed2a
ms.sourcegitcommit: ab64dc83fca28039416c26226815502d0193500c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "82720780"
---
# <a name="convert-dynamic"></a>convert dynamic

将基本磁盘转换为动态磁盘。 若要成功执行此操作，必须选择基本磁盘。 使用 "[选择磁盘" 命令](select-disk.md)选择基本磁盘，并将焦点移动到该磁盘。

> [!NOTE]
> 有关如何使用此命令的说明，请参阅[将动态磁盘改回为基本磁盘](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc755238(v=ws.11))。

## <a name="syntax"></a>语法

```
convert dynamic [noerr]
```

### <a name="parameters"></a>参数

| 参数 | 描述 |
| --------- | ----------- |
| noerr | 仅用于脚本。 出现错误时，DiskPart 继续处理命令，就像未发生错误一样。 如果没有此参数，则错误会导致 DiskPart 退出并出现错误代码。 |

#### <a name="remarks"></a>备注

- 基本磁盘上的任何现有分区都将成为简单卷。

## <a name="examples"></a>示例

若要将基本磁盘转换为动态磁盘，请键入：

```
convert dynamic
```

## <a name="additional-references"></a>其他参考

- [命令行语法项](command-line-syntax-key.md)

- [转换命令](convert.md)
