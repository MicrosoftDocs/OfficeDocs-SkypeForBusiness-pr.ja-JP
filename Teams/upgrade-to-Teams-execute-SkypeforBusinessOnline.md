---
title: チームのチームで Microsoft に Skype のオンライン ビジネスからのアップグレード
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: ビジネス オンラインの Skype からチームへのアップグレードに関する考慮事項
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: fabcd88a0444a01f950064ade0c49dfef50400e1
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25013572"
---
<span data-ttu-id="7de0b-103">![展開に重点を置いて、アップグレードの旅の段階や実装段階](media/upgrade-banner-deployment.png "展開に重点を置いて、アップグレードの旅の段階や実装段階")</span><span class="sxs-lookup"><span data-stu-id="7de0b-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="7de0b-104">この資料は、アップグレード、旅の導入と展開の段階の一部です。</span><span class="sxs-lookup"><span data-stu-id="7de0b-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="7de0b-105">進む前に、次のアクティビティを完了したしたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="7de0b-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

-   [<span data-ttu-id="7de0b-106">プロジェクトの利害関係者が参加しています。</span><span class="sxs-lookup"><span data-stu-id="7de0b-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="7de0b-107">プロジェクト スコープの定義</span><span class="sxs-lookup"><span data-stu-id="7de0b-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="7de0b-108">ビジネスとチームの共存と Skype の相互運用性を理解します。</span><span class="sxs-lookup"><span data-stu-id="7de0b-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="7de0b-109">アップグレード、旅を選択</span><span class="sxs-lookup"><span data-stu-id="7de0b-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="7de0b-110">環境を準備</span><span class="sxs-lookup"><span data-stu-id="7de0b-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="7de0b-111">組織の準備</span><span class="sxs-lookup"><span data-stu-id="7de0b-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="7de0b-112">パイロットを実施しました。</span><span class="sxs-lookup"><span data-stu-id="7de0b-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)


# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="7de0b-113">チームをオンラインでビジネス用の Skype からのアップグレード</span><span class="sxs-lookup"><span data-stu-id="7de0b-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="7de0b-114">完全 Skype をオンライン ビジネスを展開しているし、ビジネスの Skype からのチームにユーザーをアップグレードする場合のこの資料の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="7de0b-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="7de0b-115">ユーザーを選択的にアップグレードすることができますまたはアップグレードをに基づいて、オールインワンの旅を適切な共存およびアップグレード モードをユーザーに割り当てることにより、組織が選択されます。</span><span class="sxs-lookup"><span data-stu-id="7de0b-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="7de0b-116">共存およびアップグレード モードを割り当てる</span><span class="sxs-lookup"><span data-stu-id="7de0b-116">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="7de0b-117">チームへのアップグレードは、ビジネス管理センターまたは、Skype のビジネス リモートの Windows Powershell セッションでマイクロソフトのチームと Skype を使用して実行することができる TeamsUpgradePolicy の TeamsOnly モードを割り当てることによって実現できます。</span><span class="sxs-lookup"><span data-stu-id="7de0b-117">Upgrading to Teams can be accomplished by assigning the TeamsOnly mode of TeamsUpgradePolicy, which can be performed by using Microsoft Teams & Skype for Business Admin Center or a Skype for Business remote Windows Powershell session.</span></span>

<span data-ttu-id="7de0b-118">詳細についてを参照してください[、共存を設定および設定をアップグレード](https://aka.ms/SkypeToTeams-SetCoexistence)し、 [TeamsUpgradePolicy: 移行と共存を管理する](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。</span><span class="sxs-lookup"><span data-stu-id="7de0b-118">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="7de0b-119">電話システムとチームのアップグレード</span><span class="sxs-lookup"><span data-stu-id="7de0b-119">Phone System and Teams upgrade</span></span>

<span data-ttu-id="7de0b-120">場合は、オンライン ビジネスの展開、Skype には、計画を呼び出すと、電話システムが含まれています、、公衆交換電話網 (PSTN) プロバイダーが、チームにユーザーをアップグレードするは自動的に移行チームを呼び出す PSTN を受信します。</span><span class="sxs-lookup"><span data-stu-id="7de0b-120">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="7de0b-121">オンライン ビジネス展開するため、Skype には、クラウドのコネクタのエディションでの電話システムが含まれている場合は、[電話システムの直接のルーティングのための追加の考慮事項](2-envision-make-my-service-decisions-direct-routing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7de0b-121">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>