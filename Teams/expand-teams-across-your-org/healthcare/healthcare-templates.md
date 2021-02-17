---
title: 医療組織向けテンプレート
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Microsoft Graph で Microsoft Teams テンプレートを使用すると、設定、チャネル、アプリの定義済みのテンプレートを提供して、チームをすばやく簡単に作成できます。
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX
ms.openlocfilehash: e288bc68c8160fb80d4e56a6477437e0a79fea0a
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260339"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a><span data-ttu-id="fe65e-103">医療組織向け Teams テンプレートの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="fe65e-103">Get started with Teams templates for healthcare organizations</span></span>

<span data-ttu-id="fe65e-104">Microsoft Teams テンプレートを使用すると、設定、チャネル、およびプレインストールされているアプリの定義済みのテンプレートを提供することで、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="fe65e-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="fe65e-105">医療組織の場合、テンプレートは特に強力です。テンプレートは、ユーザーが Teams を効果的に使用する方法を指向するための構造を提供します。</span><span class="sxs-lookup"><span data-stu-id="fe65e-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="fe65e-106">また、テンプレートを使用すると、管理者は組織全体に一貫したチームを展開できます。</span><span class="sxs-lookup"><span data-stu-id="fe65e-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="fe65e-107">この記事は、医療組織全体で複数のチームを計画、展開、管理する責任がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fe65e-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="fe65e-108">現在、さまざまな状況で使用できる 2 つのファースト パーティの医療テンプレートを提供しています。</span><span class="sxs-lookup"><span data-stu-id="fe65e-108">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="fe65e-109">チーム テンプレート全般の詳細については、「Teams テンプレートの使用を開始 [する」を参照してください](../../get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="fe65e-109">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span>

## <a name="ward-template"></a><span data-ttu-id="fe65e-110">ワードテンプレート</span><span class="sxs-lookup"><span data-stu-id="fe65e-110">Ward template</span></span>

<span data-ttu-id="fe65e-111">ワード テンプレートは、ワード、ポッド、部署内でのコミュニケーションと共同作業を行う場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="fe65e-111">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="fe65e-112">テンプレートを使用すると、患者の管理と、ワードの業務上のニーズを容易に行えます。</span><span class="sxs-lookup"><span data-stu-id="fe65e-112">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="fe65e-113">たとえば、ワードのお知らせは [お知らせ] チャネルに投稿し、シフトはスタッフ管理で *管理できます*。</span><span class="sxs-lookup"><span data-stu-id="fe65e-113">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="fe65e-114">ワード操作を合理化する場合は、このテンプレートが最適です。</span><span class="sxs-lookup"><span data-stu-id="fe65e-114">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="fe65e-115">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="fe65e-115">Base Template Type</span></span> |<span data-ttu-id="fe65e-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="fe65e-116">baseTemplateId</span></span> |<span data-ttu-id="fe65e-117">ベースライン テンプレート チャネル</span><span class="sxs-lookup"><span data-stu-id="fe65e-117">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="fe65e-118">医療 - ワード</span><span class="sxs-lookup"><span data-stu-id="fe65e-118">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="fe65e-119">お知らせ\*</span><span class="sxs-lookup"><span data-stu-id="fe65e-119">Announcements\*</span></span> <br> <span data-ttu-id="fe65e-120">ハドル\*</span><span class="sxs-lookup"><span data-stu-id="fe65e-120">Huddles\*</span></span> <br> <span data-ttu-id="fe65e-121">丸め\*</span><span class="sxs-lookup"><span data-stu-id="fe65e-121">Rounds\*</span></span> <br> <span data-ttu-id="fe65e-122">スタッフ\*</span><span class="sxs-lookup"><span data-stu-id="fe65e-122">Staffing\*</span></span> <br> <span data-ttu-id="fe65e-123">トレーニング\*</span><span class="sxs-lookup"><span data-stu-id="fe65e-123">Training\*</span></span> |
|     | |         |

<span data-ttu-id="fe65e-124">\* 自動お気に入り</span><span class="sxs-lookup"><span data-stu-id="fe65e-124">\* Auto-favorited</span></span>

## <a name="hospital-template"></a><span data-ttu-id="fe65e-125">病院のテンプレート</span><span class="sxs-lookup"><span data-stu-id="fe65e-125">Hospital template</span></span>

<span data-ttu-id="fe65e-126">病院テンプレートは、病院内の複数のワード、ポッド、部署間のコミュニケーションと共同作業を行う場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="fe65e-126">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="fe65e-127">このテンプレートには、お知らせ、カストディアル、役員用など、いくつかの運用チャネルが含まれていますが、以下のスクリプトも用意されています。このスクリプトでは、お好みで追加、削除、または編集できる、さまざまな部門または専門中心のチャネルを含むテンプレートを拡張します。 </span><span class="sxs-lookup"><span data-stu-id="fe65e-127">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="fe65e-128">たとえば、内科学部門を持っているが *、Ophophmology* のチャネルが必要ない場合、スクリプトは内科学チャネルを含め *、Ophophmology* チャネルを削除するために適応できます。 </span><span class="sxs-lookup"><span data-stu-id="fe65e-128">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="fe65e-129">通知の飽和を避けるために、これらの専門チャネルまたはワードモデルのチャネルは自動お気に入りに追加しないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fe65e-129">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="fe65e-130">ユーザーは通常、関連するチャネルをお気に入りに追加します。</span><span class="sxs-lookup"><span data-stu-id="fe65e-130">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="fe65e-131">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="fe65e-131">Base Template Type</span></span> |<span data-ttu-id="fe65e-132">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="fe65e-132">baseTemplateId</span></span> |<span data-ttu-id="fe65e-133">ベースライン テンプレート チャネル</span><span class="sxs-lookup"><span data-stu-id="fe65e-133">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="fe65e-134">医療 - 病院</span><span class="sxs-lookup"><span data-stu-id="fe65e-134">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="fe65e-135">お知らせ\*</span><span class="sxs-lookup"><span data-stu-id="fe65e-135">Announcements\*</span></span> <br> <span data-ttu-id="fe65e-136">コンプライアンス\*</span><span class="sxs-lookup"><span data-stu-id="fe65e-136">Compliance\*</span></span> <br> <span data-ttu-id="fe65e-137">Custodial</span><span class="sxs-lookup"><span data-stu-id="fe65e-137">Custodial</span></span> <br> <span data-ttu-id="fe65e-138">人事</span><span class="sxs-lookup"><span data-stu-id="fe65e-138">Human Resources</span></span> <br> <span data-ttu-id="fe65e-139">[分数]</span><span class="sxs-lookup"><span data-stu-id="fe65e-139">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="fe65e-140">\* 自動お気に入り</span><span class="sxs-lookup"><span data-stu-id="fe65e-140">\* Auto-favorited</span></span> 

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="fe65e-141">ファースト パーティテンプレートの使い方</span><span class="sxs-lookup"><span data-stu-id="fe65e-141">How to use first-party templates</span></span>

<span data-ttu-id="fe65e-142">これらのテンプレートを使用するには、要求本文の "template@odata.bind" プロパティを "標準" から上記の TemplateID に変更します。</span><span class="sxs-lookup"><span data-stu-id="fe65e-142">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="fe65e-143">Teams テンプレートを展開する方法の詳細については、チームを作成する方法に関する Microsoft Graph の [記事を参照してください](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="fe65e-143">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="fe65e-144">テンプレートのチャネルは、[全般] タブの下に自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="fe65e-144">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="fe65e-145">例: 病院テンプレート拡張スクリプト</span><span class="sxs-lookup"><span data-stu-id="fe65e-145">Example: Hospital template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="fe65e-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe65e-146">Related topics</span></span>

[<span data-ttu-id="fe65e-147">Teams のテンプレートの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="fe65e-147">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="fe65e-148">医療関係組織のためのTeamsを始めましょう</span><span class="sxs-lookup"><span data-stu-id="fe65e-148">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)

[<span data-ttu-id="fe65e-149">管理コンソールで Teams テンプレートの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="fe65e-149">Get started with Teams templates in the admin console</span></span>](../../get-started-with-teams-templates-in-the-admin-console.md)
