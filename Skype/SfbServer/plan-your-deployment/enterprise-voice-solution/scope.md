---
title: Skype for Business Server での E9 展開のスコープを定義する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Skype for Business Server Enterprise Voice での E9 展開の計画に必要な決定。
ms.openlocfilehash: fa300ac2f4ba1c0d847abec138b6882e4f240831
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802467"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a><span data-ttu-id="40cf0-103">Skype for Business Server での E9 展開のスコープを定義する</span><span class="sxs-lookup"><span data-stu-id="40cf0-103">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>

<span data-ttu-id="40cf0-104">Skype for Business Server Enterprise Voice での E9 展開の計画に必要な決定。</span><span class="sxs-lookup"><span data-stu-id="40cf0-104">Decisions necessary for planning an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="40cf0-105">Skype for Business for E9-1 を構成する前に、E9 の展開を計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40cf0-105">Before you configure Skype for Business for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="40cf0-106">次のような点を検討します。</span><span class="sxs-lookup"><span data-stu-id="40cf0-106">Some of the questions to consider include:</span></span>

 <span data-ttu-id="40cf0-107">**E9 に関連する組織のポリシーおよび法的義務は何ですか。**</span><span class="sxs-lookup"><span data-stu-id="40cf0-107">**What are your organization's policy and legal obligations with regard to E9-1-1?**</span></span>

 <span data-ttu-id="40cf0-108">PBX (E9-1-1 用語では複数回線電話システム (MLTS) と呼ばれます) 使用時の E9-1-1 の法的義務は州ごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="40cf0-108">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="40cf0-109">法務チームに相談して、関連する地域の Skype for Business の展開に適用される可能性がある義務について理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40cf0-109">You should consult with your legal team to understand the obligations that may apply to your deployment of Skype for Business in your relevant geographies.</span></span>

 <span data-ttu-id="40cf0-110">**エンタープライズ内のどの領域で E9-1-1 を有効にする必要があるか**</span><span class="sxs-lookup"><span data-stu-id="40cf0-110">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>

 <span data-ttu-id="40cf0-p103">E9-1-1 は、エンタープライズ全体で有効にすることも、特定の場所だけで有効にすることもできます。たとえば、オフィスの E9-1-1 の要件が州によって異なる場合や、米国以外のサイトを除外する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="40cf0-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

 <span data-ttu-id="40cf0-113">**E9-1-1 をブランチ サイトにどのように展開するか**</span><span class="sxs-lookup"><span data-stu-id="40cf0-113">**How will you deploy E9-1-1 to branch sites?**</span></span>

 <span data-ttu-id="40cf0-114">E9-1-1 をブランチ サイトに展開するときは、音声の復元の概念を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="40cf0-114">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="40cf0-115">一元化された電子 9-1-1 SIP trunks を使用していて、WAN の障害が発生した場合、クライアントは、場所情報サービスからの場所を取得できないか、緊急サービスサービスプロバイダに接続できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="40cf0-115">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="40cf0-116">Skype for Business には、回復可能なデータネットワークの使用、各ブランチへの SIP トランクの展開、停止中のローカルゲートウェイへの緊急通話の配信など、支店での音声回復性を処理するためのいくつかの戦略が用意されています。</span><span class="sxs-lookup"><span data-stu-id="40cf0-116">Skype for Business provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="40cf0-117">詳細については、「[Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40cf0-117">For details, see [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).</span></span>

 <span data-ttu-id="40cf0-118">**ネットワーク外のユーザーに対し、E9-1-1 を有効にするかどうか**</span><span class="sxs-lookup"><span data-stu-id="40cf0-118">**Will you enable E9-1-1 for users working outside the network?**</span></span>

 <span data-ttu-id="40cf0-119">自動的な場所の取得は、組織のネットワーク内にあるクライアントに対してのみ利用できます。そのため、組織は、Skype for Business クライアントから発信された E9 の通話をオフプレミスでサポートするかどうかを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40cf0-119">Automatic location acquisition is available only for clients located inside the organization's network, so your organization needs to decide whether it will support E9-1-1 calls made from Skype for Business clients while off-premises.</span></span> <span data-ttu-id="40cf0-120">たとえば、ユーザーが自宅で作業している場合や顧客サイトから作業している場合に、緊急電話をかけることができますか。</span><span class="sxs-lookup"><span data-stu-id="40cf0-120">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="40cf0-121">クライアントがエンタープライズネットワークの外部に配置されている場合は、ユーザーに位置情報の入力を求めるようにクライアントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="40cf0-121">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="40cf0-122">ただし、ユーザーが指定した場所は、マスター番地の住所ガイド (MSAG) に対して prevalidated できないため、緊急サービスサービスプロバイダーディスパッチャーは、ルーティング前に発信者による場所の有効性を確認する必要があります。公衆安全応答ポイント (PSAP) への通話。</span><span class="sxs-lookup"><span data-stu-id="40cf0-122">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>

> [!NOTE]
> <span data-ttu-id="40cf0-123">VPN を使用して組織のネットワークに接続しているユーザーの Skype for Business クライアントは、内部の IP アドレス情報を取得できますが、これらのアドレスを使ってユーザーの実際の場所を特定することはできないため、VPN サブネットを除外することが重要です。場所情報サービスから。</span><span class="sxs-lookup"><span data-stu-id="40cf0-123">Skype for Business clients of users who connect to your organization's network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user's actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

 <span data-ttu-id="40cf0-124">**米国以外のサイトに緊急通話のルーティングを提供するかどうか**</span><span class="sxs-lookup"><span data-stu-id="40cf0-124">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>

 <span data-ttu-id="40cf0-p106">緊急サービスのサービス プロバイダーのサービス対象範囲外 (国外の場所など) にある会社の領域に緊急通話のルーティングを提供したい場合があります。この場合は、新しいサイトを作成し、ローカル PSTN ゲートウェイ経由で通話をルーティングする PSTN 使用法を参照する音声ポリシーをサイトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="40cf0-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>


