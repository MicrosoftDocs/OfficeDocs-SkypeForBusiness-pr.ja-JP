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
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Microsoft Phone システムのダイレクトルーティングを構成して、オンプレミスのテレフォニーインフラストラクチャを Microsoft Teams に接続する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e1c19bfcd4c220ff6b6c53d8731149eaa8b6b4b1
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031773"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="61671-103">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="61671-103">Configure Direct Routing</span></span>

<span data-ttu-id="61671-104">Microsoft 電話システムのダイレクトルーティングを使用すると、オンプレミスのテレフォニーインフラストラクチャを Microsoft Teams に接続することができます。</span><span class="sxs-lookup"><span data-stu-id="61671-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="61671-105">この記事では、サポートされているオンプレミスのセッションボーダーコントローラー (SBC) とダイレクトルーティングを接続するために必要な上位レベルの手順を示します。また、ダイレクトルーティングを使用して公衆交換電話網 (PSTN) に接続するように Teams ユーザーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="61671-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="61671-106">この記事では、詳細について関連する記事へのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="61671-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="61671-107">直接ルーティングが組織の適切なソリューションであるかどうかについては、「 [電話システムのダイレクトルーティング](direct-routing-landing-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61671-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="61671-108">前提条件と展開の計画については、「 [直接ルーティングを計画](direct-routing-plan.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61671-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="61671-109">また、次のセッションを見て、直接ルーティングの利点、計画方法、展開方法について学習することもできます。 [Microsoft Teams での直接ルーティング](https://aka.ms/teams-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="61671-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="61671-110">この記事で説明されている手順を実行するには、管理者が PowerShell コマンドレットについて理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="61671-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="61671-111">PowerShell の使用方法の詳細については、「 [Windows powershell 用にコンピューターをセットアップする](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61671-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="61671-112">以下の記事の手順を実行する前に、お客様の sbc が SBC ベンダーの推奨として既に構成されていることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="61671-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="61671-113">AudioCodes の展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="61671-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="61671-114">Oracle 展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="61671-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="61671-115">リボンの通信展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="61671-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="61671-116">TE システム (anynode) の展開ドキュメント</span><span class="sxs-lookup"><span data-stu-id="61671-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)
- [<span data-ttu-id="61671-117">Metaswitch の展開ドキュメント</span><span class="sxs-lookup"><span data-stu-id="61671-117">Metaswitch deployment documentation</span></span>](https://www.metaswitch.com/products/core-network/perimeta-sbc)

<span data-ttu-id="61671-118">サポートされている SBCs の完全な一覧については、「 [直接ルーティング用に認定されたセッション境界コントローラーの一覧](direct-routing-border-controllers.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="61671-118">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="61671-119">Microsoft 電話システムを構成し、ユーザーが直接ルーティングを使用できるようにするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="61671-119">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="61671-120">**手順1**</span><span class="sxs-lookup"><span data-stu-id="61671-120">**Step 1.**</span></span> [<span data-ttu-id="61671-121">SBC と Microsoft 電話システムを接続して接続を検証する</span><span class="sxs-lookup"><span data-stu-id="61671-121">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="61671-122">**手順2**</span><span class="sxs-lookup"><span data-stu-id="61671-122">**Step 2.**</span></span> [<span data-ttu-id="61671-123">ユーザーが直接ルーティング、音声、ボイスメールを使用できるようにする</span><span class="sxs-lookup"><span data-stu-id="61671-123">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="61671-124">**手順3**</span><span class="sxs-lookup"><span data-stu-id="61671-124">**Step 3.**</span></span> [<span data-ttu-id="61671-125">音声ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="61671-125">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="61671-126">**手順4。**</span><span class="sxs-lookup"><span data-stu-id="61671-126">**Step 4.**</span></span> [<span data-ttu-id="61671-127">数値を別の形式に変換する</span><span class="sxs-lookup"><span data-stu-id="61671-127">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="61671-128">複数のテナントに対して SBC を構成する場合は、「 [複数のテナントの sbc を構成](direct-routing-sbc-multiple-tenants.md)する」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="61671-128">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="61671-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="61671-129">Related topics</span></span>

[<span data-ttu-id="61671-130">電話システムのダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="61671-130">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="61671-131">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="61671-131">Plan Direct Routing</span></span>](direct-routing-plan.md)

