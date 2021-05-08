---
title: アプリケーションにアップグレードするための前提条件と環境Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: このガイダンスを使用して、組織にデプロイするための前提条件と環境Teams確認します。
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
ms.openlocfilehash: e9924c24f19da3cf17f8e8a124a03acc294c24b4
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282164"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="63ca1-103">アプリケーションの前提条件と環境Teams</span><span class="sxs-lookup"><span data-stu-id="63ca1-103">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="63ca1-104">![技術準備段階が協調表示されたアップグレード行程図](media/upgrade-banner-tech-readiness.png "技術準備段階が強調表示された、アップグレード行程の各段階")</span><span class="sxs-lookup"><span data-stu-id="63ca1-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="63ca1-105">この記事は、ユーザーの準備段階と並行して実行されるアクティビティである、アップグレードが行われる技術準備段階の一部です。</span><span class="sxs-lookup"><span data-stu-id="63ca1-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="63ca1-106">先に進む前に、前のステージからこれらのアクティビティを完了してください。</span><span class="sxs-lookup"><span data-stu-id="63ca1-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="63ca1-107">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="63ca1-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="63ca1-108">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="63ca1-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="63ca1-109">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="63ca1-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="63ca1-110">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="63ca1-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="63ca1-111">Teams複数のサービスとMicrosoft 365サービスOffice 365組み合わせ、そのため、これらのサービスの適切な実装と操作に依存します。</span><span class="sxs-lookup"><span data-stu-id="63ca1-111">Teams combines multiple Microsoft 365 and Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="63ca1-112">これらのサービスには、SharePoint Online、Exchange Online、および OneDrive for Business が含まれます。</span><span class="sxs-lookup"><span data-stu-id="63ca1-112">These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="63ca1-113">すべてのサービスが必要な場合は、すべて実装することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="63ca1-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="63ca1-114">特定のサービスを実装しない場合、組織に提供できる機能Teams影響します。</span><span class="sxs-lookup"><span data-stu-id="63ca1-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="63ca1-115">たとえば、SharePoint Online を実装する必要はありません。Teams はグループ会話でのファイル共有などの特定の機能を SharePoint Online に依存します。そのため、このサービスを実装しない場合、クライアントを通じて提供される機能が低下します。</span><span class="sxs-lookup"><span data-stu-id="63ca1-115">For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="63ca1-116">前提条件と、他のテクノロジとやり取りTeamsについては、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63ca1-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="63ca1-117">組織がワークロードに対してデプロイされていない場合Microsoft 365またはOffice 365を開始する」[を参照してください](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)。</span><span class="sxs-lookup"><span data-stu-id="63ca1-117">If your organization hasn't deployed any Microsoft 365 or Office 365 workloads, see [Get started](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="63ca1-118">組織がドメインまたはドメインの検証済みドメインを追加または構成Microsoft 365場合Office 365、「ドメインに関する[FAQ」を参照してください](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)。</span><span class="sxs-lookup"><span data-stu-id="63ca1-118">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see [Domains FAQ](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="63ca1-119">組織が ID を同期して id を同期Azure Active Directory、ID モデルと認証に関するページ[をMicrosoft Teams。](identify-models-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="63ca1-119">If your organization hasn't synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="63ca1-120">組織で Exchange Online が導入されていない場合は、「[Exchange と Microsoft Teams の連携](Exchange-Teams-interact.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="63ca1-120">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="63ca1-121">組織で SharePoint Online が導入されていない場合は、「[Microsoft Teams との SharePoint Online と OneDrive for Business の連携](SharePoint-OneDrive-interact.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="63ca1-121">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="63ca1-122">グループとグループ[のMicrosoft 365やり取りMicrosoft Teams詳細については、 を参照してください](Office-365-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="63ca1-122">To learn how [Microsoft 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="63ca1-123">組織が教育機関であり、学生情報システムを使用している場合は、「Microsoft[](/schooldatasync)学校データ同期 へようこそ」を参照Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="63ca1-123">If your organization is an educational institution and you use a Student Information System, see [Welcome to Microsoft School Data Sync](/schooldatasync) before deploying Microsoft Teams.</span></span>

- <span data-ttu-id="63ca1-124">組織で公衆交換電話網 (PSTN) 通話オプションを検討している場合は、「音声[- 電話システム](cloud-voice-landing-page.md)と PSTN[](calling-plan-landing-page.md)接続」を参照してください。また、どの通話プランが最適か、および直接ルーティングに関するページ電話システム[参照してください](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="63ca1-124">If your organization is considering Public Switched Telephone Network (PSTN) calling options, see [Voice - Phone System and PSTN connectivity](cloud-voice-landing-page.md), [Which Calling Plan is right for you](calling-plan-landing-page.md), and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

- <span data-ttu-id="63ca1-125">アプリケーションを展開する前に、すべてのネットワーク要件が確実に満たTeams、「組織のネットワークを準備する」[を参照Microsoft Teams。](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="63ca1-125">To ensure all network requirements have been met before rolling out Teams, see [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

- <span data-ttu-id="63ca1-126">現在、Skype for Business Online Connector を使用してサービスを管理している場合は、Teams PowerShell モジュールに移動し、既存の PowerShell スクリプトを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63ca1-126">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="63ca1-127">詳細[については、「Skype for Business Online Connector から powerShell モジュールTeamsに移動する」](teams-powershell-move-from-sfbo.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63ca1-127">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="63ca1-128">環境が該当する前提条件を満たしていることを確認した後、現在の環境を評価して、 を[Teams。](upgrade-plan-journey-evaluate-environment.md)</span><span class="sxs-lookup"><span data-stu-id="63ca1-128">After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>