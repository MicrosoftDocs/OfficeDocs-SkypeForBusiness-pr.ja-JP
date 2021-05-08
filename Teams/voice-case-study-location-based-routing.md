---
title: Teams Contoso のケース スタディ
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams企業向け音声ケース スタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786076"
---
# <a name="contoso-case-study-location-based-routing"></a><span data-ttu-id="c054e-103">Contoso のケース スタディ: Location-Based ルーティング</span><span class="sxs-lookup"><span data-stu-id="c054e-103">Contoso case study: Location-Based Routing</span></span>

<span data-ttu-id="c054e-104">Location-Based ルーティング (LBR) は、通話の設置時または受信時のポリシーとユーザーの物理的な場所に基づいて、有料バイパスを制限する機能です。</span><span class="sxs-lookup"><span data-stu-id="c054e-104">Location-Based Routing (LBR) is a feature that restricts toll bypass based on policy and the user's physical location at the time of placing or receiving a call.</span></span>  

## <a name="overview"></a><span data-ttu-id="c054e-105">概要</span><span class="sxs-lookup"><span data-stu-id="c054e-105">Overview</span></span>

<span data-ttu-id="c054e-106">Contoso は、公衆交換電話網 (PSTN) プロバイダーをバイパスして、遠距離通話コストを削減する違法な国に 2 つのオフィスを持っています。</span><span class="sxs-lookup"><span data-stu-id="c054e-106">Contoso has two offices in a country where it is illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="c054e-107">メイン オフィスには、メイン オフィスと 2 つ目のオフィスで使用されるインターネット接続があります。</span><span class="sxs-lookup"><span data-stu-id="c054e-107">The main office has an Internet connection that is used by the main office and by the second office.</span></span> <span data-ttu-id="c054e-108">各オフィスには、PSTN 通信事業者に接続された独自のセッション ボーダー コントローラー (SBC) があります。</span><span class="sxs-lookup"><span data-stu-id="c054e-108">Each office has their own Session Border Controller (SBC) connected to a PSTN carrier.</span></span>  
 
<span data-ttu-id="c054e-109">この国では、Contoso は LBR を新しいデプロイ用にSkype for Businessしました。</span><span class="sxs-lookup"><span data-stu-id="c054e-109">In this country, Contoso had LBR configured for their Skype for Business deployment.</span></span> <span data-ttu-id="c054e-110">ルーティング用に LBR を構成する方法を確認Teams Contoso は、「直接ルーティングの[ルーティングの計画Location-Based」を参照してください](location-based-routing-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="c054e-110">To determine how to configure LBR for Teams, Contoso read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md).</span></span> <span data-ttu-id="c054e-111">contoso は、Teams と Skype for Business は、通話を発信できる状況、通話を受信できる時間、PSTN 通話を Teams ユーザーに転送できる場合、および別の Teams ユーザーを PSTN 通話に転送できる場合に、同じシナリオに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c054e-111">Contoso determined that Teams and Skype for Business follow the same scenarios on when a call can be placed, when it can be received, when a PSTN call can be transferred to a Teams user, and when you can transfer another Teams user to the PSTN call.</span></span>  

<span data-ttu-id="c054e-112">たとえばSkype for Business、PSTN 通信事業者に接続するセッション ボーダー コントローラー (SBC) SIP トランクを使用して LBR が構成されています。</span><span class="sxs-lookup"><span data-stu-id="c054e-112">For Skype for Business, LBR was configured with the Session Border Controller (SBC) SIP Trunk connecting to the PSTN carrier.</span></span> <span data-ttu-id="c054e-113">この SBC について、Contoso は認定された [SBC](direct-routing-border-controllers.md) の一覧を確認し、デプロイされた SBC がダイレクト ルーティングの認定を受けたが、メディア バイパスの認定を受け取っていないと判断しました。</span><span class="sxs-lookup"><span data-stu-id="c054e-113">For this SBC, Contoso reviewed the [list of certified SBCs](direct-routing-border-controllers.md) and determined that the SBC deployed is certified for Direct Routing but is not certified for Media Bypass.</span></span> <span data-ttu-id="c054e-114">LBR をサポートするには、直接ルーティングをオンサイトの SBC に構成し、ローカルインターネットエグレスが必要であり、SBC をメディア バイパス用に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c054e-114">To support LBR, Direct Routing needs to be configured to the SBC on-site, there needs to be a local Internet egress, and the SBC needs to be configured for Media Bypass.</span></span> <span data-ttu-id="c054e-115">この情報に基づいて、Contoso は次の決定を行いました。</span><span class="sxs-lookup"><span data-stu-id="c054e-115">Based on this information, Contoso decided the following:</span></span>

- <span data-ttu-id="c054e-116">既存の SBC がメディア バイパスの認定Teams LBR の有効化を遅らせた場合。</span><span class="sxs-lookup"><span data-stu-id="c054e-116">To delay the enablement of Teams LBR until the existing SBC is certified for Media Bypass.</span></span>   

- <span data-ttu-id="c054e-117">Contoso は、メイン サイト SBC を使用して直接ルートを使用Office 365。</span><span class="sxs-lookup"><span data-stu-id="c054e-117">Contoso decided to use the main site SBC for the Direct Route to Office 365.</span></span>  <span data-ttu-id="c054e-118">メイン サイト SBC は、リモート サイトのプロキシ SBC です。</span><span class="sxs-lookup"><span data-stu-id="c054e-118">The main site SBC will be the proxy SBC for the remote site.</span></span>  

- <span data-ttu-id="c054e-119">Contoso は、インドに拠点を置くサード パーティのコンサルタントを使用して、国のテレフォニー会社との LBR 構成の認定を支援しました。</span><span class="sxs-lookup"><span data-stu-id="c054e-119">Contoso used a third-party consultant based in India to assist with certification of the LBR configuration with the telephony company in country.</span></span>  

- <span data-ttu-id="c054e-120">PSTN 通話を発信するためにオフィスの外部から作業しているユーザーをサポートするために、会社が発行した携帯電話が従業員に提供されました。</span><span class="sxs-lookup"><span data-stu-id="c054e-120">To support users working from outside of the office to place PSTN calls, the company issued mobile phone was provided to their employees.</span></span> 

<span data-ttu-id="c054e-121">次の図は、ルーティングを必要とするテレフォニー規制が適用された国の展開の前と後Location-Based示しています。</span><span class="sxs-lookup"><span data-stu-id="c054e-121">The following diagrams show the before and after deployments for a country with telephony regulations that require Location-Based Routing:</span></span>

<span data-ttu-id="c054e-122">**元のデプロイ**</span><span class="sxs-lookup"><span data-stu-id="c054e-122">**Original deployment**</span></span>

![状態の前を示す図](media/voice-case-study-5.png)

<span data-ttu-id="c054e-124">**直接ルーティングを使用したデプロイ**</span><span class="sxs-lookup"><span data-stu-id="c054e-124">**Deployment with Direct Routing**</span></span>

![状態の前を示す図](media/voice-case-study-6.png)


## <a name="configuration"></a><span data-ttu-id="c054e-126">構成:</span><span class="sxs-lookup"><span data-stu-id="c054e-126">Configuration:</span></span> 

<span data-ttu-id="c054e-127">Teams でネットワーク コンポーネントを構成するために、Contoso は「クラウド音声機能のネットワーク トポロジを管理する」の[手順に従いました](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="c054e-127">To configure the network components in Teams, Contoso followed the instructions in [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span> <span data-ttu-id="c054e-128">Contoso は、次の手順を完了して、ルーティングをLocation-Basedしました。</span><span class="sxs-lookup"><span data-stu-id="c054e-128">Contoso completed the below steps to configure Location-Based Routing:</span></span> 

- <span data-ttu-id="c054e-129">[ネットワーク リージョンの定義] - 1 つのネットワーク リージョンが定義されています。</span><span class="sxs-lookup"><span data-stu-id="c054e-129">Define Network regions -  One network region was defined.</span></span> 

- <span data-ttu-id="c054e-130">ネットワーク サイトの定義 - 2 つのネットワーク サイトが定義されています。</span><span class="sxs-lookup"><span data-stu-id="c054e-130">Define Network sites - Two network sites were defined.</span></span> <span data-ttu-id="c054e-131">地域内のオフィスの場所ごとに 1 つのサイト。</span><span class="sxs-lookup"><span data-stu-id="c054e-131">One site for each office location in the region.</span></span>

- <span data-ttu-id="c054e-132">ネットワーク サブネットの定義 - オフィスの場所内の各フロアには、有線ネットワークとワイヤレス ネットワーク用の独自のサブネットがあります。</span><span class="sxs-lookup"><span data-stu-id="c054e-132">Define Network subnets - Each floor within an office location has their own subnet for the wired and wireless network.</span></span> <span data-ttu-id="c054e-133">この構成により、Contoso のサブネットは 20 になります。</span><span class="sxs-lookup"><span data-stu-id="c054e-133">This configuration resulted in 20 subnets for Contoso.</span></span> 

- <span data-ttu-id="c054e-134">信頼できる IP アドレスの定義 - SBC の外部に接続する IP アドレスが信頼済み IP アドレスに追加されました。</span><span class="sxs-lookup"><span data-stu-id="c054e-134">Define trusted IP addresses - The external facing IP addresses for the SBC were added to the trusted IP address.</span></span>  

