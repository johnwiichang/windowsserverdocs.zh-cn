---
title: 将计算机加入到新的 Windows Server Essentials 服务器 1
description: 介绍如何使用 Windows Server Essentials
ms.custom: na
ms.date: 10/03/2016
ms.prod: windows-server-2016-essentials
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: cdfa9504-9881-4265-b308-c7ee8721bfaa
author: nnamuhcs
ms.author: coreyp
manager: dongill
ms.openlocfilehash: 0240abfff58baedd79ab038af93b107dbb898eb2
ms.sourcegitcommit: eaf071249b6eb6b1a758b38579a2d87710abfb54
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2019
ms.locfileid: "66432938"
---
# <a name="join-computers-to-the-new-windows-server-essentials-server1"></a>将计算机加入到新的 Windows Server Essentials 服务器 1

>适用于：Windows Server 2016 Essentials，Windows Server 2012 R2 Essentials 中，Windows Server 2012 Essentials

##  <a name="BKMK_JoinComputers"></a>   
 迁移过程的下一步是将客户端计算机加入到新的 Windows Server Essentials 网络并更新组策略设置。  
  
> [!NOTE]
>  如果客户端计算机已加入源服务器，则必须先在客户端计算机上卸载连接器软件，才可以将计算机连接到目标服务器。  
  
 对于加入域的计算机和未加入域的计算机而言，将客户端计算机连接到服务器的过程是相同的。  
  
- 浏览到 **http://** <em>destination-servername</em> **/connect** 并安装 Windows Server 连接器软件，就好像这是一台新计算机一样。  
  
> [!NOTE]
>  Windows Server 连接器软件不支持运行 Windows XP 或 Windows Vista 的计算机。 如果你拥有已加入域的运行 Windows XP 或 Windows Vista 的计算机，则可以跳过此步骤。  
  
### <a name="ensure-that-group-policy-has-updated"></a>确保组策略已更新  
  
> [!NOTE]
>  这是一个可选步骤，并且仅当已使用自定义组策略设置（例如文件夹重定向）配置源服务器时，它才是必选步骤。  
  
 当源服务器和目标服务器仍处于联机状态时，你应该确保组策略设置已从目标服务器复制到客户端计算机。 在每个客户端计算机上执行以下步骤：  
  
1.  打开“命令提示符”窗口。  
  
2.  在命令提示符处键入 **GPRESULT /R**，然后按 Enter。  
  
3.  查看来自应用的组策略部分的生成输出:，并确保它列出目标服务器上，例如**DestinationSrv.Domain.local**。 例如：  
  
    ```  
    USER SETTINGS  
    --------------  
        CN=User,OU=Users,DC=DOMAIN,DC=Local  
        Last time Group Policy was applied: 1/24/2011 at 1:26:27 PM  
        Group Policy was applied from:      DestinationSrv.Domain.local  
        Group Policy slow link threshold:   500 kbps  
        Domain Name:                        Domain  
        Domain Type:                        Windows 2011  
  
    ```  
  
4.  如果未列出目标服务器，则请在命令提示符下键入 **gpupdate /force**，然后按 Enter 刷新组策略设置。 然后，再次执行前面的过程。  
  
5.  如果目标服务器仍未出现，则在组策略设置中或者在将它们应用到此特定客户端计算机的过程中可能存在错误。 如果目标服务器未出现，则请执行以下步骤：  
  
    1.  依次单击“开始”  、“运行”  ，键入 **rsop.msc** （生成的策略集），然后按 Enter。  
  
    2.  展开具有对其的 X 的树，直到到达一个节点。  
  
    3.  右键单击该节点，再单击“查看错误”  ，以获取有关组策略设置为何无法应用于列出的计算机的信息。
