---
title: 子命令集-DriverGroupFilter
description: 子命令集的参考主题-DriverGroupFilter，用于在驱动程序组中添加或删除现有的驱动程序组筛选器。
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 829ab1f0-4514-421e-9cc0-767b238da69c
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: f8a8d3567785b54a722b1787c519de7eb0b7a229
ms.sourcegitcommit: ab64dc83fca28039416c26226815502d0193500c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "82721726"
---
# <a name="subcommand-set-drivergroupfilter"></a>子命令： set-DriverGroupFilter

添加或删除驱动程序组中的现有驱动程序组筛选器。

## <a name="syntax"></a>语法

```
WDSUTIL /Set-DriverGroupFilter /DriverGroup:<Group Name> [/Server:<Server name>] /FilterType:<Filter Type> [/Policy:{Include | Exclude}] [/AddValue:<Value> [/AddValue:<Value> ...]] [/RemoveValue:<Value> [/RemoveValue:<Value> ...]]
```

### <a name="parameters"></a>参数

|         参数          |                                                                                                                                                                                                                                                                                                                                                                                                                                                                               描述                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| /DriverGroup：\<组名> |                                                                                                                                                                                                                                                                                                                                                                                                                                                                 指定驱动程序组的名称。                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|  [/Server：\<Server name>]  |                                                                                                                                                                                                                                                                                                                                                                                                                指定服务器的名称。 此名称可以是 NetBIOS 名称或 FQDN。 如果未指定服务器名称，则使用本地服务器。                                                                                                                                                                                                                                                                                                                                                                                                                 |
| /FilterType：\<FilterType>  |                                                                                                                                                                                                                                                                       指定要添加或删除的驱动程序组筛选器的类型。 可以在单个命令中指定多个筛选器。 对于每个 **/FilterType**，可以使用 **/RemoveValue**和 **/AddValue**添加或删除多个值。 \<FilterType> 可以是以下项之一：</br>**BiosVendor**</br>**BiosVersion**</br>**ChassisType**</br>**制造商**</br>**Uuid**</br>**OsVersion**</br>**OsEdition**</br>**OsLanguage**                                                                                                                                                                                                                                                                        |
|     [/Policy： {Include      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                排除}]                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|    [/AddValue：\<Value>]    | 指定要添加到筛选器中的新客户端值。 您可以为单个筛选器类型指定多个值。 请参阅以下列表，了解**ChassisType**的有效属性值。 有关获取所有其他筛选器类型的值的信息，请参阅[驱动程序组筛选器](https://go.microsoft.com/fwlink/?LinkID=155158)（<https://go.microsoft.com/fwlink/?LinkID=155158>）。</br>**其他**</br>**UnknownChassis**</br>**桌面**</br>**LowProfileDesktop**</br>**PizzaBox**</br>**MiniTower**</br>**指**</br>**可移植**</br>**便携式计算机**</br>**笔记本**</br>**手持式**</br>**DockingStation**</br>**AllInOne**</br>**SubNotebook**</br>**SpaceSaving**</br>**LunchBox**</br>**MainSystemChassis**</br>**ExpansionChassis**</br>**SubChassis**</br>**BusExpansionChassis**</br>**PeripheralChassis**</br>**StorageChassis**</br>**RackMountChassis**</br>**SealedCaseComputer**</br>**MultiSystemChassis**</br>**CompactPci**</br>**AdvancedTca** |
|  [/RemoveValue：\<Value>]   |                                                                                                                                                                                                                                                                                                                                                                                                                                     指定要从筛选器中删除的现有客户端值（与 **/AddValue**指定）。                                                                                                                                                                                                                                                                                                                                                                                                                                      |

## <a name="examples"></a>示例

若要删除筛选器，请键入下列内容之一：
```
WDSUTIL /Set-DriverGroupFilter /DriverGroup:PrinterDrivers /FilterType:Manufacturer /Policy:Include /AddValue:Name1 /RemoveValue:Name2
```
```
WDSUTIL /Set-DriverGroupFilter /DriverGroup:PrinterDrivers /FilterType:Manufacturer /Policy:Include /RemoveValue:Name1 /FilterType:ChassisType /Policy:Exclude /AddValue:Tower /AddValue:MiniTower
```

## <a name="additional-references"></a>其他参考

- [命令行语法项](command-line-syntax-key.md)