---
title: Teams ヘルスケア テンプレートを使用してチームを作成する
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
description: 管理センターまたは Microsoft Graph で Microsoft Teams テンプレートを使用すると、設定、チャネル、およびアプリの定義済みのテンプレートを使用することで、チームをすばやく簡単に作成できます。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 13b85818101e1c3d42ae6dc715274ac23453e178
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117875"
---
# <a name="create-a-team-using-teams-healthcare-templates"></a><span data-ttu-id="a7189-103">Teams ヘルスケア テンプレートを使用してチームを作成する</span><span class="sxs-lookup"><span data-stu-id="a7189-103">Create a team using Teams healthcare templates</span></span>

<span data-ttu-id="a7189-104">Microsoft Teams テンプレートでは、設定、チャネル、事前にインストールされたアプリの定義済みテンプレートを使用することで、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="a7189-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="a7189-105">医療組織の場合、テンプレートは特に有益です。テンプレートにより、ユーザーは Teams を効果的に使用する方法を自然に理解できます。</span><span class="sxs-lookup"><span data-stu-id="a7189-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="a7189-106">また、テンプレートを使用すると、管理者は組織全体で一貫したチームを展開できます。</span><span class="sxs-lookup"><span data-stu-id="a7189-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="a7189-107">この記事は、貴社の医療組織全体で複数のチームを計画、展開し、管理する責任があるユーザーに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a7189-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="a7189-108">Teams ヘルスケア テンプレートを使用してチームを作成する方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7189-108">Choose a method for creating teams with the Teams healthcare templates:</span></span>

| <span data-ttu-id="a7189-109">名前</span><span class="sxs-lookup"><span data-stu-id="a7189-109">Who</span></span> | <span data-ttu-id="a7189-110">使用する方法:</span><span class="sxs-lookup"><span data-stu-id="a7189-110">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="a7189-111">管理者と IT プロフェッショナル</span><span class="sxs-lookup"><span data-stu-id="a7189-111">Admins and IT Professionals</span></span> | <span data-ttu-id="a7189-112">[Teams 管理センター を使用](#use-the-teams-templates-in-the-teams-admin-center)して、ヘルスケアの Teams のテンプレートに基づいてチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a7189-112">[Use the Teams admin center](#use-the-teams-templates-in-the-teams-admin-center) to create teams based on the healthcare Teams templates.</span></span>|
| <span data-ttu-id="a7189-113">開発者およびシステム インテグレーター</span><span class="sxs-lookup"><span data-stu-id="a7189-113">Developers and systems integrators</span></span> | <span data-ttu-id="a7189-114">[Microsoft Graph ツールを使用](#use-the-teams-templates-with-the-microsoft-graph)して、ヘルスケアの Teams のテンプレートに基づいてチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7189-114">[Use the Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) to create teams based on the healthcare Teams templates.</span></span> |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a><span data-ttu-id="a7189-115">Teams 管理センターで Teams テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="a7189-115">Use the Teams templates in the Teams admin center</span></span>

<span data-ttu-id="a7189-116">Microsoft Teams 管理者は、Teams 管理センターで、Teams テンプレートを使用してチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a7189-116">Microsoft Teams admins can use the Teams admin center to create teams with the Teams templates.</span></span> <span data-ttu-id="a7189-117">現在、ファースト パーティの医療テンプレートが 2 つ提供されています。このテンプレートはさまざまな状況で使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7189-117">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="a7189-118">一般的なチーム テンプレートの詳細については、「[管理センターで Teams テンプレートの使用を開始する](../../get-started-with-teams-templates-in-the-admin-console.md)」をご参照ください。</span><span class="sxs-lookup"><span data-stu-id="a7189-118">To learn more about team templates in general, see [Get started with Teams templates in the admin center](../../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

### <a name="collaborate-on-patient-care"></a><span data-ttu-id="a7189-119">患者の治療で共同作業を行う</span><span class="sxs-lookup"><span data-stu-id="a7189-119">Collaborate on patient care</span></span>

 <span data-ttu-id="a7189-120">病棟、ポッド、部門内の医療コミュニケーションと共同作業を合理化できます。</span><span class="sxs-lookup"><span data-stu-id="a7189-120">Streamline healthcare communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="a7189-121">このテンプレートを使用すると、患者や病棟の業務上のニーズの管理に容易に対応できます。</span><span class="sxs-lookup"><span data-stu-id="a7189-121">The template can be used to facilitate patient management and operational needs of a ward.</span></span>

| <span data-ttu-id="a7189-122">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="a7189-122">Base template type</span></span> |<span data-ttu-id="a7189-123">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a7189-123">baseTemplateId</span></span>| <span data-ttu-id="a7189-124">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="a7189-124">Properties that come with this base template</span></span> |
| ------------------ |---|----------------------------------------------------- |
| <span data-ttu-id="a7189-125">患者の治療で共同作業を行う</span><span class="sxs-lookup"><span data-stu-id="a7189-125">Collaborate on patient care</span></span> |`healthcareWard` | <span data-ttu-id="a7189-126">チャネル</span><span class="sxs-lookup"><span data-stu-id="a7189-126">Channels:</span></span><ul><li><span data-ttu-id="a7189-127">全般</span><span class="sxs-lookup"><span data-stu-id="a7189-127">General</span></span></li><li><span data-ttu-id="a7189-128">お知らせ</span><span class="sxs-lookup"><span data-stu-id="a7189-128">Announcements</span></span></li><li><span data-ttu-id="a7189-129">ハドル</span><span class="sxs-lookup"><span data-stu-id="a7189-129">Huddles</span></span></li><li><span data-ttu-id="a7189-130">ラウンド</span><span class="sxs-lookup"><span data-stu-id="a7189-130">Rounds</span></span></li><li><span data-ttu-id="a7189-131">人員配置</span><span class="sxs-lookup"><span data-stu-id="a7189-131">Staffing</span></span></li><li><span data-ttu-id="a7189-132">トレーニング</span><span class="sxs-lookup"><span data-stu-id="a7189-132">Training</span></span></li></ul> <span data-ttu-id="a7189-133">アプリ:</span><span class="sxs-lookup"><span data-stu-id="a7189-133">Apps:</span></span> <ul><li><span data-ttu-id="a7189-134">Wiki</span><span class="sxs-lookup"><span data-stu-id="a7189-134">Wiki</span></span></li><li><span data-ttu-id="a7189-135">リスト</span><span class="sxs-lookup"><span data-stu-id="a7189-135">Lists</span></span></li></ul>|
||||

### <a name="hospital"></a><span data-ttu-id="a7189-136">病院</span><span class="sxs-lookup"><span data-stu-id="a7189-136">Hospital</span></span>

<span data-ttu-id="a7189-137">病院内の複数の病棟、ポッド、部門間のコミュニケーションと共同作業を合理化します。</span><span class="sxs-lookup"><span data-stu-id="a7189-137">Streamline communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="a7189-138">このテンプレートには、病院での活動のための基本チャネルのセットが含まれています。自分で拡張して専門分野をその場で含めすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a7189-138">This template includes a set of base channels for hospital operations, and can be self-extended to include specialties, ad-hoc.</span></span>

| <span data-ttu-id="a7189-139">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="a7189-139">Base template type</span></span> |<span data-ttu-id="a7189-140">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a7189-140">baseTemplateId</span></span> | <span data-ttu-id="a7189-141">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="a7189-141">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="a7189-142">病院</span><span class="sxs-lookup"><span data-stu-id="a7189-142">Hospital</span></span>|`healthcareHospital`|<span data-ttu-id="a7189-143">チャネル</span><span class="sxs-lookup"><span data-stu-id="a7189-143">Channels:</span></span> <ul><li><span data-ttu-id="a7189-144">全般</span><span class="sxs-lookup"><span data-stu-id="a7189-144">General</span></span></li><li><span data-ttu-id="a7189-145">お知らせ</span><span class="sxs-lookup"><span data-stu-id="a7189-145">Announcements</span></span></li><li><span data-ttu-id="a7189-146">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="a7189-146">Compliance</span></span></li><li><span data-ttu-id="a7189-147">親権</span><span class="sxs-lookup"><span data-stu-id="a7189-147">Custodial</span></span></li><li><span data-ttu-id="a7189-148">人事管理</span><span class="sxs-lookup"><span data-stu-id="a7189-148">Human resources</span></span></li><li><span data-ttu-id="a7189-149">薬局</span><span class="sxs-lookup"><span data-stu-id="a7189-149">Pharmacy</span></span></li></ul> <span data-ttu-id="a7189-150">アプリ:</span><span class="sxs-lookup"><span data-stu-id="a7189-150">Apps:</span></span> <ul><li><span data-ttu-id="a7189-151">Wiki</span><span class="sxs-lookup"><span data-stu-id="a7189-151">Wiki</span></span></li><li><span data-ttu-id="a7189-152">リスト</span><span class="sxs-lookup"><span data-stu-id="a7189-152">Lists</span></span> </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a><span data-ttu-id="a7189-153">Microsoft Graph で Teams テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="a7189-153">Use the Teams templates with the Microsoft Graph</span></span>

<span data-ttu-id="a7189-154">開発者は、Microsoft Graph を使用して、Teams テンプレートでチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a7189-154">Developers can use the Microsoft Graph to create teams with the Teams templates.</span></span> <span data-ttu-id="a7189-155">現在、ファースト パーティの医療テンプレートが 2 つ提供されています。このテンプレートはさまざまな状況で使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7189-155">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="a7189-156">一般的なチーム テンプレートの詳細については、「[Teams テンプレートの使用を開始する](../../get-started-with-teams-templates.md)」をご参照ください。</span><span class="sxs-lookup"><span data-stu-id="a7189-156">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span> <span data-ttu-id="a7189-157">また、Teams テンプレートと Microsoft Graph については、「[Microsoft Teams API の概要 ](/graph/teams-concept-overview?view=graph-rest-1.0)」 および 「[Teams テンプレート リソース タイプ](/graph/api/resources/teamstemplate?view=graph-rest-1.0)」をご参照ください。</span><span class="sxs-lookup"><span data-stu-id="a7189-157">And for information about Teams templates and the Microsoft Graph, see [Microsoft Teams API overview](/graph/teams-concept-overview?view=graph-rest-1.0) and [teamsTemplate resource type](/graph/api/resources/teamstemplate?view=graph-rest-1.0).</span></span>

### <a name="ward-template"></a><span data-ttu-id="a7189-158">病棟用テンプレート</span><span class="sxs-lookup"><span data-stu-id="a7189-158">Ward template</span></span>

<span data-ttu-id="a7189-159">この病棟用テンプレートは、病棟、ポッド、部門内でのコミュニケーションと共同作業を対象としています。</span><span class="sxs-lookup"><span data-stu-id="a7189-159">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="a7189-160">このテンプレートを使用すると、患者や、病棟の業務上のニーズの管理が容易にできます。</span><span class="sxs-lookup"><span data-stu-id="a7189-160">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="a7189-161">たとえば、病棟の連絡事項は、*お知らせ* チャネルに投稿され、シフトは、 *スタッフィング* で管理できます。</span><span class="sxs-lookup"><span data-stu-id="a7189-161">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="a7189-162">このテンプレートは、病棟業務の効率化を図っている場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="a7189-162">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="a7189-163">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="a7189-163">Base Template Type</span></span> |<span data-ttu-id="a7189-164">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a7189-164">baseTemplateId</span></span> |<span data-ttu-id="a7189-165">ベースライン テンプレート チャネル</span><span class="sxs-lookup"><span data-stu-id="a7189-165">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="a7189-166">ヘルスケア - 病棟</span><span class="sxs-lookup"><span data-stu-id="a7189-166">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="a7189-167">お知らせ\*</span><span class="sxs-lookup"><span data-stu-id="a7189-167">Announcements\*</span></span> <br> <span data-ttu-id="a7189-168">ハドル\*</span><span class="sxs-lookup"><span data-stu-id="a7189-168">Huddles\*</span></span> <br> <span data-ttu-id="a7189-169">ラウンド\*</span><span class="sxs-lookup"><span data-stu-id="a7189-169">Rounds\*</span></span> <br> <span data-ttu-id="a7189-170">人員配置\*</span><span class="sxs-lookup"><span data-stu-id="a7189-170">Staffing\*</span></span> <br> <span data-ttu-id="a7189-171">トレーニング\*</span><span class="sxs-lookup"><span data-stu-id="a7189-171">Training\*</span></span> |
|     | |         |

<span data-ttu-id="a7189-172">\*自動的にお気に入りに登録する</span><span class="sxs-lookup"><span data-stu-id="a7189-172">\* Auto-favorited</span></span>

### <a name="hospital-template"></a><span data-ttu-id="a7189-173">病院のテンプレート</span><span class="sxs-lookup"><span data-stu-id="a7189-173">Hospital template</span></span>

<span data-ttu-id="a7189-174">病院のテンプレートは、病院内の複数の病棟、ポッド、部門間のコミュニケーションと共同作業を対象としています。</span><span class="sxs-lookup"><span data-stu-id="a7189-174">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="a7189-175">このテンプレートには、*お知らせ*、*カストディアル* および *薬品* を含むいくつかの運用チャネルが含まれていますが、テンプレートの拡張が可能なスクリプトも用意されています。このスクリプトに、必要に応じて追加の部門、専門的な中枢チャネルを追加、削除、または編集できます。</span><span class="sxs-lookup"><span data-stu-id="a7189-175">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="a7189-176">たとえば、*Endocrinology (内分泌学)* 部門はあるが、*Ophthalmology (眼科学)* のチャネルが必要ない場合、スクリプトで調整して、*Endocrinology (内分泌学)* チャネルを含め、 *Ophthalmology (眼科学)* のチャネルを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="a7189-176">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="a7189-177">このような専門的なチャネルまたは病棟用に特化したチャネルは、過度の通知を回避するために、自動的にお気に入りに登録しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a7189-177">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="a7189-178">ユーザーは通常、自分に関連するチャンネルをお気に入りにしています。</span><span class="sxs-lookup"><span data-stu-id="a7189-178">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="a7189-179">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="a7189-179">Base Template Type</span></span> |<span data-ttu-id="a7189-180">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a7189-180">baseTemplateId</span></span> |<span data-ttu-id="a7189-181">ベースライン テンプレート チャネル</span><span class="sxs-lookup"><span data-stu-id="a7189-181">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="a7189-182">医療 - 病院</span><span class="sxs-lookup"><span data-stu-id="a7189-182">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="a7189-183">お知らせ\*</span><span class="sxs-lookup"><span data-stu-id="a7189-183">Announcements\*</span></span> <br> <span data-ttu-id="a7189-184">コンプライアンス\*</span><span class="sxs-lookup"><span data-stu-id="a7189-184">Compliance\*</span></span> <br> <span data-ttu-id="a7189-185">カストディアル</span><span class="sxs-lookup"><span data-stu-id="a7189-185">Custodial</span></span> <br> <span data-ttu-id="a7189-186">人事</span><span class="sxs-lookup"><span data-stu-id="a7189-186">Human Resources</span></span> <br> <span data-ttu-id="a7189-187">薬局</span><span class="sxs-lookup"><span data-stu-id="a7189-187">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="a7189-188">\*自動的にお気に入りに登録する</span><span class="sxs-lookup"><span data-stu-id="a7189-188">\* Auto-favorited</span></span> 

### <a name="how-to-use-first-party-templates"></a><span data-ttu-id="a7189-189">ファースト パーティ テンプレートの使い方</span><span class="sxs-lookup"><span data-stu-id="a7189-189">How to use first-party templates</span></span>

<span data-ttu-id="a7189-190">これらのテンプレートを使用するには、要求本文の 'template@odata.bind' プロパティを '標準' から TemplateIDs に変更します。</span><span class="sxs-lookup"><span data-stu-id="a7189-190">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="a7189-191">Teams テンプレートを展開する方法の詳細については、「[チームの作成](/graph/api/team-post?view=graph-rest-beta)方法に関する Microsoft Graph の記事」をご参照ください。</span><span class="sxs-lookup"><span data-stu-id="a7189-191">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="a7189-192">テンプレートのチャネルは自動的に [全般] タブに作成されます。</span><span class="sxs-lookup"><span data-stu-id="a7189-192">The channels in the template will automatically be created under the General Tab.</span></span>

#### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="a7189-193">例: 病院テンプレート拡張機能スクリプト</span><span class="sxs-lookup"><span data-stu-id="a7189-193">Example: Hospital template extension script</span></span>

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

### <a name="related-topics"></a><span data-ttu-id="a7189-194">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7189-194">Related topics</span></span>

[<span data-ttu-id="a7189-195">Teams のテンプレートの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="a7189-195">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="a7189-196">医療組織向けの Teams の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="a7189-196">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)