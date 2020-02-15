---
title: 'Lync Server 2013: 通話受付管理の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ebe3fbdd60409523755c865f4b4f34025acf15d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="460e0-102">Lync Server 2013 で通話受付管理を構成する</span><span class="sxs-lookup"><span data-stu-id="460e0-102">Configure call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="460e0-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="460e0-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="460e0-104">通話受付管理 (CAC) は、使用可能な帯域幅に基づいてリアルタイムセッションを確立して、混雑したネットワーク上のユーザーの音声/ビデオの品質が低下しないようにするかどうかを決定するソリューションです。</span><span class="sxs-lookup"><span data-stu-id="460e0-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="460e0-105">CAC は、音声とビデオのリアルタイムトラフィックのみを制御し、データトラフィックには影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="460e0-105">CAC controls real-time traffic only for audio and video, and does not affect data traffic.</span></span> <span data-ttu-id="460e0-106">既定の WAN パスに必要な帯域幅がない場合、CAC はインターネットパス経由で通話をルーティングすることがあります。</span><span class="sxs-lookup"><span data-stu-id="460e0-106">CAC may route the call through an Internet path when the default WAN path does not have the required bandwidth.</span></span> <span data-ttu-id="460e0-107">詳細については、「計画」のドキュメントの「 [Lync Server 2013 での通話受付管理の計画](lync-server-2013-planning-for-call-admission-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="460e0-107">For details, see [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="460e0-108">ここでは、ネットワークに CAC を展開して管理する方法を例示する一連の手順例を示します。</span><span class="sxs-lookup"><span data-stu-id="460e0-108">This section provides a set of example procedures that illustrate how to deploy and manage CAC in your network.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="460e0-109">CAC を展開する前に、「計画」のドキュメントの「 <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Example: Lync Server 2013 での通話受付管理の要件の収集</A>」の説明に従って、エンタープライズネットワークトポロジに必要なすべての情報を収集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="460e0-109">Before you deploy CAC, you must gather all of the required information for your enterprise network topology, as described in <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Example: Gathering your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="460e0-110">また、「展開」のドキュメントの「 <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013 でのフロントエンドプールまたは Standard Edition サーバーの定義と構成</A>」の説明に従って、CAC コンポーネントがインストールされ、アクティブ化されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="460e0-110">Also be sure that CAC components have been installed and activated, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="460e0-111">このセクションのすべての CAC の展開と管理の例は、Lync Server 管理シェルを使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="460e0-111">All CAC deployment and management examples in this section are performed by using the Lync Server Management Shell.</span></span> <span data-ttu-id="460e0-112">別の方法として、Lync Server コントロールパネルの [<STRONG>ネットワーク構成</STRONG>] セクションを使用して CAC を管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="460e0-112">As an alternative, you can also use the <STRONG>Network Configuration</STRONG> section of Lync Server Control Panel to manage CAC.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="460e0-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="460e0-113">In This Section</span></span>

  - [<span data-ttu-id="460e0-114">Lync Server 2013 で CAC のネットワーク地域を構成する</span><span class="sxs-lookup"><span data-stu-id="460e0-114">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)

  - [<span data-ttu-id="460e0-115">Lync Server 2013 での帯域幅ポリシープロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="460e0-115">Create bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [<span data-ttu-id="460e0-116">Lync Server 2013 で CAC のネットワークサイトを構成する</span><span class="sxs-lookup"><span data-stu-id="460e0-116">Configure network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-sites-for-cac.md)

  - [<span data-ttu-id="460e0-117">Lync Server 2013 での CAC のネットワークサイトへのサブネットの関連付け</span><span class="sxs-lookup"><span data-stu-id="460e0-117">Associate subnets with network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [<span data-ttu-id="460e0-118">Lync Server 2013 でのネットワーク地域リンクの作成</span><span class="sxs-lookup"><span data-stu-id="460e0-118">Create network region links in Lync Server 2013</span></span>](lync-server-2013-create-network-region-links.md)

  - [<span data-ttu-id="460e0-119">Lync Server 2013 でのネットワーク地域間ルートの作成</span><span class="sxs-lookup"><span data-stu-id="460e0-119">Create network interregion routes in Lync Server 2013</span></span>](lync-server-2013;-create-network-interregion-routes.md)

  - [<span data-ttu-id="460e0-120">Lync Server 2013 でのネットワークサイト間ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="460e0-120">Create network intersite policies in Lync Server 2013</span></span>](lync-server-2013-create-network-intersite-policies.md)

  - [<span data-ttu-id="460e0-121">Lync Server 2013 で通話受付管理を有効にする</span><span class="sxs-lookup"><span data-stu-id="460e0-121">Enable call admission control in Lync Server 2013</span></span>](lync-server-2013-enable-call-admission-control.md)

  - [<span data-ttu-id="460e0-122">Lync Server 2013 の通話受付管理の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="460e0-122">Call admission control deployment checklist for Lync Server 2013</span></span>](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

