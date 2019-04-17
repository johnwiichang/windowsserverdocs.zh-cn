---
ms.assetid: e727a33d-133b-43c9-b6a4-7c00f9cb6000
title: "查看域型号"
description: 
author: billmath
ms.author: billmath
manager: femila
ms.date: 05/31/2017
ms.topic: article
ms.prod: windows-server-threshold
ms.technology: identity-adds
ms.openlocfilehash: c57c23c0bd8694b66ab29b45bd9e47826ed1e01d
ms.sourcegitcommit: db290fa07e9d50686667bfba3969e20377548504
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2017
---
# <a name="reviewing-the-domain-models"></a>查看域型号

>适用于：Windows Server 2016，Windows Server 2012 R2、Windows Server 2012

以下因素会影响你选择的域设计模型：  
  
-   你有想要分配给 Active Directory 域服务 (广告 DS) 你网络上的可用的容量量。 目标是信息的选择带宽可用网络提供的影响最小的高效复制型号。  
  
-   你的组织中的用户的数量。 如果你的组织中包含大量的用户，部署多个域使您能够分区您的数据，并为你提供更好地控制的可通过给定的网络连接的复制流量。 这将使您可以控制复制的数据，并减少创建者 slow 您网络中的链接上的复制交通加载。  
  
最简单的域设计为单个域。 在单个域设计，域控制器的所有复制的所有信息。 如有必要，但是，你可以将部署区域额外的域。 如果连接网络基础结构的各部分 slow 链接，按森林所有者想要确保已分配给广告 DS 容量未超过复制通信，可能会发生此。  
  
最好在最小化林中部署的域的数量。 这减少了整体复杂性部署的因此，降低总体拥有成本。 下表列出了增加区域域与之关联的管理成本。  
  
|成本|影响|  
|--------|----------------|  
|管理的服务管理员的多个组|每个域都有它自己需要分开管理的服务管理员组。 这些服务管理员组成员必须严格控制。|  
|保持一致性组策略设置共有的多个域中|必须到森林中的每个单独域单独应用需要应用树林中的组策略设置。|  
|维护访问控制一致性和审核共有的多个域的设置|森林中的每个单独域到必须单独应用访问控制和审核需要森林跨应用的设置。|  
|对象域之间移动的可能性增加|域的更多的可能性就越大，用户将需要移动到另一个域中。 此移动可能会影响最终用户。|  
  
> [!NOTE]  
>  Windows Server 2008 精准密码并锁定策略还可能会影响你选择的域设计模型的帐户。 在此版本的 Windows Server 2008 之前, 你可能应用只有一个密码和帐户锁定策略，指定默认域策略域中，在域中的所有用户。 因此，如果你希望不同的密码和帐户锁定为不同的用户的设置，你必须要创建一个密码筛选器或部署多个域。 指定多个密码策略，并将不同的密码限制和帐户锁定策略应用到不同的用户单个域中，你现在可以使用精准密码策略。 有关精准密码和帐户锁定策略的详细信息，请参阅 Step-by-Step Fine-Grained 密码和帐户锁定策略配置指南 ([https://go.microsoft.com/fwlink/?LinkID=91477](https://go.microsoft.com/fwlink/?LinkID=91477))。  
  
## <a name="single-domain-model"></a>一个域型号  
一个域模型是最简单的方法来管理和最便宜维护。 它包含包含一个域森林。 此域森林根域中，并且包含所有用户和组森林中的帐户。  
  
一个域森林模型减少管理复杂性提供以下优势：  
  
-   任何域控制器可以进行森林中的任何用户身份验证。  
  
-   所有域控制器都可以全球目录，因此你不需要的全球目录服务器放置计划。  
  
在单个域树林中，所有目录数据都复制到承载域控制器的所有地理位置。 易于管理此模型时，它还将创建两个域型号的大多数复制流量。 目录划分多个域限制复制的特定地理区域，但会在更多管理开销到的对象。  
  
## <a name="regional-domain-model"></a>区域域型号  
在某个域中的所有对象数据都复制到该域中的所有域控制器。 出于此原因，如果你森林包含大量的用户，跨不同的地理位置由 (WAN) 的宽的区域网络连接都分发你可能需要部署地减少超过 WAN 链接复制通信的区域。 可以根据网络 WAN 连接组织基于地理位置的区域。  
  
区域域模型可以长时间保留稳定环境。 基本用来在稳定元素，如大陆限制模型中定义的域的区域。 基于其他因素，例如，组织中的组域可以经常更改，并且可能会要求你重新构建环境。  
  
区域域型号和组成的森林根域一个或多个区域的域。 创建区域域型号设计涉及识别哪些域森林根域和确定其他必须满足你复制的域的数量。 如果你的组织中包括需要数据隔离或服务隔离从其他组组织中的组，创建单独林的这些组。 数据隔离或服务隔离不提供域。  
  

