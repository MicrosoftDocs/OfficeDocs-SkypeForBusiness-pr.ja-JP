---
title: 管理センターで Teams テンプレートを管理する
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: yinchang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 管理センターで Teams テンプレートを管理する方法について説明します。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: bcb99538ebd129e02e511c8260dc3bfa101bff9d
ms.sourcegitcommit: 113f587a1c09d42b7394ba1195c32cb054bdf31c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "50507970"
---
# <a name="create-and-manage-teams-templates-in-the-admin-center"></a><span data-ttu-id="c93a1-103">管理センターで Teams テンプレートを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="c93a1-103">Create and manage Teams templates in the admin center</span></span>

<span data-ttu-id="c93a1-104">エンド ユーザーに表示される Teams テンプレートを管理するには、管理センターでテンプレート ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c93a1-104">Manage the Teams templates that your end users see by creating templates policies in the admin center.</span></span> <span data-ttu-id="c93a1-105">各テンプレート ポリシー内で、表示または非表示のテンプレートを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c93a1-105">Within each template policy, you can designate which templates are shown or hidden.</span></span>
<span data-ttu-id="c93a1-106">ユーザーが指定した Teams テンプレートのサブセットのみを表示するために、異なるユーザーを異なるテンプレート ポリシーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="c93a1-106">Assign different users to different template policies so that your users only view the subset of Teams templates specified.</span></span>

## <a name="create-template-policies-and-assign-available-templates"></a><span data-ttu-id="c93a1-107">テンプレート ポリシーを作成し、使用可能なテンプレートを割り当てる</span><span class="sxs-lookup"><span data-stu-id="c93a1-107">Create template policies and assign available templates</span></span>

1. <span data-ttu-id="c93a1-108">Teams 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="c93a1-108">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="c93a1-109">**Teams テンプレート**  >  **ポリシーを展開します**。</span><span class="sxs-lookup"><span data-stu-id="c93a1-109">Expand **Teams** > **Templates policies**.</span></span>

3. <span data-ttu-id="c93a1-110">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c93a1-110">Select **Add**.</span></span>

    ![テンプレート ポリシーが選択され、[追加] が強調表示されている](media/template-policies-1.png)

1. <span data-ttu-id="c93a1-112">[テンプレート ポリシー **の設定] セクションで** 、次のフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="c93a1-112">In the **Templates Policies Settings** section, complete the following fields:</span></span>

    - <span data-ttu-id="c93a1-113">テンプレート ポリシー名</span><span class="sxs-lookup"><span data-stu-id="c93a1-113">Templates Policy name</span></span>

    - <span data-ttu-id="c93a1-114">テンプレート ポリシーの簡単な説明</span><span class="sxs-lookup"><span data-stu-id="c93a1-114">Templates Policy short description</span></span>

2. <span data-ttu-id="c93a1-115">[表示可能 **なテンプレート] テーブル** で、非表示にするテンプレートを選択し、[非表示] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="c93a1-115">In the **Viewable Templates** table, select the templates you want to hide and select **Hide**.</span></span>

    ![[非表示] が強調表示された選択したテンプレート](media/template-policies-2.png)

    <span data-ttu-id="c93a1-117">非表示に設定したテンプレートは、[非表示のテンプレート] テーブル **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="c93a1-117">You can see the templates you've selected to hide in the **Hidden Templates** table.</span></span>

1. <span data-ttu-id="c93a1-118">特定のテンプレートを再表示するには、[非表示のテンプレート] テーブル **までスクロール** します。</span><span class="sxs-lookup"><span data-stu-id="c93a1-118">To unhide certain templates, scroll to the **Hidden templates** table.</span></span>

1. <span data-ttu-id="c93a1-119">再表示するテンプレートを選択し、[表示] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="c93a1-119">Select the templates to unhide, and then select **Show**.</span></span>

   ![非表示ではない選択したテンプレート](media/template-policies-3.png)

   <span data-ttu-id="c93a1-121">選択したテンプレートが表示可能なテンプレート **テーブルに表示** されます。</span><span class="sxs-lookup"><span data-stu-id="c93a1-121">The selected templates will appear in your **Viewable templates** table.</span></span>
3. <span data-ttu-id="c93a1-122">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c93a1-122">Select **Save**.</span></span>

   <span data-ttu-id="c93a1-123">新しいテンプレート ポリシーが [テンプレート ポリシー **] リストに表示** されます。</span><span class="sxs-lookup"><span data-stu-id="c93a1-123">Your new template policy is displayed in the **Templates Policies** list.</span></span>

## <a name="assign-users-to-the-template-policies"></a><span data-ttu-id="c93a1-124">テンプレート ポリシーにユーザーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="c93a1-124">Assign users to the template policies</span></span>

<span data-ttu-id="c93a1-125">ポリシーに割り当てられたユーザーは、そのポリシー内で表示可能なテンプレートのみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c93a1-125">Users assigned to a policy will only be able to view the viewable templates within that policy.</span></span>

1. <span data-ttu-id="c93a1-126">テンプレート **ポリシーからポリシーを選択** し、[ユーザーの管理] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c93a1-126">From **Templates Policies**, select a policy, and then select **Manage users**.</span></span>

2. <span data-ttu-id="c93a1-127">このポリシーに割り当てるユーザーを入力します。</span><span class="sxs-lookup"><span data-stu-id="c93a1-127">Type the users to assign to this policy.</span></span>

   ![テンプレート ポリシーにユーザーを割り当てる](media/template-policies-4.png)

3. <span data-ttu-id="c93a1-129">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c93a1-129">Select **Apply**.</span></span>

> [!Note]
> <span data-ttu-id="c93a1-130">新しいポリシーがエンド ユーザーに有効になるには、最大で 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c93a1-130">It might take up to 24 hours for your new policy to take effect for end users.</span></span>

## <a name="size-limits-for-template-policies"></a><span data-ttu-id="c93a1-131">テンプレート ポリシーのサイズ制限</span><span class="sxs-lookup"><span data-stu-id="c93a1-131">Size limits for Template policies</span></span>

<span data-ttu-id="c93a1-132">ポリシーごとに最大 100 のテンプレートを非表示にできます。</span><span class="sxs-lookup"><span data-stu-id="c93a1-132">You can hide a max of 100 templates per policy.</span></span> <span data-ttu-id="c93a1-133">特定 **のポリシー** に既に 100 のテンプレートが非表示になっている場合、[非表示] ボタンは無効になります。</span><span class="sxs-lookup"><span data-stu-id="c93a1-133">The **Hide** button is disabled if the given policy already has 100 templates hidden.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="c93a1-134">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="c93a1-134">Frequently asked questions</span></span>

<span data-ttu-id="c93a1-135">**Q: チーム テンプレート ポリシーにユーザーをバッチ割り当てできますか?**</span><span class="sxs-lookup"><span data-stu-id="c93a1-135">**Q: Can I batch assign users to team templates policies?**</span></span>
  
<span data-ttu-id="c93a1-136">A: はい、PowerShell のテンプレート ポリシーのバッチ割り当てをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c93a1-136">A: Yes, we support batch assignment for template policy in PowerShell.</span></span> <span data-ttu-id="c93a1-137">このアクションのポリシーの種類は、TeamsTemplatePermissionPolicy です。</span><span class="sxs-lookup"><span data-stu-id="c93a1-137">The policy type for this action is TeamsTemplatePermissionPolicy.</span></span> [<span data-ttu-id="c93a1-138">詳細情報</span><span class="sxs-lookup"><span data-stu-id="c93a1-138">Learn more</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)

<span data-ttu-id="c93a1-139">**Q: グループはチーム テンプレート ポリシーに割り当てることができますか?**</span><span class="sxs-lookup"><span data-stu-id="c93a1-139">**Q: Can Groups be assigned to team templates policies?**</span></span>

<span data-ttu-id="c93a1-140">A: 現在いいえ。</span><span class="sxs-lookup"><span data-stu-id="c93a1-140">A: Currently no.</span></span> <span data-ttu-id="c93a1-141">この機能は、今後利用できる予定です。</span><span class="sxs-lookup"><span data-stu-id="c93a1-141">This functionality will be available in the future.</span></span>

<span data-ttu-id="c93a1-142">**Q: 新しいテンプレートを作成した場合、そのテンプレートはポリシーに含まれますか?**</span><span class="sxs-lookup"><span data-stu-id="c93a1-142">**Q: If a new template is created, will the template be included in my policies?**</span></span>

<span data-ttu-id="c93a1-143">A: 新しいテンプレートは既定で表示されます。</span><span class="sxs-lookup"><span data-stu-id="c93a1-143">A: Any new templates will be visible by default.</span></span> <span data-ttu-id="c93a1-144">管理センターの [テンプレート ポリシー] セクションでテンプレートを非表示にできます。</span><span class="sxs-lookup"><span data-stu-id="c93a1-144">You can choose to hide the template in the admin center in the Templates Policies section.</span></span>

<span data-ttu-id="c93a1-145">**Q: テンプレートが削除された場合は、どうなるでしょうか。**</span><span class="sxs-lookup"><span data-stu-id="c93a1-145">**Q: What happens if a template is deleted?**</span></span>

<span data-ttu-id="c93a1-146">A: 削除されたテンプレートは、テンプレート ポリシーに表示されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c93a1-146">A: Any deleted templates will no longer be present in any templates policies.</span></span>

<span data-ttu-id="c93a1-147">**Q: Teams 管理センターで複数のユーザーをテンプレート ポリシーに割り当てできますか?**</span><span class="sxs-lookup"><span data-stu-id="c93a1-147">**Q: Can I assign multiple users to a template policy in the Teams Admin Center?**</span></span>

<span data-ttu-id="c93a1-148">A: はい。</span><span class="sxs-lookup"><span data-stu-id="c93a1-148">A: Yes.</span></span>

1. <span data-ttu-id="c93a1-149">管理センターで、[ユーザー] に **移動します**。</span><span class="sxs-lookup"><span data-stu-id="c93a1-149">In the Admin center, go to **Users**.</span></span>
1. <span data-ttu-id="c93a1-150">[ユーザー] リスト テーブルで、特定のテンプレート ポリシーに割り当てるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c93a1-150">In the Users list table, select the users you want to assign to a certain templates policy.</span></span>
1. <span data-ttu-id="c93a1-151">[設定の編集] を選択し、[テンプレート ポリシー] フィールドを変更します。</span><span class="sxs-lookup"><span data-stu-id="c93a1-151">Select Edit settings, and change the Templates policies field.</span></span>
1. <span data-ttu-id="c93a1-152">[適用] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c93a1-152">Select apply.</span></span>
   <span data-ttu-id="c93a1-153">Microsoft [Teams のユーザーへのポリシーの割り当てについて詳しくは、Microsoft Teams の Microsoft Docs \| をご覧ください](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users)。</span><span class="sxs-lookup"><span data-stu-id="c93a1-153">Learn more [Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users).</span></span>

<span data-ttu-id="c93a1-154">**Q: 特定のポリシーに割り当てられているすべてのユーザーを表示する方法**</span><span class="sxs-lookup"><span data-stu-id="c93a1-154">**Q: How do I view all users assigned to a specific policy?**</span></span>

<span data-ttu-id="c93a1-155">A: 管理センターで、</span><span class="sxs-lookup"><span data-stu-id="c93a1-155">A: In the Admin center:</span></span>

1. <span data-ttu-id="c93a1-156">[ユーザー] セクション **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="c93a1-156">Go to the **Users** section.</span></span>
2. <span data-ttu-id="c93a1-157">[ユーザー] リスト テーブルでフィルターを選択し、チーム テンプレート ポリシーのフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="c93a1-157">Select the filter in the Users list table and filter for the teams template policy.</span></span>
3. <span data-ttu-id="c93a1-158">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c93a1-158">Select **Apply**.</span></span>

![選択したテンプレート ポリシーとユーザーの表示](media/template-policies-5.png)

<span data-ttu-id="c93a1-160">**Q: PowerShell でテンプレート ポリシーを管理できますか?**</span><span class="sxs-lookup"><span data-stu-id="c93a1-160">**Q: Can I manage templates policies via PowerShell?**</span></span>

<span data-ttu-id="c93a1-161">A: いいえ、PowerShell でのテンプレートの管理はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c93a1-161">A: No, managing templates in PowerShell isn't supported.</span></span>

<span data-ttu-id="c93a1-162">**Q: テンプレート ポリシーは EDU に適用されますか?**</span><span class="sxs-lookup"><span data-stu-id="c93a1-162">**Q: Are templates policies applicable to EDU?**</span></span>

<span data-ttu-id="c93a1-163">A: いいえ、EDU のテンプレート ポリシーはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c93a1-163">A: No, template policies for EDU isn't supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c93a1-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="c93a1-164">Related topics</span></span>

- [<span data-ttu-id="c93a1-165">管理センターでチーム テンプレートの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="c93a1-165">Get started with team templates in the admin center</span></span>](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-templates-in-the-admin-console)

- [<span data-ttu-id="c93a1-166">カスタム チーム テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="c93a1-166">Create a custom team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-a-team-template)

- [<span data-ttu-id="c93a1-167">既存のチームからテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="c93a1-167">Create a template from an existing team</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-team)

- [<span data-ttu-id="c93a1-168">既存のチーム テンプレートからチーム テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="c93a1-168">Create a team template from an existing team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-template)

- [<span data-ttu-id="c93a1-169">Microsoft Teams でユーザーにポリシーを割り当てる - Microsoft Teams \| Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="c93a1-169">Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs</span></span>](https://docs.microsoft.com/microsoftteams/assign-policies)

- [<span data-ttu-id="c93a1-170">ポリシーにユーザーをバッチ割り当てる</span><span class="sxs-lookup"><span data-stu-id="c93a1-170">Batch assign users to a policy</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)
