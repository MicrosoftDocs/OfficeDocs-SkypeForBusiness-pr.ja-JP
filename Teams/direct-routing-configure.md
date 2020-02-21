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
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Microsoft Phone システムのダイレクトルーティングを構成する方法について説明します。
ms.openlocfilehash: 9c56078a6d016967e518746e3567373404d1c486
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157875"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="fbdfd-103">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="fbdfd-103">Configure Direct Routing</span></span>

<span data-ttu-id="fbdfd-104">Microsoft 電話システムのダイレクトルーティングを使用すると、オンプレミスのテレフォニーインフラストラクチャを Microsoft Teams に接続することができます。</span><span class="sxs-lookup"><span data-stu-id="fbdfd-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="fbdfd-105">この記事では、サポートされているオンプレミスのセッションボーダーコントローラー (SBC) とダイレクトルーティングを接続するために必要な上位レベルの手順を示します。また、ダイレクトルーティングを使用して公衆交換電話網 (PSTN) に接続するように Teams ユーザーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fbdfd-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="fbdfd-106">この記事では、詳細について関連する記事へのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="fbdfd-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="fbdfd-107">直接ルーティングが組織の適切なソリューションであるかどうかについては、「[電話システムのダイレクトルーティング](direct-routing-landing-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbdfd-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="fbdfd-108">前提条件と展開の計画については、「[直接ルーティングを計画](direct-routing-plan.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbdfd-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="fbdfd-109">また、次のセッションを見て、直接ルーティングの利点、計画方法、展開方法について学習することもできます。 [Microsoft Teams での直接ルーティング](https://aka.ms/teams-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="fbdfd-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="fbdfd-110">この記事で説明されている手順を実行するには、管理者が PowerShell コマンドレットについて理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbdfd-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="fbdfd-111">PowerShell の使用方法の詳細については、「 [Windows powershell 用にコンピューターをセットアップする](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbdfd-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="fbdfd-112">以下の記事の手順を実行する前に、お客様の sbc が SBC ベンダーの推奨として既に構成されていることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fbdfd-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="fbdfd-113">AudioCodes の展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="fbdfd-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="fbdfd-114">Oracle 展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="fbdfd-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="fbdfd-115">リボンの通信展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="fbdfd-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="fbdfd-116">TE システム (anynode) の展開ドキュメント</span><span class="sxs-lookup"><span data-stu-id="fbdfd-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="fbdfd-117">サポートされている SBCs の完全な一覧については、「[直接ルーティング用に認定されたセッション境界コントローラーの一覧](direct-routing-border-controllers.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fbdfd-117">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="fbdfd-118">Microsoft 電話システムを構成し、ユーザーが直接ルーティングを使用できるようにするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fbdfd-118">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="fbdfd-119">**手順1**</span><span class="sxs-lookup"><span data-stu-id="fbdfd-119">**Step 1.**</span></span> [<span data-ttu-id="fbdfd-120">SBC と Microsoft 電話システムを接続して接続を検証する</span><span class="sxs-lookup"><span data-stu-id="fbdfd-120">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="fbdfd-121">**手順2**</span><span class="sxs-lookup"><span data-stu-id="fbdfd-121">**Step 2.**</span></span> [<span data-ttu-id="fbdfd-122">ユーザーが直接ルーティング、音声、ボイスメールを使用できるようにする</span><span class="sxs-lookup"><span data-stu-id="fbdfd-122">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="fbdfd-123">**手順3**</span><span class="sxs-lookup"><span data-stu-id="fbdfd-123">**Step 3.**</span></span> [<span data-ttu-id="fbdfd-124">音声ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="fbdfd-124">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="fbdfd-125">**手順4。**</span><span class="sxs-lookup"><span data-stu-id="fbdfd-125">**Step 4.**</span></span> [<span data-ttu-id="fbdfd-126">数値を別の形式に変換する</span><span class="sxs-lookup"><span data-stu-id="fbdfd-126">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="fbdfd-127">複数のテナントに対して SBC を構成する場合は、「[複数のテナントの sbc を構成](direct-routing-sbc-multiple-tenants.md)する」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fbdfd-127">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="fbdfd-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="fbdfd-128">See also</span></span>

[<span data-ttu-id="fbdfd-129">電話システムのダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="fbdfd-129">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="fbdfd-130">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="fbdfd-130">Plan Direct Routing</span></span>](direct-routing-plan.md)

