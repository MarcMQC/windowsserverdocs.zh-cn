---
title: color
description: Color 命令的参考主题，该主题可更改当前会话的命令提示符窗口中的前景色和背景色。
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: f5b67131-d196-45ec-a3f9-b5d9f091fd86
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 94b5a1e4ca4d4a01ea714adc45e64a6efaa32aa6
ms.sourcegitcommit: ab64dc83fca28039416c26226815502d0193500c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "82711932"
---
# <a name="color"></a>color

更改当前会话的命令提示符窗口中的前景色和背景色。 如果在没有参数的情况下使用，则**color**会还原默认的 "命令提示符" 窗口前景色和背景色。

## <a name="syntax"></a>语法

```
color [[<b>]<f>]
```

### <a name="parameters"></a>参数

| 参数 | 描述 |
| --------- | ----------- |
| `<b>` | 指定背景色。 |
| `<f>` | 指定前景色。 |
| /? | 在命令提示符下显示帮助。 |

其中：

下表列出了可用作`<b>`和`<f>`的值的有效十六进制数字：

| 值 | 颜色 |
| ----- | ----- |
| 0 | 黑色 |
| 1 | 蓝色 |
| 2 | 绿色 |
| 3 | Aqua |
| 4 | Red |
| 5 | 紫色 |
| 6 | Yellow |
| 7 | 白色 |
| 8 | 灰色 |
| 9 | 浅蓝色 |
| a | 浅绿 |
| b | 浅浅绿色 |
| c | 浅红色 |
| d | 浅紫色 |
| e | 浅黄色 |
| f | 亮白色 |

#### <a name="remarks"></a>备注

- 不要在和`<b>` `<f>`之间使用空格字符。

- 如果只指定一个十六进制数字，则将使用相应的颜色作为前景色，并将背景色设置为默认颜色。

- 若要设置默认的 "命令提示符" 窗口颜色，请选择 "**命令提示符**" 窗口的左上角，选择 "**默认值**"，选择 "**颜色**" 选项卡，然后选择要用于**屏幕文本**和**屏幕背景**的颜色。

- 如果`<b>`和`<f>`是相同的颜色值，则将 ERRORLEVEL 设置为`1`，并且不会对前景或背景色进行任何更改。

## <a name="examples"></a>示例

若要将 "命令提示符" 窗口的背景色更改为灰色，将前景色更改为红色，请键入：

```
color 84
```

若要将 "命令提示符" 窗口前景色更改为浅黄色，请键入：

```
color e
```

> [!NOTE]
> 在此示例中，背景设置为默认颜色，因为只指定了一个十六进制数字。

## <a name="additional-references"></a>其他参考

- [命令行语法项](command-line-syntax-key.md)
