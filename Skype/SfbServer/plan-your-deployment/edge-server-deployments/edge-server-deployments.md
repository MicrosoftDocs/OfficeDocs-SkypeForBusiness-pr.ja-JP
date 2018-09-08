---
title: Skype でビジネス サーバー用のエッジ サーバー展開の計画
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: '概要: は、サーバーのエッジをビジネス環境に、Skype を計画します。 このトピックでは、エッジの概念を紹介し、より詳細なトピックで体系的に学習できるようにします。'
ms.openlocfilehash: f558a4a9623e54a38e134716afe9b95021f237dc
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886123"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a><span data-ttu-id="cefdd-104">Skype でビジネス サーバー用のエッジ サーバー展開の計画</span><span class="sxs-lookup"><span data-stu-id="cefdd-104">Plan for Edge Server deployments in Skype for Business Server</span></span>
 
<span data-ttu-id="cefdd-105">**の概要:** サーバー エッジのビジネス環境について、Skype を計画します。</span><span class="sxs-lookup"><span data-stu-id="cefdd-105">**Summary:** Plan for your Skype for Business Server Edge environment.</span></span> <span data-ttu-id="cefdd-106">このトピックでは、エッジの概念を紹介し、より詳細なトピックで体系的に学習できるようにします。</span><span class="sxs-lookup"><span data-stu-id="cefdd-106">This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="cefdd-107">Skype の内部で適切に動作しているサーバーのビジネス環境がある場合は、エッジ サーバーまたはエッジ プールを環境に導入する次の手順があります。</span><span class="sxs-lookup"><span data-stu-id="cefdd-107">When you have a Skype for Business Server environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="cefdd-108">この役割は、内部ネットワークの外にいる人が使用するサーバーをビジネスの Skype が提供するサービスをする場合に重要になります。</span><span class="sxs-lookup"><span data-stu-id="cefdd-108">This role would be vital if you want the services provided by Skype for Business Server to be used by people who are outside your internal network.</span></span> <span data-ttu-id="cefdd-109">次の種類のユーザーが含まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cefdd-109">These can potentially include:</span></span>
  
- <span data-ttu-id="cefdd-110">リモート ユーザー: 一時的または継続的にオフサイトで作業している従業員。</span><span class="sxs-lookup"><span data-stu-id="cefdd-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="cefdd-111">: フェデレーションのユーザー、パートナー企業の従業員です。</span><span class="sxs-lookup"><span data-stu-id="cefdd-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="cefdd-112">モバイル ユーザー。</span><span class="sxs-lookup"><span data-stu-id="cefdd-112">Mobile Users.</span></span>
    
- <span data-ttu-id="cefdd-113">会議やプレゼンテーションに招待する必要がある潜在的な顧客やパートナー、および場合によっては匿名ユーザー。</span><span class="sxs-lookup"><span data-stu-id="cefdd-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="cefdd-114">、エッジ トランスポート サーバーが提供するものでは、外部ユーザー アクセスを許可すると、このようです。</span><span class="sxs-lookup"><span data-stu-id="cefdd-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="cefdd-115">内部ユーザーはビジネスのサーバーの展開に、Skype でホストされている次のサービスを利用することになります。</span><span class="sxs-lookup"><span data-stu-id="cefdd-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server deployment:</span></span>
  
- <span data-ttu-id="cefdd-116">IM とプレゼンスの通信: 許可された外部ユーザーは、IM 会話および会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="cefdd-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="cefdd-117">(ユーザーが自分のプレゼンス情報を取得する) 他のユーザーのプレゼンス情報を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="cefdd-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="cefdd-118">厳密にピア ツー ピア通信には、パブリック IM プロバイダーを使用する場合は、マルチパーティの会議を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="cefdd-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="cefdd-119">SIP および XMPP プロトコルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="cefdd-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="cefdd-120">オーディオ/ビデオ (A/V) 会議: 許可された外部ユーザーは、ビジネスのサーバーの音声およびビデオ会議用、Skype に参加できます。</span><span class="sxs-lookup"><span data-stu-id="cefdd-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server audio and video conferences.</span></span>
    
- <span data-ttu-id="cefdd-121">Web 会議: ビジネス会議は、Skype で、許可された外部ユーザーが参加できます。</span><span class="sxs-lookup"><span data-stu-id="cefdd-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="cefdd-122">希望の場合も、リモート ユーザー、フェデレーション ユーザー、および匿名ユーザーの参加を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="cefdd-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="cefdd-123">パブリック IM ユーザーは、会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="cefdd-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="cefdd-124">これらのユーザーのアプリケーションおよびデスクトップ共有への参加や、場合によっては会議の開催者または発表者の役割を可能にするオプションもあります。</span><span class="sxs-lookup"><span data-stu-id="cefdd-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="cefdd-125">モバイル デバイスへのアクセスをサポートすると、エンタープライズ VoIP では。</span><span class="sxs-lookup"><span data-stu-id="cefdd-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="cefdd-126">外部ユーザーにアクセス許可を付与する必要があれば、場合によっては匿名ユーザーを含め、外部ユーザーの参加が必要な会議に招待することができます。</span><span class="sxs-lookup"><span data-stu-id="cefdd-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="cefdd-p108">上記の機能が組織で必要であると考えられる場合は、エッジ環境を計画すると、その機能を展開するのに大いに役立ちます。その他の資料としては、以下のトピックがあります。</span><span class="sxs-lookup"><span data-stu-id="cefdd-p108">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it. For further reading, we have the topics listed below.</span></span>

> [!NOTE]
> <span data-ttu-id="cefdd-129">XMPP ゲートウェイとプロキシ サーバー 2015 のビジネス用の Skype では利用ビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="cefdd-129">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="cefdd-130">詳細については、[移行する XMPP フェデレーション](../../../SfBServer2019/migration/migrating-xmpp-federation.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cefdd-130">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
## <a name="planning-topics"></a><span data-ttu-id="cefdd-131">計画に関するトピック:</span><span class="sxs-lookup"><span data-stu-id="cefdd-131">Planning topics:</span></span>

<span data-ttu-id="cefdd-132">計画に関する記事:</span><span class="sxs-lookup"><span data-stu-id="cefdd-132">The planning articles are:</span></span>
  
- [<span data-ttu-id="cefdd-133">Skype for Business Server 2015 のエッジ サーバーのシステム要件</span><span class="sxs-lookup"><span data-stu-id="cefdd-133">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="cefdd-134">Skype for Business Server 2015 のエッジ サーバーの環境要件</span><span class="sxs-lookup"><span data-stu-id="cefdd-134">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="cefdd-135">Skype for Business Server 2015 のエッジ サーバーのシナリオ</span><span class="sxs-lookup"><span data-stu-id="cefdd-135">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

