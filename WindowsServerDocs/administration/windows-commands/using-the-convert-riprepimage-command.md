---
title: 转换-RiprepImage
description: RiprepImage 的参考主题，用于将现有远程安装准备（RIPrep）映像转换为 Windows 映像（.wim）格式。
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 88c2b96f-5947-4b64-9dcf-1946b3c013cf
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 12bdd6c49b5fdec0c0e4980a1abf7e21cefc538e
ms.sourcegitcommit: ab64dc83fca28039416c26226815502d0193500c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "82721028"
---
# <a name="convert-riprepimage"></a>转换-RiprepImage

将现有远程安装准备（RIPrep）映像转换为 Windows 映像（.wim）格式。

## <a name="syntax"></a>语法

```
WDSUTIL [Options] /Convert-RIPrepImage /FilePath:<File path and name>
     /DestinationImage
         /FilePath:<File path and name>
         [/Name:<Name>]
         [/Description:<Description>]
         [/InPlace]
         [/Overwrite:{Yes | No | Append}]
```

### <a name="parameters"></a>参数

|            参数            |                                                                                                                                                                                                                                                                                                               描述                                                                                                                                                                                                                                                                                                                |
|---------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| /FilePath：\<文件路径和名称> |                                                                                                                                                                                                       指定对应于 RIPrep 映像的 .sif 文件的完整路径和文件名。 此文件通常称为 Riprep .sif，位于包含 RIPrep 映像的文件夹的 \Templates 子文件夹中。                                                                                                                                                                                                       |
|        /DestinationImage        | 使用以下选项指定目标映像的设置。</br>-/FilePath：\<文件路径和名称>-设置新文件的完整文件路径。 例如： **C:\Temp\convert.wim**</br>-[/Name：\<Name>]-设置图像的显示名称。 如果未指定显示名称，将使用源映像的显示名称。</br>-[/Description： \<Description>]-设置映像的说明。</br>-[/InPlace]-指定应在原始 RIPrep 映像上进行转换，而不是在原始映像的副本上进行转换（这是默认行为）。</br>-[/Overwrite： {Yes |

## <a name="examples"></a>示例

若要将指定的 RIPrep 映像转换为 RIPREP，请键入：
```
WDSUTIL /Convert-RiPrepImage /FilePath:R:\RemoteInstall\Setup\English
\Images\Win2k3.SP1\i386\Templates\riprep.sif /DestinationImage
/FilePath:C:\Temp\RIPREP.wim
```
若要将指定的 RIPrep 映像转换为具有指定名称和说明的 RIPREP，并使用新文件覆盖它（如果文件已存在），请键入：
```
WDSUTIL /Verbose /Progress /Convert-RiPrepImage /FilePath:\\Server
\RemInst\Setup\English\Images\WinXP.SP2\i386\Templates\riprep.sif
/DestinationImage /FilePath:\\Server\Share\RIPREP.wim
/Name:WindowsXP image /Description:Converted RIPREP image of WindowsXP
/Overwrite:Append
```

## <a name="additional-references"></a>其他参考

- [命令行语法项](command-line-syntax-key.md)