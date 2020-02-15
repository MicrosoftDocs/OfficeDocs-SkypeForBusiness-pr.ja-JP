---
title: 'Lync Server 2013: 新しいアーカイブ機能'
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
ms.openlocfilehash: bf8c632fa5858eaf35464e9885e65343bc699e54
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043809"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a><span data-ttu-id="d270e-102">Lync Server 2013 の新しいアーカイブ機能</span><span class="sxs-lookup"><span data-stu-id="d270e-102">New Archiving features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d270e-103">_**トピックの最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="d270e-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="d270e-104">Lync Server 2013 のアーカイブでは、次の種類のコンテンツをアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="d270e-104">Archiving in Lync Server 2013 can archive the following types of content:</span></span>

  - <span data-ttu-id="d270e-105">ピアツーピア インスタント メッセージ</span><span class="sxs-lookup"><span data-stu-id="d270e-105">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="d270e-106">マルチパーティのインスタント メッセージである電話会議 (ミーティング)</span><span class="sxs-lookup"><span data-stu-id="d270e-106">Conferences (meetings) that are multi-party instant messages</span></span>

  - <span data-ttu-id="d270e-107">アップロードされたコンテンツ (配布資料など) およびイベント関連のコンテンツ (参加、退出、アップロード、共有、表示設定の変更など) を含む電話会議コンテンツ</span><span class="sxs-lookup"><span data-stu-id="d270e-107">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

<span data-ttu-id="d270e-108">さらに、Lync Server 2013 のアーカイブには、展開と運用の効率を向上させる新機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="d270e-108">Additionally, Archiving in Lync Server 2013 provides new features that improve deployment and operations efficiency.</span></span> <span data-ttu-id="d270e-109">これらの新機能には、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="d270e-109">These new features consist of:</span></span>

  - <span data-ttu-id="d270e-110">**フロントエンドサーバー上のアーカイブの併置。**   Lync server 2013 には、別のアーカイブサーバーの役割がありません。</span><span class="sxs-lookup"><span data-stu-id="d270e-110">**Collocation of Archiving on Front End Servers.**   Lync Server 2013 does not have a separate Archiving Server role.</span></span> <span data-ttu-id="d270e-111">アーカイブは、Enterprise Edition 展開のすべてのフロントエンド サーバーおよび Standard Edition サーバーにインストールできるオプションの機能であり、プールまたはサイトに対する構成として実装できます。</span><span class="sxs-lookup"><span data-stu-id="d270e-111">Archiving is an optional feature available on all Front End Servers in an Enterprise Edition deployment, and on Standard Edition servers, that can be implemented configured for a pool or a site.</span></span>

  - <span data-ttu-id="d270e-112">**Microsoft Exchange 統合。**   アーカイブを展開するときに、exchange 2013 に所属していてメールボックスがインプレース保持されているすべてのユーザーに対して、既存の exchange 2013 ストレージとのアーカイブ用のデータストレージを統合することができます。したがって、個別の SQL Server データベースを展開して Lync データをアーカイブする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d270e-112">**Microsoft Exchange integration.**   When you deploy Archiving, you can integrate data storage for Archiving with your existing Exchange 2013 storage for all users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, so you don’t need to deploy separate SQL Server databases to archive Lync data.</span></span> <span data-ttu-id="d270e-113">Exchange 2013 を展開していない場合、または統合しない場合、または Exchange 2013 に所属していない Lync 2013 ユーザーがメールボックスをインプレース保持に設定している場合は、SQL Server を使用して個別のアーカイブデータベースを管理することができます。Lync communications からアーカイブされたデータ。</span><span class="sxs-lookup"><span data-stu-id="d270e-113">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync 2013 users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="d270e-114">Microsoft exchange 統合と Lync Server 2013 アーカイブデータベースの両方を使用することができますが、展開内の一部のユーザーに対して Microsoft Exchange 統合を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d270e-114">You can use both Microsoft Exchange integration and Lync Server 2013 Archiving databases if you want to use Microsoft Exchange integration for some but not all users in your deployment.</span></span> <span data-ttu-id="d270e-115">インプレース保持の詳細については、「」の「インプレースホールド」 [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d270e-115">For details about In-Place Hold, see “In-Place Hold” at [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500).</span></span>

  - <span data-ttu-id="d270e-116">**SQL ストアのミラーリング。**   アーカイブを展開するときに、アーカイブデータベースに対して SQL Server データベースのミラーリングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d270e-116">**SQL Store Mirroring.**   When you deploy Archiving, you can enable SQL Server database mirroring for your Archiving database.</span></span>

  - <span data-ttu-id="d270e-117">**ホワイトボードと投票のアーカイブ。**   アーカイブされた会議コンテンツに、会議中に共有されるホワイトボードと投票が含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d270e-117">**Archiving of Whiteboards and Polls.**   Archived conference content now includes whiteboards and polls that are shared during the meeting.</span></span>

<span data-ttu-id="d270e-118">次の種類のコンテンツはアーカイブされません。</span><span class="sxs-lookup"><span data-stu-id="d270e-118">The following types of content are not archived:</span></span>

  - <span data-ttu-id="d270e-119">ピアツーピア ファイル転送</span><span class="sxs-lookup"><span data-stu-id="d270e-119">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="d270e-120">ピアツーピア インスタント メッセージおよび電話会議のオーディオ/ビデオ</span><span class="sxs-lookup"><span data-stu-id="d270e-120">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="d270e-121">ピアツーピア インスタント メッセージおよび電話会議のアプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="d270e-121">Application sharing for peer-to-peer instant messages and conferences</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d270e-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="d270e-122">See Also</span></span>


[<span data-ttu-id="d270e-123">Lync Server 2013 でのアーカイブの計画</span><span class="sxs-lookup"><span data-stu-id="d270e-123">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

