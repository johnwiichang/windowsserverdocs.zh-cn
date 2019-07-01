---
title: 打开 telnet
description: 'Windows 命令主题 * * *- '
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: e30ad68c-2366-4754-ac36-311a2392902a vhorne
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 186664a75978f589a9a26047c72b9db74dd2dc4d
ms.sourcegitcommit: eaf071249b6eb6b1a758b38579a2d87710abfb54
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2019
ms.locfileid: "66441127"
---
# <a name="telnet-open"></a>telnet： 打开

>适用于：Windows 服务器 （半年频道），Windows Server 2016 中，Windows Server 2012 R2、 Windows Server 2012

连接到 telnet 服务器。    
## <a name="syntax"></a>语法  
```  
o[pen] <hostname> [<Port>]  
```  
### <a name="parameters"></a>Parameters  

| 参数  |                                        描述                                         |
|------------|--------------------------------------------------------------------------------------------|
| <hostname> |                         指定的计算机名称或 IP 地址。                         |
|  [<Port>]  | 指定 telnet 服务器正在侦听的 TCP 端口。 默认端口为 TCP 端口 23。 |

## <a name="BKMK_Examples"></a>示例  
连接到 telnet 服务器在 telnet.microsoft.com。  
```  
o telnet.microsoft.com  
```  
## <a name="additional-references"></a>其他参考  
-   [命令行语法项](command-line-syntax-key.md)  