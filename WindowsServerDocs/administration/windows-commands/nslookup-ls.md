---
title: nslookup ls
description: '* * * * 的参考主题'
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: f15f06fe-67e7-41a9-93b5-192ab14ab380
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 8357208406c0fca5d68da419baa2092d94fa9ec9
ms.sourcegitcommit: ab64dc83fca28039416c26226815502d0193500c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "82723707"
---
# <a name="nslookup-ls"></a>nslookup ls

> 适用于： Windows Server （半年频道），Windows Server 2019，Windows Server 2016，Windows Server 2012 R2，Windows Server 2012

列出域名系统（DNS）域的信息。
## <a name="syntax"></a>语法
```
ls [<Option>] <DNSDomain> [{[>] <FileName>|[>>] <FileName>}]
```
### <a name="parameters"></a>参数

|    参数    |                                                                                                                                                                                                                                                                                                               描述                                                                                                                                                                                                                                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    <Option>     | 下表列出了有效选项。<p>--t：列出指定类型的所有记录。 有关的<querytype>说明，请参阅**setquerytype** in 其他引用。<br />--a：列出 DNS 域中计算机的别名。 此参数是 **-t CNAME**的同义词<br />--d：列出 DNS 域的所有记录。 此参数是 **-t ANY**的同义词<br />--h：列出 DNS 域的 CPU 和操作系统信息。 此参数是 **-t HINFO**的同义词<br />--s：列出 DNS 域中计算机的已知服务。 此参数是 **-t WKS**的同义词。 |
|   <DNSDomain>   |                                                                                                                                                                                                                                                                                         指定要获取其信息的 DNS 域。                                                                                                                                                                                                                                                                                         |
|   <FileName>    |                                                                                                                                                                                                                                 指定用于保存输出的文件名。 您可以使用大于（>）和双大于号（>>）字符以常规方式重定向输出。                                                                                                                                                                                                                                  |
| {help &#124;？} |                                                                                                                                                                                                                                                                                          显示**nslookup**子命令的简短摘要。                                                                                                                                                                                                                                                                                           |

## <a name="remarks"></a>备注
- 默认输出包含计算机名称及其 IP 地址。 将输出定向到文件时，会为从服务器接收的每个50记录打印哈希标记
  ## <a name="additional-references"></a>其他参考
  - [命令行语法 Key](command-line-syntax-key.md)
  [nslookup set querytype](nslookup-set-querytype.md)
