---
title: 小売業の Teams テンプレートの使用を開始する
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: 定義済みの設定、チャネル、および事前にインストールされたアプリを提供することで、小売業者のニーズに合わせて設計されたチーム構造を作成する Teams テンプレートの使用方法を説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8d72f88bb33dca16254ec09a2ea89ac90a0e7aca
ms.sourcegitcommit: 900f28c4ac12d65ccbd996028205ba183b4afb03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995145"
---
# <a name="create-a-team-using-teams-retail-templates"></a><span data-ttu-id="a3910-103">リテール テンプレートを使用してTeamsを作成する</span><span class="sxs-lookup"><span data-stu-id="a3910-103">Create a team using Teams retail templates</span></span>

<span data-ttu-id="a3910-104">Microsoft Teams テンプレートでは、設定、チャネル、事前にインストールされたアプリの定義済みテンプレートを使用することで、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="a3910-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="a3910-105">Teams テンプレートには、小売業者のニーズに基づいて設計されたチーム構造の定義が事前に作成されています。</span><span class="sxs-lookup"><span data-stu-id="a3910-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="a3910-106">Teams テンプレートを使用すると、小売業者にとって適切なチームの種類をすばやく作成し、組織全体に展開できます。</span><span class="sxs-lookup"><span data-stu-id="a3910-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="a3910-107">Teams テンプレートを拡張して、組織固有のニーズに合わせてチームを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="a3910-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="a3910-108">この記事では、各 Teams テンプレートを紹介し、それらの使用方法を推奨します。</span><span class="sxs-lookup"><span data-stu-id="a3910-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="a3910-109">この記事は、小売業の組織全体で複数のチームを計画、展開し、管理する責任があるユーザーに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a3910-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="a3910-110">組織内に Teams サービスがすでに展開されています。</span><span class="sxs-lookup"><span data-stu-id="a3910-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="a3910-111">展開がまだの場合は、「[Microsoft Teams の展開方法](./deploy-overview.md)」をお読みになって展開を開始してください。</span><span class="sxs-lookup"><span data-stu-id="a3910-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="a3910-112">一般的なチーム テンプレートの詳細については、「[Teams テンプレートの使用を開始する](get-started-with-teams-templates.md)」をご参照ください。</span><span class="sxs-lookup"><span data-stu-id="a3910-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

| <span data-ttu-id="a3910-113">名前</span><span class="sxs-lookup"><span data-stu-id="a3910-113">Who</span></span> | <span data-ttu-id="a3910-114">使用する方法:</span><span class="sxs-lookup"><span data-stu-id="a3910-114">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="a3910-115">管理者と IT プロフェッショナル</span><span class="sxs-lookup"><span data-stu-id="a3910-115">Admins and IT Professionals</span></span> | <span data-ttu-id="a3910-116">[Teams管理センターを使用して](#use-the-teams-templates-in-the-teams-admin-center)、リテール版のテンプレートに基づいてチームTeamsします。</span><span class="sxs-lookup"><span data-stu-id="a3910-116">[Use the Teams admin center](#use-the-teams-templates-in-the-teams-admin-center) to create teams based on the retail Teams templates.</span></span>|
| <span data-ttu-id="a3910-117">開発者およびシステム インテグレーター</span><span class="sxs-lookup"><span data-stu-id="a3910-117">Developers and systems integrators</span></span> | <span data-ttu-id="a3910-118">[Microsoft Graphを使用](#use-the-teams-templates-with-the-microsoft-graph)して、リテール版のテンプレートに基づいてチームTeamsします。</span><span class="sxs-lookup"><span data-stu-id="a3910-118">[Use the Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) to create teams based on the retail Teams templates.</span></span> |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a><span data-ttu-id="a3910-119">Teams 管理センターで Teams テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="a3910-119">Use the Teams templates in the Teams admin center</span></span>

### <a name="organize-a-store"></a><span data-ttu-id="a3910-120">店舗を整理する</span><span class="sxs-lookup"><span data-stu-id="a3910-120">Organize a store</span></span>

<span data-ttu-id="a3910-121">小売業の従業員を 1 つのエクスペリエンスにまとめ、タスクの管理、ドキュメントの共有、およびお客様の問題の解決を行います。</span><span class="sxs-lookup"><span data-stu-id="a3910-121">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="a3910-122">追加のアプリケーションを統合して、シフトの開始と終了のプロセスを合理化します。</span><span class="sxs-lookup"><span data-stu-id="a3910-122">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="a3910-123">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="a3910-123">Base template type</span></span> |<span data-ttu-id="a3910-124">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a3910-124">baseTemplateId</span></span> | <span data-ttu-id="a3910-125">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="a3910-125">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="a3910-126">店舗を整理する</span><span class="sxs-lookup"><span data-stu-id="a3910-126">Organize a store</span></span>|`retailStore`|<span data-ttu-id="a3910-127">チャネル:</span><span class="sxs-lookup"><span data-stu-id="a3910-127">Channels:</span></span> <ul><li><span data-ttu-id="a3910-128">全般</span><span class="sxs-lookup"><span data-stu-id="a3910-128">General</span></span><li><span data-ttu-id="a3910-129">シフトのハンドオフ</span><span class="sxs-lookup"><span data-stu-id="a3910-129">Shift handoff</span></span></li><li><span data-ttu-id="a3910-130">学習</span><span class="sxs-lookup"><span data-stu-id="a3910-130">Learning</span></span></li></ul> <span data-ttu-id="a3910-131">アプリ:</span><span class="sxs-lookup"><span data-stu-id="a3910-131">Apps:</span></span> <ul><li><span data-ttu-id="a3910-132">Wiki</span><span class="sxs-lookup"><span data-stu-id="a3910-132">Wiki</span></span></li></ul>|
||||

### <a name="manager-collaboration"></a><span data-ttu-id="a3910-133">マネージャー コラボレーション</span><span class="sxs-lookup"><span data-stu-id="a3910-133">Manager Collaboration</span></span>

<span data-ttu-id="a3910-134">マネージャー コラボレーション テンプレートは、複数のマネージャーが複数の店舗/地域間で共同作業を行うチームを作成する場合に最適です。たとえば、組織にリージョンがある場合は、カリフォルニア地域のマネージャー コラボレーション チームを作成し、その地域のすべてのストア マネージャーをその地域の地域マネージャーと共に含める場合があります。</span><span class="sxs-lookup"><span data-stu-id="a3910-134">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, along with the regional manager for that region.</span></span>

| <span data-ttu-id="a3910-135">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="a3910-135">Base template type</span></span>| <span data-ttu-id="a3910-136">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a3910-136">baseTemplateId</span></span> | <span data-ttu-id="a3910-137">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="a3910-137">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="a3910-138">小売業 - マネージャー コラボレーション</span><span class="sxs-lookup"><span data-stu-id="a3910-138">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="a3910-139">チャネル:</span><span class="sxs-lookup"><span data-stu-id="a3910-139">Channels:</span></span> <ul><li><span data-ttu-id="a3910-140">全般</span><span class="sxs-lookup"><span data-stu-id="a3910-140">General</span></span><li><span data-ttu-id="a3910-141">操作</span><span class="sxs-lookup"><span data-stu-id="a3910-141">Operations</span></span></li><li><span data-ttu-id="a3910-142">学習</span><span class="sxs-lookup"><span data-stu-id="a3910-142">Learning</span></span></li></ul> <span data-ttu-id="a3910-143">アプリ:</span><span class="sxs-lookup"><span data-stu-id="a3910-143">Apps:</span></span> <ul><li><span data-ttu-id="a3910-144">Wiki</span><span class="sxs-lookup"><span data-stu-id="a3910-144">Wiki</span></span></li></ul>|
||||

## <a name="use-the-teams-templates-with-the-microsoft-graph"></a><span data-ttu-id="a3910-145">Microsoft Graph で Teams テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="a3910-145">Use the Teams templates with the Microsoft Graph</span></span>

### <a name="store-template"></a><span data-ttu-id="a3910-146">店舗テンプレート</span><span class="sxs-lookup"><span data-stu-id="a3910-146">Store template</span></span>

<span data-ttu-id="a3910-147">店舗テンプレートは、個々の小売店の場所を表すチームを作成するのに最適です。</span><span class="sxs-lookup"><span data-stu-id="a3910-147">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="a3910-148">店舗テンプレートを使用して、組織内の小売店の場所ごとにチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a3910-148">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="a3910-149">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="a3910-149">Base template type</span></span> | <span data-ttu-id="a3910-150">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a3910-150">baseTemplateId</span></span> | <span data-ttu-id="a3910-151">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="a3910-151">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="a3910-152">小売業 -</span><span class="sxs-lookup"><span data-stu-id="a3910-152">Retail -</span></span> <br><span data-ttu-id="a3910-153">店舗</span><span class="sxs-lookup"><span data-stu-id="a3910-153">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="a3910-154">チャネル</span><span class="sxs-lookup"><span data-stu-id="a3910-154">Channels</span></span> <ul><li><span data-ttu-id="a3910-155">シフト ハンドオフ\*</span><span class="sxs-lookup"><span data-stu-id="a3910-155">Shifts handoff\*</span></span></li><li><span data-ttu-id="a3910-156">学習\*</span><span class="sxs-lookup"><span data-stu-id="a3910-156">Learning\*</span></span></li></ul><span data-ttu-id="a3910-157">\*自動的にお気に入りに登録されたチャネル</span><span class="sxs-lookup"><span data-stu-id="a3910-157">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="a3910-158">チームのプロパティ</span><span class="sxs-lookup"><span data-stu-id="a3910-158">Team properties</span></span> <ul><li><span data-ttu-id="a3910-159">チームの可視性を公開に設定</span><span class="sxs-lookup"><span data-stu-id="a3910-159">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="a3910-160">メンバーのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="a3910-160">Member permissions</span></span> <ul><li><span data-ttu-id="a3910-161">チャネルを作成/更新/削除できません</span><span class="sxs-lookup"><span data-stu-id="a3910-161">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="a3910-162">アプリを追加/削除できません</span><span class="sxs-lookup"><span data-stu-id="a3910-162">Can't add/remove apps</span></span> </li><li><span data-ttu-id="a3910-163">タブを作成/更新/削除できません</span><span class="sxs-lookup"><span data-stu-id="a3910-163">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="a3910-164">コネクタを作成/更新/削除できません</span><span class="sxs-lookup"><span data-stu-id="a3910-164">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="a3910-165">組織の店舗テンプレートをカスタマイズするための推奨される方法:</span><span class="sxs-lookup"><span data-stu-id="a3910-165">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="a3910-166">組織の各店舗に部門がある場合は、部門ごとにチャネルを追加します。</span><span class="sxs-lookup"><span data-stu-id="a3910-166">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="a3910-167">チャネルを追加すると、部門内のコミュニケーションとコラボレーションが容易になります。</span><span class="sxs-lookup"><span data-stu-id="a3910-167">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="a3910-168">組織に内部 Web サイト (SharePoint サイトなど) がある場合は、それらを関連するチーム チャネルのタブとして固定することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="a3910-168">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="a3910-169">手順については、「[Teams テンプレートの使用を開始する](get-started-with-teams-templates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3910-169">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

### <a name="manager-collaboration-template"></a><span data-ttu-id="a3910-170">マネージャー コラボレーションのテンプレート</span><span class="sxs-lookup"><span data-stu-id="a3910-170">Manager Collaboration template</span></span>

<span data-ttu-id="a3910-171">マネージャー コラボレーションのテンプレートは、小売業者のニーズに合わせて設計されたもう 1 つの Teams テンプレートです。</span><span class="sxs-lookup"><span data-stu-id="a3910-171">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="a3910-172">マネージャー コラボレーションのテンプレートは、マネージャーのグループが店舗や地域間でコラボレーションするためのチームを作成する場合などに最適です。</span><span class="sxs-lookup"><span data-stu-id="a3910-172">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="a3910-173">たとえば、組織に地域別のグループがある場合、カリフォルニア地域のマネージャー コラボレーション チームを作成し、その地域のすべての店舗マネージャーと、その地域の地域マネージャーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a3910-173">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="a3910-174">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="a3910-174">Base template type</span></span> | <span data-ttu-id="a3910-175">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a3910-175">baseTemplateId</span></span> | <span data-ttu-id="a3910-176">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="a3910-176">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="a3910-177">小売業 -</span><span class="sxs-lookup"><span data-stu-id="a3910-177">Retail -</span></span> <br><span data-ttu-id="a3910-178">店舗</span><span class="sxs-lookup"><span data-stu-id="a3910-178">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="a3910-179">チャネル</span><span class="sxs-lookup"><span data-stu-id="a3910-179">Channels</span></span> <ul><li><span data-ttu-id="a3910-180">操作\*</span><span class="sxs-lookup"><span data-stu-id="a3910-180">Operations\*</span></span></li><li><span data-ttu-id="a3910-181">学習\*</span><span class="sxs-lookup"><span data-stu-id="a3910-181">Learning\*</span></span></li></ul><span data-ttu-id="a3910-182">\*自動的にお気に入りに登録されたチャネル</span><span class="sxs-lookup"><span data-stu-id="a3910-182">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="a3910-183">チームのプロパティ</span><span class="sxs-lookup"><span data-stu-id="a3910-183">Team properties</span></span> <ul><li><span data-ttu-id="a3910-184">チームの可視性を非公開に設定</span><span class="sxs-lookup"><span data-stu-id="a3910-184">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="a3910-185">メンバーのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="a3910-185">Member permissions</span></span> <ul><li><span data-ttu-id="a3910-186">チャネルを作成/更新/削除できます</span><span class="sxs-lookup"><span data-stu-id="a3910-186">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="a3910-187">アプリを追加/削除できます</span><span class="sxs-lookup"><span data-stu-id="a3910-187">Can add/remove apps</span></span> </li><li><span data-ttu-id="a3910-188">タブを作成/更新/削除できます</span><span class="sxs-lookup"><span data-stu-id="a3910-188">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="a3910-189">コネクタを作成/更新/削除できます</span><span class="sxs-lookup"><span data-stu-id="a3910-189">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="a3910-190">組織のマネージャー コラボレーションのテンプレートをカスタマイズするための推奨される方法:</span><span class="sxs-lookup"><span data-stu-id="a3910-190">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="a3910-191">組織に、SharePoint サイトなど、マネージャーに関連する内部 Web サイトがある場合は、それらを関連するチーム チャネルのタブとして固定することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="a3910-191">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="a3910-192">手順については、「[Microsoft Teams テンプレートのドキュメント](get-started-with-teams-templates.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a3910-192">You can take a look at the [Microsoft Teams Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="a3910-193">ファースト パーティ テンプレートの使い方</span><span class="sxs-lookup"><span data-stu-id="a3910-193">How to use first party templates</span></span>

<span data-ttu-id="a3910-194">これらのテンプレートを使用するには、要求本文の「template@odata.bind」プロパティを「standard」から上記の TemplateID に変更します。</span><span class="sxs-lookup"><span data-stu-id="a3910-194">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="a3910-195">Teams テンプレートを展開する方法の詳細については、「[Teams の作成](/graph/api/team-post?view=graph-rest-beta)方法に関する Microsoft Graph の記事」をご参照ください。</span><span class="sxs-lookup"><span data-stu-id="a3910-195">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="a3910-196">テンプレートのチャネルは自動的に [全般] タブに作成されます。</span><span class="sxs-lookup"><span data-stu-id="a3910-196">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="a3910-197">例: 店舗テンプレート拡張スクリプト</span><span class="sxs-lookup"><span data-stu-id="a3910-197">Example: Store template extension script</span></span>

``` PowerShell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('retailStore')",
  "DisplayName": "Contoso Store",
  "Description": "Team for all staff in Contoso Store",
  "Channels": [
    {
      "displayName": "Additional store channel",
      "IsFavoriteByDefault": false
    }
  ]
}
```
