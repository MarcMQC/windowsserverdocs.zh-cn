---
title: sfc
description: 用于 sfc 的参考主题，它扫描并验证所有受保护系统文件的完整性并将错误版本替换为正确的版本。
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: c58c25da-e028-42a6-9e10-973484a4b953
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: af2167e1e23b0698c17159b1ae6b1970a06219d4
ms.sourcegitcommit: 4f407b82435afe3111c215510b0ef797863f9cb4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2020
ms.locfileid: "83821258"
---
# <a name="sfc"></a>sfc

> 适用于： Windows Server （半年频道），Windows Server 2019，Windows Server 2016，Windows Server 2012 R2，Windows Server 2012

扫描并验证所有受保护系统文件的完整性，并将错误版本替换为正确的版本。


## <a name="syntax"></a>语法
```
sfc [/scannow] [/verifyonly] [/scanfile=<file>] [/verifyfile=<file>] [/offwindir=<offline windows directory> /offbootdir=<offline boot directory>]
```

#### <a name="parameters"></a>参数
|参数|说明|
|-------|--------|
|/scannow|扫描所有受保护系统文件的完整性，并在可能的情况中修复包含问题的文件。|
|/verifyonly|扫描所有受保护系统文件的完整性。 不执行任何修复操作。|
|/scanfile|如果检测到问题，则扫描指定文件的完整性并修复文件（如果可能）。|
|\<文件>|指定的完整路径和文件名|
|/verifyfile|验证指定文件的完整性。 不执行任何修复操作。|
|/offwindir|指定脱机修复的脱机 windows 目录的位置。|
|/offbootdir|指定脱机启动目录的脱机位置|
|/?|在命令提示符下显示帮助。|

## <a name="remarks"></a>备注
-   您必须以 Administrators 组成员的身份登录才能运行**sfc**。
-   如果**sfc**发现某个受保护的文件已被覆盖，则它将从**systemroot\system32\dllcache**文件夹中检索正确的文件版本，并替换错误的文件。
-   Windows Server 2003、Windows Server 2008 和 Windows Server 2008 R2 上的**sfc**之间存在功能差异：
-   有关 Windows Server 2003 上的**sfc**的详细信息，请参阅 Microsoft 知识库中的[文章 310747](https://go.microsoft.com/fwlink/?LinkId=227069) 。
-   有关 Windows Server 2008 和 Windows Server 2008 R2 上的**sfc**的详细信息，请参阅[系统文件检查器](https://go.microsoft.com/fwlink/?LinkId=227071)。

## <a name="examples"></a>示例
若要验证**kernel32.dll 文件**，请键入：
```
sfc /verifyfile=c:\windows\system32\kernel32.dll
```
若要设置脱机**kernel32.dll**文件的脱机修复，并将脱机启动目录设置为 " **d：** "，并将 "脱机 windows 目录" 设置为 " **d:\windows**"，请键入：
```
sfc /scanfile=d:\windows\system32\kernel32.dll /offbootdir=d:\ /offwindir=d:\windows
```

## <a name="additional-references"></a>其他参考
- [命令行语法项](command-line-syntax-key.md)

