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
description: オンプレミスのテレフォニー インフラストラクチャを Microsoft Teams に接続するために Microsoft Phone System Direct Routing を構成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ecd8579ccd092e6b82deb06aa670901cdfc3b023
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122241"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="e315d-103">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="e315d-103">Configure Direct Routing</span></span>

<span data-ttu-id="e315d-104">Microsoft Phone System Direct Routing を使用すると、オンプレミスのテレフォニー インフラストラクチャを Microsoft Teams に接続できます。</span><span class="sxs-lookup"><span data-stu-id="e315d-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="e315d-105">この記事では、サポートされているオンプレミス セッション ボーダー コントローラー (SBC) を直接ルーティングに接続するために必要な高レベルの手順と、パブリック交換電話ネットワーク (PSTN) に接続するために直接ルーティングを使用する Teams ユーザーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e315d-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="e315d-106">この記事では、詳細について関連記事にリンクしています。</span><span class="sxs-lookup"><span data-stu-id="e315d-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="e315d-107">直接ルーティングが組織に適切なソリューションであるかどうかを確認する方法については、「電話システム ダイレクト ルーティング」 [を参照してください](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="e315d-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="e315d-108">前提条件と展開の計画については、「直接ルーティングを計画する [」を参照してください](direct-routing-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="e315d-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="e315d-109">また、次のセッションを見て、直接ルーティングの利点、プランの方法、展開方法について説明します [。Microsoft Teams](https://aka.ms/teams-direct-routing)での直接ルーティング。</span><span class="sxs-lookup"><span data-stu-id="e315d-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="e315d-110">この記事で説明する手順を完了するには、管理者は PowerShell コマンドレットに精通している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e315d-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="e315d-111">PowerShell の使用の詳細については、「PowerShell を使用するコンピューター [をセットアップする」を](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e315d-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="e315d-112">これらの記事の手順を実行する前に、Microsoft では、SBC ベンダーが推奨するように SBC が既に構成されていることを確認するようにお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e315d-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="e315d-113">AudioCodes 展開ドキュメント</span><span class="sxs-lookup"><span data-stu-id="e315d-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="e315d-114">Oracle の展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="e315d-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="e315d-115">リボンコミュニケーションの展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="e315d-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="e315d-116">TE-Systems (anynode) 展開ドキュメント</span><span class="sxs-lookup"><span data-stu-id="e315d-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)
- [<span data-ttu-id="e315d-117">メタスイッチの展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="e315d-117">Metaswitch deployment documentation</span></span>](https://www.metaswitch.com/products/core-network/perimeta-sbc)

<span data-ttu-id="e315d-118">サポートされている SPC の完全なリストについては、「ダイレクト ルーティング用に認定されたセッション ボーダー コントローラーのリスト [」を参照してください](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="e315d-118">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="e315d-119">Microsoft Phone System を構成し、ユーザーが直接ルーティングを使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e315d-119">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="e315d-120">**手順 1.**</span><span class="sxs-lookup"><span data-stu-id="e315d-120">**Step 1.**</span></span> [<span data-ttu-id="e315d-121">SBC を Microsoft Phone System に接続し、接続を検証する</span><span class="sxs-lookup"><span data-stu-id="e315d-121">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="e315d-122">**手順 2.**</span><span class="sxs-lookup"><span data-stu-id="e315d-122">**Step 2.**</span></span> [<span data-ttu-id="e315d-123">直接ルーティング、音声、ボイスメールのユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="e315d-123">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="e315d-124">**手順 3.**</span><span class="sxs-lookup"><span data-stu-id="e315d-124">**Step 3.**</span></span> [<span data-ttu-id="e315d-125">音声ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="e315d-125">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="e315d-126">**手順 4.**</span><span class="sxs-lookup"><span data-stu-id="e315d-126">**Step 4.**</span></span> [<span data-ttu-id="e315d-127">数値を別の形式に翻訳する</span><span class="sxs-lookup"><span data-stu-id="e315d-127">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="e315d-128">複数のテナントに対して SBC を構成する場合は、「複数のテナントに対して SBC を構成する」も [参照する必要があります](direct-routing-sbc-multiple-tenants.md)。</span><span class="sxs-lookup"><span data-stu-id="e315d-128">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="e315d-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="e315d-129">Related topics</span></span>

[<span data-ttu-id="e315d-130">電話システムのダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="e315d-130">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="e315d-131">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="e315d-131">Plan Direct Routing</span></span>](direct-routing-plan.md)