---
title: select volume
description: '* * * * 的参考主题'
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 5d70d776-80ad-4f20-8288-a7997fb1df28
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: a3885d5d40e35e975ebe1cc28ddc26d4c1e78e24
ms.sourcegitcommit: ab64dc83fca28039416c26226815502d0193500c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "82721992"
---
# <a name="select-volume"></a>select volume

> 适用于： Windows Server （半年频道），Windows Server 2019，Windows Server 2016，Windows Server 2012 R2，Windows Server 2012

选择指定的卷并将焦点移动到该卷。 此命令还可用于显示当前在所选磁盘中有焦点的卷。  
  
  
  
## <a name="syntax"></a>语法  
  
```  
select volume={<n>|<d>}  
```  
  
### <a name="parameters"></a>参数  
  
| 参数 |                                                                               描述                                                                                |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    <n>    | 要接收焦点的卷的编号。 可以通过使用 DiskPart 中的 "**列出卷**" 命令，查看当前所选磁盘上的所有卷的编号。 |
|    <d>    |                                                 要接收焦点的卷的驱动器号或装入点路径。                                                 |
  
## <a name="remarks"></a>备注  
  
-   如果未指定卷，则此命令将显示当前在所选磁盘中有焦点的卷。  
  
-   在基本磁盘上，选择卷还会将焦点提供给相应的分区。  
  
-   如果选择了包含相应分区的卷，则会自动选择该分区。  
  
-   如果使用相应的卷选择了分区，则会自动选择该卷。  
  
## <a name="examples"></a>示例  
若要将焦点转移到第2卷，请键入：  
  
```  
select volume=2  
```  
  
若要将焦点转移到驱动器 C，请键入：  
  
```  
select volume=c  
```  
  
若要将焦点移动到名为 mountpath 的文件夹中的卷，请键入：  
  
```  
select volume=c:\mountpath  
```  
  
若要显示当前在所选磁盘中有焦点的卷，请键入：  
  
```  
select volume  
```  
  
## <a name="additional-references"></a>其他参考  
- [命令行语法项](command-line-syntax-key.md)  
  

  

