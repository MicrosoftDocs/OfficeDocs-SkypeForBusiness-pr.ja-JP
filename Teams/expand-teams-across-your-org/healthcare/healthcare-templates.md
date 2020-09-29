---
title: 医療機関向けのテンプレート
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Microsoft Teams テンプレートを使用して、設定、チャネル、アプリの定義済みのテンプレートを用意することで、チームをすばやく簡単に作成できます。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f2ef6bd4bf358a90654e7fda643effbfcc34b3c2
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294440"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations-using-microsoft-graph"></a><span data-ttu-id="98174-103">Microsoft Graph を使用して医療機関向けの Teams テンプレートを使ってみる</span><span class="sxs-lookup"><span data-stu-id="98174-103">Get started with Teams templates for Healthcare organizations using Microsoft Graph</span></span>

<span data-ttu-id="98174-104">Microsoft Teams のテンプレートを使用すると、設定、チャネル、プリインストールされているアプリに定義済みのテンプレートを提供して、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="98174-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="98174-105">医療機関の場合、テンプレートは、ユーザーが Teams を効果的に使用する方法を示す構造を提供するため、特に強力です。</span><span class="sxs-lookup"><span data-stu-id="98174-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="98174-106">テンプレートを使用すると、管理者は組織全体で一貫したチームを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="98174-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="98174-107">この記事は、医療組織全体で複数のチームの計画、展開、管理を担当している場合に使います。</span><span class="sxs-lookup"><span data-stu-id="98174-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your Healthcare organization.</span></span>

<span data-ttu-id="98174-108">現在、さまざまな状況で使用できる、2つのファーストパーティの医療機関向けテンプレートが提供されています。</span><span class="sxs-lookup"><span data-stu-id="98174-108">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="98174-109">チームテンプレート全般の詳細については、「 [チームテンプレートの概要](../../get-started-with-teams-templates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98174-109">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span>

## <a name="ward-template"></a><span data-ttu-id="98174-110">ワードテンプレート</span><span class="sxs-lookup"><span data-stu-id="98174-110">Ward template</span></span>

<span data-ttu-id="98174-111">このテンプレートは、ワード、ポッド、または部門でのコミュニケーションとコラボレーションを目的としています。</span><span class="sxs-lookup"><span data-stu-id="98174-111">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="98174-112">このテンプレートを使用すると、患者の管理や、補助の運用ニーズを簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="98174-112">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="98174-113">たとえば、"いいね!" を *お知らせ* チャネルに投稿して、 *スタッフ*でシフトを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="98174-113">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="98174-114">ワード操作の合理化を検討している場合は、このテンプレートが適しています。</span><span class="sxs-lookup"><span data-stu-id="98174-114">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="98174-115">ベーステンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="98174-115">Base Template Type</span></span> |<span data-ttu-id="98174-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="98174-116">baseTemplateId</span></span> |<span data-ttu-id="98174-117">ベースラインテンプレートのチャネル</span><span class="sxs-lookup"><span data-stu-id="98174-117">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="98174-118">医療</span><span class="sxs-lookup"><span data-stu-id="98174-118">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="98174-119">お知らせ\*</span><span class="sxs-lookup"><span data-stu-id="98174-119">Announcements\*</span></span> <br> <span data-ttu-id="98174-120">Huddles\*</span><span class="sxs-lookup"><span data-stu-id="98174-120">Huddles\*</span></span> <br> <span data-ttu-id="98174-121">切り下げ\*</span><span class="sxs-lookup"><span data-stu-id="98174-121">Rounds\*</span></span> <br> <span data-ttu-id="98174-122">割り当てる\*</span><span class="sxs-lookup"><span data-stu-id="98174-122">Staffing\*</span></span> <br> <span data-ttu-id="98174-123">トレーニング\*</span><span class="sxs-lookup"><span data-stu-id="98174-123">Training\*</span></span> |
|     | |         |

<span data-ttu-id="98174-124">\* 自動お気に入り</span><span class="sxs-lookup"><span data-stu-id="98174-124">\* Auto-favorited</span></span>

## <a name="hospital-template"></a><span data-ttu-id="98174-125">病院のテンプレート</span><span class="sxs-lookup"><span data-stu-id="98174-125">Hospital template</span></span>

<span data-ttu-id="98174-126">病院のテンプレートは、病院内の複数の wards、ポッド、部門間のコミュニケーションとコラボレーションを目的としています。</span><span class="sxs-lookup"><span data-stu-id="98174-126">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="98174-127">このテンプレートには、 *お知らせ*、 *Custodial*、 *薬剤*など、いくつかの運用チャネルが含まれていますが、次のスクリプトも提供しています。ここでは、自由に追加、削除、または編集できるさまざまな追加の部門または専用のチャネルを使用してテンプレートを拡張します。</span><span class="sxs-lookup"><span data-stu-id="98174-127">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="98174-128">たとえば、 *Endocrinology* department を持っているが、 *Ophthalmology*のチャネルが必要ない場合、スクリプトは *Endocrinology* チャネルを含めて *Ophthalmology* チャネルを削除するように調整できます。</span><span class="sxs-lookup"><span data-stu-id="98174-128">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="98174-129">通知の飽和を回避するために、これらの専門分野または補助のチャネルは自動お気に入りにならないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="98174-129">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="98174-130">通常、ユーザーは関連するチャネルをお気に入りにお気に入りに表示します。</span><span class="sxs-lookup"><span data-stu-id="98174-130">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="98174-131">ベーステンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="98174-131">Base Template Type</span></span> |<span data-ttu-id="98174-132">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="98174-132">baseTemplateId</span></span> |<span data-ttu-id="98174-133">ベースラインテンプレートのチャネル</span><span class="sxs-lookup"><span data-stu-id="98174-133">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="98174-134">医療-病院</span><span class="sxs-lookup"><span data-stu-id="98174-134">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="98174-135">お知らせ\*</span><span class="sxs-lookup"><span data-stu-id="98174-135">Announcements\*</span></span> <br> <span data-ttu-id="98174-136">コンプライアンス\*</span><span class="sxs-lookup"><span data-stu-id="98174-136">Compliance\*</span></span> <br> <span data-ttu-id="98174-137">Custodial</span><span class="sxs-lookup"><span data-stu-id="98174-137">Custodial</span></span> <br> <span data-ttu-id="98174-138">人事</span><span class="sxs-lookup"><span data-stu-id="98174-138">Human Resources</span></span> <br> <span data-ttu-id="98174-139">薬</span><span class="sxs-lookup"><span data-stu-id="98174-139">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="98174-140">\* 自動お気に入り</span><span class="sxs-lookup"><span data-stu-id="98174-140">\* Auto-favorited</span></span> 

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="98174-141">ファーストパーティテンプレートの使用方法</span><span class="sxs-lookup"><span data-stu-id="98174-141">How to use first-party templates</span></span>

<span data-ttu-id="98174-142">これらのテンプレートを使用するには、要求本文の ' template@odata ' プロパティを ' standard ' から TemplateIDs に変更します。</span><span class="sxs-lookup"><span data-stu-id="98174-142">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="98174-143">Teams テンプレートの展開方法の詳細については、Microsoft Graph の記事「 [チームを作成](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98174-143">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="98174-144">テンプレートのチャネルは、[全般] タブに自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="98174-144">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="98174-145">例: 病院テンプレート拡張スクリプト</span><span class="sxs-lookup"><span data-stu-id="98174-145">Example: Hospital template extension script</span></span>

``` Powershell
{ 
          "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')",
          "DisplayName": "Contoso Hospital",
          "Description": "Team for all staff in Contoso Hospital",
          "Channels": [
            {
              "displayName": "Ambulatory",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Anesthesiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Cardiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "CCU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ear, Nose, and Throat",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Emergency Care",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Family Medicine",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Gynecology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "ICU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Mother-Baby",
              "IsFavoriteByDefault": false
            }, 
            {
              "displayName": "Neonatal",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Neurology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Oncology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ophthalmology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "PACU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Psychiatric",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Radiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Rehabilitation",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Surgical",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Urology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Women's Health",
              "IsFavoriteByDefault": false
            }
          ],
          "Apps": [
            {
              "Id": "1542629c-01b3-4a6d-8f76-1938b779e48d"
            }
          ]
          }

```

## <a name="related-topics"></a><span data-ttu-id="98174-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="98174-146">Related topics</span></span>

[<span data-ttu-id="98174-147">Teams のテンプレートの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="98174-147">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="98174-148">医療関係組織のためのTeamsを始めましょう</span><span class="sxs-lookup"><span data-stu-id="98174-148">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)

[<span data-ttu-id="98174-149">管理コンソールで Teams のテンプレートを使ってみる</span><span class="sxs-lookup"><span data-stu-id="98174-149">Get started with Teams templates in the admin console</span></span>](../../get-started-with-teams-templates-in-the-admin-console.md)
