---
title: 医療テンプレートを使用してチームを作成する
author: cichur
ms.author: v-cichur
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
description: 管理センターまたは Microsoft Graph でチーム テンプレートを使用すると、設定、チャネル、アプリの定義済みのテンプレートを提供することで、チームをすばやく簡単に作成できます。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f90ddfa9682c7000c4698977c51a39c9631ff9b1
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684354"
---
# <a name="use-a-healthcare-team-templates"></a><span data-ttu-id="2f6b4-103">医療チーム テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="2f6b4-103">Use a healthcare team templates</span></span>

<span data-ttu-id="2f6b4-104">テンプレートを使用すると、設定、チャネル、およびプレインストールされたアプリの定義済みのテンプレートを提供することで、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-104">Templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="2f6b4-105">医療組織の場合、テンプレートは特に強力です。テンプレートは、ユーザーがアプリケーションを効果的に使用する方法を指向する構造を提供Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Microsoft Teams.</span></span> <span data-ttu-id="2f6b4-106">また、テンプレートを使用すると、管理者は組織全体で一貫したチームを展開できます。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="2f6b4-107">この記事は、貴社の医療組織全体で複数のチームを計画、展開し、管理する責任があるユーザーに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="2f6b4-108">チームの医療テンプレートを使用してチームを作成する方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-108">Choose a method for creating teams with the team healthcare templates:</span></span>

| <span data-ttu-id="2f6b4-109">名前</span><span class="sxs-lookup"><span data-stu-id="2f6b4-109">Who</span></span> | <span data-ttu-id="2f6b4-110">使用する方法:</span><span class="sxs-lookup"><span data-stu-id="2f6b4-110">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="2f6b4-111">管理者と IT プロフェッショナル</span><span class="sxs-lookup"><span data-stu-id="2f6b4-111">Admins and IT Professionals</span></span> | <span data-ttu-id="2f6b4-112">[管理センター Teams、](#use-the-team-templates-in-the-admin-center)医療チームテンプレートに基づいてチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-112">[Use the Teams admin center](#use-the-team-templates-in-the-admin-center) to create teams based on the healthcare team templates.</span></span>|
| <span data-ttu-id="2f6b4-113">開発者およびシステム インテグレーター</span><span class="sxs-lookup"><span data-stu-id="2f6b4-113">Developers and systems integrators</span></span> | <span data-ttu-id="2f6b4-114">[Microsoft Graph](#use-the-team-templates-with-the-microsoft-graph)を使用して、医療チーム のテンプレートに基づいてチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-114">[Use the Microsoft Graph](#use-the-team-templates-with-the-microsoft-graph) to create a team based on the healthcare team templates.</span></span> |

## <a name="use-the-team-templates-in-the-admin-center"></a><span data-ttu-id="2f6b4-115">管理センターでチーム テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="2f6b4-115">Use the team templates in the admin center</span></span>

<span data-ttu-id="2f6b4-116">Microsoft Teams管理者は、管理センター Teamsチーム テンプレートを使用してチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-116">Microsoft Teams admins can use the Teams admin center to create teams with the team templates.</span></span> <span data-ttu-id="2f6b4-117">現在、ファースト パーティの医療テンプレートが 2 つ提供されています。このテンプレートはさまざまな状況で使用できます。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-117">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="2f6b4-118">チーム テンプレート全般の詳細については、「管理センターでチーム テンプレートの使用を開始する [」を参照してください](../../get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-118">To learn more about team templates in general, see [Get started with team templates in the admin center](../../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

### <a name="collaborate-on-patient-care"></a><span data-ttu-id="2f6b4-119">患者の治療で共同作業を行う</span><span class="sxs-lookup"><span data-stu-id="2f6b4-119">Collaborate on patient care</span></span>

 <span data-ttu-id="2f6b4-120">病棟、ポッド、部門内の医療コミュニケーションと共同作業を合理化できます。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-120">Streamline healthcare communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="2f6b4-121">このテンプレートを使用すると、患者や病棟の業務上のニーズの管理に容易に対応できます。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-121">The template can be used to facilitate patient management and operational needs of a ward.</span></span>

| <span data-ttu-id="2f6b4-122">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="2f6b4-122">Base template type</span></span> |<span data-ttu-id="2f6b4-123">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="2f6b4-123">baseTemplateId</span></span>| <span data-ttu-id="2f6b4-124">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="2f6b4-124">Properties that come with this base template</span></span> |
| ------------------ |---|----------------------------------------------------- |
| <span data-ttu-id="2f6b4-125">患者の治療で共同作業を行う</span><span class="sxs-lookup"><span data-stu-id="2f6b4-125">Collaborate on patient care</span></span> |`healthcareWard` | <span data-ttu-id="2f6b4-126">チャネル</span><span class="sxs-lookup"><span data-stu-id="2f6b4-126">Channels:</span></span><ul><li><span data-ttu-id="2f6b4-127">全般</span><span class="sxs-lookup"><span data-stu-id="2f6b4-127">General</span></span></li><li><span data-ttu-id="2f6b4-128">お知らせ</span><span class="sxs-lookup"><span data-stu-id="2f6b4-128">Announcements</span></span></li><li><span data-ttu-id="2f6b4-129">ハドル</span><span class="sxs-lookup"><span data-stu-id="2f6b4-129">Huddles</span></span></li><li><span data-ttu-id="2f6b4-130">ラウンド</span><span class="sxs-lookup"><span data-stu-id="2f6b4-130">Rounds</span></span></li><li><span data-ttu-id="2f6b4-131">人員配置</span><span class="sxs-lookup"><span data-stu-id="2f6b4-131">Staffing</span></span></li><li><span data-ttu-id="2f6b4-132">トレーニング</span><span class="sxs-lookup"><span data-stu-id="2f6b4-132">Training</span></span></li></ul> <span data-ttu-id="2f6b4-133">アプリ:</span><span class="sxs-lookup"><span data-stu-id="2f6b4-133">Apps:</span></span> <ul><li><span data-ttu-id="2f6b4-134">Wiki</span><span class="sxs-lookup"><span data-stu-id="2f6b4-134">Wiki</span></span></li><li><span data-ttu-id="2f6b4-135">リスト</span><span class="sxs-lookup"><span data-stu-id="2f6b4-135">Lists</span></span></li></ul>|
||||

### <a name="hospital"></a><span data-ttu-id="2f6b4-136">病院</span><span class="sxs-lookup"><span data-stu-id="2f6b4-136">Hospital</span></span>

<span data-ttu-id="2f6b4-137">病院内の複数の病棟、ポッド、部門間のコミュニケーションと共同作業を合理化します。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-137">Streamline communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="2f6b4-138">このテンプレートには、病院での活動のための基本チャネルのセットが含まれています。自分で拡張して専門分野をその場で含めすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-138">This template includes a set of base channels for hospital operations, and can be self-extended to include specialties, ad-hoc.</span></span>

| <span data-ttu-id="2f6b4-139">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="2f6b4-139">Base template type</span></span> |<span data-ttu-id="2f6b4-140">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="2f6b4-140">baseTemplateId</span></span> | <span data-ttu-id="2f6b4-141">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="2f6b4-141">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="2f6b4-142">病院</span><span class="sxs-lookup"><span data-stu-id="2f6b4-142">Hospital</span></span>|`healthcareHospital`|<span data-ttu-id="2f6b4-143">チャネル</span><span class="sxs-lookup"><span data-stu-id="2f6b4-143">Channels:</span></span> <ul><li><span data-ttu-id="2f6b4-144">全般</span><span class="sxs-lookup"><span data-stu-id="2f6b4-144">General</span></span></li><li><span data-ttu-id="2f6b4-145">お知らせ</span><span class="sxs-lookup"><span data-stu-id="2f6b4-145">Announcements</span></span></li><li><span data-ttu-id="2f6b4-146">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="2f6b4-146">Compliance</span></span></li><li><span data-ttu-id="2f6b4-147">親権</span><span class="sxs-lookup"><span data-stu-id="2f6b4-147">Custodial</span></span></li><li><span data-ttu-id="2f6b4-148">人事管理</span><span class="sxs-lookup"><span data-stu-id="2f6b4-148">Human resources</span></span></li><li><span data-ttu-id="2f6b4-149">薬局</span><span class="sxs-lookup"><span data-stu-id="2f6b4-149">Pharmacy</span></span></li></ul> <span data-ttu-id="2f6b4-150">アプリ:</span><span class="sxs-lookup"><span data-stu-id="2f6b4-150">Apps:</span></span> <ul><li><span data-ttu-id="2f6b4-151">Wiki</span><span class="sxs-lookup"><span data-stu-id="2f6b4-151">Wiki</span></span></li><li><span data-ttu-id="2f6b4-152">リスト</span><span class="sxs-lookup"><span data-stu-id="2f6b4-152">Lists</span></span> </li></ul>|
||||


## <a name="use-the-team-templates-with-the-microsoft-graph"></a><span data-ttu-id="2f6b4-153">Microsoft アカウントでチーム テンプレートを使用Graph</span><span class="sxs-lookup"><span data-stu-id="2f6b4-153">Use the team templates with the Microsoft Graph</span></span>

<span data-ttu-id="2f6b4-154">開発者は、Microsoft Graphを使用して、チーム テンプレートを使用してチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-154">Developers can use the Microsoft Graph to create teams with the team templates.</span></span> <span data-ttu-id="2f6b4-155">現在、ファースト パーティの医療テンプレートが 2 つ提供されています。このテンプレートはさまざまな状況で使用できます。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-155">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="2f6b4-156">チーム テンプレート全般の詳細については、「チーム テンプレートの概要 [」を参照してください](../../get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-156">To learn more about team templates in general, see [Get started with team templates](../../get-started-with-teams-templates.md).</span></span> <span data-ttu-id="2f6b4-157">また、チーム テンプレートと Microsoft Graphについては、「Microsoft Teams [API](/graph/teams-concept-overview?view=graph-rest-1.0)の概要」と[「teamsTemplate リソースの種類」を参照してください](/graph/api/resources/teamstemplate?view=graph-rest-1.0)。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-157">And for information about team templates and the Microsoft Graph, see [Microsoft Teams API overview](/graph/teams-concept-overview?view=graph-rest-1.0) and [teamsTemplate resource type](/graph/api/resources/teamstemplate?view=graph-rest-1.0).</span></span>

### <a name="ward-template"></a><span data-ttu-id="2f6b4-158">病棟用テンプレート</span><span class="sxs-lookup"><span data-stu-id="2f6b4-158">Ward template</span></span>

<span data-ttu-id="2f6b4-159">この病棟用テンプレートは、病棟、ポッド、部門内でのコミュニケーションと共同作業を対象としています。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-159">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="2f6b4-160">このテンプレートを使用すると、患者や、病棟の業務上のニーズの管理が容易にできます。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-160">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="2f6b4-161">たとえば、病棟の連絡事項は、*お知らせ* チャネルに投稿され、シフトは、 *スタッフィング* で管理できます。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-161">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="2f6b4-162">このテンプレートは、病棟業務の効率化を図っている場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-162">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="2f6b4-163">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="2f6b4-163">Base Template Type</span></span> |<span data-ttu-id="2f6b4-164">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="2f6b4-164">baseTemplateId</span></span> |<span data-ttu-id="2f6b4-165">ベースライン テンプレート チャネル</span><span class="sxs-lookup"><span data-stu-id="2f6b4-165">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="2f6b4-166">ヘルスケア - 病棟</span><span class="sxs-lookup"><span data-stu-id="2f6b4-166">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="2f6b4-167">お知らせ\*</span><span class="sxs-lookup"><span data-stu-id="2f6b4-167">Announcements\*</span></span> <br> <span data-ttu-id="2f6b4-168">ハドル\*</span><span class="sxs-lookup"><span data-stu-id="2f6b4-168">Huddles\*</span></span> <br> <span data-ttu-id="2f6b4-169">ラウンド\*</span><span class="sxs-lookup"><span data-stu-id="2f6b4-169">Rounds\*</span></span> <br> <span data-ttu-id="2f6b4-170">人員配置\*</span><span class="sxs-lookup"><span data-stu-id="2f6b4-170">Staffing\*</span></span> <br> <span data-ttu-id="2f6b4-171">トレーニング\*</span><span class="sxs-lookup"><span data-stu-id="2f6b4-171">Training\*</span></span> |
|     | |         |

<span data-ttu-id="2f6b4-172">\*自動的にお気に入りに登録する</span><span class="sxs-lookup"><span data-stu-id="2f6b4-172">\* Auto-favorited</span></span>

### <a name="hospital-template"></a><span data-ttu-id="2f6b4-173">病院のテンプレート</span><span class="sxs-lookup"><span data-stu-id="2f6b4-173">Hospital template</span></span>

<span data-ttu-id="2f6b4-174">病院のテンプレートは、病院内の複数の病棟、ポッド、部門間のコミュニケーションと共同作業を対象としています。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-174">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="2f6b4-175">このテンプレートには、*お知らせ*、*カストディアル* および *薬品* を含むいくつかの運用チャネルが含まれていますが、テンプレートの拡張が可能なスクリプトも用意されています。このスクリプトに、必要に応じて追加の部門、専門的な中枢チャネルを追加、削除、または編集できます。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-175">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="2f6b4-176">たとえば、*Endocrinology (内分泌学)* 部門はあるが、*Ophthalmology (眼科学)* のチャネルが必要ない場合、スクリプトで調整して、*Endocrinology (内分泌学)* チャネルを含め、 *Ophthalmology (眼科学)* のチャネルを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-176">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="2f6b4-177">このような専門的なチャネルまたは病棟用に特化したチャネルは、過度の通知を回避するために、自動的にお気に入りに登録しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-177">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="2f6b4-178">ユーザーは通常、自分に関連するチャンネルをお気に入りにしています。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-178">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="2f6b4-179">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="2f6b4-179">Base Template Type</span></span> |<span data-ttu-id="2f6b4-180">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="2f6b4-180">baseTemplateId</span></span> |<span data-ttu-id="2f6b4-181">ベースライン テンプレート チャネル</span><span class="sxs-lookup"><span data-stu-id="2f6b4-181">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="2f6b4-182">医療 - 病院</span><span class="sxs-lookup"><span data-stu-id="2f6b4-182">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="2f6b4-183">お知らせ\*</span><span class="sxs-lookup"><span data-stu-id="2f6b4-183">Announcements\*</span></span> <br> <span data-ttu-id="2f6b4-184">コンプライアンス\*</span><span class="sxs-lookup"><span data-stu-id="2f6b4-184">Compliance\*</span></span> <br> <span data-ttu-id="2f6b4-185">カストディアル</span><span class="sxs-lookup"><span data-stu-id="2f6b4-185">Custodial</span></span> <br> <span data-ttu-id="2f6b4-186">人事</span><span class="sxs-lookup"><span data-stu-id="2f6b4-186">Human Resources</span></span> <br> <span data-ttu-id="2f6b4-187">薬局</span><span class="sxs-lookup"><span data-stu-id="2f6b4-187">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="2f6b4-188">\*自動的にお気に入りに登録する</span><span class="sxs-lookup"><span data-stu-id="2f6b4-188">\* Auto-favorited</span></span> 

### <a name="how-to-use-first-party-templates"></a><span data-ttu-id="2f6b4-189">ファースト パーティ テンプレートの使い方</span><span class="sxs-lookup"><span data-stu-id="2f6b4-189">How to use first-party templates</span></span>

<span data-ttu-id="2f6b4-190">これらのテンプレートを使用するには、要求本文の 'template@odata.bind' プロパティを '標準' から TemplateIDs に変更します。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-190">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="2f6b4-191">チーム テンプレートをデプロイする方法の詳細については、チームの作成方法に関する Microsoft Graph記事[を参照してください](/graph/api/team-post?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-191">For more information on how to deploy team templates, see the Microsoft Graph article on how to [create a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="2f6b4-192">テンプレートのチャネルは自動的に [全般] タブに作成されます。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-192">The channels in the template will automatically be created under the General Tab.</span></span>

#### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="2f6b4-193">例: 病院テンプレート拡張機能スクリプト</span><span class="sxs-lookup"><span data-stu-id="2f6b4-193">Example: Hospital template extension script</span></span>

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

### <a name="related-topics"></a><span data-ttu-id="2f6b4-194">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f6b4-194">Related topics</span></span>

[<span data-ttu-id="2f6b4-195">チーム テンプレートの使用</span><span class="sxs-lookup"><span data-stu-id="2f6b4-195">Get started with team templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="2f6b4-196">医療組織向けチームの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="2f6b4-196">Get started with team for Healthcare organizations</span></span>](teams-in-hc.md)