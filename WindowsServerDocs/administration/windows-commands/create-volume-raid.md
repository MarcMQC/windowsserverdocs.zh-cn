---
title: create volume raid
description: 使用三个或更多指定的动态磁盘创建 RAID-5 卷的 create volume raid 命令的参考主题。
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 9f257950-9240-4d5f-9537-8ad653d48ebf
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 1c773cf4412640759910e8c127a95f7cc34581d4
ms.sourcegitcommit: fad2ba64bbc13763772e21ed3eabd010f6a5da34
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2020
ms.locfileid: "82993233"
---
# <a name="create-volume-raid"></a>create volume raid

> 适用于： Windows Server （半年频道），Windows Server 2019，Windows Server 2016，Windows Server 2012 R2，Windows Server 2012

使用三个或更多指定的动态磁盘创建一个 RAID-5 卷。 创建卷完成后，焦点会自动移到新卷。

## <a name="syntax"></a>语法

```
create volume raid [size=<n>] disk=<n>,<n>,<n>[,<n>,...] [align=<n>] [noerr]
```

### <a name="parameters"></a>参数

| 参数 | 说明 |
| --------- | ----------- |
| 大小 =`<n>` | 该卷将占用的每个磁盘上的磁盘空间量（以 MB 为单位）。 如果没有给定大小，则将创建最大可能的 RAID-5 卷。 具有最小可用连续空间的磁盘决定 RAID-5 卷的大小并从每个磁盘分配相同的空间量。 RAID-5 卷中可使用磁盘空间的实际容量小于磁盘空间的总容量，因为某些磁盘空间需要用于奇偶校验。 |
| 磁盘 =`<n>,<n>,<n>[,<n>,...]` | 要在其上创建 RAID-5 卷的动态磁盘。 若要创建一个 RAID-5 卷，至少需要三个动态磁盘。 每个磁盘上分配的`size=<n>`空间量等于。 |
| align =`<n>` | 将所有卷区与最接近的对齐边界对齐。 通常与硬件 RAID 逻辑单元号（LUN）阵列一起使用以提高性能。 `<n>`从磁盘开始到最接近的对齐边界的千字节（KB）数。 |
| noerr | 仅用于脚本。 出现错误时，DiskPart 继续处理命令，就像未发生错误一样。 如果没有此参数，则错误会导致 DiskPart 退出并出现错误代码。 |

## <a name="examples"></a>示例

若要创建大小为 1000 mb 的 RAID-5 卷，请使用磁盘1、2和3，键入：

```
create volume raid size=1000 disk=1,2,3
```

## <a name="additional-references"></a>其他参考

- [命令行语法项](command-line-syntax-key.md)

- [create 命令](create.md)
