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
ms.openlocfilehash: b45c949b70aa2a299f2aafe54d81cdd8a1a6c0b5
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260309"
---
# <a name="create-a-team-using-teams-healthcare-templates"></a><span data-ttu-id="8fb49-103">Teams ヘルスケア テンプレートを使用してチームを作成する</span><span class="sxs-lookup"><span data-stu-id="8fb49-103">Create a team using Teams healthcare templates</span></span>

<span data-ttu-id="8fb49-104">Microsoft Teams テンプレートでは、設定、チャネル、事前にインストールされたアプリの定義済みテンプレートを使用することで、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="8fb49-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="8fb49-105">医療組織の場合、テンプレートは特に有益です。テンプレートにより、ユーザーは Teams を効果的に使用する方法を自然に理解できます。</span><span class="sxs-lookup"><span data-stu-id="8fb49-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="8fb49-106">また、テンプレートを使用すると、管理者は組織全体で一貫したチームを展開できます。</span><span class="sxs-lookup"><span data-stu-id="8fb49-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="8fb49-107">この記事は、貴社の医療組織全体で複数のチームを計画、展開し、管理する責任があるユーザーに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8fb49-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="8fb49-108">Teams ヘルスケア テンプレートを使用してチームを作成する方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="8fb49-108">Choose a method for creating teams with the Teams healthcare templates:</span></span>

| <span data-ttu-id="8fb49-109">名前</span><span class="sxs-lookup"><span data-stu-id="8fb49-109">Who</span></span> | <span data-ttu-id="8fb49-110">使用する方法:</span><span class="sxs-lookup"><span data-stu-id="8fb49-110">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="8fb49-111">管理者と IT プロフェッショナル</span><span class="sxs-lookup"><span data-stu-id="8fb49-111">Admins and IT Professionals</span></span> | <span data-ttu-id="8fb49-112">[Teams 管理センター を使用](#use-the-teams-templates-in-the-teams-admin-center)して、ヘルスケアの Teams のテンプレートに基づいてチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8fb49-112">[Use the Teams admin center](#use-the-teams-templates-in-the-teams-admin-center) to create teams based on the healthcare Teams templates.</span></span>|
| <span data-ttu-id="8fb49-113">開発者およびシステム インテグレーター</span><span class="sxs-lookup"><span data-stu-id="8fb49-113">Developers and systems integrators</span></span> | <span data-ttu-id="8fb49-114">[Microsoft Graph ツールを使用](#use-the-teams-templates-with-the-microsoft-graph)して、ヘルスケアの Teams のテンプレートに基づいてチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="8fb49-114">[Use the Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) to create teams based on the healthcare Teams templates.</span></span> |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a><span data-ttu-id="8fb49-115">Teams 管理センターで Teams テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="8fb49-115">Use the Teams templates in the Teams admin center</span></span>

<span data-ttu-id="8fb49-116">Microsoft Teams 管理者は、Teams 管理センターで、Teams テンプレートを使用してチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8fb49-116">Microsoft Teams admins can use the Teams admin center to create teams with the Teams templates.</span></span> <span data-ttu-id="8fb49-117">現在、ファースト パーティの医療テンプレートが 2 つ提供されています。このテンプレートはさまざまな状況で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8fb49-117">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="8fb49-118">一般的なチーム テンプレートの詳細については、「[管理センターで Teams テンプレートの使用を開始する](../../get-started-with-teams-templates-in-the-admin-console.md)」をご参照ください。</span><span class="sxs-lookup"><span data-stu-id="8fb49-118">To learn more about team templates in general, see [Get started with Teams templates in the admin center](../../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

### <a name="collaborate-on-patient-care"></a><span data-ttu-id="8fb49-119">患者の治療で共同作業を行う</span><span class="sxs-lookup"><span data-stu-id="8fb49-119">Collaborate on patient care</span></span>

 <span data-ttu-id="8fb49-120">病棟、ポッド、部門内の医療コミュニケーションと共同作業を合理化できます。</span><span class="sxs-lookup"><span data-stu-id="8fb49-120">Streamline healthcare communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="8fb49-121">このテンプレートを使用すると、患者や病棟の業務上のニーズの管理に容易に対応できます。</span><span class="sxs-lookup"><span data-stu-id="8fb49-121">The template can be used to facilitate patient management and operational needs of a ward.</span></span>

| <span data-ttu-id="8fb49-122">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="8fb49-122">Base template type</span></span> |<span data-ttu-id="8fb49-123">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="8fb49-123">baseTemplateId</span></span>| <span data-ttu-id="8fb49-124">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="8fb49-124">Properties that come with this base template</span></span> |
| ------------------ |---|----------------------------------------------------- |
| <span data-ttu-id="8fb49-125">患者の治療で共同作業を行う</span><span class="sxs-lookup"><span data-stu-id="8fb49-125">Collaborate on patient care</span></span> |`healthcareWard` | <span data-ttu-id="8fb49-126">チャネル</span><span class="sxs-lookup"><span data-stu-id="8fb49-126">Channels:</span></span><ul><li><span data-ttu-id="8fb49-127">全般</span><span class="sxs-lookup"><span data-stu-id="8fb49-127">General</span></span></li><li><span data-ttu-id="8fb49-128">お知らせ</span><span class="sxs-lookup"><span data-stu-id="8fb49-128">Announcements</span></span></li><li><span data-ttu-id="8fb49-129">ハドル</span><span class="sxs-lookup"><span data-stu-id="8fb49-129">Huddles</span></span></li><li><span data-ttu-id="8fb49-130">ラウンド</span><span class="sxs-lookup"><span data-stu-id="8fb49-130">Rounds</span></span></li><li><span data-ttu-id="8fb49-131">人員配置</span><span class="sxs-lookup"><span data-stu-id="8fb49-131">Staffing</span></span></li><li><span data-ttu-id="8fb49-132">トレーニング</span><span class="sxs-lookup"><span data-stu-id="8fb49-132">Training</span></span></li></ul> <span data-ttu-id="8fb49-133">アプリ:</span><span class="sxs-lookup"><span data-stu-id="8fb49-133">Apps:</span></span> <ul><li><span data-ttu-id="8fb49-134">Wiki</span><span class="sxs-lookup"><span data-stu-id="8fb49-134">Wiki</span></span></li><li><span data-ttu-id="8fb49-135">リスト</span><span class="sxs-lookup"><span data-stu-id="8fb49-135">Lists</span></span></li></ul>|
||||

### <a name="hospital"></a><span data-ttu-id="8fb49-136">病院</span><span class="sxs-lookup"><span data-stu-id="8fb49-136">Hospital</span></span>

<span data-ttu-id="8fb49-137">病院内の複数の病棟、ポッド、部門間のコミュニケーションと共同作業を合理化します。</span><span class="sxs-lookup"><span data-stu-id="8fb49-137">Streamline communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="8fb49-138">このテンプレートには、病院での活動のための基本チャネルのセットが含まれています。自分で拡張して専門分野をその場で含めすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8fb49-138">This template includes a set of base channels for hospital operations, and can be self-extended to include specialties, ad-hoc.</span></span>

| <span data-ttu-id="8fb49-139">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="8fb49-139">Base template type</span></span> |<span data-ttu-id="8fb49-140">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="8fb49-140">baseTemplateId</span></span> | <span data-ttu-id="8fb49-141">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="8fb49-141">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="8fb49-142">病院</span><span class="sxs-lookup"><span data-stu-id="8fb49-142">Hospital</span></span>|`healthcareHospital`|<span data-ttu-id="8fb49-143">チャネル</span><span class="sxs-lookup"><span data-stu-id="8fb49-143">Channels:</span></span> <ul><li><span data-ttu-id="8fb49-144">全般</span><span class="sxs-lookup"><span data-stu-id="8fb49-144">General</span></span></li><li><span data-ttu-id="8fb49-145">お知らせ</span><span class="sxs-lookup"><span data-stu-id="8fb49-145">Announcements</span></span></li><li><span data-ttu-id="8fb49-146">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="8fb49-146">Compliance</span></span></li><li><span data-ttu-id="8fb49-147">親権</span><span class="sxs-lookup"><span data-stu-id="8fb49-147">Custodial</span></span></li><li><span data-ttu-id="8fb49-148">人事管理</span><span class="sxs-lookup"><span data-stu-id="8fb49-148">Human resources</span></span></li><li><span data-ttu-id="8fb49-149">薬局</span><span class="sxs-lookup"><span data-stu-id="8fb49-149">Pharmacy</span></span></li></ul> <span data-ttu-id="8fb49-150">アプリ:</span><span class="sxs-lookup"><span data-stu-id="8fb49-150">Apps:</span></span> <ul><li><span data-ttu-id="8fb49-151">Wiki</span><span class="sxs-lookup"><span data-stu-id="8fb49-151">Wiki</span></span></li><li><span data-ttu-id="8fb49-152">リスト</span><span class="sxs-lookup"><span data-stu-id="8fb49-152">Lists</span></span> </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a><span data-ttu-id="8fb49-153">Microsoft Graph で Teams テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="8fb49-153">Use the Teams templates with the Microsoft Graph</span></span>

<span data-ttu-id="8fb49-154">開発者は、Microsoft Graph を使用して、Teams テンプレートでチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8fb49-154">Developers can use the Microsoft Graph to create teams with the Teams templates.</span></span> <span data-ttu-id="8fb49-155">現在、ファースト パーティの医療テンプレートが 2 つ提供されています。このテンプレートはさまざまな状況で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8fb49-155">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="8fb49-156">一般的なチーム テンプレートの詳細については、「[Teams テンプレートの使用を開始する](../../get-started-with-teams-templates.md)」をご参照ください。</span><span class="sxs-lookup"><span data-stu-id="8fb49-156">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span> <span data-ttu-id="8fb49-157">また、Teams テンプレートと Microsoft Graph については、「[Microsoft Teams API の概要 ](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0)」 および 「[Teams テンプレート リソース タイプ](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0)」をご参照ください。</span><span class="sxs-lookup"><span data-stu-id="8fb49-157">And for information about Teams templates and the Microsoft Graph, see [Microsoft Teams API overview](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) and [teamsTemplate resource type](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0).</span></span>

### <a name="ward-template"></a><span data-ttu-id="8fb49-158">病棟用テンプレート</span><span class="sxs-lookup"><span data-stu-id="8fb49-158">Ward template</span></span>

<span data-ttu-id="8fb49-159">この病棟用テンプレートは、病棟、ポッド、部門内でのコミュニケーションと共同作業を対象としています。</span><span class="sxs-lookup"><span data-stu-id="8fb49-159">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="8fb49-160">このテンプレートを使用すると、患者や、病棟の業務上のニーズの管理が容易にできます。</span><span class="sxs-lookup"><span data-stu-id="8fb49-160">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="8fb49-161">たとえば、病棟の連絡事項は、*お知らせ* チャネルに投稿され、シフトは、 *スタッフィング* で管理できます。</span><span class="sxs-lookup"><span data-stu-id="8fb49-161">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="8fb49-162">このテンプレートは、病棟業務の効率化を図っている場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="8fb49-162">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="8fb49-163">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="8fb49-163">Base Template Type</span></span> |<span data-ttu-id="8fb49-164">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="8fb49-164">baseTemplateId</span></span> |<span data-ttu-id="8fb49-165">ベースライン テンプレート チャネル</span><span class="sxs-lookup"><span data-stu-id="8fb49-165">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="8fb49-166">ヘルスケア - 病棟</span><span class="sxs-lookup"><span data-stu-id="8fb49-166">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="8fb49-167">お知らせ\*</span><span class="sxs-lookup"><span data-stu-id="8fb49-167">Announcements\*</span></span> <br> <span data-ttu-id="8fb49-168">ハドル\*</span><span class="sxs-lookup"><span data-stu-id="8fb49-168">Huddles\*</span></span> <br> <span data-ttu-id="8fb49-169">ラウンド\*</span><span class="sxs-lookup"><span data-stu-id="8fb49-169">Rounds\*</span></span> <br> <span data-ttu-id="8fb49-170">人員配置\*</span><span class="sxs-lookup"><span data-stu-id="8fb49-170">Staffing\*</span></span> <br> <span data-ttu-id="8fb49-171">トレーニング\*</span><span class="sxs-lookup"><span data-stu-id="8fb49-171">Training\*</span></span> |
|     | |         |

<span data-ttu-id="8fb49-172">\*自動的にお気に入りに登録する</span><span class="sxs-lookup"><span data-stu-id="8fb49-172">\* Auto-favorited</span></span>

### <a name="hospital-template"></a><span data-ttu-id="8fb49-173">病院のテンプレート</span><span class="sxs-lookup"><span data-stu-id="8fb49-173">Hospital template</span></span>

<span data-ttu-id="8fb49-174">病院のテンプレートは、病院内の複数の病棟、ポッド、部門間のコミュニケーションと共同作業を対象としています。</span><span class="sxs-lookup"><span data-stu-id="8fb49-174">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="8fb49-175">このテンプレートには、*お知らせ*、*カストディアル* および *薬品* を含むいくつかの運用チャネルが含まれていますが、テンプレートの拡張が可能なスクリプトも用意されています。このスクリプトに、必要に応じて追加の部門、専門的な中枢チャネルを追加、削除、または編集できます。</span><span class="sxs-lookup"><span data-stu-id="8fb49-175">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="8fb49-176">たとえば、*Endocrinology (内分泌学)* 部門はあるが、*Ophthalmology (眼科学)* のチャネルが必要ない場合、スクリプトで調整して、*Endocrinology (内分泌学)* チャネルを含め、 *Ophthalmology (眼科学)* のチャネルを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="8fb49-176">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="8fb49-177">このような専門的なチャネルまたは病棟用に特化したチャネルは、過度の通知を回避するために、自動的にお気に入りに登録しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8fb49-177">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="8fb49-178">ユーザーは通常、自分に関連するチャンネルをお気に入りにしています。</span><span class="sxs-lookup"><span data-stu-id="8fb49-178">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="8fb49-179">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="8fb49-179">Base Template Type</span></span> |<span data-ttu-id="8fb49-180">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="8fb49-180">baseTemplateId</span></span> |<span data-ttu-id="8fb49-181">ベースライン テンプレート チャネル</span><span class="sxs-lookup"><span data-stu-id="8fb49-181">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="8fb49-182">医療 - 病院</span><span class="sxs-lookup"><span data-stu-id="8fb49-182">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="8fb49-183">お知らせ\*</span><span class="sxs-lookup"><span data-stu-id="8fb49-183">Announcements\*</span></span> <br> <span data-ttu-id="8fb49-184">コンプライアンス\*</span><span class="sxs-lookup"><span data-stu-id="8fb49-184">Compliance\*</span></span> <br> <span data-ttu-id="8fb49-185">カストディアル</span><span class="sxs-lookup"><span data-stu-id="8fb49-185">Custodial</span></span> <br> <span data-ttu-id="8fb49-186">人事</span><span class="sxs-lookup"><span data-stu-id="8fb49-186">Human Resources</span></span> <br> <span data-ttu-id="8fb49-187">薬局</span><span class="sxs-lookup"><span data-stu-id="8fb49-187">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="8fb49-188">\*自動的にお気に入りに登録する</span><span class="sxs-lookup"><span data-stu-id="8fb49-188">\* Auto-favorited</span></span> 

### <a name="how-to-use-first-party-templates"></a><span data-ttu-id="8fb49-189">ファースト パーティ テンプレートの使い方</span><span class="sxs-lookup"><span data-stu-id="8fb49-189">How to use first-party templates</span></span>

<span data-ttu-id="8fb49-190">これらのテンプレートを使用するには、要求本文の 'template@odata.bind' プロパティを '標準' から TemplateIDs に変更します。</span><span class="sxs-lookup"><span data-stu-id="8fb49-190">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="8fb49-191">Teams テンプレートを展開する方法の詳細については、「[チームの作成](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)方法に関する Microsoft Graph の記事」をご参照ください。</span><span class="sxs-lookup"><span data-stu-id="8fb49-191">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="8fb49-192">テンプレートのチャネルは自動的に [全般] タブに作成されます。</span><span class="sxs-lookup"><span data-stu-id="8fb49-192">The channels in the template will automatically be created under the General Tab.</span></span>

#### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="8fb49-193">例: 病院テンプレート拡張機能スクリプト</span><span class="sxs-lookup"><span data-stu-id="8fb49-193">Example: Hospital template extension script</span></span>

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

### <a name="related-topics"></a><span data-ttu-id="8fb49-194">関連項目</span><span class="sxs-lookup"><span data-stu-id="8fb49-194">Related topics</span></span>

[<span data-ttu-id="8fb49-195">Teams のテンプレートの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="8fb49-195">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="8fb49-196">医療組織向けの Teams の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="8fb49-196">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)
