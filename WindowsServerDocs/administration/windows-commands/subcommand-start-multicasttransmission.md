---
title: 子命令 /start-multicasttransmission
description: 'Windows 命令主题 * * *- '
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: a1b2d459-1ece-49d4-997c-9d206c463b61
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: d7e3e59a0907caf2769d5df00aeaf00589ab450d
ms.sourcegitcommit: 0d0b32c8986ba7db9536e0b8648d4ddf9b03e452
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2019
ms.locfileid: "59842678"
---
# <a name="subcommand-start-multicasttransmission"></a>子命令： /start-multicasttransmission

>适用于：Windows 服务器 （半年频道），Windows Server 2016 中，Windows Server 2012 R2、 Windows Server 2012

启动映像的 Scheduled-cast 传输。
## <a name="syntax"></a>语法
**Windows Server 2008**
```
wdsutil /start-MulticastTransmissiomedia:<Image name> [/Server:<Server namemediatype:InstallmediaGroup:<Image group name>] [/Filename:<File name>]
```
**Windows Server 2008 R2**的启动映像：
```
wdsutil [Options] /start-MulticastTransmissiomedia:<Image name>
        [/Server:<Server name>]
      mediatype:Boot
        /Architecture:{x86 | ia64 | x64}
        [/Filename:<File name>]
```
对于安装映像：
```
wdsutil [Options] /start-MulticastTransmissiomedia:<Image name>
        [/Server:<Server name>]
      mediatype:Install
       mediaGroup:<Image Group>]
        [/Filename:<File name>]
```
## <a name="parameters"></a>Parameters
|参数|描述|
|-------|--------|
媒体：<Image name>|指定映像的名称。|
|[/ 服务器：<Server name>]|指定的服务器的名称。 这可以是 NetBIOS 名称或完全限定的域名 (FQDN)。 如果指定没有服务器名称，则将使用本地服务器。|
媒体类型: {安装&#124;启动}|指定图像类型。 请注意，此选项必须设置为**安装**对于 Windows Server 2008。|
|/ 体系结构: {x86 &#124; ia64 &#124; x64}|与传输启动相关联的启动映像的体系结构。 由于它是可以在不同的体系结构中包含的启动映像的映像名称，则应指定体系结构，以确保使用正确的传输。|
|\mediaGroup:<Image group name>]|指定映像的映像组。 如果未指定任何映像组名称和服务器上只有一个映像组存在，将使用该映像组。 如果在服务器上存在多个映像组，必须使用此选项来指定映像组名称。|
|[/ Filename:<File name>]|指定包含图像的文件的名称。 如果名称不能唯一标识该映像，必须使用此选项以指定的文件的名称。|
## <a name="BKMK_examples"></a>示例
若要启动的多播的传输，请键入以下项之一：
```
wdsutil /start-MulticastTransmissiomedia:"Vista with Office"
/Imagetype:Install
wdsutil /start-MulticastTransmission /Server:MyWDSServemedia:"Vista with Officemediatype:InstalmediaGroup:ImageGroup1 /Filename:install.wim
```
若要开始启动映像的 Windows Server 2008 R2，类型的多播的传输：
```
wdsutil /start-MulticastTransmission /Server:MyWDSServemedia:"X64 Boot Imagemediatype:Boot /Architecture:x64
/Filename:boot.wim\n\
```
#### <a name="additional-references"></a>其他参考
[命令行语法解答](command-line-syntax-key.md)
[使用 get AllMulticastTransmissions 命令](using-the-get-allmulticasttransmissions-command.md)
[使用 /get-multicasttransmission 命令](using-the-get-multicasttransmission-command.md)
[使用新 MulticastTransmission 命令](using-the-new-multicasttransmission-command.md)
[使用 /remove-multicasttransmission 命令](using-the-remove-multicasttransmission-command.md)