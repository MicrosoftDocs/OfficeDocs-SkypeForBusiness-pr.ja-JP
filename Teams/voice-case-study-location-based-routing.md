---
title: チームボイスの Contoso のケーススタディ
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
description: 多国籍企業向けの Teams の音声のケーススタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786076"
---
# <a name="contoso-case-study-location-based-routing"></a><span data-ttu-id="ae433-103">Contoso のケーススタディ: 場所に基づくルーティング</span><span class="sxs-lookup"><span data-stu-id="ae433-103">Contoso case study: Location-Based Routing</span></span>

<span data-ttu-id="ae433-104">位置情報に基づくルーティング (LBR) は、通話を発信または受信するときに、ポリシーとユーザーの物理的な場所に基づいて、有料でのバイパスを制限する機能です。</span><span class="sxs-lookup"><span data-stu-id="ae433-104">Location-Based Routing (LBR) is a feature that restricts toll bypass based on policy and the user's physical location at the time of placing or receiving a call.</span></span>  

## <a name="overview"></a><span data-ttu-id="ae433-105">概要</span><span class="sxs-lookup"><span data-stu-id="ae433-105">Overview</span></span>

<span data-ttu-id="ae433-106">Contoso には、公衆交換電話網 (PSTN) プロバイダーをバイパスして長距離通話料金を削減することができない2つの支社が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ae433-106">Contoso has two offices in a country where it is illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="ae433-107">メインの office には、本社と2番目の office で使用されるインターネット接続があります。</span><span class="sxs-lookup"><span data-stu-id="ae433-107">The main office has an Internet connection that is used by the main office and by the second office.</span></span> <span data-ttu-id="ae433-108">各 office には、PSTN キャリアに接続された独自のセッションボーダーコントローラー (SBC) があります。</span><span class="sxs-lookup"><span data-stu-id="ae433-108">Each office has their own Session Border Controller (SBC) connected to a PSTN carrier.</span></span>  
 
<span data-ttu-id="ae433-109">この国では、Contoso は Skype for Business 展開用に LBR が構成されています。</span><span class="sxs-lookup"><span data-stu-id="ae433-109">In this country, Contoso had LBR configured for their Skype for Business deployment.</span></span> <span data-ttu-id="ae433-110">Teams 用に LBR を構成する方法を決定するために、Contoso は[ダイレクトルーティング用の位置情報に基づくルーティングを](location-based-routing-plan.md)参照します。</span><span class="sxs-lookup"><span data-stu-id="ae433-110">To determine how to configure LBR for Teams, Contoso read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md).</span></span> <span data-ttu-id="ae433-111">Contoso は、Skype for Business が通話の発信元として、着信可能なときには、PSTN 通話を Teams ユーザーに転送でき、別の Teams ユーザーを PSTN 通話に移行できるようになったときに、同じシナリオに従っていることを確認しました。</span><span class="sxs-lookup"><span data-stu-id="ae433-111">Contoso determined that Teams and Skype for Business follow the same scenarios on when a call can be placed, when it can be received, when a PSTN call can be transferred to a Teams user, and when you can transfer another Teams user to the PSTN call.</span></span>  

<span data-ttu-id="ae433-112">Skype for Business については、「セッションボーダーコントローラー (SBC) SIP トランクで PSTN キャリアに接続する」を使用して LBR を構成しました。</span><span class="sxs-lookup"><span data-stu-id="ae433-112">For Skype for Business, LBR was configured with the Session Border Controller (SBC) SIP Trunk connecting to the PSTN carrier.</span></span> <span data-ttu-id="ae433-113">この SBC では、Contoso は認定された[SBCs のリスト](direct-routing-border-controllers.md)を確認しました。 SBC は、ダイレクトルーティングが認定されているが、メディアのバイパスは認められていないことがわかりました。</span><span class="sxs-lookup"><span data-stu-id="ae433-113">For this SBC, Contoso reviewed the [list of certified SBCs](direct-routing-border-controllers.md) and determined that the SBC deployed is certified for Direct Routing but is not certified for Media Bypass.</span></span> <span data-ttu-id="ae433-114">LBR をサポートするには、直接ルーティングが SBC オンサイトに設定されている必要があります。そのためには、ローカルのインターネット出口が必要であり、SBC はメディアバイパス用に構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae433-114">To support LBR, Direct Routing needs to be configured to the SBC on-site, there needs to be a local Internet egress, and the SBC needs to be configured for Media Bypass.</span></span> <span data-ttu-id="ae433-115">この情報に基づいて、Contoso は以下を決定しました。</span><span class="sxs-lookup"><span data-stu-id="ae433-115">Based on this information, Contoso decided the following:</span></span>

- <span data-ttu-id="ae433-116">既存の SBC がメディアバイパスに対して認定されるまで、Teams の有効化を延期します。</span><span class="sxs-lookup"><span data-stu-id="ae433-116">To delay the enablement of Teams LBR until the existing SBC is certified for Media Bypass.</span></span>   

- <span data-ttu-id="ae433-117">Contoso は、Office 365 への直接ルートとして、メインサイト SBC の使用を決定しました。</span><span class="sxs-lookup"><span data-stu-id="ae433-117">Contoso decided to use the main site SBC for the Direct Route to Office 365.</span></span>  <span data-ttu-id="ae433-118">メインサイトの SBC は、リモートサイト用のプロキシとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae433-118">The main site SBC will be the proxy SBC for the remote site.</span></span>  

- <span data-ttu-id="ae433-119">Contoso は、インドに基づくサードパーティコンサルタントを使用して、国内のテレフォニー会社での LBR 構成の認定を支援しました。</span><span class="sxs-lookup"><span data-stu-id="ae433-119">Contoso used a third-party consultant based in India to assist with certification of the LBR configuration with the telephony company in country.</span></span>  

- <span data-ttu-id="ae433-120">Office の外部で PSTN 通話を行うことができるようにするため、会社が発行した携帯電話は従業員に提供されました。</span><span class="sxs-lookup"><span data-stu-id="ae433-120">To support users working from outside of the office to place PSTN calls, the company issued mobile phone was provided to their employees.</span></span> 

<span data-ttu-id="ae433-121">次の図は、場所に基づくルーティングが必要なテレフォニーの規則を使用している国の前と後の展開を示しています。</span><span class="sxs-lookup"><span data-stu-id="ae433-121">The following diagrams show the before and after deployments for a country with telephony regulations that require Location-Based Routing:</span></span>

<span data-ttu-id="ae433-122">**元の展開**</span><span class="sxs-lookup"><span data-stu-id="ae433-122">**Original deployment**</span></span>

![以前の状態を示す図](media/voice-case-study-5.png)

<span data-ttu-id="ae433-124">**ダイレクトルーティングを使用した展開**</span><span class="sxs-lookup"><span data-stu-id="ae433-124">**Deployment with Direct Routing**</span></span>

![以前の状態を示す図](media/voice-case-study-6.png)


## <a name="configuration"></a><span data-ttu-id="ae433-126">構成</span><span class="sxs-lookup"><span data-stu-id="ae433-126">Configuration:</span></span> 

<span data-ttu-id="ae433-127">Teams のネットワークコンポーネントを構成するには、「[クラウド音声機能のネットワークトポロジを管理](manage-your-network-topology.md)する」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="ae433-127">To configure the network components in Teams, Contoso followed the instructions in [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span> <span data-ttu-id="ae433-128">Contoso は、次の手順を完了して、位置情報に基づくルーティングを構成しました。</span><span class="sxs-lookup"><span data-stu-id="ae433-128">Contoso completed the below steps to configure Location-Based Routing:</span></span> 

- <span data-ttu-id="ae433-129">ネットワーク領域の定義-1 つのネットワークリージョンが定義されました。</span><span class="sxs-lookup"><span data-stu-id="ae433-129">Define Network regions -  One network region was defined.</span></span> 

- <span data-ttu-id="ae433-130">ネットワークサイトを定義します。2つのネットワークサイトが定義されています。</span><span class="sxs-lookup"><span data-stu-id="ae433-130">Define Network sites - Two network sites were defined.</span></span> <span data-ttu-id="ae433-131">地域内のオフィスの場所ごとに1つのサイト。</span><span class="sxs-lookup"><span data-stu-id="ae433-131">One site for each office location in the region.</span></span>

- <span data-ttu-id="ae433-132">ネットワークサブネットを定義する-オフィス内の各フロアには、有線およびワイヤレスネットワーク用の独自のサブネットがあります。</span><span class="sxs-lookup"><span data-stu-id="ae433-132">Define Network subnets - Each floor within an office location has their own subnet for the wired and wireless network.</span></span> <span data-ttu-id="ae433-133">この構成により、Contoso に20個のサブネットが生まれました。</span><span class="sxs-lookup"><span data-stu-id="ae433-133">This configuration resulted in 20 subnets for Contoso.</span></span> 

- <span data-ttu-id="ae433-134">信頼できる IP アドレスを定義する-SBC の外部の IP アドレスが、信頼できる IP アドレスに追加されました。</span><span class="sxs-lookup"><span data-stu-id="ae433-134">Define trusted IP addresses - The external facing IP addresses for the SBC were added to the trusted IP address.</span></span>  

