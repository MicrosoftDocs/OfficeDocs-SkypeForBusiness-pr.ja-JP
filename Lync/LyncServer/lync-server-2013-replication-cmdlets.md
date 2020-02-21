---
title: 'Lync Server 2013: レプリケーションのコマンドレット'
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
ms.openlocfilehash: 9cefd52750a3fc54c56e7bcbafaecab661a9c10f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="replication-cmdlets-in-lync-server-2013"></a><span data-ttu-id="ca3b1-102">Lync Server 2013 のレプリケーションのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="ca3b1-102">Replication cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca3b1-103">_**トピックの最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="ca3b1-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="ca3b1-104">レプリケーションのコマンドレットを使用すると、Lync Server レプリケーションの監視と管理の両方を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ca3b1-104">The replication cmdlets provide a way for you to both monitor and manage Lync Server replication.</span></span> <span data-ttu-id="ca3b1-105">これらのコマンドレットを使用して、レプリケーション設定を構成できます。レプリケーションの進行状況を監視するにはサーバーでレプリケーションを手動で強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="ca3b1-105">You can use these cmdlets to configure replication settings; to monitor replication progress; and to manually force replication on a server.</span></span>

<div>

## <a name="replication-cmdlets"></a><span data-ttu-id="ca3b1-106">Replication Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ca3b1-106">Replication Cmdlets</span></span>

<span data-ttu-id="ca3b1-107">以下に、レプリケーションの管理に直接関連するコマンドレットの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="ca3b1-107">The following is a list of cmdlets that relate directly to managing replication:</span></span>

<span data-ttu-id="ca3b1-108">**レプリケーション**</span><span class="sxs-lookup"><span data-stu-id="ca3b1-108">**Replication**</span></span>

  - <span></span>  
    <span data-ttu-id="ca3b1-109">[デバッグ-CsInterPoolReplication](https://technet.microsoft.com/library/JJ619185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca3b1-109">[Debug-CsInterPoolReplication](https://technet.microsoft.com/library/JJ619185(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca3b1-110">[Invoke-csmanagementstorereplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca3b1-110">[Invoke-CsManagementStoreReplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca3b1-111">[Get-csmanagementstorereplicationstatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca3b1-111">[Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca3b1-112">[を有効にする-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca3b1-112">[Enable-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca3b1-113">[テスト-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca3b1-113">[Test-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca3b1-114">[-CsUserReplicatorConfiguration の取得](https://technet.microsoft.com/library/Gg398548(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca3b1-114">[Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca3b1-115">[新しい-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca3b1-115">[New-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca3b1-116">[-CsUserReplicatorConfiguration の削除](https://technet.microsoft.com/library/Gg425738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca3b1-116">[Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca3b1-117">[設定-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca3b1-117">[Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ca3b1-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca3b1-118">See Also</span></span>


[<span data-ttu-id="ca3b1-119">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="ca3b1-119">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

