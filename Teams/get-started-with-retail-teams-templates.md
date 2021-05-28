---
title: リテールでのチーム テンプレートの使用
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
description: 定義済みの設定、チャネル、およびプレインストールされたアプリを提供することで、チーム テンプレートを使用して小売業者のニーズに合ったチーム構造を作成する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: edc3b646af4577199b13a5803837625b8a9ea354
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684555"
---
# <a name="create-a-team-using-retail-team-templates"></a><span data-ttu-id="98329-103">リテール チーム テンプレートを使用してチームを作成する</span><span class="sxs-lookup"><span data-stu-id="98329-103">Create a team using retail team templates</span></span>

<span data-ttu-id="98329-104">Microsoft チーム テンプレートを使用すると、設定、チャネル、およびプレインストールされたアプリの定義済みのテンプレートを提供することで、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="98329-104">Microsoft team templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="98329-105">チーム テンプレートには、小売業者のニーズを中心に設計されたチーム構造の事前構築された定義があります。</span><span class="sxs-lookup"><span data-stu-id="98329-105">Team templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="98329-106">チーム テンプレートを使用すると、小売業者にとってうまく機能するチームの種類をすばやく作成し、組織全体に展開できます。</span><span class="sxs-lookup"><span data-stu-id="98329-106">You can use team templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="98329-107">また、チーム テンプレートを拡張して、特定の組織のニーズに合わせて調整されたチームを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="98329-107">You can also extend the team templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="98329-108">この記事では、各チーム テンプレートを紹介し、その使い方をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="98329-108">In this article, we'll introduce each of the team templates and recommend how to use them.</span></span>

<span data-ttu-id="98329-109">この記事は、小売業の組織全体で複数のチームを計画、展開し、管理する責任があるユーザーに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="98329-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="98329-110">組織内に Teams サービスがすでに展開されています。</span><span class="sxs-lookup"><span data-stu-id="98329-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="98329-111">展開がまだの場合は、「[Microsoft Teams の展開方法](./deploy-overview.md)」をお読みになって展開を開始してください。</span><span class="sxs-lookup"><span data-stu-id="98329-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="98329-112">チーム テンプレート全般の詳細については、「チーム テンプレートの概要 [」を参照してください](get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="98329-112">To learn more about team templates in general, refer to [Get started with team templates](get-started-with-teams-templates.md).</span></span>

| <span data-ttu-id="98329-113">名前</span><span class="sxs-lookup"><span data-stu-id="98329-113">Who</span></span> | <span data-ttu-id="98329-114">使用する方法:</span><span class="sxs-lookup"><span data-stu-id="98329-114">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="98329-115">管理者と IT プロフェッショナル</span><span class="sxs-lookup"><span data-stu-id="98329-115">Admins and IT Professionals</span></span> | <span data-ttu-id="98329-116">[管理センター Teamsを使用して](#use-the-team-templates-in-the-teams-admin-center)、リテール チーム テンプレートに基づいてチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="98329-116">[Use the Teams admin center](#use-the-team-templates-in-the-teams-admin-center) to create teams based on the retail team templates.</span></span>|
| <span data-ttu-id="98329-117">開発者およびシステム インテグレーター</span><span class="sxs-lookup"><span data-stu-id="98329-117">Developers and systems integrators</span></span> | <span data-ttu-id="98329-118">[Microsoft Graphを使用](#use-the-team-templates-with-the-microsoft-graph)して、リテール チーム テンプレートに基づいてチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="98329-118">[Use the Microsoft Graph](#use-the-team-templates-with-the-microsoft-graph) to create teams based on the retail team templates.</span></span> |

## <a name="use-the-team-templates-in-the-teams-admin-center"></a><span data-ttu-id="98329-119">管理センターでチーム テンプレートTeams使用する</span><span class="sxs-lookup"><span data-stu-id="98329-119">Use the team templates in the Teams admin center</span></span>

### <a name="organize-a-store"></a><span data-ttu-id="98329-120">店舗を整理する</span><span class="sxs-lookup"><span data-stu-id="98329-120">Organize a store</span></span>

<span data-ttu-id="98329-121">小売業の従業員を 1 つのエクスペリエンスにまとめ、タスクの管理、ドキュメントの共有、およびお客様の問題の解決を行います。</span><span class="sxs-lookup"><span data-stu-id="98329-121">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="98329-122">追加のアプリケーションを統合して、シフトの開始と終了のプロセスを合理化します。</span><span class="sxs-lookup"><span data-stu-id="98329-122">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="98329-123">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="98329-123">Base template type</span></span> |<span data-ttu-id="98329-124">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="98329-124">baseTemplateId</span></span> | <span data-ttu-id="98329-125">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="98329-125">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="98329-126">店舗を整理する</span><span class="sxs-lookup"><span data-stu-id="98329-126">Organize a store</span></span>|`retailStore`|<span data-ttu-id="98329-127">チャネル:</span><span class="sxs-lookup"><span data-stu-id="98329-127">Channels:</span></span> <ul><li><span data-ttu-id="98329-128">全般</span><span class="sxs-lookup"><span data-stu-id="98329-128">General</span></span><li><span data-ttu-id="98329-129">シフトのハンドオフ</span><span class="sxs-lookup"><span data-stu-id="98329-129">Shift handoff</span></span></li><li><span data-ttu-id="98329-130">学習</span><span class="sxs-lookup"><span data-stu-id="98329-130">Learning</span></span></li></ul> <span data-ttu-id="98329-131">アプリ:</span><span class="sxs-lookup"><span data-stu-id="98329-131">Apps:</span></span> <ul><li><span data-ttu-id="98329-132">Wiki</span><span class="sxs-lookup"><span data-stu-id="98329-132">Wiki</span></span></li></ul>|
||||

### <a name="manager-collaboration"></a><span data-ttu-id="98329-133">マネージャー コラボレーション</span><span class="sxs-lookup"><span data-stu-id="98329-133">Manager Collaboration</span></span>

<span data-ttu-id="98329-134">マネージャー コラボレーション テンプレートは、複数のマネージャーが複数の店舗/地域間で共同作業を行うチームを作成する場合に最適です。たとえば、組織にリージョンがある場合は、カリフォルニア地域のマネージャー コラボレーション チームを作成し、その地域のすべてのストア マネージャーをその地域の地域マネージャーと共に含める場合があります。</span><span class="sxs-lookup"><span data-stu-id="98329-134">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, along with the regional manager for that region.</span></span>

| <span data-ttu-id="98329-135">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="98329-135">Base template type</span></span>| <span data-ttu-id="98329-136">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="98329-136">baseTemplateId</span></span> | <span data-ttu-id="98329-137">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="98329-137">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="98329-138">小売業 - マネージャー コラボレーション</span><span class="sxs-lookup"><span data-stu-id="98329-138">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="98329-139">チャネル:</span><span class="sxs-lookup"><span data-stu-id="98329-139">Channels:</span></span> <ul><li><span data-ttu-id="98329-140">全般</span><span class="sxs-lookup"><span data-stu-id="98329-140">General</span></span><li><span data-ttu-id="98329-141">操作</span><span class="sxs-lookup"><span data-stu-id="98329-141">Operations</span></span></li><li><span data-ttu-id="98329-142">学習</span><span class="sxs-lookup"><span data-stu-id="98329-142">Learning</span></span></li></ul> <span data-ttu-id="98329-143">アプリ:</span><span class="sxs-lookup"><span data-stu-id="98329-143">Apps:</span></span> <ul><li><span data-ttu-id="98329-144">Wiki</span><span class="sxs-lookup"><span data-stu-id="98329-144">Wiki</span></span></li></ul>|
||||

## <a name="use-the-team-templates-with-the-microsoft-graph"></a><span data-ttu-id="98329-145">Microsoft アカウントでチーム テンプレートを使用Graph</span><span class="sxs-lookup"><span data-stu-id="98329-145">Use the team templates with the Microsoft Graph</span></span>

### <a name="store-template"></a><span data-ttu-id="98329-146">店舗テンプレート</span><span class="sxs-lookup"><span data-stu-id="98329-146">Store template</span></span>

<span data-ttu-id="98329-147">店舗テンプレートは、個々の小売店の場所を表すチームを作成するのに最適です。</span><span class="sxs-lookup"><span data-stu-id="98329-147">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="98329-148">店舗テンプレートを使用して、組織内の小売店の場所ごとにチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="98329-148">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="98329-149">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="98329-149">Base template type</span></span> | <span data-ttu-id="98329-150">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="98329-150">baseTemplateId</span></span> | <span data-ttu-id="98329-151">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="98329-151">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="98329-152">小売業 -</span><span class="sxs-lookup"><span data-stu-id="98329-152">Retail -</span></span> <br><span data-ttu-id="98329-153">店舗</span><span class="sxs-lookup"><span data-stu-id="98329-153">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="98329-154">チャネル</span><span class="sxs-lookup"><span data-stu-id="98329-154">Channels</span></span> <ul><li><span data-ttu-id="98329-155">シフト ハンドオフ\*</span><span class="sxs-lookup"><span data-stu-id="98329-155">Shifts handoff\*</span></span></li><li><span data-ttu-id="98329-156">学習\*</span><span class="sxs-lookup"><span data-stu-id="98329-156">Learning\*</span></span></li></ul><span data-ttu-id="98329-157">\*自動的にお気に入りに登録されたチャネル</span><span class="sxs-lookup"><span data-stu-id="98329-157">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="98329-158">チームのプロパティ</span><span class="sxs-lookup"><span data-stu-id="98329-158">Team properties</span></span> <ul><li><span data-ttu-id="98329-159">チームの可視性を公開に設定</span><span class="sxs-lookup"><span data-stu-id="98329-159">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="98329-160">メンバーのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="98329-160">Member permissions</span></span> <ul><li><span data-ttu-id="98329-161">チャネルを作成/更新/削除できません</span><span class="sxs-lookup"><span data-stu-id="98329-161">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="98329-162">アプリを追加/削除できません</span><span class="sxs-lookup"><span data-stu-id="98329-162">Can't add/remove apps</span></span> </li><li><span data-ttu-id="98329-163">タブを作成/更新/削除できません</span><span class="sxs-lookup"><span data-stu-id="98329-163">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="98329-164">コネクタを作成/更新/削除できません</span><span class="sxs-lookup"><span data-stu-id="98329-164">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="98329-165">組織の店舗テンプレートをカスタマイズするための推奨される方法:</span><span class="sxs-lookup"><span data-stu-id="98329-165">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="98329-166">組織の各店舗に部門がある場合は、部門ごとにチャネルを追加します。</span><span class="sxs-lookup"><span data-stu-id="98329-166">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="98329-167">チャネルを追加すると、部門内のコミュニケーションとコラボレーションが容易になります。</span><span class="sxs-lookup"><span data-stu-id="98329-167">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="98329-168">組織に内部 Web サイト (SharePoint サイトなど) がある場合は、それらを関連するチーム チャネルのタブとして固定することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="98329-168">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="98329-169">手順については [、「チーム テンプレートの使用」](get-started-with-teams-templates.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98329-169">Refer to [Get started with team templates](get-started-with-teams-templates.md) for instructions.</span></span>

### <a name="manager-collaboration-template"></a><span data-ttu-id="98329-170">マネージャー コラボレーションのテンプレート</span><span class="sxs-lookup"><span data-stu-id="98329-170">Manager Collaboration template</span></span>

<span data-ttu-id="98329-171">マネージャー コラボレーション テンプレートは、小売業者のニーズを中心に設計されたチーム テンプレートの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="98329-171">The Manager Collaboration template is another one of the team templates designed around retailer needs.</span></span> <span data-ttu-id="98329-172">マネージャー コラボレーションのテンプレートは、マネージャーのグループが店舗や地域間でコラボレーションするためのチームを作成する場合などに最適です。</span><span class="sxs-lookup"><span data-stu-id="98329-172">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="98329-173">たとえば、組織に地域別のグループがある場合、カリフォルニア地域のマネージャー コラボレーション チームを作成し、その地域のすべての店舗マネージャーと、その地域の地域マネージャーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="98329-173">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="98329-174">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="98329-174">Base template type</span></span> | <span data-ttu-id="98329-175">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="98329-175">baseTemplateId</span></span> | <span data-ttu-id="98329-176">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="98329-176">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="98329-177">小売業 -</span><span class="sxs-lookup"><span data-stu-id="98329-177">Retail -</span></span> <br><span data-ttu-id="98329-178">店舗</span><span class="sxs-lookup"><span data-stu-id="98329-178">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="98329-179">チャネル</span><span class="sxs-lookup"><span data-stu-id="98329-179">Channels</span></span> <ul><li><span data-ttu-id="98329-180">操作\*</span><span class="sxs-lookup"><span data-stu-id="98329-180">Operations\*</span></span></li><li><span data-ttu-id="98329-181">学習\*</span><span class="sxs-lookup"><span data-stu-id="98329-181">Learning\*</span></span></li></ul><span data-ttu-id="98329-182">\*自動的にお気に入りに登録されたチャネル</span><span class="sxs-lookup"><span data-stu-id="98329-182">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="98329-183">チームのプロパティ</span><span class="sxs-lookup"><span data-stu-id="98329-183">Team properties</span></span> <ul><li><span data-ttu-id="98329-184">チームの可視性を非公開に設定</span><span class="sxs-lookup"><span data-stu-id="98329-184">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="98329-185">メンバーのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="98329-185">Member permissions</span></span> <ul><li><span data-ttu-id="98329-186">チャネルを作成/更新/削除できます</span><span class="sxs-lookup"><span data-stu-id="98329-186">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="98329-187">アプリを追加/削除できます</span><span class="sxs-lookup"><span data-stu-id="98329-187">Can add/remove apps</span></span> </li><li><span data-ttu-id="98329-188">タブを作成/更新/削除できます</span><span class="sxs-lookup"><span data-stu-id="98329-188">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="98329-189">コネクタを作成/更新/削除できます</span><span class="sxs-lookup"><span data-stu-id="98329-189">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="98329-190">組織のマネージャー コラボレーションのテンプレートをカスタマイズするための推奨される方法:</span><span class="sxs-lookup"><span data-stu-id="98329-190">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="98329-191">組織に、SharePoint サイトなど、マネージャーに関連する内部 Web サイトがある場合は、それらを関連するチーム チャネルのタブとして固定することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="98329-191">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="98329-192">手順については、Microsoft チーム テンプレート [のドキュメント](get-started-with-teams-templates.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98329-192">You can take a look at the [Microsoft team Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="98329-193">ファースト パーティ テンプレートの使い方</span><span class="sxs-lookup"><span data-stu-id="98329-193">How to use first-party templates</span></span>

<span data-ttu-id="98329-194">これらのテンプレートを使用するには、要求本文の「template@odata.bind」プロパティを「standard」から上記の TemplateID に変更します。</span><span class="sxs-lookup"><span data-stu-id="98329-194">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="98329-195">チーム テンプレートをデプロイする方法の詳細については、チームの作成方法に関する Microsoft Graph記事[を参照してください](/graph/api/team-post?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="98329-195">For more information on how to deploy team templates, see the Microsoft Graph article on how to [create a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="98329-196">テンプレートのチャネルは自動的に [全般] タブに作成されます。</span><span class="sxs-lookup"><span data-stu-id="98329-196">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="98329-197">例: 店舗テンプレート拡張スクリプト</span><span class="sxs-lookup"><span data-stu-id="98329-197">Example: Store template extension script</span></span>

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
