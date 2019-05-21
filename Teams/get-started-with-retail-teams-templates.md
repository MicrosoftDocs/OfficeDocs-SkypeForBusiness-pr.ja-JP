---
title: 小売業の Teams テンプレートの使用を開始する
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
description: チームテンプレートを使用して、小売業者のニーズに合わせて設計されたチーム構造を作成する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e463061dca0633480124bbe91fb2e8e6f9f926f6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245747"
---
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="a0384-103">小売業の Teams テンプレートの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="a0384-103">Get started with Teams templates in retail</span></span> 

<span data-ttu-id="a0384-104">Teams テンプレートを使用すると、設定、チャネル、プリインストールされているアプリに定義済みのテンプレートを提供して、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="a0384-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="a0384-105">Teams のテンプレートには、小売業者のニーズに合わせて設計されたチーム構造の事前定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a0384-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="a0384-106">Teams テンプレートを使用すると、小売業者に適したチームの種類をすばやく作成して、組織全体に展開することができます。</span><span class="sxs-lookup"><span data-stu-id="a0384-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="a0384-107">また、チームテンプレートを拡張して、特定の組織のニーズに合わせてカスタマイズされたチームを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="a0384-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="a0384-108">この記事では、各チームテンプレートを紹介し、その使用をお勧めする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0384-108">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="a0384-109">この記事は、小売組織全体で複数のチームの計画、展開、管理を担当している場合に使います。</span><span class="sxs-lookup"><span data-stu-id="a0384-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span>

<span data-ttu-id="a0384-110">チームテンプレートの詳細については、「[チームテンプレートの使用を開始](get-started-with-teams-templates.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0384-110">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="a0384-111">ストアテンプレート</span><span class="sxs-lookup"><span data-stu-id="a0384-111">Store template</span></span>

<span data-ttu-id="a0384-112">ストアテンプレートは、個々の小売店の場所を表すチームの作成に適しています。</span><span class="sxs-lookup"><span data-stu-id="a0384-112">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="a0384-113">ストアテンプレートを使用して、組織内の各小売店舗の場所に対してチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a0384-113">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="a0384-114">ベーステンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="a0384-114">Base template type</span></span> | <span data-ttu-id="a0384-115">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a0384-115">baseTemplateId</span></span> | <span data-ttu-id="a0384-116">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="a0384-116">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="a0384-117">向け</span><span class="sxs-lookup"><span data-stu-id="a0384-117">Retail -</span></span> <br><span data-ttu-id="a0384-118">ストア</span><span class="sxs-lookup"><span data-stu-id="a0384-118">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="a0384-119">チャネル</span><span class="sxs-lookup"><span data-stu-id="a0384-119">Channels</span></span> <ul><li><span data-ttu-id="a0384-120">シフトシフト\*</span><span class="sxs-lookup"><span data-stu-id="a0384-120">Shifts handoff\*</span></span></li><li><span data-ttu-id="a0384-121">意欲\*</span><span class="sxs-lookup"><span data-stu-id="a0384-121">Learning\*</span></span></li></ul><span data-ttu-id="a0384-122">\*自動お気に入りチャネル</span><span class="sxs-lookup"><span data-stu-id="a0384-122">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="a0384-123">チームのプロパティ</span><span class="sxs-lookup"><span data-stu-id="a0384-123">Team properties</span></span> <ul><li><span data-ttu-id="a0384-124">チームの表示がパブリックに設定</span><span class="sxs-lookup"><span data-stu-id="a0384-124">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="a0384-125">メンバーの権限</span><span class="sxs-lookup"><span data-stu-id="a0384-125">Member permissions</span></span> <ul><li><span data-ttu-id="a0384-126">チャンネルを作成、更新、削除できません</span><span class="sxs-lookup"><span data-stu-id="a0384-126">Cannot create/update/delete channels</span></span> </li><li><span data-ttu-id="a0384-127">アプリを追加または削除できません</span><span class="sxs-lookup"><span data-stu-id="a0384-127">Cannot add/remove apps</span></span> </li><li><span data-ttu-id="a0384-128">タブの作成、更新、削除ができない</span><span class="sxs-lookup"><span data-stu-id="a0384-128">Cannot create/update/remove tabs</span></span></li><li><span data-ttu-id="a0384-129">コネクタの作成、更新、削除ができない</span><span class="sxs-lookup"><span data-stu-id="a0384-129">Cannot create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="a0384-130">組織のストアテンプレートをカスタマイズするための推奨される方法:</span><span class="sxs-lookup"><span data-stu-id="a0384-130">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="a0384-131">組織が各ストア内に部署を持っている場合は、部門ごとにチャネルを追加します。</span><span class="sxs-lookup"><span data-stu-id="a0384-131">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="a0384-132">これにより、部門内でのコミュニケーションとコラボレーションが容易になります。</span><span class="sxs-lookup"><span data-stu-id="a0384-132">This will facilitate communication and collaboration within the department.</span></span>

- <span data-ttu-id="a0384-133">組織に内部の web サイトがある場合 (SharePoint サイトなど) は、関連するチームチャネルのタブとしてピン留めすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="a0384-133">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="a0384-134">手順については、「[チームテンプレートの使用を開始](get-started-with-teams-templates.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0384-134">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="a0384-135">Manager グループ作業テンプレート</span><span class="sxs-lookup"><span data-stu-id="a0384-135">Manager Collaboration template</span></span>

<span data-ttu-id="a0384-136">マネージャーコラボレーションテンプレートは、小売業者のニーズに合わせて設計された Teams テンプレートのもう1つです。</span><span class="sxs-lookup"><span data-stu-id="a0384-136">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="a0384-137">マネージャーコラボレーションテンプレートは、ストアや地域で共同作業するためのチームを作成するのに適しています。たとえば、組織に地域がある場合は、カリフォルニア地域のマネージャーコラボレーションチームを作成し、その地域のすべてのストアマネージャーとその地域の地域マネージャーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a0384-137">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="a0384-138">ベーステンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="a0384-138">Base template type</span></span> | <span data-ttu-id="a0384-139">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a0384-139">baseTemplateId</span></span> | <span data-ttu-id="a0384-140">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="a0384-140">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="a0384-141">向け</span><span class="sxs-lookup"><span data-stu-id="a0384-141">Retail -</span></span> <br><span data-ttu-id="a0384-142">ストア</span><span class="sxs-lookup"><span data-stu-id="a0384-142">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="a0384-143">チャネル</span><span class="sxs-lookup"><span data-stu-id="a0384-143">Channels</span></span> <ul><li><span data-ttu-id="a0384-144">操作\*</span><span class="sxs-lookup"><span data-stu-id="a0384-144">Operations\*</span></span></li><li><span data-ttu-id="a0384-145">意欲\*</span><span class="sxs-lookup"><span data-stu-id="a0384-145">Learning\*</span></span></li></ul><span data-ttu-id="a0384-146">\*自動お気に入りチャネル</span><span class="sxs-lookup"><span data-stu-id="a0384-146">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="a0384-147">チームのプロパティ</span><span class="sxs-lookup"><span data-stu-id="a0384-147">Team properties</span></span> <ul><li><span data-ttu-id="a0384-148">チームの表示はプライベートに設定</span><span class="sxs-lookup"><span data-stu-id="a0384-148">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="a0384-149">メンバーの権限</span><span class="sxs-lookup"><span data-stu-id="a0384-149">Member permissions</span></span> <ul><li><span data-ttu-id="a0384-150">チャンネルを作成、更新、削除できます</span><span class="sxs-lookup"><span data-stu-id="a0384-150">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="a0384-151">アプリを追加/削除できる</span><span class="sxs-lookup"><span data-stu-id="a0384-151">Can add/remove apps</span></span> </li><li><span data-ttu-id="a0384-152">タブを作成、更新、削除できます</span><span class="sxs-lookup"><span data-stu-id="a0384-152">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="a0384-153">コネクタを作成、更新、削除できます</span><span class="sxs-lookup"><span data-stu-id="a0384-153">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="a0384-154">組織のマネージャーコラボレーションテンプレートをカスタマイズするには、次の方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a0384-154">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="a0384-155">組織に、マネージャーに関連する内部の web サイト (SharePoint サイトなど) がある場合は、それらを関連チームチャネルのタブとして固定することを検討してください (手順について[は、こちら](get-started-with-teams-templates.md)のドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="a0384-155">If your organization has any internal websites (for example, a SharePoint site) that are relevant for managers, consider pinning them as tabs in a relevant team channel (refer to documentation [here](get-started-with-teams-templates.md) for instructions).</span></span>