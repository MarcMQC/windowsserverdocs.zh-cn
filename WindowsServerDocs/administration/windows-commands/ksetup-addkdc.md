---
title: ksetup addkdc
description: 用于为给定 Kerberos 领域广告密钥发行中心（KDC）地址的 ksetup addkdc 命令的参考主题。
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 98bfc23a-14c4-401c-bcb3-9903c5cdde64
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: e51279166bf60196d12f877506d3228b78c4a711
ms.sourcegitcommit: 4f407b82435afe3111c215510b0ef797863f9cb4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2020
ms.locfileid: "83818087"
---
# <a name="ksetup-addkdc"></a>ksetup addkdc

添加给定 Kerberos 领域的密钥发行中心（KDC）地址

该映射存储在注册表中的**HKEY_LOCAL_MACHINE \system\currentcontrolset\control\lsa\kerberos\domains**下，必须重新启动计算机，然后才能使用新领域设置。

> [!NOTE]
> 若要将 Kerberos 领域配置数据部署到多台计算机，必须在单独的计算机上显式使用**安全配置模板**管理单元和策略分发。 不能使用此命令。

## <a name="syntax"></a>语法

```
ksetup /addkdc <realmname> [<KDCname>]
```

### <a name="parameters"></a>参数

| 参数 | 说明 |
| --------- | ----------- |
| `<realmname>` | 指定大写的 DNS 名称，例如 CORP。CONTOSO.COM。 在运行**ksetup**时，此值还显示为默认领域，并且是要添加其他 KDC 的领域。 |
| `<KDCname>` | 指定不区分大小写的完全限定的域名，例如 mitkdc.contoso.com。 如果省略了 KDC 名称，DNS 将定位 Kdc。 |

### <a name="examples"></a>示例

若要配置非 Windows KDC 服务器和工作站应使用的领域，请键入：

```
ksetup /addkdc CORP.CONTOSO.COM mitkdc.contoso.com
```

若要将本地计算机帐户密码设置为与 p@sswrd1 上一示例中相同的计算机上的%，然后重新启动计算机，请键入：

```
ksetup /setcomputerpassword p@sswrd1%
```

若要验证计算机的默认领域名称或验证此命令是否按预期方式工作，请键入：

```
ksetup
```
检查注册表以确保按预期方式进行映射。

## <a name="additional-references"></a>其他参考

- [命令行语法项](command-line-syntax-key.md)

- [ksetup 命令](ksetup.md)

- [ksetup setcomputerpassword 命令](ksetup-setcomputerpassword.md)
