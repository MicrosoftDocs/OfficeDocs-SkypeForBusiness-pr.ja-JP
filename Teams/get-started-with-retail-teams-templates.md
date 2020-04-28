---
title: 小売業の Teams テンプレートの使用を開始する
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: 4477d42cf7036ac93d79684407ee97b7b9e9b900
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904662"
---
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="fa486-103">小売業の Teams テンプレートの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="fa486-103">Get started with Teams templates in retail</span></span> 

<span data-ttu-id="fa486-104">Teams テンプレートを使用すると、設定、チャネル、プリインストールされているアプリに定義済みのテンプレートを提供して、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="fa486-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="fa486-105">Teams のテンプレートには、小売業者のニーズに合わせて設計されたチーム構造の事前定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fa486-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="fa486-106">Teams テンプレートを使用すると、小売業者に適したチームの種類をすばやく作成して、組織全体に展開することができます。</span><span class="sxs-lookup"><span data-stu-id="fa486-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="fa486-107">また、チームテンプレートを拡張して、特定の組織のニーズに合わせてカスタマイズされたチームを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="fa486-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="fa486-108">この記事では、各チームテンプレートを紹介し、その使用をお勧めする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fa486-108">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="fa486-109">この記事は、小売組織全体で複数のチームの計画、展開、管理を担当している場合に使います。</span><span class="sxs-lookup"><span data-stu-id="fa486-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="fa486-110">組織に Teams サービスを既に展開していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="fa486-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="fa486-111">まだチームをロールアウトしていない場合は、「 [Microsoft teams をロールアウトする方法](How-to-roll-out-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa486-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="fa486-112">チームテンプレートの詳細については、「[チームテンプレートの使用を開始](get-started-with-teams-templates.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa486-112">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="fa486-113">ストアテンプレート</span><span class="sxs-lookup"><span data-stu-id="fa486-113">Store template</span></span>

<span data-ttu-id="fa486-114">ストアテンプレートは、個々の小売店の場所を表すチームの作成に適しています。</span><span class="sxs-lookup"><span data-stu-id="fa486-114">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="fa486-115">ストアテンプレートを使用して、組織内の各小売店舗の場所に対してチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="fa486-115">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="fa486-116">ベーステンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="fa486-116">Base template type</span></span> | <span data-ttu-id="fa486-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="fa486-117">baseTemplateId</span></span> | <span data-ttu-id="fa486-118">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="fa486-118">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="fa486-119">向け</span><span class="sxs-lookup"><span data-stu-id="fa486-119">Retail -</span></span> <br><span data-ttu-id="fa486-120">ストア</span><span class="sxs-lookup"><span data-stu-id="fa486-120">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="fa486-121">チャネル</span><span class="sxs-lookup"><span data-stu-id="fa486-121">Channels</span></span> <ul><li><span data-ttu-id="fa486-122">シフトシフト\*</span><span class="sxs-lookup"><span data-stu-id="fa486-122">Shifts handoff\*</span></span></li><li><span data-ttu-id="fa486-123">意欲\*</span><span class="sxs-lookup"><span data-stu-id="fa486-123">Learning\*</span></span></li></ul><span data-ttu-id="fa486-124">\*自動お気に入りチャネル</span><span class="sxs-lookup"><span data-stu-id="fa486-124">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="fa486-125">チームのプロパティ</span><span class="sxs-lookup"><span data-stu-id="fa486-125">Team properties</span></span> <ul><li><span data-ttu-id="fa486-126">チームの表示がパブリックに設定</span><span class="sxs-lookup"><span data-stu-id="fa486-126">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="fa486-127">メンバーの権限</span><span class="sxs-lookup"><span data-stu-id="fa486-127">Member permissions</span></span> <ul><li><span data-ttu-id="fa486-128">チャンネルを作成、更新、削除できません</span><span class="sxs-lookup"><span data-stu-id="fa486-128">Cannot create/update/delete channels</span></span> </li><li><span data-ttu-id="fa486-129">アプリを追加または削除できません</span><span class="sxs-lookup"><span data-stu-id="fa486-129">Cannot add/remove apps</span></span> </li><li><span data-ttu-id="fa486-130">タブの作成、更新、削除ができない</span><span class="sxs-lookup"><span data-stu-id="fa486-130">Cannot create/update/remove tabs</span></span></li><li><span data-ttu-id="fa486-131">コネクタの作成、更新、削除ができない</span><span class="sxs-lookup"><span data-stu-id="fa486-131">Cannot create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="fa486-132">組織のストアテンプレートをカスタマイズするための推奨される方法:</span><span class="sxs-lookup"><span data-stu-id="fa486-132">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="fa486-133">組織が各ストア内に部署を持っている場合は、部門ごとにチャネルを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa486-133">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="fa486-134">これにより、部門内でのコミュニケーションとコラボレーションが容易になります。</span><span class="sxs-lookup"><span data-stu-id="fa486-134">This will facilitate communication and collaboration within the department.</span></span>

- <span data-ttu-id="fa486-135">組織に内部の web サイトがある場合 (SharePoint サイトなど) は、関連するチームチャネルのタブとしてピン留めすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="fa486-135">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="fa486-136">手順については、「[チームテンプレートの使用を開始](get-started-with-teams-templates.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa486-136">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="fa486-137">Manager グループ作業テンプレート</span><span class="sxs-lookup"><span data-stu-id="fa486-137">Manager Collaboration template</span></span>

<span data-ttu-id="fa486-138">マネージャーコラボレーションテンプレートは、小売業者のニーズに合わせて設計された Teams テンプレートのもう1つです。</span><span class="sxs-lookup"><span data-stu-id="fa486-138">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="fa486-139">マネージャーコラボレーションテンプレートは、ストアや地域で共同作業するためのチームを作成するのに適しています。たとえば、組織に地域がある場合は、カリフォルニア地域のマネージャーコラボレーションチームを作成し、その地域のすべてのストアマネージャーとその地域の地域マネージャーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="fa486-139">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="fa486-140">ベーステンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="fa486-140">Base template type</span></span> | <span data-ttu-id="fa486-141">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="fa486-141">baseTemplateId</span></span> | <span data-ttu-id="fa486-142">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="fa486-142">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="fa486-143">向け</span><span class="sxs-lookup"><span data-stu-id="fa486-143">Retail -</span></span> <br><span data-ttu-id="fa486-144">ストア</span><span class="sxs-lookup"><span data-stu-id="fa486-144">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="fa486-145">チャネル</span><span class="sxs-lookup"><span data-stu-id="fa486-145">Channels</span></span> <ul><li><span data-ttu-id="fa486-146">操作\*</span><span class="sxs-lookup"><span data-stu-id="fa486-146">Operations\*</span></span></li><li><span data-ttu-id="fa486-147">意欲\*</span><span class="sxs-lookup"><span data-stu-id="fa486-147">Learning\*</span></span></li></ul><span data-ttu-id="fa486-148">\*自動お気に入りチャネル</span><span class="sxs-lookup"><span data-stu-id="fa486-148">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="fa486-149">チームのプロパティ</span><span class="sxs-lookup"><span data-stu-id="fa486-149">Team properties</span></span> <ul><li><span data-ttu-id="fa486-150">チームの表示はプライベートに設定</span><span class="sxs-lookup"><span data-stu-id="fa486-150">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="fa486-151">メンバーの権限</span><span class="sxs-lookup"><span data-stu-id="fa486-151">Member permissions</span></span> <ul><li><span data-ttu-id="fa486-152">チャンネルを作成、更新、削除できます</span><span class="sxs-lookup"><span data-stu-id="fa486-152">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="fa486-153">アプリを追加/削除できる</span><span class="sxs-lookup"><span data-stu-id="fa486-153">Can add/remove apps</span></span> </li><li><span data-ttu-id="fa486-154">タブを作成、更新、削除できます</span><span class="sxs-lookup"><span data-stu-id="fa486-154">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="fa486-155">コネクタを作成、更新、削除できます</span><span class="sxs-lookup"><span data-stu-id="fa486-155">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="fa486-156">組織のマネージャーコラボレーションテンプレートをカスタマイズするには、次の方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fa486-156">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="fa486-157">組織に、マネージャーに関連する内部 web サイト (SharePoint サイトなど) がある場合は、それらを関連チームチャネルのタブとして固定することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="fa486-157">If your organization has any internal websites (for example, a SharePoint site) that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="fa486-158">手順については、 [Microsoft Teams のテンプレート](get-started-with-teams-templates.md)に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa486-158">You can take a look at the [Microsoft Teams Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="fa486-159">ファーストパーティテンプレートの使用方法</span><span class="sxs-lookup"><span data-stu-id="fa486-159">How to use first party templates</span></span>

<span data-ttu-id="fa486-160">これらのテンプレートを使用するには、要求本文の ' template@odata ' プロパティを ' standard ' から TemplateIDs に変更します。</span><span class="sxs-lookup"><span data-stu-id="fa486-160">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="fa486-161">Teams テンプレートの展開方法の詳細については、Microsoft Graph の記事「[チームを作成](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa486-161">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="fa486-162">テンプレートのチャネルは、[全般] タブに自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="fa486-162">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="fa486-163">例: ストアテンプレート拡張機能スクリプト</span><span class="sxs-lookup"><span data-stu-id="fa486-163">Example: Store template extension script</span></span>

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
