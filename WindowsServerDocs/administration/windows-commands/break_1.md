---
title: break
description: Break 命令的参考主题。 此命令已不再使用。
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: c89b7357-d69e-4141-826e-73c9ba0fc630
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 301c526903c95dec90c4883a54713eee20f516d2
ms.sourcegitcommit: ab64dc83fca28039416c26226815502d0193500c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "82708785"
---
# <a name="break"></a>break

> [!IMPORTANT]
> 此命令已不再使用。 包括该命令仅用于保持与现有 MS-DOS 文件的兼容性，但由于该命令的功能是自动的，因此在命令行上不起作用。

设置或清除对 MS-DOS 系统的扩展 CTRL + C 检查。 如果在没有参数的情况下使用，则**break**将显示现有设置值。

如果命令扩展已在 Windows 平台上启用并运行，则在批处理文件中插入**break**命令将进入硬编码的断点，前提是调试器正在调试该断点。

## <a name="syntax"></a>语法

```
break=[on|off]
```

## <a name="additional-references"></a>其他参考

- [命令行语法项](command-line-syntax-key.md)
  
- [break 命令](break.md)
