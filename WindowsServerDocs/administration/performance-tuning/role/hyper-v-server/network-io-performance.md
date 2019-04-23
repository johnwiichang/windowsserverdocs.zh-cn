---
title: HYPER-V 网络 I/O 性能
description: 网络中的 HYPER-V 性能优化的 i/o 性能注意事项
ms.prod: windows-server-threshold
ms.technology: performance-tuning-guide
ms.topic: article
ms.author: Asmahi; SandySp; JoPoulso
author: phstee
ms.date: 10/16/2017
ms.openlocfilehash: d52c4fff6c7e06fb0a9f2b44ea51a0a790e6674d
ms.sourcegitcommit: 0d0b32c8986ba7db9536e0b8648d4ddf9b03e452
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2019
ms.locfileid: "59814358"
---
# <a name="hyper-v-network-io-performance"></a>HYPER-V 网络 I/O 性能

Server 2016 包含几项改进和新功能，以优化网络性能下的 HYPER-V。  这篇文章的未来版本中，将包含有关如何优化网络性能的文档。

## <a name="live-migration"></a>实时迁移

实时迁移可让你以透明方式将运行的虚拟机从故障转移群集的一个节点移到另一个节点，而无需断开的网络连接和假设停机时间在同一群集中。

**请注意**  故障转移群集需要共享的存储的群集节点。

移动正在运行的虚拟机的过程可以分为两个主要阶段。 第一阶段将复制到新的主机的当前主机的虚拟机的内存。 第二个阶段将从当前主机到新主机传输虚拟机状态。 可以上从当前主机到新的主机中传输数据的速度大大取决于这两个阶段的持续时间。

提供专用的网络进行实时迁移流量可帮助最大程度减少完成实时迁移所需的时间，并确保一致的迁移时间。

![示例中的 hyper-v 实时迁移配置](../../media/perftune-guide-live-migration.png)

此外，增加发送和接收缓冲区在每个网络适配器所涉及的迁移可以提高迁移性能。

如果您的硬件支持，Windows Server 2012 R2 引入了通过压缩通过网络传输之前的内存来提高实时迁移速度，或使用远程直接内存访问 (RDMA)，一个选项。

## <a name="see-also"></a>请参阅

-   [HYPER-V 术语](terminology.md)

-   [HYPER-V 体系结构](architecture.md)

-   [HYPER-V 服务器配置](configuration.md)

-   [HYPER-V 处理器性能](processor-performance.md)

-   [HYPER-V 内存性能](memory-performance.md)

-   [HYPER-V 存储 I/O 性能](storage-io-performance.md)

-   [虚拟化环境中检测瓶颈](detecting-virtualized-environment-bottlenecks.md)

-   [Linux 虚拟机](linux-virtual-machine-considerations.md)