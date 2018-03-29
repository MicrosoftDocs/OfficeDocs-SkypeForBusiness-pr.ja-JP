---
title: Skype for Business Server 2015 での E9-1-1 展開の範囲の定義
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: ビジネス サーバーのエンタープライズ VoIP の Skype で ~ 9-1-1 展開の計画のために必要なを決定します。
ms.openlocfilehash: f81a2c56642557bf92a965de025aecbdbcadadcd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server-2015"></a><span data-ttu-id="b6e36-103">Skype for Business Server 2015 での E9-1-1 展開の範囲の定義</span><span class="sxs-lookup"><span data-stu-id="b6e36-103">Define the scope of the E9-1-1 deployment in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b6e36-104">ビジネス サーバーのエンタープライズ VoIP の Skype で ~ 9-1-1 展開の計画のために必要なを決定します。</span><span class="sxs-lookup"><span data-stu-id="b6e36-104">Decisions necessary for planning an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="b6e36-105">~ 9-1-1 のビジネス用の Skype を構成する前に ~ 9-1-1 の展開を計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6e36-105">Before you configure Skype for Business for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="b6e36-106">次のような点を検討します。</span><span class="sxs-lookup"><span data-stu-id="b6e36-106">Some of the questions to consider include:</span></span>
  
 <span data-ttu-id="b6e36-107">**組織のポリシーおよび ~ 9-1-1 に関する法的義務とは?**</span><span class="sxs-lookup"><span data-stu-id="b6e36-107">**What are your organization's policy and legal obligations with regard to E9-1-1?**</span></span>
  
 <span data-ttu-id="b6e36-108">PBX (E9-1-1 用語では複数回線電話システム (MLTS) と呼ばれます) 使用時の E9-1-1 の法的義務は州ごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="b6e36-108">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="b6e36-109">Skype を関連する地域でのビジネスの展開に適用される義務を理解するのには法的なチームを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6e36-109">You should consult with your legal team to understand the obligations that may apply to your deployment of Skype for Business in your relevant geographies.</span></span>
    
 <span data-ttu-id="b6e36-110">**エンタープライズ内のどの領域で E9-1-1 を有効にする必要があるか**</span><span class="sxs-lookup"><span data-stu-id="b6e36-110">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>
  
 <span data-ttu-id="b6e36-p103">E9-1-1 は、エンタープライズ全体で有効にすることも、特定の場所だけで有効にすることもできます。たとえば、オフィスの E9-1-1 の要件が州によって異なる場合や、米国以外のサイトを除外する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="b6e36-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span> 
    
 <span data-ttu-id="b6e36-113">**E9-1-1 をブランチ サイトにどのように展開するか**</span><span class="sxs-lookup"><span data-stu-id="b6e36-113">**How will you deploy E9-1-1 to branch sites?**</span></span>
  
 <span data-ttu-id="b6e36-114">E9-1-1 をブランチ サイトに展開するときは、音声の復元の概念を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="b6e36-114">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="b6e36-115">E-9-1-1 の SIP トランクを集中化すると、WAN の障害が発生する、クライアントにサインインできないことがあります場所情報サービスから場所を取得するか、緊急サービスのサービス プロバイダーに接続します。</span><span class="sxs-lookup"><span data-stu-id="b6e36-115">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="b6e36-116">ビジネス用の Skype など、ブランチ オフィスでの音声の復元機能を処理するためのいくつかの方法が用意されています: 弾力性のあるデータ ・ ネットワークを持つ、各支店に SIP トランクを展開するまたはさせようとして緊急通報ローカル ゲートウェイの停止中にします。</span><span class="sxs-lookup"><span data-stu-id="b6e36-116">Skype for Business provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="b6e36-117">詳細については、[ブランチ サイトの音声の復元の計画](http://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6e36-117">For details, see [Planning for Branch-Site Voice Resiliency](http://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).</span></span>
    
 <span data-ttu-id="b6e36-118">**ネットワーク外のユーザーに対し、E9-1-1 を有効にするかどうか**</span><span class="sxs-lookup"><span data-stu-id="b6e36-118">**Will you enable E9-1-1 for users working outside the network?**</span></span>
  
 <span data-ttu-id="b6e36-119">自動場所の取得、~ 9-1-1 からの呼び出し Skype オフプレミスの中にビジネスのクライアントをサポートするかどうかを決定するのには、組織が必要なために、組織のネットワーク内にあるクライアントに対してのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="b6e36-119">Automatic location acquisition is available only for clients located inside the organization's network, so your organization needs to decide whether it will support E9-1-1 calls made from Skype for Business clients while off-premises.</span></span> <span data-ttu-id="b6e36-120">ユーザーが自宅から、またはお客様のサイトから作業する場合は、緊急の呼び出しを配置するを有効にたとえば、しますか。</span><span class="sxs-lookup"><span data-stu-id="b6e36-120">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="b6e36-121">クライアントは企業ネットワークの外に配置されている場合は、場所をユーザーに確認する、クライアントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="b6e36-121">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="b6e36-122">ただし、これらのユーザーが指定した場所は、マスター住所アドレス ガイド (MSAG) を prevalidated ことはできません、ため、緊急サービスのサービス プロバイダー ディスパッチャーがルーティングする前に、呼び出し元で口頭で指定した場所の有効性を確認する必要パブリックの安全性への応答ポイント (PSAP) への呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="b6e36-122">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>
    
> [!NOTE]
> <span data-ttu-id="b6e36-123">VPN を使用して、組織のネットワークに接続しているユーザーのビジネス クライアント用の Skype は、内部の IP アドレス情報を選択できますが、これらのアドレスは、ユーザーの実際の場所を識別するのには使用できません、ため VPN のサブネットを除外することが不可欠位置情報サービスです。</span><span class="sxs-lookup"><span data-stu-id="b6e36-123">Skype for Business clients of users who connect to your organization's network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user's actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span> 
  
 <span data-ttu-id="b6e36-124">**米国以外のサイトに緊急通話のルーティングを提供するかどうか**</span><span class="sxs-lookup"><span data-stu-id="b6e36-124">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>
  
 <span data-ttu-id="b6e36-p106">緊急サービスのサービス プロバイダーのサービス対象範囲外 (国外の場所など) にある会社の領域に緊急通話のルーティングを提供したい場合があります。この場合は、新しいサイトを作成し、ローカル PSTN ゲートウェイ経由で通話をルーティングする PSTN 使用法を参照する音声ポリシーをサイトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b6e36-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>
    

