---
title: 'Lync Server 2013: バックアップと高可用性のコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and high availability cmdlets
ms:assetid: 5aff41a3-7a0e-4c51-9d5f-7f08e36bf046
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204925(v=OCS.15)
ms:contentKeyID: 48184236
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b730d265d32341b329bf5ba3a1055b37bd240a55
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-high-availability-cmdlets-in-lync-server-2013"></a><span data-ttu-id="7b08c-102">Lync Server 2013 のバックアップと高可用性のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="7b08c-102">Backup and high availability cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b08c-103">_**最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="7b08c-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="7b08c-104">バックアップと高可用性のコマンドレットを使用すると、管理者は Microsoft Lync Server 2013 で導入されたプールのバックアップ、復元、高可用性の機能を管理できます。</span><span class="sxs-lookup"><span data-stu-id="7b08c-104">The backup and high availability cmdlets enable administrators to manage the pool backup, restore, and high availability capabilities introduced in Microsoft Lync Server 2013.</span></span>

<div>

## <a name="backup-and-high-availability-cmdlets"></a><span data-ttu-id="7b08c-105">バックアップと高可用性のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="7b08c-105">Backup and High Availability Cmdlets</span></span>

<span data-ttu-id="7b08c-106">次に、Lync Server トポロジのバックアップと可用性の設定に直接関連するコマンドレットの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="7b08c-106">The following is a list of cmdlets that relate directly to backing up and configuring the availability of your Lync Server topology:</span></span>

<span data-ttu-id="7b08c-107">**バックアップと高可用性のコマンドレット**</span><span class="sxs-lookup"><span data-stu-id="7b08c-107">**Backup and High Availability Cmdlets**</span></span>

  - <span data-ttu-id="7b08c-108">[Get-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205087(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7b08c-108">[Get-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205087(v=OCS.15))</span></span>

  - <span data-ttu-id="7b08c-109">[Remove-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ204903(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7b08c-109">[Remove-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ204903(v=OCS.15))</span></span>

  - <span data-ttu-id="7b08c-110">[Set-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205006(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7b08c-110">[Set-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205006(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="7b08c-111">[Get-CsBackupServiceStatus](https://technet.microsoft.com/en-us/library/JJ205032(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7b08c-111">[Get-CsBackupServiceStatus](https://technet.microsoft.com/en-us/library/JJ205032(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="7b08c-112">[CsBackupServiceSync](https://technet.microsoft.com/en-us/library/JJ205374(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7b08c-112">[Invoke-CsBackupServiceSync](https://technet.microsoft.com/en-us/library/JJ205374(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="7b08c-113">[Debug-CsIntraPoolReplication](https://technet.microsoft.com/en-us/library/JJ205103(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7b08c-113">[Debug-CsIntraPoolReplication](https://technet.microsoft.com/en-us/library/JJ205103(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="7b08c-114">[Backup-CsPool](https://technet.microsoft.com/en-us/library/JJ204955(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7b08c-114">[Backup-CsPool](https://technet.microsoft.com/en-us/library/JJ204955(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="7b08c-115">[Get-CsPoolBackupRelationship](https://technet.microsoft.com/en-us/library/JJ204745(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7b08c-115">[Get-CsPoolBackupRelationship](https://technet.microsoft.com/en-us/library/JJ204745(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="7b08c-116">[Get-CsPoolFabricState](https://technet.microsoft.com/en-us/library/JJ619188(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7b08c-116">[Get-CsPoolFabricState](https://technet.microsoft.com/en-us/library/JJ619188(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="7b08c-117">[Invoke-CsPoolFailBack](https://technet.microsoft.com/en-us/library/JJ204873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7b08c-117">[Invoke-CsPoolFailBack](https://technet.microsoft.com/en-us/library/JJ204873(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="7b08c-118">[Invoke-CsPoolFailOver](https://technet.microsoft.com/en-us/library/JJ205189(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7b08c-118">[Invoke-CsPoolFailOver](https://technet.microsoft.com/en-us/library/JJ205189(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="7b08c-119">[Get-CsPoolUpgradeReadinessState](https://technet.microsoft.com/en-us/library/JJ204689(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7b08c-119">[Get-CsPoolUpgradeReadinessState](https://technet.microsoft.com/en-us/library/JJ204689(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="7b08c-120">[CsStorageServiceFlush](https://technet.microsoft.com/en-us/library/JJ619175(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7b08c-120">[Invoke-CsStorageServiceFlush](https://technet.microsoft.com/en-us/library/JJ619175(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="7b08c-121">[同期-CsUserData](https://technet.microsoft.com/en-us/library/JJ205242(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7b08c-121">[Sync-CsUserData](https://technet.microsoft.com/en-us/library/JJ205242(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="7b08c-122">[CsUserStoreBackupData を削除します](https://technet.microsoft.com/en-us/library/JJ205003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7b08c-122">[Remove-CsUserStoreBackupData](https://technet.microsoft.com/en-us/library/JJ205003(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

