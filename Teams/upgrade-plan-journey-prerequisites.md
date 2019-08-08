---
title: Microsoft Teams の前提条件 |依存関係の導入のアップグレード
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
audience: admin
description: このガイダンスを使用して、組織にチームを展開するための前提条件と環境の依存関係について説明します。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0da49178a55cc14b98946beb7212a1627829c13e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236074"
---
<span data-ttu-id="51da8-103">![テクニカルレディネスステージを強調したアップグレードの図](media/upgrade-banner-tech-readiness.png "技術的な準備段階に重点を置いたアップグレードの段階")</span><span class="sxs-lookup"><span data-stu-id="51da8-103">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="51da8-104">この記事は、アップグレードが行われる技術準備段階の一部であり、ユーザーの準備段階と並行して実行されるアクティビティです。</span><span class="sxs-lookup"><span data-stu-id="51da8-104">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="51da8-105">続行する前に、以前のステージでこれらのアクティビティが完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="51da8-105">Before proceeding, confirm that you’ve completed these activities from previous stages:</span></span>

- [<span data-ttu-id="51da8-106">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="51da8-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="51da8-107">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="51da8-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="51da8-108">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="51da8-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="51da8-109">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="51da8-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="51da8-110">Teams の前提条件と環境上の依存関係</span><span class="sxs-lookup"><span data-stu-id="51da8-110">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="51da8-111">Teams では、複数の Office 365 サービスが組み合わされているため、これらのサービスの適切な実装と運用によって異なります。</span><span class="sxs-lookup"><span data-stu-id="51da8-111">Teams combines multiple Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="51da8-112">これらのサービスには、SharePoint Online、Exchange Online、OneDrive for Business などが含まれますが、これらは限定されません。</span><span class="sxs-lookup"><span data-stu-id="51da8-112">These services include—but aren’t limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="51da8-113">すべてのサービスが必要となるわけではありませんが、すべてのサービスを実装することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="51da8-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="51da8-114">特定のサービスを実装しない場合は、チームが組織に提供できる機能に影響します。</span><span class="sxs-lookup"><span data-stu-id="51da8-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="51da8-115">たとえば、SharePoint Online を実装する必要はありませんが、チームは SharePoint Online を使用して、グループ会話でのファイル共有などの特定の機能を利用しているため、このサービスを実装しないと、クライアント.</span><span class="sxs-lookup"><span data-stu-id="51da8-115">For example, though you don’t have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="51da8-116">前提条件については、次の記事を参照してください。チームと他のテクノロジとの相互作用について説明します。</span><span class="sxs-lookup"><span data-stu-id="51da8-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="51da8-117">組織で Office 365 ワークロードを展開していない場合は、「一般[法人向け office 365](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)の概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51da8-117">If your organization hasn’t deployed any Office 365 workloads, see [Getting Started with Office 365 for business](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="51da8-118">組織で Office 365 の確認済みドメインを追加または構成していない場合は、「 [office 365 ドメインを確認](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51da8-118">If your organization hasn’t added or configured a verified domain for Office 365, see [Verify your Office 365 domain](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="51da8-119">組織で id が Azure Active Directory に同期されていない場合は、「 [Microsoft Teams の id モデルと認証](identify-models-authentication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51da8-119">If your organization hasn’t synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="51da8-120">組織に Exchange Online がインストールされていない場合は、「 [exchange と Microsoft Teams の相互作用](Exchange-Teams-interact.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51da8-120">If your organization doesn¹t have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="51da8-121">組織に SharePoint Online がインストールされていない場合は、「 [Sharepoint online と OneDrive For business が Microsoft Teams とどのように連携するかについ](SharePoint-OneDrive-interact.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51da8-121">If your organization doesn’t have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="51da8-122">[Office 365 グループと Microsoft Teams の相互作用](Office-365-groups.md)について説明します。</span><span class="sxs-lookup"><span data-stu-id="51da8-122">Learn how [Office 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="51da8-123">組織が教育機関であり、学生の情報システムを使用している場合は、Microsoft Teams を展開する前に[School Data Sync を展開](https://docs.microsoft.com/schooldatasync)してください。</span><span class="sxs-lookup"><span data-stu-id="51da8-123">If your organization is an educational institution and you use a Student Information System, [deploy School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>

<span data-ttu-id="51da8-124">環境が該当するすべての前提条件を満たしていることを確認したら、[チームの現在の環境を評価](upgrade-plan-journey-evaluate-environment.md)します。</span><span class="sxs-lookup"><span data-stu-id="51da8-124">After you’ve verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>
