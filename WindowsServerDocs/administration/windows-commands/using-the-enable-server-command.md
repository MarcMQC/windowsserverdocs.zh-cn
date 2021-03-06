---
title: 启用-服务器
description: 启用服务器的参考主题，该主题启用所有服务 Windows 部署服务。
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 939ffbfb-cf3c-4310-9627-6e7e0c0644d6
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: bf7bf57c0784fa16719b9f77da50212bca0ef850
ms.sourcegitcommit: ab64dc83fca28039416c26226815502d0193500c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "82720932"
---
# <a name="enable-server"></a>启用-服务器

> 适用于： Windows Server （半年频道），Windows Server 2019，Windows Server 2016，Windows Server 2012 R2，Windows Server 2012

启用 Windows 部署服务的所有服务。

## <a name="syntax"></a>语法
```
wdsutil [Options] /Enable-Server [/Server:<Server name>]
```
### <a name="parameters"></a>参数
|参数|描述|
|-------|--------|
|[/Server：<Server name>]|指定服务器的名称。 此名称可以是 NetBIOS 名称或完全限定的域名（FQDN）。 如果未指定服务器名称，将使用本地服务器。|
## <a name="examples"></a>示例
若要在服务器上启用这些服务，请运行下列操作之一：
```
wdsutil /Enable-Server
wdsutil /verbose /Enable-Server /Server:MyWDSServer
```
## <a name="additional-references"></a>其他参考
- [使用命令行语法的命令行语法键](command-line-syntax-key.md)
[Using the disable-Server Command](using-the-disable-server-command.md)

使用 "服务器"[命令通过 "](using-the-get-server-command.md)[初始化-](using-the-initialize-server-command.md)
服务器" 命令[执行命令： set-server](subcommand-set-server.md)
[子命令：启动-服务器](subcommand-start-server.md)
[子命令：停止-服务器](subcommand-stop-server.md)
["取消初始化-服务器" 选项](the-uninitialize-server-option.md)
