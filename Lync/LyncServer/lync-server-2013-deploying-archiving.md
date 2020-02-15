---
title: 'Lync Server 2013: アーカイブの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Archiving
ms:assetid: a89edd16-12d5-4602-ad2f-194b47d1188e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205147(v=OCS.15)
ms:contentKeyID: 48185031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 436870bd932a0cf92168555d298bf81aff1de667
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-archiving-in-lync-server-2013"></a><span data-ttu-id="0c2fe-102">Lync Server 2013 でのアーカイブの展開</span><span class="sxs-lookup"><span data-stu-id="0c2fe-102">Deploying Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c2fe-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="0c2fe-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="0c2fe-104">Lync Server 2013 には、Lync Server でのインスタントメッセージング (IM) コンテンツと会議の通信をアーカイブするためのソリューションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="0c2fe-104">Lync Server 2013 provides a solution for archiving instant messaging (IM) content and conferencing communications in Lync Server.</span></span> <span data-ttu-id="0c2fe-105">アーカイブストレージを実装するには、Lync Server 2013 のアーカイブデータの保存に SQL Server データベースを使用するか、Lync Server の2013と Exchange の2013ストレージの両方を使用して、アーカイブストレージを Exchange 2013 ストレージに統合します。</span><span class="sxs-lookup"><span data-stu-id="0c2fe-105">You can implement archiving support by integrating archiving storage with Exchange 2013 storage, by using SQL Server databases for storage of Lync Server 2013 archiving data, or by using both Lync Server 2013 and Exchange 2013 storage.</span></span> <span data-ttu-id="0c2fe-106">ポリシーやアーカイブの構成を使用してデータのアーカイブ方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="0c2fe-106">You control how data is archived using policies and archiving configurations.</span></span> <span data-ttu-id="0c2fe-107">詳細については、「計画」、「展開」、または「操作」のドキュメントの「planning [For アーカイビング in 2013 lync](lync-server-2013-planning-for-archiving.md) server [2013」](lync-server-2013-how-archiving-works.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c2fe-107">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation and [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<span data-ttu-id="0c2fe-108">このセクションの情報を使用して、最初にアーカイブをセットアップして構成することができます。</span><span class="sxs-lookup"><span data-stu-id="0c2fe-108">You can use the information in this section to set up and configure Archiving initially.</span></span> <span data-ttu-id="0c2fe-109">展開後に、アーカイブ設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="0c2fe-109">After deployment, you can change Archiving settings.</span></span> <span data-ttu-id="0c2fe-110">日常の管理のアーカイブサポートを実装する方法、または組織の新しい要件を満たす方法の詳細については、「操作」のドキュメントの「 [Lync Server 2013 アーカイブの管理](lync-server-2013-managing-archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c2fe-110">For details about how you implement archiving support for day-to-day management or to meet new requirements in your organization, see [Managing Lync Server 2013 Archiving](lync-server-2013-managing-archiving.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0c2fe-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0c2fe-111">In This Section</span></span>

  - [<span data-ttu-id="0c2fe-112">Lync Server 2013 でのアーカイブのしくみ</span><span class="sxs-lookup"><span data-stu-id="0c2fe-112">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="0c2fe-113">Lync Server 2013 でのアーカイブの展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="0c2fe-113">Deployment checklist for Archiving in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-archiving.md)

  - [<span data-ttu-id="0c2fe-114">Lync Server 2013 でのアーカイブ用のシステムおよびインフラストラクチャのセットアップ</span><span class="sxs-lookup"><span data-stu-id="0c2fe-114">Setting up systems and infrastructure for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md)

  - [<span data-ttu-id="0c2fe-115">既存の Lync Server 2013 展開へのアーカイブデータベースの追加</span><span class="sxs-lookup"><span data-stu-id="0c2fe-115">Adding Archiving databases to an existing Lync Server 2013 Deployment</span></span>](lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md)

  - [<span data-ttu-id="0c2fe-116">Lync Server 2013 でのアーカイブのサポートの構成</span><span class="sxs-lookup"><span data-stu-id="0c2fe-116">Configuring support for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-archiving.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

