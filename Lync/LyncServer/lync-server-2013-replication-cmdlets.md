---
title: 'Lync Server 2013: レプリケーションコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Replication cmdlets
ms:assetid: e0c49601-d2a3-45a1-b05c-26c7ff820708
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415677(v=OCS.15)
ms:contentKeyID: 48185527
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e1772a538330c897cdcc77e75e7ad796792c1d2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="replication-cmdlets-in-lync-server-2013"></a><span data-ttu-id="6eff7-102">Lync Server 2013 のレプリケーションコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6eff7-102">Replication cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6eff7-103">_**最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="6eff7-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="6eff7-104">レプリケーションコマンドレットを使用すると、Lync Server のレプリケーションを監視および管理することができます。</span><span class="sxs-lookup"><span data-stu-id="6eff7-104">The replication cmdlets provide a way for you to both monitor and manage Lync Server replication.</span></span> <span data-ttu-id="6eff7-105">これらのコマンドレットを使用して、レプリケーション設定を構成できます。レプリケーションの進行状況を監視するにはサーバー上のレプリケーションを手動で強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="6eff7-105">You can use these cmdlets to configure replication settings; to monitor replication progress; and to manually force replication on a server.</span></span>

<div>

## <a name="replication-cmdlets"></a><span data-ttu-id="6eff7-106">レプリケーションコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6eff7-106">Replication Cmdlets</span></span>

<span data-ttu-id="6eff7-107">次に、レプリケーションの管理に直接関連するコマンドレットの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="6eff7-107">The following is a list of cmdlets that relate directly to managing replication:</span></span>

<span data-ttu-id="6eff7-108">**レプリケート**</span><span class="sxs-lookup"><span data-stu-id="6eff7-108">**Replication**</span></span>

  - <span></span>  
    <span data-ttu-id="6eff7-109">[Debug-CsInterPoolReplication](https://technet.microsoft.com/en-us/library/JJ619185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6eff7-109">[Debug-CsInterPoolReplication](https://technet.microsoft.com/en-us/library/JJ619185(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6eff7-110">[CsManagementStoreReplication](https://technet.microsoft.com/en-us/library/Gg413060(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6eff7-110">[Invoke-CsManagementStoreReplication](https://technet.microsoft.com/en-us/library/Gg413060(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6eff7-111">[Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/en-us/library/Gg399052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6eff7-111">[Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/en-us/library/Gg399052(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6eff7-112">[CsReplica を有効にする](https://technet.microsoft.com/en-us/library/Gg425965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6eff7-112">[Enable-CsReplica](https://technet.microsoft.com/en-us/library/Gg425965(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6eff7-113">[CsReplica のテスト](https://technet.microsoft.com/en-us/library/JJ205289(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6eff7-113">[Test-CsReplica](https://technet.microsoft.com/en-us/library/JJ205289(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6eff7-114">[CsUserReplicatorConfiguration の入手](https://technet.microsoft.com/en-us/library/Gg398548(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6eff7-114">[Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg398548(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6eff7-115">[New-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg399059(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6eff7-115">[New-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg399059(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6eff7-116">[Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg425738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6eff7-116">[Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg425738(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6eff7-117">[Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg398540(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6eff7-117">[Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg398540(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6eff7-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="6eff7-118">See Also</span></span>


[<span data-ttu-id="6eff7-119">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="6eff7-119">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

