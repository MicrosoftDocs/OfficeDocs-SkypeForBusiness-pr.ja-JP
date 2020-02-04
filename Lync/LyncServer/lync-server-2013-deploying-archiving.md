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
ms.openlocfilehash: 86b1394df9bb52502e1e0c605bedb05a0579042e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-archiving-in-lync-server-2013"></a><span data-ttu-id="caa4b-102">Lync Server 2013 でのアーカイブの展開</span><span class="sxs-lookup"><span data-stu-id="caa4b-102">Deploying Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="caa4b-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="caa4b-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="caa4b-104">Lync Server 2013 には、Lync Server でインスタントメッセージング (IM) コンテンツと会議の通信をアーカイブするためのソリューションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="caa4b-104">Lync Server 2013 provides a solution for archiving instant messaging (IM) content and conferencing communications in Lync Server.</span></span> <span data-ttu-id="caa4b-105">アーカイブストレージを Exchange 2013 ストレージと統合して、Lync Server 2013 データの保存に SQL Server データベースを使用するか、Lync Server 2013 と Exchange 2013 ストレージの両方を使用することによって、アーカイブのサポートを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="caa4b-105">You can implement archiving support by integrating archiving storage with Exchange 2013 storage, by using SQL Server databases for storage of Lync Server 2013 archiving data, or by using both Lync Server 2013 and Exchange 2013 storage.</span></span> <span data-ttu-id="caa4b-106">ポリシーとアーカイブ構成を使用して、データをアーカイブする方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="caa4b-106">You control how data is archived using policies and archiving configurations.</span></span> <span data-ttu-id="caa4b-107">詳細については、計画ドキュメントの「 [Lync server 2013 でのアーカイブの計画](lync-server-2013-planning-for-archiving.md)」および「計画ドキュメント、展開ドキュメント、または運用ドキュメント」の「 [lync server 2013 でのアーカイブのしくみ](lync-server-2013-how-archiving-works.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="caa4b-107">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation and [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<span data-ttu-id="caa4b-108">このセクションの情報を使用して、アーカイブを最初に設定して構成することができます。</span><span class="sxs-lookup"><span data-stu-id="caa4b-108">You can use the information in this section to set up and configure Archiving initially.</span></span> <span data-ttu-id="caa4b-109">展開後、アーカイブ設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="caa4b-109">After deployment, you can change Archiving settings.</span></span> <span data-ttu-id="caa4b-110">日常的な管理のためのアーカイブサポートを実装する方法、または組織の新しい要件を満たす方法について詳しくは、「運用ドキュメントの[Lync Server 2013 アーカイブを管理](lync-server-2013-managing-archiving.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="caa4b-110">For details about how you implement archiving support for day-to-day management or to meet new requirements in your organization, see [Managing Lync Server 2013 Archiving](lync-server-2013-managing-archiving.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="caa4b-111">このセクション中</span><span class="sxs-lookup"><span data-stu-id="caa4b-111">In This Section</span></span>

  - [<span data-ttu-id="caa4b-112">Lync Server 2013 でのアーカイブのしくみ</span><span class="sxs-lookup"><span data-stu-id="caa4b-112">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="caa4b-113">Lync Server 2013 のアーカイブの展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="caa4b-113">Deployment checklist for Archiving in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-archiving.md)

  - [<span data-ttu-id="caa4b-114">Lync Server 2013 でアーカイブするためのシステムとインフラストラクチャを設定する</span><span class="sxs-lookup"><span data-stu-id="caa4b-114">Setting up systems and infrastructure for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md)

  - [<span data-ttu-id="caa4b-115">既存の Lync Server 2013 展開にアーカイブデータベースを追加する</span><span class="sxs-lookup"><span data-stu-id="caa4b-115">Adding Archiving databases to an existing Lync Server 2013 Deployment</span></span>](lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md)

  - [<span data-ttu-id="caa4b-116">Lync Server 2013 でアーカイブのサポートを構成する</span><span class="sxs-lookup"><span data-stu-id="caa4b-116">Configuring support for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-archiving.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

