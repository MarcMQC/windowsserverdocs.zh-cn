---
title: 复制-映像
description: 复制映像的参考主题，用于复制同一个映像组中的映像。
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: bea41cf4-36e6-4181-afa5-00170ebd4fdc
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: b3ffd590682ec36f78d3cbd53fd67fe3b5981e4c
ms.sourcegitcommit: ab64dc83fca28039416c26226815502d0193500c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "82721002"
---
# <a name="copy-image"></a>复制-映像

> 适用于： Windows Server （半年频道），Windows Server 2019，Windows Server 2016，Windows Server 2012 R2，Windows Server 2012

复制同一映像组中的映像。 若要在映像组之间复制图像，请使用 "[导出图像](using-the-export-image-command.md)" 命令命令，然后使用 "[添加图像](using-the-add-image-command.md)命令" 命令。

## <a name="syntax"></a>语法
```
wdsutil [Options] /copy-Imagmedia:<Image name> [/Server:<Server name>]
   mediatype:Install
    mediaGroup:<Image group name>]
     [/Filename:<File name>]
     /DestinationImage
         /Name:<Name>
         /Filename:<File name>
         [/Description:<Description>]
```
### <a name="parameters"></a>参数
|参数|描述|
|-------|--------|
许可证<Image name>|指定要复制的映像的名称。|
|[/Server：<Server name>]|指定服务器的名称。 此名称可以是 NetBIOS 名称或完全限定的域名（FQDN）。 如果未指定服务器名称，将使用本地服务器。|
媒体媒体：安装|指定要复制的映像类型。 必须将此选项设置为 "**安装**"。|
|\mediaGroup：<Image group name>]|指定包含要复制的映像的映像组。 如果未指定映像组并且服务器上只存在一个组，则默认情况下将使用该映像组。 如果服务器上存在多个映像组，则必须指定映像组。|
|[/Filename：<Filename>]|指定要复制的映像的文件名。 如果无法按名称唯一地标识源映像，则必须指定文件名。|
|/DestinationImage|指定目标映像的设置，如下表所述。<p>-/Name：<Name> -设置要复制的映像的显示名称。<br />-/Filename：<Filename> -设置将包含图像副本的目标映像文件的名称。<br />-[/Description： <Description>]-设置图像副本的说明。|
## <a name="examples"></a>示例
若要创建指定映像的副本并将其命名为 WindowsVista，请键入：
```
wdsutil /copy-Imagmedia:Windows Vista with Officemediatype:Install /DestinationImage /Name:copy of Windows Vista with Office /Filename:WindowsVista.wim
```
若要创建指定映像的副本，应用指定的设置，并将副本命名为 WindowsVista，请键入：
```
wdsutil /verbose /Progress /copy-Imagmedia:Windows Vista with Office /Server:MyWDSServemediatype:InstalmediaGroup:ImageGroup1 
/Filename:install.wim /DestinationImage /Name:copy of Windows Vista with Office /Filename:WindowsVista.wim /Description:This is a copy of the original Windows image with Office installed
```
## <a name="additional-references"></a>其他参考
- [命令行语法键](command-line-syntax-key.md)
[Using the add-Image Command](using-the-add-image-command.md)
使用 "[输出](using-the-export-image-command.md)
映像" 命令通过 "[获取](using-the-get-image-command.md)
映像" 命令通过 "删除图像" 命令使用 "[删除](using-the-remove-image-command.md)
图像" 命令，使用 "[替换图像](using-the-replace-image-command.md)
" 命令[子命令。](subcommand-set-image.md)
