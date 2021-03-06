---
title: dcgpofix
description: Dcgpofix 命令的参考主题，用于重新创建域的默认组策略对象（Gpo）。
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 81d5fa65-2aea-49d3-b353-357441846c00
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: f11b7db8110cd2d7dcf08cd250eba411e7ff21a8
ms.sourcegitcommit: fad2ba64bbc13763772e21ed3eabd010f6a5da34
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2020
ms.locfileid: "82993170"
---
# <a name="dcgpofix"></a>dcgpofix

重新创建域的默认组策略对象（Gpo）。 若要访问组策略管理控制台（GPMC），必须通过服务器管理器将组策略管理作为功能安装。

>[!IMPORTANT]
> 最佳做法是，应仅将默认域策略 GPO 配置为管理默认的**帐户策略**设置、密码策略、帐户锁定策略和 Kerberos 策略。 此外，还应将默认域控制器策略 GPO 配置为仅设置用户权限和审核策略。

## <a name="syntax"></a>语法

```
dcgpofix [/ignoreschema] [/target: {domain | dc | both}] [/?]
```

### <a name="parameters"></a>参数

| 参数 | 说明 |
| --------- | ----------- |
| /ignoreschema | 当你运行此命令时，将忽略 Active Directory 架构的版本。 否则，该命令仅适用于在其中附带了命令的 Windows 版本的架构版本。 |
| `/target {domain | dc | both` | 指定是以默认域策略、默认域控制器策略还是这两种策略类型为目标。 |
| /? | 在命令提示符下显示帮助。 |

## <a name="examples"></a>示例

若要管理默认**帐户策略**设置、密码策略、帐户锁定策略和 Kerberos 策略，同时忽略 Active Directory 架构版本，请键入：

```
dcgpofix /ignoreschema /target:domain
```

若要将默认域控制器策略 GPO 配置为仅设置用户权限和审核策略，同时忽略 Active Directory 架构版本，请键入：

```
dcgpofix /ignoreschema /target:dc
```

## <a name="additional-references"></a>其他参考

- [命令行语法项](command-line-syntax-key.md)