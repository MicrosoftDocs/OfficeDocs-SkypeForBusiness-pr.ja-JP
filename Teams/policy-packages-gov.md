---
title: Government の Teams ポリシーパッケージ
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: 政府機関組織の Teams ポリシーパッケージを使用および管理する方法について説明します。
ms.openlocfilehash: 738197a82303c1149ebc89a8e3ad7c6b37df90eb
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804033"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="b42ad-103">Government の Teams ポリシーパッケージ</span><span class="sxs-lookup"><span data-stu-id="b42ad-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="b42ad-104">ポリシーパッケージは、現在、Microsoft 365 Government GCC 高または米国の展開では利用できません。</span><span class="sxs-lookup"><span data-stu-id="b42ad-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="b42ad-105">概要</span><span class="sxs-lookup"><span data-stu-id="b42ad-105">Overview</span></span>

<span data-ttu-id="b42ad-106">Microsoft Teams の [ポリシーパッケージ](manage-policy-packages.md) は、組織内で同様の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="b42ad-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="b42ad-107">ポリシー パッケージにより、ポリシー管理を簡素化し、合理化し、一貫性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="b42ad-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="b42ad-108">パッケージ内のポリシーの設定をカスタマイズして、ユーザーのニーズに合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="b42ad-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="b42ad-109">ポリシーパッケージのポリシーの設定を変更すると、そのパッケージに割り当てられているすべてのユーザーが更新された設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="b42ad-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="b42ad-110">ポリシーパッケージを管理するには、Microsoft Teams 管理センターまたは PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="b42ad-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="b42ad-111">ポリシーパッケージでは、パッケージに応じて、次のポリシーが事前に定義されています。</span><span class="sxs-lookup"><span data-stu-id="b42ad-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="b42ad-112">Messaging</span><span class="sxs-lookup"><span data-stu-id="b42ad-112">Messaging</span></span>
- <span data-ttu-id="b42ad-113">会議</span><span class="sxs-lookup"><span data-stu-id="b42ad-113">Meetings</span></span>
- <span data-ttu-id="b42ad-114">通話</span><span class="sxs-lookup"><span data-stu-id="b42ad-114">Calling</span></span>
- <span data-ttu-id="b42ad-115">アプリのセットアップ</span><span class="sxs-lookup"><span data-stu-id="b42ad-115">App setup</span></span>
- <span data-ttu-id="b42ad-116">ライブ イベント</span><span class="sxs-lookup"><span data-stu-id="b42ad-116">Live events</span></span>

<span data-ttu-id="b42ad-117">現在、Teams には、政府向けの次のポリシーパッケージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b42ad-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="b42ad-118">Microsoft Teams 管理センターのパッケージ名</span><span class="sxs-lookup"><span data-stu-id="b42ad-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="b42ad-119">以下の目的での使用に最適です</span><span class="sxs-lookup"><span data-stu-id="b42ad-119">Best used for</span></span>|<span data-ttu-id="b42ad-120">説明</span><span class="sxs-lookup"><span data-stu-id="b42ad-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b42ad-121">公安責任者</span><span class="sxs-lookup"><span data-stu-id="b42ad-121">Public safety officer</span></span>  |<span data-ttu-id="b42ad-122">政府機関組織の公安責任者</span><span class="sxs-lookup"><span data-stu-id="b42ad-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="b42ad-123">組織の公衆安全責任者に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="b42ad-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="b42ad-124">Firstline manager</span><span class="sxs-lookup"><span data-stu-id="b42ad-124">Firstline manager</span></span>  |<span data-ttu-id="b42ad-125">政府機関組織の firstline Manager</span><span class="sxs-lookup"><span data-stu-id="b42ad-125">Firstline Managers in your government organization</span></span> |<span data-ttu-id="b42ad-126">一連のポリシーを作成し、組織の Firstline Manager にそれらの設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="b42ad-126">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span>|
|<span data-ttu-id="b42ad-127">Firstline worker</span><span class="sxs-lookup"><span data-stu-id="b42ad-127">Firstline worker</span></span>  |<span data-ttu-id="b42ad-128">政府機関組織の firstline 員</span><span class="sxs-lookup"><span data-stu-id="b42ad-128">Firstline Workers in your government organization</span></span> |<span data-ttu-id="b42ad-129">一連のポリシーを作成し、それらの設定を組織の Firstline Worker に適用します。</span><span class="sxs-lookup"><span data-stu-id="b42ad-129">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span>|

![ヘルスケアポリシーパッケージのスクリーンショット](media/policy-packages-gov.png)

<span data-ttu-id="b42ad-131">個々のポリシーには、ポリシーパッケージの名前が割り当てられているため、ポリシーパッケージにリンクされているポリシーを簡単に識別することができます。</span><span class="sxs-lookup"><span data-stu-id="b42ad-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="b42ad-132">たとえば、パブリックセーフティオフィサーポリシーパッケージを組織内のユーザーに割り当てると、PublicSafety_Officer という名前のポリシーがパッケージ内のポリシーごとに作成されます。</span><span class="sxs-lookup"><span data-stu-id="b42ad-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![医療用臨床 worker パッケージのポリシーのスクリーンショット](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="b42ad-134">ポリシー パッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="b42ad-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="b42ad-135">表示</span><span class="sxs-lookup"><span data-stu-id="b42ad-135">View</span></span>

<span data-ttu-id="b42ad-136">パッケージを割り当てる前に、ポリシーパッケージの各ポリシーの設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="b42ad-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="b42ad-137">Microsoft Teams 管理センターの左のナビゲーションで、[ **ポリシーパッケージ**] を選択し、パッケージ名を選択して、ポリシー名を選びます。</span><span class="sxs-lookup"><span data-stu-id="b42ad-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="b42ad-138">定義済みの値が組織に適しているかどうかを判断します。または、組織のニーズに基づいて、ユーザー設定の値をカスタマイズする必要があるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="b42ad-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="b42ad-139">カスタマイズ</span><span class="sxs-lookup"><span data-stu-id="b42ad-139">Customize</span></span>

<span data-ttu-id="b42ad-140">組織のニーズに合わせて、ポリシーパッケージのポリシーの設定を必要に応じてカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="b42ad-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="b42ad-141">ポリシー設定に加えた変更は、パッケージを割り当てられたユーザーに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b42ad-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="b42ad-142">ポリシーパッケージ内のポリシーの設定を編集するには、Microsoft Teams 管理センターでポリシーパッケージを選び、編集するポリシーの名前を選んで、[ **編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b42ad-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="b42ad-143">ポリシーパッケージを割り当てると、パッケージのポリシーの設定を変更できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b42ad-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="b42ad-144">詳細については、「 [ポリシーパッケージの](manage-policy-packages.md#customize-policies-in-a-policy-package)ポリシーをカスタマイズする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b42ad-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="b42ad-145">割り当てる</span><span class="sxs-lookup"><span data-stu-id="b42ad-145">Assign</span></span>

<span data-ttu-id="b42ad-146">ポリシーパッケージをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b42ad-146">Assign the policy package to users.</span></span> <span data-ttu-id="b42ad-147">ポリシーパッケージを1人または複数のユーザーに割り当てるには、[ **ユーザーの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b42ad-147">To assign a policy package to one or multiple users, click **Manage users**.</span></span> <span data-ttu-id="b42ad-148">[PowerShell を使用](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation)して、ユーザーの大規模なバッチにポリシーパッケージを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="b42ad-148">You can also [use PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) to assign a policy package to large batches of users.</span></span> 

<span data-ttu-id="b42ad-149">Microsoft Teams 管理センターまたは PowerShell を使用してポリシーパッケージを割り当てる手順については、「 [ポリシーパッケージを割り当てる](manage-policy-packages.md#assign-a-policy-package)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b42ad-149">For steps on how to assign a policy package using the Microsoft Teams admin center or PowerShell, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

![管理センターでポリシーパッケージを割り当てる方法のスクリーンショット](media/policy-packages-gov-assign.png)

<span data-ttu-id="b42ad-151">ユーザーにポリシーが割り当てられていて、後で別のポリシーを割り当てると、最新の割り当てが優先されます。</span><span class="sxs-lookup"><span data-stu-id="b42ad-151">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b42ad-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="b42ad-152">Related topics</span></span>

[<span data-ttu-id="b42ad-153">Teams でポリシー パッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="b42ad-153">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="b42ad-154">チームのユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b42ad-154">Assign policies to your users in Teams</span></span>](assign-policies.md) 
