---
title: Skype for Business Server での E9-1-1 展開の範囲を定義する
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Skype for Business Server アプリケーションで E9-1-1 展開を計画するために必要なエンタープライズ VoIP。
ms.openlocfilehash: 39397064fe525a2b1324b8ef0a0f0bb1df287653
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114573"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a><span data-ttu-id="28668-103">Skype for Business Server での E9-1-1 展開の範囲を定義する</span><span class="sxs-lookup"><span data-stu-id="28668-103">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>

<span data-ttu-id="28668-104">Skype for Business Server アプリケーションで E9-1-1 展開を計画するために必要なエンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="28668-104">Decisions necessary for planning an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="28668-105">Skype for Business for E9-1-1 を構成する前に、E9-1-1 展開を計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28668-105">Before you configure Skype for Business for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="28668-106">次のような点を検討します。</span><span class="sxs-lookup"><span data-stu-id="28668-106">Some of the questions to consider include:</span></span>

 <span data-ttu-id="28668-107">**E9-1-1 に関する組織のポリシーと法的義務は何ですか?**</span><span class="sxs-lookup"><span data-stu-id="28668-107">**What are your organization's policy and legal obligations with regard to E9-1-1?**</span></span>

 <span data-ttu-id="28668-108">PBX (E9-1-1 用語では複数回線電話システム (MLTS) と呼ばれます) 使用時の E9-1-1 の法的義務は州ごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="28668-108">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="28668-109">関連する地域での Skype for Business の展開に適用される可能性のある義務を理解するには、法務チームに相談する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28668-109">You should consult with your legal team to understand the obligations that may apply to your deployment of Skype for Business in your relevant geographies.</span></span>

 <span data-ttu-id="28668-110">**エンタープライズ内のどの領域で E9-1-1 を有効にする必要があるか**</span><span class="sxs-lookup"><span data-stu-id="28668-110">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>

 <span data-ttu-id="28668-p103">E9-1-1 は、エンタープライズ全体で有効にすることも、特定の場所だけで有効にすることもできます。たとえば、オフィスの E9-1-1 の要件が州によって異なる場合や、米国以外のサイトを除外する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="28668-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

 <span data-ttu-id="28668-113">**E9-1-1 をブランチ サイトにどのように展開するか**</span><span class="sxs-lookup"><span data-stu-id="28668-113">**How will you deploy E9-1-1 to branch sites?**</span></span>

 <span data-ttu-id="28668-114">E9-1-1 をブランチ サイトに展開するときは、音声の復元の概念を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="28668-114">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="28668-115">E-9-1-1 SIP トランクを集中管理し、WAN の停止が発生した場合、サインインしているクライアントは、位置情報サービスから場所を取得したり、緊急サービス サービス プロバイダーに接続したりできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="28668-115">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="28668-116">Skype for Business には、回復力のあるデータ ネットワークの構築、各ブランチでの SIP トランクの展開、停止中のローカル ゲートウェイへの緊急通話のプッシュなど、ブランチ オフィスでの音声復元を処理するためのいくつかの戦略が用意されています。</span><span class="sxs-lookup"><span data-stu-id="28668-116">Skype for Business provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="28668-117">詳細については、「[Planning for Branch-Site Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-branch-site-voice-resiliency)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28668-117">For details, see [Planning for Branch-Site Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-branch-site-voice-resiliency).</span></span>

 <span data-ttu-id="28668-118">**ネットワーク外のユーザーに対し、E9-1-1 を有効にするかどうか**</span><span class="sxs-lookup"><span data-stu-id="28668-118">**Will you enable E9-1-1 for users working outside the network?**</span></span>

 <span data-ttu-id="28668-119">場所の自動取得は、組織のネットワーク内にあるクライアントでのみ使用できます。そのため、組織は、オフオンプレミスの Skype for Business クライアントから行われた E9-1-1 通話をサポートするかどうかを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28668-119">Automatic location acquisition is available only for clients located inside the organization's network, so your organization needs to decide whether it will support E9-1-1 calls made from Skype for Business clients while off-premises.</span></span> <span data-ttu-id="28668-120">たとえば、ユーザーが自宅や顧客サイトから作業している場合に、緊急電話を出すのを有効にしますか?</span><span class="sxs-lookup"><span data-stu-id="28668-120">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="28668-121">クライアントがエンタープライズ ネットワークの外部にある場合、クライアントはユーザーに場所を求めるメッセージを表示するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="28668-121">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="28668-122">ただし、これらのユーザーが指定した場所はマスター ストリート アドレス ガイド (MSAG) に対して事前に評価できないので、緊急サービス サービス プロバイダーのディスパッチャーは、呼び出しを公衆安全応答ポイント (PSAP) にルーティングする前に、その場所の有効性を発信者と口頭で確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28668-122">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>

> [!NOTE]
> <span data-ttu-id="28668-123">VPN を使用して組織のネットワークに接続するユーザーの Skype for Business クライアントは、内部 IP アドレス情報を取得できますが、これらのアドレスを使用してユーザーの実際の場所を特定することはできませんので、VPN サブネットを位置情報サービスから除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28668-123">Skype for Business clients of users who connect to your organization's network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user's actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

 <span data-ttu-id="28668-124">**米国以外のサイトに緊急通話のルーティングを提供するかどうか**</span><span class="sxs-lookup"><span data-stu-id="28668-124">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>

 <span data-ttu-id="28668-p106">緊急サービスのサービス プロバイダーのサービス対象範囲外 (国外の場所など) にある会社の領域に緊急通話のルーティングを提供したい場合があります。この場合は、新しいサイトを作成し、ローカル PSTN ゲートウェイ経由で通話をルーティングする PSTN 使用法を参照する音声ポリシーをサイトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="28668-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>