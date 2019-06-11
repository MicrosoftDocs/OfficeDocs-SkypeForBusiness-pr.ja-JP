---
title: 'Lync Server 2013: アーカイブの新機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d736e823892aa6d6edcc5ab90df900a5c6b7ac79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a><span data-ttu-id="6d6df-102">Lync Server 2013 のアーカイブの新機能</span><span class="sxs-lookup"><span data-stu-id="6d6df-102">New Archiving features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d6df-103">_**最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="6d6df-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="6d6df-104">Lync Server 2013 でアーカイブすると、次の種類のコンテンツをアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="6d6df-104">Archiving in Lync Server 2013 can archive the following types of content:</span></span>

  - <span data-ttu-id="6d6df-105">ピアツーピアのインスタント メッセージ</span><span class="sxs-lookup"><span data-stu-id="6d6df-105">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="6d6df-106">マルチパーティのインスタントメッセージである会議 (会議)</span><span class="sxs-lookup"><span data-stu-id="6d6df-106">Conferences (meetings) that are multi-party instant messages</span></span>

  - <span data-ttu-id="6d6df-107">アップロードされたコンテンツ (配付資料など) およびイベント関連のコンテンツ (参加、退席、アップロード、共有、表示設定の変更など) を含む会議コンテンツ</span><span class="sxs-lookup"><span data-stu-id="6d6df-107">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

<span data-ttu-id="6d6df-108">さらに、Lync Server 2013 でアーカイブすると、展開と運用の効率を向上させるための新機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="6d6df-108">Additionally, Archiving in Lync Server 2013 provides new features that improve deployment and operations efficiency.</span></span> <span data-ttu-id="6d6df-109">次の新機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6d6df-109">These new features consist of:</span></span>

  - <span data-ttu-id="6d6df-110">**フロントエンドサーバー上のアーカイブの collocation。**   Lync server 2013 には、別のアーカイブサーバーの役割がありません。</span><span class="sxs-lookup"><span data-stu-id="6d6df-110">**Collocation of Archiving on Front End Servers.**   Lync Server 2013 does not have a separate Archiving Server role.</span></span> <span data-ttu-id="6d6df-111">アーカイブは、Enterprise Edition の展開におけるすべてのフロントエンドサーバーと、プールまたはサイト用に構成できる標準エディションのサーバーで利用できるオプションの機能です。</span><span class="sxs-lookup"><span data-stu-id="6d6df-111">Archiving is an optional feature available on all Front End Servers in an Enterprise Edition deployment, and on Standard Edition servers, that can be implemented configured for a pool or a site.</span></span>

  - <span data-ttu-id="6d6df-112">**Microsoft Exchange の統合。**   アーカイブを展開するときに、exchange 2013 を使用しているすべてのユーザーに対して、既存の exchange 2013 ストレージを使用してアーカイブするデータストレージを統合することができます。そのため、別の SQL Server を展開する必要はありません。Lync データをアーカイブするデータベース。</span><span class="sxs-lookup"><span data-stu-id="6d6df-112">**Microsoft Exchange integration.**   When you deploy Archiving, you can integrate data storage for Archiving with your existing Exchange 2013 storage for all users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, so you don’t need to deploy separate SQL Server databases to archive Lync data.</span></span> <span data-ttu-id="6d6df-113">Exchange 2013 を展開していない場合、または統合したくない場合、または、Exchange 2013 を使用していない Lync 2013 ユーザーがメールボックスをインプレースホールドしている場合は、SQL Server を使用して別のアーカイブデータベースを展開することができます。e Lync コミュニケーションからデータをアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="6d6df-113">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync 2013 users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="6d6df-114">Microsoft exchange 統合と Lync Server 2013 アーカイブデータベースの両方を使用できますが、展開内のすべてのユーザーに対して、Microsoft Exchange 統合を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6d6df-114">You can use both Microsoft Exchange integration and Lync Server 2013 Archiving databases if you want to use Microsoft Exchange integration for some but not all users in your deployment.</span></span> <span data-ttu-id="6d6df-115">インプレースホールドの詳細については、「インプレースホールド」を参照し[http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500)てください。</span><span class="sxs-lookup"><span data-stu-id="6d6df-115">For details about In-Place Hold, see “In-Place Hold” at [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500).</span></span>

  - <span data-ttu-id="6d6df-116">**SQL ストアのミラーリング。**   アーカイブを展開するときに、アーカイブデータベースに対して SQL Server データベースのミラーリングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6d6df-116">**SQL Store Mirroring.**   When you deploy Archiving, you can enable SQL Server database mirroring for your Archiving database.</span></span>

  - <span data-ttu-id="6d6df-117">**ホワイトボードと投票のアーカイブ。**   アーカイブされた会議コンテンツには、会議中に共有されるホワイトボードと投票が含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6d6df-117">**Archiving of Whiteboards and Polls.**   Archived conference content now includes whiteboards and polls that are shared during the meeting.</span></span>

<span data-ttu-id="6d6df-118">次の種類のコンテンツはアーカイブされません。</span><span class="sxs-lookup"><span data-stu-id="6d6df-118">The following types of content are not archived:</span></span>

  - <span data-ttu-id="6d6df-119">ピアツーピアのファイル転送</span><span class="sxs-lookup"><span data-stu-id="6d6df-119">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="6d6df-120">ピアツーピアのインスタント メッセージおよび会議の音声ビデオ</span><span class="sxs-lookup"><span data-stu-id="6d6df-120">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="6d6df-121">ピアツーピアインスタントメッセージ (im) と会議のアプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="6d6df-121">Application sharing for peer-to-peer instant messages and conferences</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="6d6df-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d6df-122">See Also</span></span>


[<span data-ttu-id="6d6df-123">Lync Server 2013 のアーカイブの計画</span><span class="sxs-lookup"><span data-stu-id="6d6df-123">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

