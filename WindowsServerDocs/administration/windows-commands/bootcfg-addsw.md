---
title: bootcfg addsw
description: Bootcfg addsw 命令的参考主题，它为指定的操作系统条目添加操作系统加载选项。
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: d8389293-ecd9-42f0-b84b-b9ead4cf52e6
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 17abdc1ba28afad173ea6486519277916f08ad3d
ms.sourcegitcommit: ab64dc83fca28039416c26226815502d0193500c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "82709947"
---
# <a name="bootcfg-addsw"></a>bootcfg addsw

> 适用于： Windows Server （半年频道），Windows Server 2019，Windows Server 2016，Windows Server 2012 R2，Windows Server 2012

为指定的操作系统项添加操作系统加载选项。

## <a name="syntax"></a>语法

```
bootcfg /addsw [/s <computer> [/u <domain>\<user> /p <password>]] [/mm <maximumram>] [/bv] [/so] [/ng] /id <osentrylinenum>
```

### <a name="parameters"></a>参数

| 术语 | 定义 |
| ---- | ---------- |
| `/s <computer>` | 指定远程计算机的名称或 IP 地址（请勿使用反斜杠）。 默认值为本地计算机。 |
| `/u <domain>\<user>`  | 使用`<user>`或`<domain>\<user>`指定的用户的帐户权限运行命令。 默认为发出命令的计算机上当前登录用户的权限。 |
| `/p <password>` | 指定在 **/u**参数中指定的用户帐户的密码。 |
| `/mm <maximumram>` | 指定操作系统可以使用的最大 RAM 量（以 mb 为单位）。 该值必须等于或大于 32 Mb。 |
| /bv | 将 **/basevideo**选项添加到指定`<osentrylinenum>`的，指导操作系统为安装的视频驱动程序使用标准 VGA 模式。 |
| /so | 将 **/sos**选项添加到指定`<osentrylinenum>`的中，指示操作系统在加载时显示设备驱动程序名称。 |
| /ng | 将 **/noguiboot**选项添加到指定`<osentrylinenum>`的中，禁用出现在 CTRL + ALT + DEL logon 提示符之前的进度栏。 |
| `/id <osentrylinenum>` | 指定 Boot.ini 文件的 [操作系统] 部分中添加了操作系统加载选项的操作系统条目行号。 [操作系统] 部分标题后面的第一行是1。 |
| /? | 在命令提示符下显示帮助。 |

## <a name="examples"></a>示例

使用**bootcfg/addsw**命令：

```
bootcfg /addsw /mm 64 /id 2
bootcfg /addsw /so /id 3
bootcfg /addsw /so /ng /s srvmain /u hiropln /id 2
bootcfg /addsw /ng /id 2
bootcfg /addsw /mm 96 /ng /s srvmain /u maindom\hiropln /p p@ssW23 /id 2
```

## <a name="additional-references"></a>其他参考

- [命令行语法项](command-line-syntax-key.md)

- [bootcfg 命令](bootcfg.md)
