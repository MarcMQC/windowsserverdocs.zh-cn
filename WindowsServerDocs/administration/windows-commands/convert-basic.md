---
title: convert basic
description: Convert basic 命令的参考主题，它将空的动态磁盘转换为基本磁盘。
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 61329896-3b56-4959-8d58-45cbe18ba860
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: e44ecc9f5d18bbe426c63f8854e7c3347f418bb2
ms.sourcegitcommit: ab64dc83fca28039416c26226815502d0193500c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "82720792"
---
# <a name="convert-basic"></a>convert basic

将空的动态磁盘转换为基本磁盘。 若要成功执行此操作，必须选择一个动态磁盘。 使用 "[选择磁盘" 命令](select-disk.md)选择动态磁盘并将焦点移动到该磁盘。

> [!IMPORTANT]
> 若要将磁盘转换成基本磁盘，该磁盘必须为空。 转换磁盘之前，请备份数据，然后删除全部分区或卷。

> [!NOTE]
> 有关如何使用此命令的说明，请参阅[将动态磁盘改回为基本磁盘](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc755238(v=ws.11))。

## <a name="syntax"></a>语法

```
convert basic [noerr]
```

### <a name="parameters"></a>参数

| 参数 | 描述 |
| --------- | ----------- |
| noerr | 仅用于脚本。 出现错误时，DiskPart 继续处理命令，就像未发生错误一样。 如果没有此参数，则错误会导致 DiskPart 退出并出现错误代码。 |

## <a name="examples"></a>示例

若要将所选的动态磁盘转换为基本磁盘，请键入：

```
convert basic
```

## <a name="additional-references"></a>其他参考

- [命令行语法项](command-line-syntax-key.md)

- [转换命令](convert.md)
