---
title: change logon
description: Change logon 命令的参考主题，可用于启用或禁用来自客户端会话的登录，或者显示当前登录状态。
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 41466260-aee9-4333-bcb6-178112c22afd
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 4a2ebe75f6efa8c3bcfc0018d1f4e6051bb9ebb7
ms.sourcegitcommit: ab64dc83fca28039416c26226815502d0193500c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "82716123"
---
# <a name="change-logon"></a>change logon

> 适用于： Windows Server （半年频道），Windows Server 2019，Windows Server 2016，Windows Server 2012 R2，Windows Server 2012

启用或禁用来自客户端会话的登录，或者显示当前登录状态。 此实用程序对于系统维护非常有用。 您必须是管理员才能运行此命令。

> [!NOTE]
> 在 Windows Server 2008 R2 中，终端服务被重命名为远程桌面服务。 若要了解最新版本中的新增功能，请参阅[Windows Server 中远程桌面服务的新增功能](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn283323(v=ws.11))。

## <a name="syntax"></a>语法

```
change logon {/query | /enable | /disable | /drain | /drainuntilrestart}
```

### <a name="parameters"></a>参数

| 参数 | 描述 |
| --------- | ----------- |
| /query | 显示当前登录状态，不管是启用还是禁用。 |
| /enable | 允许来自客户端会话的登录，但不允许来自控制台的登录。 |
| /disable | 禁止来自客户端会话的后续登录，而不是从控制台中登录。 不会影响当前登录的用户。 |
| /drain | 禁止从新客户端会话登录，但允许重新断开现有会话的登录。 |
| /drainuntilrestart | 禁止在重新启动计算机之前从新的客户端会话登录，但允许重新与现有会话进行重新启动。 |
| /? | 在命令提示符下显示帮助。 |

#### <a name="remarks"></a>备注

- 重新启动系统时，将重新启用登录。

- 如果从客户端会话连接到远程桌面会话主机服务器，然后在重新启用登录之前禁用登录和注销，则无法重新连接到会话。 若要重新启用来自客户端会话的登录，请在控制台上登录。

### <a name="examples"></a>示例

- 若要显示当前登录状态，请键入：
  
  ```
  change logon /query
  ```

- 若要允许从客户端会话登录，请键入：

  ```
  change logon /enable
  ```

- 若要禁用客户端登录，请键入：

  ```
  change logon /disable
  ```
  
## <a name="additional-references"></a>其他参考

- [命令行语法项](command-line-syntax-key.md)

- [change 命令](change.md)

- [远程桌面服务（终端服务）命令参考](remote-desktop-services-terminal-services-command-reference.md)
