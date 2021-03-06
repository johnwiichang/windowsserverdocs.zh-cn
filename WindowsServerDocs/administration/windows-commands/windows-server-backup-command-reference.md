---
title: Windows Server 备份命令参考
description: '适用于 * * * * 的 Windows 命令主题 '
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 03de0a65-21f0-4dd7-a3ae-251c98bbf6eb
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: c05a44d3390e110fbaf276dfb9b40c1f0adc1dd5
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2019
ms.locfileid: "71362046"
---
# <a name="windows-server-backup-command-reference"></a>Windows Server 备份命令参考



以下用于**wbadmin**的子命令通过命令提示符提供备份和恢复功能。

若要配置备份计划，您必须是**Administrators**组的成员。 若要使用此命令执行所有其他任务，您必须是**Backup Operators**或**Administrators**组的成员，或者您必须被委派了适当的权限。

必须从提升的命令提示符运行**wbadmin** 。 （若要打开提升的命令提示符，请单击 "**开始**"，右键单击 "**命令提示符**"，然后单击 "以**管理员身份运行**"。）

|命令|描述|
|----------|-----------|
|[Wbadmin enable backup](wbadmin-enable-backup.md)|配置并启用每日备份计划。|
|[Wbadmin disable backup](wbadmin-disable-backup.md)|禁用日常备份。|
|[Wbadmin start backup](wbadmin-start-backup.md)|运行一次性备份。 如果与不带参数一起使用，则将使用每日备份计划的设置。|
|[Wbadmin stop job](wbadmin-stop-job.md)|停止当前正在运行的备份或恢复操作。|
|[Wbadmin get versions](wbadmin-get-versions.md)|列出从本地计算机恢复的备份的详细信息，或者，如果指定了其他位置，则从另一台计算机。|
|[Wbadmin get items](wbadmin-get-items.md)|列出特定备份中包含的项。|
|[Wbadmin start recovery](wbadmin-start-recovery.md)|运行指定的卷、应用程序、文件或文件夹的恢复。|
|[Wbadmin get status](wbadmin-get-status.md)|显示当前正在运行的备份或恢复操作的状态。|
|[Wbadmin get disks](wbadmin-get-disks.md)|列出当前处于联机状态的磁盘。|
|[Wbadmin start systemstaterecovery](wbadmin-start-systemstaterecovery.md)|运行系统状态恢复。|
|[Wbadmin start systemstatebackup](wbadmin-start-systemstatebackup.md)|运行系统状态备份。|
|[Wbadmin delete systemstatebackup](wbadmin-delete-systemstatebackup.md)|删除一个或多个系统状态备份。|
|[Wbadmin start sysrecovery](wbadmin-start-sysrecovery.md)|运行完整系统的恢复（至少包含操作系统状态的所有卷）。 仅当使用 Windows 恢复环境时，此子命令才可用。|
|[Wbadmin restore catalog](wbadmin-restore-catalog.md)|在本地计算机上的备份目录已损坏的情况下，从指定的存储位置恢复备份目录。|
|[Wbadmin delete catalog](wbadmin-delete-catalog.md)|删除本地计算机上的备份目录。 仅当此计算机上的备份目录已损坏，并且你没有将备份存储在可用于还原目录的其他位置时，才使用此命令。|