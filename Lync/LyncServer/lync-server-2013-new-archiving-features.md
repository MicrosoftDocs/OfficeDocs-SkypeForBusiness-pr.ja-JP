---
title: 'Lync Server 2013: 新しいアーカイブ機能'
description: 'Lync Server 2013: 新しいアーカイブ機能。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5b69c90e62914284f178ae328375c6e350f5b3e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561353"
---
# <a name="new-archiving-features-in-lync-server-2013"></a><span data-ttu-id="dcade-103">Lync Server 2013 の新しいアーカイブ機能</span><span class="sxs-lookup"><span data-stu-id="dcade-103">New Archiving features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dcade-104">_**トピックの最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="dcade-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="dcade-105">Lync Server 2013 のアーカイブでは、次の種類のコンテンツをアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="dcade-105">Archiving in Lync Server 2013 can archive the following types of content:</span></span>

  - <span data-ttu-id="dcade-106">ピアツーピア インスタント メッセージ</span><span class="sxs-lookup"><span data-stu-id="dcade-106">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="dcade-107">マルチパーティのインスタント メッセージである電話会議 (ミーティング)</span><span class="sxs-lookup"><span data-stu-id="dcade-107">Conferences (meetings) that are multi-party instant messages</span></span>

  - <span data-ttu-id="dcade-108">アップロードされたコンテンツ (配布資料など) およびイベント関連のコンテンツ (参加、退出、アップロード、共有、表示設定の変更など) を含む電話会議コンテンツ</span><span class="sxs-lookup"><span data-stu-id="dcade-108">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

<span data-ttu-id="dcade-109">さらに、Lync Server 2013 のアーカイブには、展開と運用の効率を向上させる新機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="dcade-109">Additionally, Archiving in Lync Server 2013 provides new features that improve deployment and operations efficiency.</span></span> <span data-ttu-id="dcade-110">これらの新機能には、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="dcade-110">These new features consist of:</span></span>

  - <span data-ttu-id="dcade-111">**フロントエンドサーバー上のアーカイブの併置。**    Lync Server 2013 には、別のアーカイブサーバーの役割がありません。</span><span class="sxs-lookup"><span data-stu-id="dcade-111">**Collocation of Archiving on Front End Servers.**   Lync Server 2013 does not have a separate Archiving Server role.</span></span> <span data-ttu-id="dcade-112">アーカイブは、Enterprise Edition 展開のすべてのフロントエンド サーバーおよび Standard Edition サーバーにインストールできるオプションの機能であり、プールまたはサイトに対する構成として実装できます。</span><span class="sxs-lookup"><span data-stu-id="dcade-112">Archiving is an optional feature available on all Front End Servers in an Enterprise Edition deployment, and on Standard Edition servers, that can be implemented configured for a pool or a site.</span></span>

  - <span data-ttu-id="dcade-113">**Microsoft Exchange 統合。**    アーカイブを展開するときに、Exchange 2013 に所属しているすべてのユーザーに対して既存の Exchange 2013 ストレージとのアーカイブ用のデータストレージを統合し、メールボックスを In-Place 保持に配置することができます。したがって、個別の SQL Server データベースを展開して Lync データをアーカイブする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dcade-113">**Microsoft Exchange integration.**   When you deploy Archiving, you can integrate data storage for Archiving with your existing Exchange 2013 storage for all users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, so you don’t need to deploy separate SQL Server databases to archive Lync data.</span></span> <span data-ttu-id="dcade-114">Exchange 2013 の展開を行っていない場合、または統合しない場合、または Exchange 2013 に所属していない Lync 2013 ユーザーがメールボックスを In-Place 保持している場合は、SQL Server を使用して Lync コミュニケーションからアーカイブされたデータを格納することで、別のアーカイブデータベースを展開できます。</span><span class="sxs-lookup"><span data-stu-id="dcade-114">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync 2013 users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="dcade-115">Microsoft exchange 統合と Lync Server 2013 アーカイブデータベースの両方を使用することができますが、展開内の一部のユーザーに対して Microsoft Exchange 統合を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcade-115">You can use both Microsoft Exchange integration and Lync Server 2013 Archiving databases if you want to use Microsoft Exchange integration for some but not all users in your deployment.</span></span> <span data-ttu-id="dcade-116">In-Place ホールドの詳細については、「」の「インプレースホールド」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500) 。</span><span class="sxs-lookup"><span data-stu-id="dcade-116">For details about In-Place Hold, see “In-Place Hold” at [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500).</span></span>

  - <span data-ttu-id="dcade-117">**SQL ストアのミラーリング。**    アーカイブを展開するときに、アーカイブデータベースに対して SQL Server データベースのミラーリングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="dcade-117">**SQL Store Mirroring.**   When you deploy Archiving, you can enable SQL Server database mirroring for your Archiving database.</span></span>

  - <span data-ttu-id="dcade-118">**ホワイトボードと投票のアーカイブ。**    アーカイブされた会議コンテンツに、会議中に共有されるホワイトボードと投票が含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="dcade-118">**Archiving of Whiteboards and Polls.**   Archived conference content now includes whiteboards and polls that are shared during the meeting.</span></span>

<span data-ttu-id="dcade-119">次の種類のコンテンツはアーカイブされません。</span><span class="sxs-lookup"><span data-stu-id="dcade-119">The following types of content are not archived:</span></span>

  - <span data-ttu-id="dcade-120">ピアツーピア ファイル転送</span><span class="sxs-lookup"><span data-stu-id="dcade-120">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="dcade-121">ピアツーピア インスタント メッセージおよび電話会議のオーディオ/ビデオ</span><span class="sxs-lookup"><span data-stu-id="dcade-121">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="dcade-122">ピアツーピア インスタント メッセージおよび電話会議のアプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="dcade-122">Application sharing for peer-to-peer instant messages and conferences</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="dcade-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="dcade-123">See Also</span></span>


[<span data-ttu-id="dcade-124">Lync Server 2013 でのアーカイブの計画</span><span class="sxs-lookup"><span data-stu-id="dcade-124">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

