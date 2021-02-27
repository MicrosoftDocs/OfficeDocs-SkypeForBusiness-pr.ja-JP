---
title: Teams にアップグレードするための前提条件と環境の依存関係
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: このガイダンスを使用して、組織に Teams を展開するための前提条件と環境の依存関係について説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b0ad5716dbbe1925a93f4fbfadca7084e39a9599
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347808"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="7e7c4-103">Teams の前提条件と環境の依存関係</span><span class="sxs-lookup"><span data-stu-id="7e7c4-103">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="7e7c4-104">![技術準備段階が協調表示されたアップグレード行程図](media/upgrade-banner-tech-readiness.png "技術準備段階が強調表示された、アップグレード行程の各段階")</span><span class="sxs-lookup"><span data-stu-id="7e7c4-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="7e7c4-105">この記事は、ユーザーの準備段階と並行して実行されるアクティビティである、アップグレードが行われる技術準備段階の一部です。</span><span class="sxs-lookup"><span data-stu-id="7e7c4-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="7e7c4-106">次の手順に進む前に、前のステージからこれらのアクティビティを完了したと確認します。</span><span class="sxs-lookup"><span data-stu-id="7e7c4-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="7e7c4-107">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="7e7c4-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="7e7c4-108">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="7e7c4-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="7e7c4-109">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="7e7c4-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="7e7c4-110">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="7e7c4-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="7e7c4-111">Teams は複数の Microsoft 365 サービスと Office 365 サービスを組み合わせたため、これらのサービスの適切な実装と運用に依存します。</span><span class="sxs-lookup"><span data-stu-id="7e7c4-111">Teams combines multiple Microsoft 365 and Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="7e7c4-112">これらのサービスには、SharePoint Online、Exchange Online、OneDrive for Business が含まれますが、これらに限定される機能があります。</span><span class="sxs-lookup"><span data-stu-id="7e7c4-112">These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="7e7c4-113">すべてのサービスが必要な場合は、必ずしもすべてのサービスを実装することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7e7c4-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="7e7c4-114">特定のサービスを実装しない場合、Teams が組織に提供できる機能に影響します。</span><span class="sxs-lookup"><span data-stu-id="7e7c4-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="7e7c4-115">たとえば、SharePoint Online を実装する必要はありません。Teams は、グループ会話でのファイル共有などの特定の機能を SharePoint Online に依存します。そのため、このサービスを実装しない場合、クライアントを通じて提供される機能が削減されます。</span><span class="sxs-lookup"><span data-stu-id="7e7c4-115">For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="7e7c4-116">前提条件と Teams が他のテクノロジとやり取りする方法については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e7c4-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="7e7c4-117">組織が Microsoft 365 または 365 ワークロードを展開Office場合は、「使用を開始する」を [参照してください](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)。</span><span class="sxs-lookup"><span data-stu-id="7e7c4-117">If your organization hasn't deployed any Microsoft 365 or Office 365 workloads, see [Get started](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="7e7c4-118">組織で Microsoft 365 または Office 365 の確認済みドメインが追加または構成されていない場合は、「ドメインに関する [FAQ」](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e7c4-118">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see [Domains FAQ](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="7e7c4-119">組織が Azure Active Directory と ID を同期しない場合は、「Microsoft Teams の ID モデルと認証」 [を参照してください](identify-models-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="7e7c4-119">If your organization hasn't synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="7e7c4-120">組織に Exchange Online がインストールされていない場合は、「Exchange と Microsoft Teams のやり取り方法について理解する」を [参照してください](Exchange-Teams-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="7e7c4-120">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="7e7c4-121">組織に SharePoint Online がインストールされていない場合は [、「SharePoint Online](SharePoint-OneDrive-interact.md)と OneDrive for Business が Microsoft Teams とやり取りする方法について理解する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e7c4-121">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="7e7c4-122">[Microsoft 365 グループと Microsoft Teams の対話方法について説明します](Office-365-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="7e7c4-122">To learn how [Microsoft 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="7e7c4-123">組織が教育機関で学生情報システムを使用している場合は、Microsoft Teams を展開する前に [、「Microsoft School Data Sync](https://docs.microsoft.com/schooldatasync) へようこそ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e7c4-123">If your organization is an educational institution and you use a Student Information System, see [Welcome to Microsoft School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>

- <span data-ttu-id="7e7c4-124">組織で公衆交換電話網 (PSTN) 通話オプションを検討している場合は、「音声 - 電話システムと[](calling-plan-landing-page.md)[PSTN](cloud-voice-landing-page.md)接続、最適な通話プラン、[](direct-routing-landing-page.md)電話システムダイレクト ルーティング」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e7c4-124">If your organization is considering Public Switched Telephone Network (PSTN) calling options, see [Voice - Phone System and PSTN connectivity](cloud-voice-landing-page.md), [Which Calling Plan is right for you](calling-plan-landing-page.md), and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

- <span data-ttu-id="7e7c4-125">Teams を展開する前に、すべてのネットワーク要件を満たしていることを確認するには [、「Microsoft Teams](prepare-network.md)用に組織のネットワークを準備する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e7c4-125">To ensure all network requirements have been met before rolling out Teams, see [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

- <span data-ttu-id="7e7c4-126">現在 Skype for Business Online Connector を使用してサービスを管理している場合は、Teams PowerShell モジュールに移動し、既存の PowerShell スクリプトを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e7c4-126">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="7e7c4-127">詳細 [については、「Skype for Business Online Connector から Teams PowerShell](teams-powershell-move-from-sfbo.md) モジュールに移動する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e7c4-127">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="7e7c4-128">使用している環境がすべての該当する前提条件を満たしていることを確認した後、Teams の現在 [の環境を評価します](upgrade-plan-journey-evaluate-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="7e7c4-128">After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>
