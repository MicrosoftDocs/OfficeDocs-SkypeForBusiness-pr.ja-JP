---
title: Skype for Business Server で Edge Server の展開を計画する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: '概要: Skype for Business Server Edge 環境を計画します。 このトピックでは、エッジの概念を紹介し、より詳細なトピックで体系的に学習できるようにします。'
ms.openlocfilehash: 536ab82ec6845c55a0ee067ad8c1a4f5d9b9e153
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277161"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a><span data-ttu-id="a2952-104">Skype for Business Server で Edge Server の展開を計画する</span><span class="sxs-lookup"><span data-stu-id="a2952-104">Plan for Edge Server deployments in Skype for Business Server</span></span>
 
<span data-ttu-id="a2952-105">**概要:** Skype for Business Server Edge 環境を計画します。</span><span class="sxs-lookup"><span data-stu-id="a2952-105">**Summary:** Plan for your Skype for Business Server Edge environment.</span></span> <span data-ttu-id="a2952-106">このトピックでは、エッジの概念を紹介し、より詳細なトピックで体系的に学習できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a2952-106">This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="a2952-107">社内で動作する Skype for Business Server 環境がある場合、次の手順では、Edge サーバーまたはエッジプールを環境に導入することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a2952-107">When you have a Skype for Business Server environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="a2952-108">この役割は、Skype for Business Server によって提供されるサービスを内部ネットワークの外部ユーザーが使用できるようにする場合に非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="a2952-108">This role would be vital if you want the services provided by Skype for Business Server to be used by people who are outside your internal network.</span></span> <span data-ttu-id="a2952-109">次の種類のユーザーが含まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a2952-109">These can potentially include:</span></span>
  
- <span data-ttu-id="a2952-110">リモート ユーザー: 一時的または継続的にオフサイトで作業している従業員。</span><span class="sxs-lookup"><span data-stu-id="a2952-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="a2952-111">フェデレーションされたユーザー: パートナー組織の従業員。</span><span class="sxs-lookup"><span data-stu-id="a2952-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="a2952-112">モバイル ユーザー。</span><span class="sxs-lookup"><span data-stu-id="a2952-112">Mobile Users.</span></span>
    
- <span data-ttu-id="a2952-113">会議やプレゼンテーションに招待する必要がある潜在的な顧客やパートナー、および場合によっては匿名ユーザー。</span><span class="sxs-lookup"><span data-stu-id="a2952-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="a2952-114">外部ユーザーアクセス (エッジサーバーが提供する機能) により、すべての操作が可能になります。</span><span class="sxs-lookup"><span data-stu-id="a2952-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="a2952-115">組織内のユーザーは、Skype for Business Server の展開によってホストされている次のサービスを利用することができます。</span><span class="sxs-lookup"><span data-stu-id="a2952-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server deployment:</span></span>
  
- <span data-ttu-id="a2952-116">通信の IM とプレゼンス: 承認された外部ユーザーは、IM 会話と会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="a2952-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="a2952-117">他のユーザーのプレゼンス情報を取得することができます (自分のプレゼンス情報も取得します)。</span><span class="sxs-lookup"><span data-stu-id="a2952-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="a2952-118">パブリック IM プロバイダーを使用している場合は、ピアツーピア通信であるため、マルチパーティ会議を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="a2952-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="a2952-119">ただし、SIP と XMPP の両方のプロトコルがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a2952-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="a2952-120">音声/ビデオ (A/V) 会議: 承認された外部ユーザーは、Skype for Business Server の音声とビデオ会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="a2952-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server audio and video conferences.</span></span>
    
- <span data-ttu-id="a2952-121">Web 会議: 承認された外部ユーザーは、Skype for Business 会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="a2952-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="a2952-122">必要に応じて、リモートユーザー、フェデレーションユーザー、匿名ユーザーへの参加を有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a2952-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="a2952-123">パブリック IM ユーザーは、会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="a2952-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="a2952-124">これらのユーザーのアプリケーションおよびデスクトップ共有への参加や、場合によっては会議の開催者または発表者の役割を可能にするオプションもあります。</span><span class="sxs-lookup"><span data-stu-id="a2952-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="a2952-125">エンタープライズ Voip として、モバイルデバイスのアクセスがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a2952-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="a2952-126">外部ユーザーにアクセス許可を付与する必要があれば、場合によっては匿名ユーザーを含め、外部ユーザーの参加が必要な会議に招待することができます。</span><span class="sxs-lookup"><span data-stu-id="a2952-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="a2952-p108">上記の機能が組織で必要であると考えられる場合は、エッジ環境を計画すると、その機能を展開するのに大いに役立ちます。その他の資料としては、以下のトピックがあります。</span><span class="sxs-lookup"><span data-stu-id="a2952-p108">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it. For further reading, we have the topics listed below.</span></span>

> [!NOTE]
> <span data-ttu-id="a2952-129">XMPP ゲートウェイとプロキシは、Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a2952-129">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a2952-130">詳細については、「 [XMPP フェデレーションを移行](../../../SfBServer2019/migration/migrating-xmpp-federation.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2952-130">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
## <a name="planning-topics"></a><span data-ttu-id="a2952-131">計画に関するトピック:</span><span class="sxs-lookup"><span data-stu-id="a2952-131">Planning topics:</span></span>

<span data-ttu-id="a2952-132">計画に関する記事:</span><span class="sxs-lookup"><span data-stu-id="a2952-132">The planning articles are:</span></span>
  
- [<span data-ttu-id="a2952-133">Skype for Business Server 2015 のエッジ サーバーのシステム要件</span><span class="sxs-lookup"><span data-stu-id="a2952-133">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="a2952-134">Skype for Business Server 2015 のエッジ サーバーの環境要件</span><span class="sxs-lookup"><span data-stu-id="a2952-134">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="a2952-135">Skype for Business Server 2015 のエッジ サーバーのシナリオ</span><span class="sxs-lookup"><span data-stu-id="a2952-135">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

