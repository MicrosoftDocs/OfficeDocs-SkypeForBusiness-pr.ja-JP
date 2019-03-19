---
title: 小売のチーム テンプレートを使い始める
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/11/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
localization_priority: Normal
search.appverid: MET150
description: 小売業者のニーズを満たすように設計チームの構造を作成するチーム テンプレートを使用する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e463061dca0633480124bbe91fb2e8e6f9f926f6
ms.sourcegitcommit: 8e62025d630c511ffb0361b9643d46c762188102
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "30664709"
---
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="b2577-103">小売のチーム テンプレートを使い始める</span><span class="sxs-lookup"><span data-stu-id="b2577-103">Get started with Teams templates in retail</span></span> 

<span data-ttu-id="b2577-104">チーム テンプレートでは、迅速にすることし、設定、チャネル、およびプリインストールされているアプリケーションの定義済みのテンプレートを提供することで簡単にチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2577-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="b2577-105">チーム テンプレートでは、小売業者のニーズに沿って設計されているチームの構造体の定義が作成済みがされます。</span><span class="sxs-lookup"><span data-stu-id="b2577-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="b2577-106">チーム テンプレートを使用すると、小売業者に対しても正常に機能し、組織全体に展開チームの種類を簡単に作成します。</span><span class="sxs-lookup"><span data-stu-id="b2577-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="b2577-107">組織のニーズに合わせたチームを作成するチーム テンプレートを拡張することもできます。</span><span class="sxs-lookup"><span data-stu-id="b2577-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="b2577-108">この資料では、チーム テンプレートとどのように使用をお勧めするを紹介します。</span><span class="sxs-lookup"><span data-stu-id="b2577-108">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="b2577-109">この資料は、計画、展開、および小売組織全体で複数のチームの管理を担当する場合のです。</span><span class="sxs-lookup"><span data-stu-id="b2577-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span>

<span data-ttu-id="b2577-110">チームの詳細についてテンプレート一般を参照してください[チーム テンプレートを使用して開始](get-started-with-teams-templates.md)します。</span><span class="sxs-lookup"><span data-stu-id="b2577-110">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="b2577-111">ストアのテンプレート</span><span class="sxs-lookup"><span data-stu-id="b2577-111">Store template</span></span>

<span data-ttu-id="b2577-112">ストアのテンプレートは、チームは、個々 の小売店舗の場所を表すための作成に最適です。</span><span class="sxs-lookup"><span data-stu-id="b2577-112">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="b2577-113">ストアのテンプレートを使用すると、組織内の小売店舗ごとのチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b2577-113">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="b2577-114">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="b2577-114">Base template type</span></span> | <span data-ttu-id="b2577-115">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="b2577-115">baseTemplateId</span></span> | <span data-ttu-id="b2577-116">この基本テンプレートに用意されているプロパティ</span><span class="sxs-lookup"><span data-stu-id="b2577-116">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="b2577-117">小売-</span><span class="sxs-lookup"><span data-stu-id="b2577-117">Retail -</span></span> <br><span data-ttu-id="b2577-118">ストア</span><span class="sxs-lookup"><span data-stu-id="b2577-118">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="b2577-119">チャネル</span><span class="sxs-lookup"><span data-stu-id="b2577-119">Channels</span></span> <ul><li><span data-ttu-id="b2577-120">ハンドオフにシフトします。\*</span><span class="sxs-lookup"><span data-stu-id="b2577-120">Shifts handoff\*</span></span></li><li><span data-ttu-id="b2577-121">学習\*</span><span class="sxs-lookup"><span data-stu-id="b2577-121">Learning\*</span></span></li></ul><span data-ttu-id="b2577-122">\*自動お気に入りチャンネル</span><span class="sxs-lookup"><span data-stu-id="b2577-122">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="b2577-123">チーム プロパティ</span><span class="sxs-lookup"><span data-stu-id="b2577-123">Team properties</span></span> <ul><li><span data-ttu-id="b2577-124">チームの可視性がパブリックに設定</span><span class="sxs-lookup"><span data-stu-id="b2577-124">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="b2577-125">メンバーのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="b2577-125">Member permissions</span></span> <ul><li><span data-ttu-id="b2577-126">チャネルの作成、更新または削除をことはできません。</span><span class="sxs-lookup"><span data-stu-id="b2577-126">Cannot create/update/delete channels</span></span> </li><li><span data-ttu-id="b2577-127">アプリケーションの追加と削除できません。</span><span class="sxs-lookup"><span data-stu-id="b2577-127">Cannot add/remove apps</span></span> </li><li><span data-ttu-id="b2577-128">作成/更新/削除タブをことはできません。</span><span class="sxs-lookup"><span data-stu-id="b2577-128">Cannot create/update/remove tabs</span></span></li><li><span data-ttu-id="b2577-129">コネクタの作成/更新/削除をことはできません。</span><span class="sxs-lookup"><span data-stu-id="b2577-129">Cannot create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="b2577-130">組織のストアのテンプレートをカスタマイズする方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b2577-130">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="b2577-131">組織部門各店舗内である場合は、各部門用のチャネルを追加します。</span><span class="sxs-lookup"><span data-stu-id="b2577-131">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="b2577-132">これは、部門のコミュニケーションやコラボレーションを容易になります。</span><span class="sxs-lookup"><span data-stu-id="b2577-132">This will facilitate communication and collaboration within the department.</span></span>

- <span data-ttu-id="b2577-133">組織が、内部の web サイト (SharePoint サイトなど) の場合は、チームの適切なチャネルでのタブとしてそれらの固定を検討してください。</span><span class="sxs-lookup"><span data-stu-id="b2577-133">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="b2577-134">手順については、[チーム テンプレートを使用](get-started-with-teams-templates.md)する参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2577-134">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="b2577-135">マネージャー コラボレーション テンプレート</span><span class="sxs-lookup"><span data-stu-id="b2577-135">Manager Collaboration template</span></span>

<span data-ttu-id="b2577-136">マネージャー コラボレーション テンプレートは、別販売店に沿って設計されているチーム テンプレートのいずれかが必要です。</span><span class="sxs-lookup"><span data-stu-id="b2577-136">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="b2577-137">マネージャーの共同作業のテンプレートは、一連の管理者は、複数の店舗や地域、その他のチームの作成に最適です。などの組織に領域がある場合は、カリフォルニア地域のマネージャーの共同作業チームを作成し、その地域の地域マネージャーと同様に、その領域内のすべてのストア マネージャーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b2577-137">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="b2577-138">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="b2577-138">Base template type</span></span> | <span data-ttu-id="b2577-139">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="b2577-139">baseTemplateId</span></span> | <span data-ttu-id="b2577-140">この基本テンプレートに用意されているプロパティ</span><span class="sxs-lookup"><span data-stu-id="b2577-140">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="b2577-141">小売-</span><span class="sxs-lookup"><span data-stu-id="b2577-141">Retail -</span></span> <br><span data-ttu-id="b2577-142">ストア</span><span class="sxs-lookup"><span data-stu-id="b2577-142">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="b2577-143">チャネル</span><span class="sxs-lookup"><span data-stu-id="b2577-143">Channels</span></span> <ul><li><span data-ttu-id="b2577-144">運用\*</span><span class="sxs-lookup"><span data-stu-id="b2577-144">Operations\*</span></span></li><li><span data-ttu-id="b2577-145">学習\*</span><span class="sxs-lookup"><span data-stu-id="b2577-145">Learning\*</span></span></li></ul><span data-ttu-id="b2577-146">\*自動お気に入りチャンネル</span><span class="sxs-lookup"><span data-stu-id="b2577-146">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="b2577-147">チーム プロパティ</span><span class="sxs-lookup"><span data-stu-id="b2577-147">Team properties</span></span> <ul><li><span data-ttu-id="b2577-148">チームの可視性が Private に設定</span><span class="sxs-lookup"><span data-stu-id="b2577-148">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="b2577-149">メンバーのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="b2577-149">Member permissions</span></span> <ul><li><span data-ttu-id="b2577-150">チャネルの作成、更新または削除ができます。</span><span class="sxs-lookup"><span data-stu-id="b2577-150">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="b2577-151">アプリケーションの追加と削除できます。</span><span class="sxs-lookup"><span data-stu-id="b2577-151">Can add/remove apps</span></span> </li><li><span data-ttu-id="b2577-152">作成/更新/削除タブをことができます。</span><span class="sxs-lookup"><span data-stu-id="b2577-152">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="b2577-153">コネクタの作成/更新/削除をことができます。</span><span class="sxs-lookup"><span data-stu-id="b2577-153">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="b2577-154">組織のマネージャーの共同作業のテンプレートをカスタマイズする方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b2577-154">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="b2577-155">組織の内部 web サイト (SharePoint サイトなど)、マネージャーに関連する場合、チームの適切なチャネルでのタブとしてそれらの固定を検討してください (のマニュアルを参照してください[ここでは](get-started-with-teams-templates.md))。</span><span class="sxs-lookup"><span data-stu-id="b2577-155">If your organization has any internal websites (for example, a SharePoint site) that are relevant for managers, consider pinning them as tabs in a relevant team channel (refer to documentation [here](get-started-with-teams-templates.md) for instructions).</span></span>