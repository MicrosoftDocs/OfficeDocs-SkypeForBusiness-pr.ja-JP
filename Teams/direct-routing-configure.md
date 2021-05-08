---
title: ダイレクト ルーティングを構成する
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: オンプレミスのテレフォニー インフラストラクチャをMicrosoft 電話システム ダイレクト ルーティングを構成する方法について説明Microsoft Teams。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ecd8579ccd092e6b82deb06aa670901cdfc3b023
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122241"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="b6311-103">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="b6311-103">Configure Direct Routing</span></span>

<span data-ttu-id="b6311-104">Microsoft 電話システム ダイレクト ルーティングを使用すると、オンプレミスのテレフォニー インフラストラクチャをネットワークにMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="b6311-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="b6311-105">この記事では、サポートされているオンプレミスのセッション ボーダー コントローラー (SBC) を直接ルーティングに接続するために必要な大きな手順と、直接ルーティングを使用して公衆交換電話網 (PSTN) に接続するために Teams ユーザーを構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b6311-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="b6311-106">この記事では、関連する記事にリンクして詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="b6311-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="b6311-107">ダイレクト ルーティングが組織に適切なソリューションであるかどうかを確認するには、「ダイレクト ルーティング」を電話システム[参照してください](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="b6311-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="b6311-108">前提条件とデプロイの計画については、「直接ルーティングを計画 [する」を参照してください](direct-routing-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="b6311-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="b6311-109">ダイレクト ルーティングの利点、その計画方法、デプロイ方法については、次のセッションをご[Microsoft Teams覧](https://aka.ms/teams-direct-routing)ください。</span><span class="sxs-lookup"><span data-stu-id="b6311-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="b6311-110">この記事で説明する手順を完了するには、管理者が PowerShell コマンドレットに精通している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6311-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="b6311-111">PowerShell の使用の詳細については、「コンピューターをセットアップする」[を](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)参照Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b6311-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="b6311-112">これらの記事の手順を実行する前に、SBC ベンダーによって推奨される SBC が既に構成されていることを確認するようにお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b6311-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="b6311-113">AudioCodes デプロイのドキュメント</span><span class="sxs-lookup"><span data-stu-id="b6311-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="b6311-114">Oracle デプロイのドキュメント</span><span class="sxs-lookup"><span data-stu-id="b6311-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="b6311-115">リボンコミュニケーションの展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="b6311-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="b6311-116">TE-Systems (anynode) のデプロイに関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="b6311-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)
- [<span data-ttu-id="b6311-117">Metaswitch のデプロイに関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="b6311-117">Metaswitch deployment documentation</span></span>](https://www.metaswitch.com/products/core-network/perimeta-sbc)

<span data-ttu-id="b6311-118">サポートされている SBC の完全な一覧については、「ダイレクト ルーティングの認定を受けたセッション ボーダー コントローラーの一覧 [」を参照してください](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="b6311-118">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="b6311-119">Microsoft 電話 システムを構成し、ユーザーが直接ルーティングを使用するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b6311-119">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="b6311-120">**手順 1.**</span><span class="sxs-lookup"><span data-stu-id="b6311-120">**Step 1.**</span></span> [<span data-ttu-id="b6311-121">Connect システムを使用して SBC Microsoft 電話し、接続を検証する</span><span class="sxs-lookup"><span data-stu-id="b6311-121">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="b6311-122">**手順 2.**</span><span class="sxs-lookup"><span data-stu-id="b6311-122">**Step 2.**</span></span> [<span data-ttu-id="b6311-123">ダイレクト ルーティング、音声、ボイスメールのユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="b6311-123">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="b6311-124">**手順 3.**</span><span class="sxs-lookup"><span data-stu-id="b6311-124">**Step 3.**</span></span> [<span data-ttu-id="b6311-125">音声ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="b6311-125">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="b6311-126">**手順 4.**</span><span class="sxs-lookup"><span data-stu-id="b6311-126">**Step 4.**</span></span> [<span data-ttu-id="b6311-127">数値を別の形式に変換する</span><span class="sxs-lookup"><span data-stu-id="b6311-127">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="b6311-128">複数のテナントに対して SBC を構成する場合は、複数のテナントの SBC の構成に関する記事 [も参照してください](direct-routing-sbc-multiple-tenants.md)。</span><span class="sxs-lookup"><span data-stu-id="b6311-128">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="b6311-129">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b6311-129">Related topics</span></span>

[<span data-ttu-id="b6311-130">電話システムのダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="b6311-130">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="b6311-131">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="b6311-131">Plan Direct Routing</span></span>](direct-routing-plan.md)