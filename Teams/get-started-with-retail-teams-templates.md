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
description: チームテンプレートを使用して、定義済みの設定、チャネル、およびプレインストールされたアプリを提供することで、小売業者のニーズに合わせて設計されたチーム構造を作成する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 33be31797833152aea9dd477698be56884a5aa0b
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294633"
---
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="552a6-103">小売業の Teams テンプレートの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="552a6-103">Get started with Teams templates in retail</span></span>

<span data-ttu-id="552a6-104">Teams テンプレートを使用すると、設定、チャネル、プリインストールされているアプリに定義済みのテンプレートを提供して、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="552a6-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="552a6-105">Teams のテンプレートには、小売業者のニーズに合わせて設計されたチーム構造の事前定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="552a6-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="552a6-106">Teams テンプレートを使用すると、小売業者に適したチームの種類をすばやく作成して、組織全体に展開することができます。</span><span class="sxs-lookup"><span data-stu-id="552a6-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="552a6-107">また、チームテンプレートを拡張して、特定の組織のニーズに合わせてカスタマイズされたチームを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="552a6-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="552a6-108">この記事では、各チームテンプレートを紹介し、その使用方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="552a6-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="552a6-109">この記事は、小売組織全体で複数のチームの計画、展開、管理を担当している場合に使います。</span><span class="sxs-lookup"><span data-stu-id="552a6-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="552a6-110">組織に Teams サービスを既に展開している。</span><span class="sxs-lookup"><span data-stu-id="552a6-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="552a6-111">まだチームをロールアウトしていない場合は、「 [Microsoft teams をロールアウトする方法](How-to-roll-out-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="552a6-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="552a6-112">チームテンプレート全般の詳細については、「 [チームテンプレートの概要](get-started-with-teams-templates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="552a6-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="552a6-113">ストアテンプレート</span><span class="sxs-lookup"><span data-stu-id="552a6-113">Store template</span></span>

<span data-ttu-id="552a6-114">ストアテンプレートは、個々の小売店の場所を表すチームの作成に適しています。</span><span class="sxs-lookup"><span data-stu-id="552a6-114">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="552a6-115">ストアテンプレートを使用して、組織内の各小売店舗の場所に対してチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="552a6-115">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="552a6-116">ベーステンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="552a6-116">Base template type</span></span> | <span data-ttu-id="552a6-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="552a6-117">baseTemplateId</span></span> | <span data-ttu-id="552a6-118">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="552a6-118">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="552a6-119">向け</span><span class="sxs-lookup"><span data-stu-id="552a6-119">Retail -</span></span> <br><span data-ttu-id="552a6-120">ストア</span><span class="sxs-lookup"><span data-stu-id="552a6-120">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="552a6-121">チャネル</span><span class="sxs-lookup"><span data-stu-id="552a6-121">Channels</span></span> <ul><li><span data-ttu-id="552a6-122">シフトシフト\*</span><span class="sxs-lookup"><span data-stu-id="552a6-122">Shifts handoff\*</span></span></li><li><span data-ttu-id="552a6-123">意欲\*</span><span class="sxs-lookup"><span data-stu-id="552a6-123">Learning\*</span></span></li></ul><span data-ttu-id="552a6-124">\*自動お気に入りチャネル</span><span class="sxs-lookup"><span data-stu-id="552a6-124">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="552a6-125">チームのプロパティ</span><span class="sxs-lookup"><span data-stu-id="552a6-125">Team properties</span></span> <ul><li><span data-ttu-id="552a6-126">チームの表示がパブリックに設定</span><span class="sxs-lookup"><span data-stu-id="552a6-126">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="552a6-127">メンバーの権限</span><span class="sxs-lookup"><span data-stu-id="552a6-127">Member permissions</span></span> <ul><li><span data-ttu-id="552a6-128">チャンネルを作成、更新、削除できません</span><span class="sxs-lookup"><span data-stu-id="552a6-128">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="552a6-129">アプリを追加または削除できない</span><span class="sxs-lookup"><span data-stu-id="552a6-129">Can't add/remove apps</span></span> </li><li><span data-ttu-id="552a6-130">タブの作成、更新、削除ができない</span><span class="sxs-lookup"><span data-stu-id="552a6-130">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="552a6-131">コネクタの作成、更新、削除ができない</span><span class="sxs-lookup"><span data-stu-id="552a6-131">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="552a6-132">組織のストアテンプレートをカスタマイズするための推奨される方法:</span><span class="sxs-lookup"><span data-stu-id="552a6-132">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="552a6-133">組織が各ストア内に部署を持っている場合は、部門ごとにチャネルを追加します。</span><span class="sxs-lookup"><span data-stu-id="552a6-133">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="552a6-134">チャネルを追加すると、部門内での通信とコラボレーションが容易になります。</span><span class="sxs-lookup"><span data-stu-id="552a6-134">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="552a6-135">組織に内部の web サイトがある場合 (SharePoint サイトなど) は、関連するチームチャネルのタブとしてピン留めすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="552a6-135">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="552a6-136">手順については、「 [チームテンプレートの使用を開始](get-started-with-teams-templates.md) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="552a6-136">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="552a6-137">Manager グループ作業テンプレート</span><span class="sxs-lookup"><span data-stu-id="552a6-137">Manager Collaboration template</span></span>

<span data-ttu-id="552a6-138">マネージャーコラボレーションテンプレートは、小売業者のニーズに合わせて設計された Teams テンプレートのもう1つです。</span><span class="sxs-lookup"><span data-stu-id="552a6-138">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="552a6-139">マネージャーグループ作業テンプレートは、ストアや地域などで共同作業するためのチームを作成するのに適しています。</span><span class="sxs-lookup"><span data-stu-id="552a6-139">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="552a6-140">たとえば、組織に地域がある場合は、カリフォルニア地域のマネージャーコラボレーションチームを作成し、その地域のすべてのストアマネージャーとその地域の地域マネージャーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="552a6-140">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="552a6-141">ベーステンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="552a6-141">Base template type</span></span> | <span data-ttu-id="552a6-142">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="552a6-142">baseTemplateId</span></span> | <span data-ttu-id="552a6-143">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="552a6-143">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="552a6-144">向け</span><span class="sxs-lookup"><span data-stu-id="552a6-144">Retail -</span></span> <br><span data-ttu-id="552a6-145">ストア</span><span class="sxs-lookup"><span data-stu-id="552a6-145">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="552a6-146">チャネル</span><span class="sxs-lookup"><span data-stu-id="552a6-146">Channels</span></span> <ul><li><span data-ttu-id="552a6-147">操作\*</span><span class="sxs-lookup"><span data-stu-id="552a6-147">Operations\*</span></span></li><li><span data-ttu-id="552a6-148">意欲\*</span><span class="sxs-lookup"><span data-stu-id="552a6-148">Learning\*</span></span></li></ul><span data-ttu-id="552a6-149">\*自動お気に入りチャネル</span><span class="sxs-lookup"><span data-stu-id="552a6-149">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="552a6-150">チームのプロパティ</span><span class="sxs-lookup"><span data-stu-id="552a6-150">Team properties</span></span> <ul><li><span data-ttu-id="552a6-151">チームの表示はプライベートに設定</span><span class="sxs-lookup"><span data-stu-id="552a6-151">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="552a6-152">メンバーの権限</span><span class="sxs-lookup"><span data-stu-id="552a6-152">Member permissions</span></span> <ul><li><span data-ttu-id="552a6-153">チャンネルを作成、更新、削除できます</span><span class="sxs-lookup"><span data-stu-id="552a6-153">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="552a6-154">アプリを追加/削除できる</span><span class="sxs-lookup"><span data-stu-id="552a6-154">Can add/remove apps</span></span> </li><li><span data-ttu-id="552a6-155">タブを作成、更新、削除できます</span><span class="sxs-lookup"><span data-stu-id="552a6-155">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="552a6-156">コネクタを作成、更新、削除できます</span><span class="sxs-lookup"><span data-stu-id="552a6-156">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="552a6-157">組織のマネージャーコラボレーションテンプレートをカスタマイズするには、次の方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="552a6-157">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="552a6-158">組織に SharePoint サイトなどの内部 web サイトがあり、マネージャーに関連している場合は、それらを関連チームチャネルのタブとしてピン留めすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="552a6-158">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="552a6-159">手順については、 [Microsoft Teams のテンプレート](get-started-with-teams-templates.md) に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="552a6-159">You can take a look at the [Microsoft Teams Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="552a6-160">ファーストパーティテンプレートの使用方法</span><span class="sxs-lookup"><span data-stu-id="552a6-160">How to use first party templates</span></span>

<span data-ttu-id="552a6-161">これらのテンプレートを使用するには、要求本文の ' template@odata ' プロパティを ' standard ' から TemplateIDs に変更します。</span><span class="sxs-lookup"><span data-stu-id="552a6-161">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="552a6-162">Teams テンプレートの展開方法の詳細については、Microsoft Graph の記事「 [チームを作成](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="552a6-162">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="552a6-163">テンプレートのチャネルは、[全般] タブに自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="552a6-163">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="552a6-164">例: ストアテンプレート拡張機能スクリプト</span><span class="sxs-lookup"><span data-stu-id="552a6-164">Example: Store template extension script</span></span>

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
## <a name="relate-topic"></a><span data-ttu-id="552a6-165">トピックの関連付け</span><span class="sxs-lookup"><span data-stu-id="552a6-165">Relate topic</span></span>

[<span data-ttu-id="552a6-166">管理コンソールで Teams のテンプレートを使ってみる</span><span class="sxs-lookup"><span data-stu-id="552a6-166">Get started with Teams templates in the Admin console</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
