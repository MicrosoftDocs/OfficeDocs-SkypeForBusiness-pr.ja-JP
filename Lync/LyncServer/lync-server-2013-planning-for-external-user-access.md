---
title: 'Lync Server 2013: 外部ユーザーアクセスの計画'
description: 'Lync Server 2013: 外部ユーザーアクセスの計画。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8f1854791ed837b963d4c80f3467e4e89555592
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562783"
---
# <a name="planning-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="6c251-103">Lync Server 2013 での外部ユーザーアクセスの計画</span><span class="sxs-lookup"><span data-stu-id="6c251-103">Planning for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c251-104">_**トピックの最終更新日:** 2013-01-19_</span><span class="sxs-lookup"><span data-stu-id="6c251-104">_**Topic Last Modified:** 2013-01-19_</span></span>

<span data-ttu-id="6c251-p101">ほとんどの組織の通信には、内部ネットワーク外のサービスやユーザーが関与しています。 これらのサービスやユーザーには、一時的または恒久的にオフサイトにいる従業員、顧客組織やパートナー組織の従業員、パブリック インスタント メッセージング (IM) サービスの利用者、会議やプレゼンテーションに招待した見込み顧客やパートナー、匿名ユーザーなどが含まれます。 このドキュメントでは、これらの人々を総称して外部ユーザー\*\* と呼びます。</span><span class="sxs-lookup"><span data-stu-id="6c251-p101">Communications in most organizations involve services and users that are not inside your internal network. These services and users include employees who are temporarily or permanently offsite, employees of customer or partner organizations, people who use public instant messaging (IM) services, and potential customers, partners and anonymous users whom you invite to meetings and presentations. In this documentation, these people are collectively referred to as *external users*.</span></span>

<span data-ttu-id="6c251-108">Microsoft Lync Server 2013 を使用すると、組織内のユーザーは IM とプレゼンスを使用して外部ユーザーと通信することができ、オフサイトの従業員やその他の種類の外部ユーザーとの音声ビデオ (A/V) 会議や web 会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="6c251-108">With Microsoft Lync Server 2013, users in your organization can use IM and presence to communicate with external users, and they can participate in audio/video (A/V) conferencing and web conferencing with your offsite employees and other types of external users.</span></span> <span data-ttu-id="6c251-109">モバイル デバイスからの外部アクセスや、エンタープライズ VoIP を利用した外部アクセスもサポートできます。</span><span class="sxs-lookup"><span data-stu-id="6c251-109">You can also support external access from mobile devices and over Enterprise Voice.</span></span> <span data-ttu-id="6c251-110">組織のメンバーではない外部ユーザーは、Lync Server 2013 の会議に参加して、匿名の出席者を許可することができます。</span><span class="sxs-lookup"><span data-stu-id="6c251-110">External users who are not members of your organization can participate in Lync Server 2013 meetings, allowing anonymous attendees.</span></span>

<span data-ttu-id="6c251-111">組織のファイアウォール間での通信をサポートするには、wan Server 2013 エッジサーバーを境界ネットワーク (DMZ、非武装地帯、スクリーンサブネットとも呼ばれます) に展開します。</span><span class="sxs-lookup"><span data-stu-id="6c251-111">To support communications across your organization’s firewall, you deploy Lync Server 2013 Edge Server in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="6c251-112">エッジサーバーは、ファイアウォールの外側にあるユーザーが内部の Lync Server 2013 展開に接続する方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="6c251-112">The Edge Server controls how users outside the firewall can connect to your internal Lync Server 2013 deployment.</span></span> <span data-ttu-id="6c251-113">ファイアウォールの内側から発信された外部ユーザーへの通信も制御します。</span><span class="sxs-lookup"><span data-stu-id="6c251-113">It also controls communications with external users that originate within the firewall.</span></span>

<span data-ttu-id="6c251-114">要件に応じて、1 つまたは複数の場所に、1 つまたは複数のエッジ サーバーを展開できます。</span><span class="sxs-lookup"><span data-stu-id="6c251-114">Depending on your requirements, you can deploy one or more Edge Servers in one or more locations.</span></span> <span data-ttu-id="6c251-115">このセクションでは、Lync Server 2013 の外部ユーザーアクセスのシナリオと、エッジおよびリバースプロキシトポロジを計画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6c251-115">This section describes scenarios for external user access in Lync Server 2013, and it explains how to plan your edge and reverse proxy topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6c251-116">エンタープライズ Voip と外部ユーザーアクセスをサポートするエッジサーバーが必要ですが、このセクションでは IM、プレゼンス、音声ビデオ会議、フェデレーション、web 会議、Lync Mobile のサポートに焦点を当てます。</span><span class="sxs-lookup"><span data-stu-id="6c251-116">Although you need an Edge Server to support Enterprise Voice and external user access, this section focuses on support for IM, presence, A/V conferencing, federation, web conferencing, and Lync Mobile.</span></span> <span data-ttu-id="6c251-117">エンタープライズ Voip のサポートの詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-planning-for-enterprise-voice.md">planning For Enterprise voice In Lync Server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c251-117">For details about support for Enterprise Voice, see <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6c251-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6c251-118">In This Section</span></span>

  - [<span data-ttu-id="6c251-119">エッジサーバーの計画に影響する Lync Server 2013 の変更点</span><span class="sxs-lookup"><span data-stu-id="6c251-119">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [<span data-ttu-id="6c251-120">Lync Server 2013 の外部ユーザーアクセスコンポーネントのシステム要件</span><span class="sxs-lookup"><span data-stu-id="6c251-120">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="6c251-121">Lync Server 2013 の外部ユーザーアクセスの概要</span><span class="sxs-lookup"><span data-stu-id="6c251-121">Overview of external user access in Lync Server 2013</span></span>](lync-server-2013-overview-of-external-user-access.md)

  - [<span data-ttu-id="6c251-122">Lync Server 2013 の自動検出について</span><span class="sxs-lookup"><span data-stu-id="6c251-122">Understanding Autodiscover in Lync Server 2013</span></span>](lync-server-2013-understanding-autodiscover.md)

  - [<span data-ttu-id="6c251-123">Lync Server 2013 でのトポロジの選択</span><span class="sxs-lookup"><span data-stu-id="6c251-123">Choosing a topology in Lync Server 2013</span></span>](lync-server-2013-choosing-a-topology.md)

  - [<span data-ttu-id="6c251-124">Lync Server 2013 のデータ収集</span><span class="sxs-lookup"><span data-stu-id="6c251-124">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="6c251-125">Lync Server 2013 の DNS 要件を決定する</span><span class="sxs-lookup"><span data-stu-id="6c251-125">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="6c251-126">Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を決定する</span><span class="sxs-lookup"><span data-stu-id="6c251-126">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="6c251-127">Lync Server 2013 でエッジサーバー証明書を計画する</span><span class="sxs-lookup"><span data-stu-id="6c251-127">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)

  - [<span data-ttu-id="6c251-128">Lync Server 2013 での外部ユーザーアクセスのシナリオ</span><span class="sxs-lookup"><span data-stu-id="6c251-128">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

