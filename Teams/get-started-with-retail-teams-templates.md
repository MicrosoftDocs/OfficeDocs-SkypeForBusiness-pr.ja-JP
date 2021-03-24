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
ms.openlocfilehash: e0fecf419f6fc3ac0ef15097fe54571d85018587
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101203"
---
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="503a1-103">小売業の Teams テンプレートの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="503a1-103">Get started with Teams templates in retail</span></span>

<span data-ttu-id="503a1-104">Teams テンプレートでは、設定、チャネル、事前にインストールされたアプリの定義済みテンプレートを使用することで、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="503a1-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="503a1-105">Teams テンプレートには、小売業者のニーズに基づいて設計されたチーム構造の定義が事前に作成されています。</span><span class="sxs-lookup"><span data-stu-id="503a1-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="503a1-106">Teams テンプレートを使用すると、小売業者にとって適切なチームの種類をすばやく作成し、組織全体に展開できます。</span><span class="sxs-lookup"><span data-stu-id="503a1-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="503a1-107">Teams テンプレートを拡張して、組織固有のニーズに合わせてチームを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="503a1-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="503a1-108">この記事では、各 Teams テンプレートを紹介し、それらの使用方法を推奨します。</span><span class="sxs-lookup"><span data-stu-id="503a1-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="503a1-109">この記事は、小売業の組織全体で複数のチームを計画、展開し、管理する責任があるユーザーに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="503a1-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="503a1-110">組織内に Teams サービスがすでに展開されています。</span><span class="sxs-lookup"><span data-stu-id="503a1-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="503a1-111">展開がまだの場合は、「[Microsoft Teams の展開方法](./deploy-overview.md)」をお読みになって展開を開始してください。</span><span class="sxs-lookup"><span data-stu-id="503a1-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="503a1-112">一般的なチーム テンプレートの詳細については、「[Teams テンプレートの使用を開始する](get-started-with-teams-templates.md)」をご参照ください。</span><span class="sxs-lookup"><span data-stu-id="503a1-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="503a1-113">店舗テンプレート</span><span class="sxs-lookup"><span data-stu-id="503a1-113">Store template</span></span>

<span data-ttu-id="503a1-114">店舗テンプレートは、個々の小売店の場所を表すチームを作成するのに最適です。</span><span class="sxs-lookup"><span data-stu-id="503a1-114">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="503a1-115">店舗テンプレートを使用して、組織内の小売店の場所ごとにチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="503a1-115">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="503a1-116">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="503a1-116">Base template type</span></span> | <span data-ttu-id="503a1-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="503a1-117">baseTemplateId</span></span> | <span data-ttu-id="503a1-118">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="503a1-118">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="503a1-119">小売業 -</span><span class="sxs-lookup"><span data-stu-id="503a1-119">Retail -</span></span> <br><span data-ttu-id="503a1-120">店舗</span><span class="sxs-lookup"><span data-stu-id="503a1-120">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="503a1-121">チャネル</span><span class="sxs-lookup"><span data-stu-id="503a1-121">Channels</span></span> <ul><li><span data-ttu-id="503a1-122">シフト ハンドオフ\*</span><span class="sxs-lookup"><span data-stu-id="503a1-122">Shifts handoff\*</span></span></li><li><span data-ttu-id="503a1-123">学習\*</span><span class="sxs-lookup"><span data-stu-id="503a1-123">Learning\*</span></span></li></ul><span data-ttu-id="503a1-124">\*自動的にお気に入りに登録されたチャネル</span><span class="sxs-lookup"><span data-stu-id="503a1-124">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="503a1-125">チームのプロパティ</span><span class="sxs-lookup"><span data-stu-id="503a1-125">Team properties</span></span> <ul><li><span data-ttu-id="503a1-126">チームの可視性を公開に設定</span><span class="sxs-lookup"><span data-stu-id="503a1-126">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="503a1-127">メンバーのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="503a1-127">Member permissions</span></span> <ul><li><span data-ttu-id="503a1-128">チャネルを作成/更新/削除できません</span><span class="sxs-lookup"><span data-stu-id="503a1-128">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="503a1-129">アプリを追加/削除できません</span><span class="sxs-lookup"><span data-stu-id="503a1-129">Can't add/remove apps</span></span> </li><li><span data-ttu-id="503a1-130">タブを作成/更新/削除できません</span><span class="sxs-lookup"><span data-stu-id="503a1-130">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="503a1-131">コネクタを作成/更新/削除できません</span><span class="sxs-lookup"><span data-stu-id="503a1-131">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="503a1-132">組織の店舗テンプレートをカスタマイズするための推奨される方法:</span><span class="sxs-lookup"><span data-stu-id="503a1-132">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="503a1-133">組織の各店舗に部門がある場合は、部門ごとにチャネルを追加します。</span><span class="sxs-lookup"><span data-stu-id="503a1-133">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="503a1-134">チャネルを追加すると、部門内のコミュニケーションとコラボレーションが容易になります。</span><span class="sxs-lookup"><span data-stu-id="503a1-134">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="503a1-135">組織に内部 Web サイト (SharePoint サイトなど) がある場合は、それらを関連するチーム チャネルのタブとして固定することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="503a1-135">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="503a1-136">手順については、「[Teams テンプレートの使用を開始する](get-started-with-teams-templates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="503a1-136">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="503a1-137">マネージャー コラボレーションのテンプレート</span><span class="sxs-lookup"><span data-stu-id="503a1-137">Manager Collaboration template</span></span>

<span data-ttu-id="503a1-138">マネージャー コラボレーションのテンプレートは、小売業者のニーズに合わせて設計されたもう 1 つの Teams テンプレートです。</span><span class="sxs-lookup"><span data-stu-id="503a1-138">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="503a1-139">マネージャー コラボレーションのテンプレートは、マネージャーのグループが店舗や地域間でコラボレーションするためのチームを作成する場合などに最適です。</span><span class="sxs-lookup"><span data-stu-id="503a1-139">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="503a1-140">たとえば、組織に地域別のグループがある場合、カリフォルニア地域のマネージャー コラボレーション チームを作成し、その地域のすべての店舗マネージャーと、その地域の地域マネージャーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="503a1-140">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="503a1-141">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="503a1-141">Base template type</span></span> | <span data-ttu-id="503a1-142">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="503a1-142">baseTemplateId</span></span> | <span data-ttu-id="503a1-143">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="503a1-143">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="503a1-144">小売業 -</span><span class="sxs-lookup"><span data-stu-id="503a1-144">Retail -</span></span> <br><span data-ttu-id="503a1-145">店舗</span><span class="sxs-lookup"><span data-stu-id="503a1-145">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="503a1-146">チャネル</span><span class="sxs-lookup"><span data-stu-id="503a1-146">Channels</span></span> <ul><li><span data-ttu-id="503a1-147">操作\*</span><span class="sxs-lookup"><span data-stu-id="503a1-147">Operations\*</span></span></li><li><span data-ttu-id="503a1-148">学習\*</span><span class="sxs-lookup"><span data-stu-id="503a1-148">Learning\*</span></span></li></ul><span data-ttu-id="503a1-149">\*自動的にお気に入りに登録されたチャネル</span><span class="sxs-lookup"><span data-stu-id="503a1-149">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="503a1-150">チームのプロパティ</span><span class="sxs-lookup"><span data-stu-id="503a1-150">Team properties</span></span> <ul><li><span data-ttu-id="503a1-151">チームの可視性を非公開に設定</span><span class="sxs-lookup"><span data-stu-id="503a1-151">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="503a1-152">メンバーのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="503a1-152">Member permissions</span></span> <ul><li><span data-ttu-id="503a1-153">チャネルを作成/更新/削除できます</span><span class="sxs-lookup"><span data-stu-id="503a1-153">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="503a1-154">アプリを追加/削除できます</span><span class="sxs-lookup"><span data-stu-id="503a1-154">Can add/remove apps</span></span> </li><li><span data-ttu-id="503a1-155">タブを作成/更新/削除できます</span><span class="sxs-lookup"><span data-stu-id="503a1-155">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="503a1-156">コネクタを作成/更新/削除できます</span><span class="sxs-lookup"><span data-stu-id="503a1-156">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="503a1-157">組織のマネージャー コラボレーションのテンプレートをカスタマイズするための推奨される方法:</span><span class="sxs-lookup"><span data-stu-id="503a1-157">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="503a1-158">組織に、SharePoint サイトなど、マネージャーに関連する内部 Web サイトがある場合は、それらを関連するチーム チャネルのタブとして固定することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="503a1-158">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="503a1-159">手順については、「[Microsoft Teams テンプレートのドキュメント](get-started-with-teams-templates.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="503a1-159">You can take a look at the [Microsoft Teams Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="503a1-160">ファースト パーティ テンプレートの使い方</span><span class="sxs-lookup"><span data-stu-id="503a1-160">How to use first party templates</span></span>

<span data-ttu-id="503a1-161">これらのテンプレートを使用するには、要求本文の「template@odata.bind」プロパティを「standard」から上記の TemplateID に変更します。</span><span class="sxs-lookup"><span data-stu-id="503a1-161">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="503a1-162">Teams テンプレートを展開する方法の詳細については、「[Teams の作成](/graph/api/team-post?view=graph-rest-beta)方法に関する Microsoft Graph の記事」をご参照ください。</span><span class="sxs-lookup"><span data-stu-id="503a1-162">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="503a1-163">テンプレートのチャネルは自動的に [全般] タブに作成されます。</span><span class="sxs-lookup"><span data-stu-id="503a1-163">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="503a1-164">例: 店舗テンプレート拡張スクリプト</span><span class="sxs-lookup"><span data-stu-id="503a1-164">Example: Store template extension script</span></span>

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
## <a name="relate-topic"></a><span data-ttu-id="503a1-165">関連トピック</span><span class="sxs-lookup"><span data-stu-id="503a1-165">Relate topic</span></span>

[<span data-ttu-id="503a1-166">管理センターで Teams テンプレートの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="503a1-166">Get started with Teams templates in the Admin center</span></span>](get-started-with-teams-templates-in-the-admin-console.md)