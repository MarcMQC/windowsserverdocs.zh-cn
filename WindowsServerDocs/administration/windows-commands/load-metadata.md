---
title: 加载元数据
description: 加载元数据命令的参考主题，此命令在导入可传送的卷影副本之前加载元数据 .cab 文件，或者在还原时加载写入器元数据。
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 2c535487-668b-44fc-babb-ff59cf7d190e
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: c7dc967476412261e7afc228088566f74ec4208c
ms.sourcegitcommit: 4f407b82435afe3111c215510b0ef797863f9cb4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2020
ms.locfileid: "83820187"
---
# <a name="load-metadata"></a>加载元数据

在导入可传送的卷影副本之前加载元数据 .cab 文件，或者在还原时加载写入器元数据。 如果在没有参数的情况下使用，**加载元数据**将在命令提示符下显示帮助。

## <a name="syntax"></a>语法

```
load metadata [<drive>:][<path>]<metadata.cab>
```

### <a name="parameters"></a>参数

| 参数 | 说明 |
| --------- | ----------- |
| `[<drive>:][<path>]` | 指定元数据文件的位置。 |
| metadata .cab | 指定要加载的元数据 .cab 文件。 |

## <a name="remarks"></a>备注

- 您可以使用 "**导入**" 命令根据**负载元数据**指定的元数据导入可传送的卷影副本。

- 必须先运行此命令，然后才能加载所选的编写器和组件以**进行还原。**

## <a name="examples"></a>示例

若要从默认位置加载名为元文件的元数据文件，请键入：

```
load metadata metafile.cab
```

## <a name="additional-references"></a>其他参考

- [命令行语法项](command-line-syntax-key.md)

- [导入 diskshadow 命令](import.md)

- [开始 restore 命令](begin-restore.md)
