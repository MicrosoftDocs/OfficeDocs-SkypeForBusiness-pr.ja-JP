---
title: 前提条件とマイクロソフトのチーム - マイクロソフトのチーム環境の依存関係
author: turgayo
ms.author: turgayo
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: turgayo
description: このガイドを使用して、前提条件、およびチームを組織に展開する環境の依存関係について説明するには
localization_priority: Priority
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 02189643a08eaace7a35e505d60044254f746c4d
ms.sourcegitcommit: 046cc4a880f3b6b5f912278483cf28fa25619b6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2018
ms.locfileid: "21600526"
---
<span data-ttu-id="51c37-103">![技術的な準備段階に重点を置いて、旅アップグレードの段階](media/upgrade-banner-tech-readiness.png "技術的な準備段階に重点を置いて、旅アップグレードの段階")</span><span class="sxs-lookup"><span data-stu-id="51c37-103">![Stages of the upgrade journey, with emphasis on the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="51c37-104">この資料は、ユーザーの準備段階と並行して、完了したアクティビティ、アップグレード、旅の技術的な準備段階の一部です。</span><span class="sxs-lookup"><span data-stu-id="51c37-104">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="51c37-105">次に進む前に前の段階からこれらの活動を完了していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="51c37-105">Before proceeding, confirm that you’ve completed these activities from previous stages:</span></span>

-   [<span data-ttu-id="51c37-106">プロジェクトの利害関係者が参加しています。</span><span class="sxs-lookup"><span data-stu-id="51c37-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="51c37-107">プロジェクト スコープの定義</span><span class="sxs-lookup"><span data-stu-id="51c37-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="51c37-108">ビジネスとチームの共存と Skype の相互運用性を理解します。</span><span class="sxs-lookup"><span data-stu-id="51c37-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="51c37-109">アップグレード、旅を選択</span><span class="sxs-lookup"><span data-stu-id="51c37-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="51c37-110">前提条件とチームの環境の依存関係</span><span class="sxs-lookup"><span data-stu-id="51c37-110">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="51c37-111">チームは、複数の Office 365 サービスを結合しは、適切な実装とこれらのサービスの操作に依存するため。</span><span class="sxs-lookup"><span data-stu-id="51c37-111">Teams combines multiple Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="51c37-112">これらのサービスが含まれます: だけではありませんが、-Exchange Online では、SharePoint Online およびビジネスのための OneDrive です。</span><span class="sxs-lookup"><span data-stu-id="51c37-112">These services include—but aren’t limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="51c37-113">必要なすべてのサービスが、それらのすべてを実装することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="51c37-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="51c37-114">特定のサービスを導入していない場合は、チームが、組織を提供する機能を影響します。</span><span class="sxs-lookup"><span data-stu-id="51c37-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="51c37-115">など、SharePoint Online を実装する必要はありませんがチームに依存して SharePoint Online の特定の機能など、このサービスを実装しないため、グループの会話でのファイル共有のによって提供される機能が減少しますクライアントです。</span><span class="sxs-lookup"><span data-stu-id="51c37-115">For example, though you don’t have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="51c37-116">前提条件、およびチームが他の技術とどのように対話する方法について説明する以下の資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51c37-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

-   <span data-ttu-id="51c37-117">組織では、任意の Office 365 のワークロードを展開していない場合、は、[ビジネス向けの Office 365 の概要](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51c37-117">If your organization hasn’t deployed any Office 365 workloads, see [Getting Started with Office 365 for business](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

-   <span data-ttu-id="51c37-118">組織は、追加や、検証済みのドメインを Office 365 用に構成されていない場合、は[、Office 365 のドメインの確認](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51c37-118">If your organization hasn’t added or configured a verified domain for Office 365, see [Verify your Office 365 domain](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

-   <span data-ttu-id="51c37-119">組織が Azure Active Directory にユーザーを同期していない場合は、[識別情報モデルとマイクロソフトのチームでの認証](identify-models-authentication.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51c37-119">If your organization hasn’t synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

-   <span data-ttu-id="51c37-120">組織 doesn¹t は、Exchange オンライン場合は、 [Exchange および Microsoft のチームがやり取りする方法を理解する](Exchange-Teams-interact.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51c37-120">If your organization doesn¹t have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

-   <span data-ttu-id="51c37-121">組織は、SharePoint Online に割り当てられていない、 [SharePoint Online およびビジネスのための OneDrive がマイクロソフトのチームとどのようにやり取りする方法を理解する](SharePoint-OneDrive-interact.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51c37-121">If your organization doesn’t have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

-   <span data-ttu-id="51c37-122">学習方法[Office 365 のグループとマイクロソフトのチームが対話します](Office-365-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="51c37-122">Learn how [Office 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

-   <span data-ttu-id="51c37-123">組織は、教育機関、学生情報システムでは、マイクロソフトのチームを展開する前に[学校のデータの同期を展開する](https://docs.microsoft.com/schooldatasync)に使用する場合。</span><span class="sxs-lookup"><span data-stu-id="51c37-123">If your organization is an educational institution and you use a Student Information System, [deploy School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>
                                                                           

<span data-ttu-id="51c37-124">ことの確認、環境がすべて該当する場合の前提条件、[チームの現在の環境の評価](upgrade-plan-journey-evaluate-environment.md)を満たしています。</span><span class="sxs-lookup"><span data-stu-id="51c37-124">After you’ve verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>