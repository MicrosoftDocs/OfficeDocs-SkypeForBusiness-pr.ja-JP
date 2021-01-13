---
title: Skype for Business Server でのエッジ サーバーの展開を計画する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: '概要: Skype for Business Server Edge 環境を計画します。 このトピックでは、Edge の概念について説明し、より詳細なトピックを整理できます。'
ms.openlocfilehash: 277e344448f5229d15addf965695f19ec2884649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813807"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a><span data-ttu-id="0c2c2-104">Skype for Business Server でのエッジ サーバーの展開を計画する</span><span class="sxs-lookup"><span data-stu-id="0c2c2-104">Plan for Edge Server deployments in Skype for Business Server</span></span>
 
<span data-ttu-id="0c2c2-105">**概要:** Skype for Business Server Edge 環境を計画します。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-105">**Summary:** Plan for your Skype for Business Server Edge environment.</span></span> <span data-ttu-id="0c2c2-106">このトピックでは、Edge の概念について説明し、より詳細なトピックを整理できます。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-106">This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="0c2c2-107">Skype for Business Server 環境が内部でうまく機能している場合は、次の手順として、エッジ サーバーまたはエッジ プールを環境に導入します。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-107">When you have a Skype for Business Server environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="0c2c2-108">この役割は、内部ネットワークの外部のユーザーが Skype for Business Server によって提供されるサービスを使用する場合に非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-108">This role would be vital if you want the services provided by Skype for Business Server to be used by people who are outside your internal network.</span></span> <span data-ttu-id="0c2c2-109">次のような場合があります。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-109">These can potentially include:</span></span>
  
- <span data-ttu-id="0c2c2-110">リモート ユーザー: 一時的または継続的な方法でオフサイトの従業員。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="0c2c2-111">フェデレーション ユーザー: パートナー組織の従業員。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="0c2c2-112">モバイル ユーザー。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-112">Mobile Users.</span></span>
    
- <span data-ttu-id="0c2c2-113">潜在的な顧客、パートナー、会議やプレゼンテーションに招待する匿名ユーザー。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="0c2c2-114">エッジ サーバーが提供する外部ユーザー アクセスにより、このすべてが可能になります。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="0c2c2-115">内部ユーザーは、Skype for Business Server 展開でホストされている次のサービスを利用できます。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server deployment:</span></span>
  
- <span data-ttu-id="0c2c2-116">通信用の IM とプレゼンス: 承認された外部ユーザーは、IM 会話および会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="0c2c2-117">他のユーザー (自分のプレゼンス情報も取得するユーザー) のプレゼンス情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="0c2c2-118">パブリック IM プロバイダーを使用している場合、マルチパーティ会議を行うのは、厳密にはピアツーピア通信です。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="0c2c2-119">ただし、SIP プロトコルと XMPP プロトコルの両方がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="0c2c2-120">音声ビデオ (A/V) 会議: 承認された外部ユーザーは、Skype for Business Server の音声ビデオ会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server audio and video conferences.</span></span>
    
- <span data-ttu-id="0c2c2-121">Web 会議: 承認された外部ユーザーは、Skype for Business 会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="0c2c2-122">必要に合った場合は、リモート ユーザー、フェデレーション ユーザー、および匿名ユーザーの参加を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="0c2c2-123">パブリック IM ユーザーは会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="0c2c2-124">また、これらのユーザーがアプリケーションとデスクトップの共有に参加したり、会議の開催者や発表者として機能したりするためのオプションも用意されています。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="0c2c2-125">モバイル デバイスのアクセスは、次の場合と同様にエンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="0c2c2-126">外部ユーザーにアクセス許可を付与する場合は、外部ユーザーを招待して、匿名ユーザーを含め、出席を希望する会議に招待できます。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="0c2c2-127">組織に必要なもののように思える場合は、エッジ環境の計画が展開の大きな助けになります。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-127">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it.</span></span> <span data-ttu-id="0c2c2-128">詳細については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-128">For further reading, we have the topics listed below.</span></span>

> [!NOTE]
> <span data-ttu-id="0c2c2-129">XMPP ゲートウェイとプロキシは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-129">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="0c2c2-130">詳細 [については、「XMPP フェデレーションの移行](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-130">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
## <a name="planning-topics"></a><span data-ttu-id="0c2c2-131">計画に関するトピック:</span><span class="sxs-lookup"><span data-stu-id="0c2c2-131">Planning topics:</span></span>

<span data-ttu-id="0c2c2-132">計画に関する記事は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0c2c2-132">The planning articles are:</span></span>
  
- [<span data-ttu-id="0c2c2-133">Skype for Business Server 2015 のエッジ サーバーのシステム要件</span><span class="sxs-lookup"><span data-stu-id="0c2c2-133">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="0c2c2-134">Skype for Business Server 2015 のエッジ サーバーの環境要件</span><span class="sxs-lookup"><span data-stu-id="0c2c2-134">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="0c2c2-135">Skype for Business Server 2015 のエッジ サーバーのシナリオ</span><span class="sxs-lookup"><span data-stu-id="0c2c2-135">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

