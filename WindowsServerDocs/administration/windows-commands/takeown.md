---
title: takeown
description: 了解如何通过成为文件所有者来获取对文件的访问权限。
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 0683cd65-a6db-4cab-962b-45a0ff61f43c
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: da43b13f0333f3a12a8763db4cad31e12283bb8b
ms.sourcegitcommit: bf887504703337f8ad685d778124f65fe8c3dc13
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "83436192"
---
# <a name="takeown"></a>takeown

使管理员作为文件的所有者，恢复对之前被拒文件的访问权限。



## <a name="syntax"></a>语法

```
takeown [/s <Computer> [/u [<Domain>\]<User name> [/p [<Password>]]]] /f <File name> [/a] [/r [/d {Y|N}]]
```

#### <a name="parameters"></a>参数

|参数|说明|
|---------|-----------|
|/s \< 计算机>|指定远程计算机的名称或 IP 地址（不使用反斜杠）。 默认值为本地计算机。 此参数适用于命令中指定的所有文件和文件夹。|
|/u [ \< 域>\]<User name>|用指定用户帐户的权限运行脚本。 默认值为 "系统权限"。|
|/p [ \< Password>]|指定在 **/u**参数中指定的用户帐户的密码。|
|/f \< 文件名>|指定文件名或目录名称模式。 指定模式时，可以使用通配符 *。 你还可以使用语法*共享名* \* FileName *。|
|/a|向管理员组而不是当前用户提供所有权。|
|/r|对指定目录和子目录中的所有文件执行递归操作。|
|/d {Y \| N}|取消当当前用户对指定目录没有 "列出文件夹" 权限时显示的确认提示，而是使用指定的默认值。 **/D**选项的有效值如下所示：</br>-Y：取得目录的所有权。</br>-N：跳过目录。</br>请注意，必须将此选项与 **/r**选项一起使用。|
|/?|在命令提示符下显示帮助。|

## <a name="remarks"></a>备注

-   通常在批处理文件中使用此命令。
-   如果未指定 **/a**参数，则会为当前登录到计算机的用户提供文件所有权。
-   混合模式使用（**？** **takeown**命令不支持和 **&#42;**）。
-   删除**takeown**的锁定后，你可能需要使用 Windows 资源管理器或**cacls**命令向自己授予对文件和目录的完全权限，然后才能删除它们。 有关**cacls**的详细信息，请参阅本主题末尾的 "其他参考"。

## <a name="examples"></a><a name="BKMK_examples"></a>示例

若要获取名为 Lostfile 的文件的所有权，请键入：
```
takeown /f lostfile
```

## <a name="additional-references"></a>其他参考

- [命令行语法项](command-line-syntax-key.md)