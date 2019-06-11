---
title: 'Lync Server 2013: 外部ユーザー アクセスの計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d76d4853e7e748128214fc93b721a59e979af03e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="4ba16-102">Lync Server 2013 の外部ユーザー アクセスの計画</span><span class="sxs-lookup"><span data-stu-id="4ba16-102">Planning for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ba16-103">_**最終更新日:** 2013-01-19_</span><span class="sxs-lookup"><span data-stu-id="4ba16-103">_**Topic Last Modified:** 2013-01-19_</span></span>

<span data-ttu-id="4ba16-104">ほとんどの組織の通信には、内部ネットワーク内にないサービスやユーザーが関係しています。</span><span class="sxs-lookup"><span data-stu-id="4ba16-104">Communications in most organizations involve services and users that are not inside your internal network.</span></span> <span data-ttu-id="4ba16-105">これらのサービスとユーザーには、一時的または完全にオフサイトになっている従業員、顧客またはパートナーの組織の従業員、パブリックインスタントメッセージング (IM) サービスを使用しているユーザー、招待する可能性のある顧客、パートナー、匿名ユーザーが含まれます。会議やプレゼンテーションを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4ba16-105">These services and users include employees who are temporarily or permanently offsite, employees of customer or partner organizations, people who use public instant messaging (IM) services, and potential customers, partners and anonymous users whom you invite to meetings and presentations.</span></span> <span data-ttu-id="4ba16-106">このドキュメントでは、これらのユーザーを、"*外部ユーザー*" と総称して示します。</span><span class="sxs-lookup"><span data-stu-id="4ba16-106">In this documentation, these people are collectively referred to as *external users*.</span></span>

<span data-ttu-id="4ba16-107">Microsoft Lync Server 2013 では、組織内のユーザーは IM とプレゼンスを使って外部ユーザーと通信できます。また、オフサイトの従業員や他の種類の外部ユーザーとの音声/ビデオ (A/V) 会議や web 会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="4ba16-107">With Microsoft Lync Server 2013, users in your organization can use IM and presence to communicate with external users, and they can participate in audio/video (A/V) conferencing and web conferencing with your offsite employees and other types of external users.</span></span> <span data-ttu-id="4ba16-108">また、モバイルデバイスやエンタープライズ Voip からの外部アクセスをサポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4ba16-108">You can also support external access from mobile devices and over Enterprise Voice.</span></span> <span data-ttu-id="4ba16-109">組織のメンバーではない外部ユーザーは、Lync Server 2013 会議に参加して、匿名の出席者を許可することができます。</span><span class="sxs-lookup"><span data-stu-id="4ba16-109">External users who are not members of your organization can participate in Lync Server 2013 meetings, allowing anonymous attendees.</span></span>

<span data-ttu-id="4ba16-110">組織のファイアウォール間の通信をサポートするには、境界ネットワーク (DMZ、非武装地帯、スクリーンサブネットとも呼ばれます) に Lync Server 2013 エッジサーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="4ba16-110">To support communications across your organization’s firewall, you deploy Lync Server 2013 Edge Server in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="4ba16-111">エッジサーバーは、ファイアウォール外のユーザーが内部の Lync Server 2013 展開に接続する方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="4ba16-111">The Edge Server controls how users outside the firewall can connect to your internal Lync Server 2013 deployment.</span></span> <span data-ttu-id="4ba16-112">また、ファイアウォール内で発生する外部ユーザーとの通信も制御します。</span><span class="sxs-lookup"><span data-stu-id="4ba16-112">It also controls communications with external users that originate within the firewall.</span></span>

<span data-ttu-id="4ba16-113">必要に応じて、1つ以上の場所に1つ以上のエッジサーバーを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="4ba16-113">Depending on your requirements, you can deploy one or more Edge Servers in one or more locations.</span></span> <span data-ttu-id="4ba16-114">このセクションでは、Lync Server 2013 での外部ユーザーアクセスのシナリオについて説明し、エッジとリバースプロキシトポロジを計画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ba16-114">This section describes scenarios for external user access in Lync Server 2013, and it explains how to plan your edge and reverse proxy topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4ba16-115">エンタープライズボイスと外部ユーザーのアクセスをサポートするにはエッジサーバーが必要ですが、このセクションでは IM、プレゼンス、A/V 会議、フェデレーション、web 会議、Lync Mobile のサポートについて重点的に説明します。</span><span class="sxs-lookup"><span data-stu-id="4ba16-115">Although you need an Edge Server to support Enterprise Voice and external user access, this section focuses on support for IM, presence, A/V conferencing, federation, web conferencing, and Lync Mobile.</span></span> <span data-ttu-id="4ba16-116">エンタープライズ Voip のサポートの詳細については、計画ドキュメントの「 <A href="lync-server-2013-planning-for-enterprise-voice.md">Lync Server 2013 でのエンタープライズ voip の計画</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ba16-116">For details about support for Enterprise Voice, see <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4ba16-117">このセクション中</span><span class="sxs-lookup"><span data-stu-id="4ba16-117">In This Section</span></span>

  - [<span data-ttu-id="4ba16-118">エッジ サーバーの計画に影響する Lync Server 2013 での変更点</span><span class="sxs-lookup"><span data-stu-id="4ba16-118">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [<span data-ttu-id="4ba16-119">Lync Server 2013 の外部ユーザー アクセス コンポーネントのシステム要件</span><span class="sxs-lookup"><span data-stu-id="4ba16-119">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="4ba16-120">Lync Server 2013 における外部ユーザー アクセスの概要</span><span class="sxs-lookup"><span data-stu-id="4ba16-120">Overview of external user access in Lync Server 2013</span></span>](lync-server-2013-overview-of-external-user-access.md)

  - [<span data-ttu-id="4ba16-121">Lync Server 2013 での自動検出について</span><span class="sxs-lookup"><span data-stu-id="4ba16-121">Understanding Autodiscover in Lync Server 2013</span></span>](lync-server-2013-understanding-autodiscover.md)

  - [<span data-ttu-id="4ba16-122">Lync Server 2013 でのトポロジの選択</span><span class="sxs-lookup"><span data-stu-id="4ba16-122">Choosing a topology in Lync Server 2013</span></span>](lync-server-2013-choosing-a-topology.md)

  - [<span data-ttu-id="4ba16-123">Lync Server 2013 のデータの収集</span><span class="sxs-lookup"><span data-stu-id="4ba16-123">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="4ba16-124">Lync Server 2013 の DNS の要件を確認する</span><span class="sxs-lookup"><span data-stu-id="4ba16-124">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="4ba16-125">Lync Server 2013 の外部の音声ビデオ ファイアウォールおよびポートの要件を決定する</span><span class="sxs-lookup"><span data-stu-id="4ba16-125">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="4ba16-126">Lync Server 2013 でエッジ サーバー証明書を計画する</span><span class="sxs-lookup"><span data-stu-id="4ba16-126">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)

  - [<span data-ttu-id="4ba16-127">Lync Server 2013 の外部ユーザー アクセスのシナリオ</span><span class="sxs-lookup"><span data-stu-id="4ba16-127">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

