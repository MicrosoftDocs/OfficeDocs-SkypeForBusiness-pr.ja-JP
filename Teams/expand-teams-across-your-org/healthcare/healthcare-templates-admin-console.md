---
title: Teams の医療テンプレートを使用してチームを作成する
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
description: 管理センターまたは Microsoft Graph で Microsoft Teams テンプレートを使用すると、設定、チャネル、アプリの定義済みのテンプレートを提供して、チームをすばやく簡単に作成できます。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b45c949b70aa2a299f2aafe54d81cdd8a1a6c0b5
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260309"
---
# <a name="create-a-team-using-teams-healthcare-templates"></a><span data-ttu-id="3f245-103">Teams の医療テンプレートを使用してチームを作成する</span><span class="sxs-lookup"><span data-stu-id="3f245-103">Create a team using Teams healthcare templates</span></span>

<span data-ttu-id="3f245-104">Microsoft Teams テンプレートを使用すると、設定、チャネル、およびプレインストールされているアプリの定義済みのテンプレートを提供することで、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="3f245-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="3f245-105">医療組織の場合、テンプレートは特に強力です。テンプレートは、ユーザーが Teams を効果的に使用する方法を指向するための構造を提供します。</span><span class="sxs-lookup"><span data-stu-id="3f245-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="3f245-106">また、テンプレートを使用すると、管理者は組織全体に一貫したチームを展開できます。</span><span class="sxs-lookup"><span data-stu-id="3f245-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="3f245-107">この記事は、医療組織全体で複数のチームを計画、展開、管理する責任がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3f245-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="3f245-108">Teams の医療テンプレートを使用してチームを作成する方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f245-108">Choose a method for creating teams with the Teams healthcare templates:</span></span>

| <span data-ttu-id="3f245-109">誰が</span><span class="sxs-lookup"><span data-stu-id="3f245-109">Who</span></span> | <span data-ttu-id="3f245-110">使用する方法:</span><span class="sxs-lookup"><span data-stu-id="3f245-110">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="3f245-111">管理者と IT プロフェッショナル</span><span class="sxs-lookup"><span data-stu-id="3f245-111">Admins and IT Professionals</span></span> | <span data-ttu-id="3f245-112">[Teams 管理センターを使用して、](#use-the-teams-templates-in-the-teams-admin-center) 医療 Teams テンプレートに基づいてチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="3f245-112">[Use the Teams admin center](#use-the-teams-templates-in-the-teams-admin-center) to create teams based on the healthcare Teams templates.</span></span>|
| <span data-ttu-id="3f245-113">開発者とシステム インテグレーター</span><span class="sxs-lookup"><span data-stu-id="3f245-113">Developers and systems integrators</span></span> | <span data-ttu-id="3f245-114">[Microsoft Graph を使用して](#use-the-teams-templates-with-the-microsoft-graph) 、医療チームのテンプレートに基づいてチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="3f245-114">[Use the Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) to create teams based on the healthcare Teams templates.</span></span> |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a><span data-ttu-id="3f245-115">Teams 管理センターで Teams テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="3f245-115">Use the Teams templates in the Teams admin center</span></span>

<span data-ttu-id="3f245-116">Microsoft Teams 管理者は、Teams 管理センターを使用して、Teams テンプレートを使用してチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3f245-116">Microsoft Teams admins can use the Teams admin center to create teams with the Teams templates.</span></span> <span data-ttu-id="3f245-117">現在、さまざまな状況で使用できる 2 つのファースト パーティの医療テンプレートを提供しています。</span><span class="sxs-lookup"><span data-stu-id="3f245-117">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="3f245-118">チーム テンプレート全般の詳細については、管理センターの「Teams テンプレートの使用を開始する」 [を参照してください](../../get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="3f245-118">To learn more about team templates in general, see [Get started with Teams templates in the admin center](../../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

### <a name="collaborate-on-patient-care"></a><span data-ttu-id="3f245-119">患者の治療で共同作業する</span><span class="sxs-lookup"><span data-stu-id="3f245-119">Collaborate on patient care</span></span>

 <span data-ttu-id="3f245-120">ワード、ポッド、部署内の医療コミュニケーションとコラボレーションを合理化します。</span><span class="sxs-lookup"><span data-stu-id="3f245-120">Streamline healthcare communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="3f245-121">テンプレートを使用すると、患者管理とワードの業務上のニーズを容易に行えます。</span><span class="sxs-lookup"><span data-stu-id="3f245-121">The template can be used to facilitate patient management and operational needs of a ward.</span></span>

| <span data-ttu-id="3f245-122">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="3f245-122">Base template type</span></span> |<span data-ttu-id="3f245-123">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3f245-123">baseTemplateId</span></span>| <span data-ttu-id="3f245-124">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="3f245-124">Properties that come with this base template</span></span> |
| ------------------ |---|----------------------------------------------------- |
| <span data-ttu-id="3f245-125">患者の治療で共同作業する</span><span class="sxs-lookup"><span data-stu-id="3f245-125">Collaborate on patient care</span></span> |`healthcareWard` | <span data-ttu-id="3f245-126">チャネル:</span><span class="sxs-lookup"><span data-stu-id="3f245-126">Channels:</span></span><ul><li><span data-ttu-id="3f245-127">General</span><span class="sxs-lookup"><span data-stu-id="3f245-127">General</span></span></li><li><span data-ttu-id="3f245-128">お知らせ</span><span class="sxs-lookup"><span data-stu-id="3f245-128">Announcements</span></span></li><li><span data-ttu-id="3f245-129">ハドル</span><span class="sxs-lookup"><span data-stu-id="3f245-129">Huddles</span></span></li><li><span data-ttu-id="3f245-130">丸め</span><span class="sxs-lookup"><span data-stu-id="3f245-130">Rounds</span></span></li><li><span data-ttu-id="3f245-131">スタッフ</span><span class="sxs-lookup"><span data-stu-id="3f245-131">Staffing</span></span></li><li><span data-ttu-id="3f245-132">トレーニング</span><span class="sxs-lookup"><span data-stu-id="3f245-132">Training</span></span></li></ul> <span data-ttu-id="3f245-133">アプリ:</span><span class="sxs-lookup"><span data-stu-id="3f245-133">Apps:</span></span> <ul><li><span data-ttu-id="3f245-134">Wiki</span><span class="sxs-lookup"><span data-stu-id="3f245-134">Wiki</span></span></li><li><span data-ttu-id="3f245-135">リスト</span><span class="sxs-lookup"><span data-stu-id="3f245-135">Lists</span></span></li></ul>|
||||

### <a name="hospital"></a><span data-ttu-id="3f245-136">病院</span><span class="sxs-lookup"><span data-stu-id="3f245-136">Hospital</span></span>

<span data-ttu-id="3f245-137">病院内の複数のワード、ポッド、部署間のコミュニケーションとコラボレーションを合理化します。</span><span class="sxs-lookup"><span data-stu-id="3f245-137">Streamline communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="3f245-138">このテンプレートには、病院の運営のための基本チャネルのセットが含まれています。自己拡張して専門分野を臨時に含めすることができます。</span><span class="sxs-lookup"><span data-stu-id="3f245-138">This template includes a set of base channels for hospital operations, and can be self-extended to include specialties, ad-hoc.</span></span>

| <span data-ttu-id="3f245-139">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="3f245-139">Base template type</span></span> |<span data-ttu-id="3f245-140">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3f245-140">baseTemplateId</span></span> | <span data-ttu-id="3f245-141">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="3f245-141">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="3f245-142">病院</span><span class="sxs-lookup"><span data-stu-id="3f245-142">Hospital</span></span>|`healthcareHospital`|<span data-ttu-id="3f245-143">チャネル:</span><span class="sxs-lookup"><span data-stu-id="3f245-143">Channels:</span></span> <ul><li><span data-ttu-id="3f245-144">General</span><span class="sxs-lookup"><span data-stu-id="3f245-144">General</span></span></li><li><span data-ttu-id="3f245-145">お知らせ</span><span class="sxs-lookup"><span data-stu-id="3f245-145">Announcements</span></span></li><li><span data-ttu-id="3f245-146">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="3f245-146">Compliance</span></span></li><li><span data-ttu-id="3f245-147">Custodial</span><span class="sxs-lookup"><span data-stu-id="3f245-147">Custodial</span></span></li><li><span data-ttu-id="3f245-148">人事</span><span class="sxs-lookup"><span data-stu-id="3f245-148">Human resources</span></span></li><li><span data-ttu-id="3f245-149">[分数]</span><span class="sxs-lookup"><span data-stu-id="3f245-149">Pharmacy</span></span></li></ul> <span data-ttu-id="3f245-150">アプリ:</span><span class="sxs-lookup"><span data-stu-id="3f245-150">Apps:</span></span> <ul><li><span data-ttu-id="3f245-151">Wiki</span><span class="sxs-lookup"><span data-stu-id="3f245-151">Wiki</span></span></li><li><span data-ttu-id="3f245-152">リスト</span><span class="sxs-lookup"><span data-stu-id="3f245-152">Lists</span></span> </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a><span data-ttu-id="3f245-153">Microsoft Graph で Teams テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="3f245-153">Use the Teams templates with the Microsoft Graph</span></span>

<span data-ttu-id="3f245-154">開発者は Microsoft Graph を使用して、Teams テンプレートを使用してチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3f245-154">Developers can use the Microsoft Graph to create teams with the Teams templates.</span></span> <span data-ttu-id="3f245-155">現在、さまざまな状況で使用できる 2 つのファースト パーティの医療テンプレートを提供しています。</span><span class="sxs-lookup"><span data-stu-id="3f245-155">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="3f245-156">チーム テンプレート全般の詳細については、「Teams テンプレートの使用を開始 [する」を参照してください](../../get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="3f245-156">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span> <span data-ttu-id="3f245-157">Teams テンプレートと Microsoft Graph の詳細については [、Microsoft Teams API](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) の概要と [teamsTemplate リソースの種類を参照してください](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0)。</span><span class="sxs-lookup"><span data-stu-id="3f245-157">And for information about Teams templates and the Microsoft Graph, see [Microsoft Teams API overview](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) and [teamsTemplate resource type](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0).</span></span>

### <a name="ward-template"></a><span data-ttu-id="3f245-158">ワードテンプレート</span><span class="sxs-lookup"><span data-stu-id="3f245-158">Ward template</span></span>

<span data-ttu-id="3f245-159">ワード テンプレートは、ワード、ポッド、部署内でのコミュニケーションと共同作業を行う場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="3f245-159">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="3f245-160">テンプレートを使用すると、患者の管理と、ワードの業務上のニーズを容易に行えます。</span><span class="sxs-lookup"><span data-stu-id="3f245-160">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="3f245-161">たとえば、ワードのお知らせは [お知らせ] チャネルに投稿し、シフトはスタッフ管理で *管理できます*。</span><span class="sxs-lookup"><span data-stu-id="3f245-161">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="3f245-162">ワード操作を合理化する場合は、このテンプレートが最適です。</span><span class="sxs-lookup"><span data-stu-id="3f245-162">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="3f245-163">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="3f245-163">Base Template Type</span></span> |<span data-ttu-id="3f245-164">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3f245-164">baseTemplateId</span></span> |<span data-ttu-id="3f245-165">ベースライン テンプレート チャネル</span><span class="sxs-lookup"><span data-stu-id="3f245-165">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="3f245-166">医療 - ワード</span><span class="sxs-lookup"><span data-stu-id="3f245-166">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="3f245-167">お知らせ\*</span><span class="sxs-lookup"><span data-stu-id="3f245-167">Announcements\*</span></span> <br> <span data-ttu-id="3f245-168">ハドル\*</span><span class="sxs-lookup"><span data-stu-id="3f245-168">Huddles\*</span></span> <br> <span data-ttu-id="3f245-169">丸め\*</span><span class="sxs-lookup"><span data-stu-id="3f245-169">Rounds\*</span></span> <br> <span data-ttu-id="3f245-170">スタッフ\*</span><span class="sxs-lookup"><span data-stu-id="3f245-170">Staffing\*</span></span> <br> <span data-ttu-id="3f245-171">トレーニング\*</span><span class="sxs-lookup"><span data-stu-id="3f245-171">Training\*</span></span> |
|     | |         |

<span data-ttu-id="3f245-172">\* 自動お気に入り</span><span class="sxs-lookup"><span data-stu-id="3f245-172">\* Auto-favorited</span></span>

### <a name="hospital-template"></a><span data-ttu-id="3f245-173">病院のテンプレート</span><span class="sxs-lookup"><span data-stu-id="3f245-173">Hospital template</span></span>

<span data-ttu-id="3f245-174">病院テンプレートは、病院内の複数のワード、ポッド、部署間のコミュニケーションと共同作業を行う場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="3f245-174">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="3f245-175">このテンプレートには、お知らせ、カストディアル、役員用など、いくつかの運用チャネルが含まれていますが、以下のスクリプトも用意されています。このスクリプトでは、お好みで追加、削除、または編集できる、さまざまな部門または専門中心のチャネルを含むテンプレートを拡張します。 </span><span class="sxs-lookup"><span data-stu-id="3f245-175">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="3f245-176">たとえば、内科学部門を持っているが *、Ophophmology* のチャネルが必要ない場合、スクリプトは内科学チャネルを含め *、Ophophmology* チャネルを削除するために適応できます。 </span><span class="sxs-lookup"><span data-stu-id="3f245-176">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="3f245-177">通知の飽和を避けるために、これらの専門チャネルまたはワードモデルのチャネルは自動お気に入りに追加しないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3f245-177">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="3f245-178">ユーザーは通常、関連するチャネルをお気に入りに追加します。</span><span class="sxs-lookup"><span data-stu-id="3f245-178">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="3f245-179">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="3f245-179">Base Template Type</span></span> |<span data-ttu-id="3f245-180">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3f245-180">baseTemplateId</span></span> |<span data-ttu-id="3f245-181">ベースライン テンプレート チャネル</span><span class="sxs-lookup"><span data-stu-id="3f245-181">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="3f245-182">医療 - 病院</span><span class="sxs-lookup"><span data-stu-id="3f245-182">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="3f245-183">お知らせ\*</span><span class="sxs-lookup"><span data-stu-id="3f245-183">Announcements\*</span></span> <br> <span data-ttu-id="3f245-184">コンプライアンス\*</span><span class="sxs-lookup"><span data-stu-id="3f245-184">Compliance\*</span></span> <br> <span data-ttu-id="3f245-185">Custodial</span><span class="sxs-lookup"><span data-stu-id="3f245-185">Custodial</span></span> <br> <span data-ttu-id="3f245-186">人事</span><span class="sxs-lookup"><span data-stu-id="3f245-186">Human Resources</span></span> <br> <span data-ttu-id="3f245-187">[分数]</span><span class="sxs-lookup"><span data-stu-id="3f245-187">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="3f245-188">\* 自動お気に入り</span><span class="sxs-lookup"><span data-stu-id="3f245-188">\* Auto-favorited</span></span> 

### <a name="how-to-use-first-party-templates"></a><span data-ttu-id="3f245-189">ファースト パーティテンプレートの使い方</span><span class="sxs-lookup"><span data-stu-id="3f245-189">How to use first-party templates</span></span>

<span data-ttu-id="3f245-190">これらのテンプレートを使用するには、要求本文の "template@odata.bind" プロパティを "標準" から上記の TemplateID に変更します。</span><span class="sxs-lookup"><span data-stu-id="3f245-190">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="3f245-191">Teams テンプレートを展開する方法の詳細については、チームを作成する方法に関する Microsoft Graph の [記事を参照してください](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="3f245-191">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="3f245-192">テンプレートのチャネルは、[全般] タブの下に自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="3f245-192">The channels in the template will automatically be created under the General Tab.</span></span>

#### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="3f245-193">例: 病院テンプレート拡張スクリプト</span><span class="sxs-lookup"><span data-stu-id="3f245-193">Example: Hospital template extension script</span></span>

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

### <a name="related-topics"></a><span data-ttu-id="3f245-194">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f245-194">Related topics</span></span>

[<span data-ttu-id="3f245-195">Teams のテンプレートの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="3f245-195">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="3f245-196">医療関係組織のためのTeamsを始めましょう</span><span class="sxs-lookup"><span data-stu-id="3f245-196">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)
