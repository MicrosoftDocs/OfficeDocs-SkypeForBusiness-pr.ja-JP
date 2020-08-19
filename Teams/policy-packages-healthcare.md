---
title: 医療用の Teams ポリシーパッケージ
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
description: 医療組織の Teams ポリシーパッケージを使用および管理する方法について説明します。
ms.openlocfilehash: dbbc0956f339760bedf1ce9cc2c5012cc317e152
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "46803975"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="68c8a-103">医療用の Teams ポリシーパッケージ</span><span class="sxs-lookup"><span data-stu-id="68c8a-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="68c8a-104">概要</span><span class="sxs-lookup"><span data-stu-id="68c8a-104">Overview</span></span>

<span data-ttu-id="68c8a-105">Microsoft Teams の [ポリシーパッケージ](manage-policy-packages.md) は、組織内で同様の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="68c8a-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="68c8a-106">ポリシー パッケージにより、ポリシー管理を簡素化し、合理化し、一貫性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="68c8a-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="68c8a-107">パッケージ内のポリシーの設定をカスタマイズして、ユーザーのニーズに合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="68c8a-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="68c8a-108">ポリシーパッケージのポリシーの設定を変更すると、そのパッケージに割り当てられているすべてのユーザーが更新された設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="68c8a-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="68c8a-109">ポリシーパッケージを管理するには、Microsoft Teams 管理センターまたは PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="68c8a-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="68c8a-110">ポリシーパッケージでは、パッケージに応じて、次のポリシーが事前に定義されています。</span><span class="sxs-lookup"><span data-stu-id="68c8a-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="68c8a-111">Messaging</span><span class="sxs-lookup"><span data-stu-id="68c8a-111">Messaging</span></span>
- <span data-ttu-id="68c8a-112">会議</span><span class="sxs-lookup"><span data-stu-id="68c8a-112">Meetings</span></span>
- <span data-ttu-id="68c8a-113">通話</span><span class="sxs-lookup"><span data-stu-id="68c8a-113">Calling</span></span>
- <span data-ttu-id="68c8a-114">アプリのセットアップ</span><span class="sxs-lookup"><span data-stu-id="68c8a-114">App setup</span></span>
- <span data-ttu-id="68c8a-115">ライブ イベント</span><span class="sxs-lookup"><span data-stu-id="68c8a-115">Live events</span></span>

<span data-ttu-id="68c8a-116">Teams には現在、以下の医療ポリシーパッケージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="68c8a-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="68c8a-117">Microsoft Teams 管理センターのパッケージ名</span><span class="sxs-lookup"><span data-stu-id="68c8a-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="68c8a-118">以下の目的での使用に最適です</span><span class="sxs-lookup"><span data-stu-id="68c8a-118">Best used for</span></span>|<span data-ttu-id="68c8a-119">説明</span><span class="sxs-lookup"><span data-stu-id="68c8a-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="68c8a-120">医療診療員</span><span class="sxs-lookup"><span data-stu-id="68c8a-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="68c8a-121">医療機関向けの臨床従業員</span><span class="sxs-lookup"><span data-stu-id="68c8a-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="68c8a-122">登録された看護師、料金の看護師、医師、ソーシャルワーカーなどの、チャット、通話、シフト管理、および会議へのフルアクセスを可能にする、一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="68c8a-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="68c8a-123">医療情報の作業者</span><span class="sxs-lookup"><span data-stu-id="68c8a-123">Healthcare information worker</span></span>  |<span data-ttu-id="68c8a-124">医療機関のインフォメーションワーカー</span><span class="sxs-lookup"><span data-stu-id="68c8a-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="68c8a-125">IT 担当者、informatics 職員、財務担当者、コンプライアンス責任者、チャット、通話、会議へのフルアクセスなどの情報を提供する一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="68c8a-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="68c8a-126">医療の治療室</span><span class="sxs-lookup"><span data-stu-id="68c8a-126">Healthcare patient room</span></span>  |<span data-ttu-id="68c8a-127">患者室のデバイス</span><span class="sxs-lookup"><span data-stu-id="68c8a-127">Patient room devices</span></span>|<span data-ttu-id="68c8a-128">医療機関の患者の会議室に適用される一連のポリシーとポリシー設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="68c8a-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![ヘルスケアポリシーパッケージのスクリーンショット](media/policy-packages-healthcare.png)

<span data-ttu-id="68c8a-130">個々のポリシーには、ポリシーパッケージの名前が割り当てられているため、ポリシーパッケージにリンクされているポリシーを簡単に識別することができます。</span><span class="sxs-lookup"><span data-stu-id="68c8a-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="68c8a-131">たとえば、医療臨床 worker ポリシーパッケージを組織内の clinicians に割り当てると、パッケージ内のポリシーごとに Healthcare_ClinicalWorker という名前のポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="68c8a-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![医療用臨床 worker パッケージのポリシーのスクリーンショット](media/policy-packages-healthcare-clinical-worker.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="68c8a-133">ポリシー パッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="68c8a-133">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="68c8a-134">表示</span><span class="sxs-lookup"><span data-stu-id="68c8a-134">View</span></span>

<span data-ttu-id="68c8a-135">パッケージを割り当てる前に、ポリシーパッケージの各ポリシーの設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="68c8a-135">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="68c8a-136">Microsoft Teams 管理センターの左のナビゲーションで、[ **ポリシーパッケージ**] を選択し、パッケージ名を選択して、ポリシー名を選びます。</span><span class="sxs-lookup"><span data-stu-id="68c8a-136">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="68c8a-137">定義済みの値が組織に適しているかどうかを判断します。または、組織のニーズに基づいて、ユーザー設定の値をカスタマイズする必要があるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="68c8a-137">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="68c8a-138">カスタマイズ</span><span class="sxs-lookup"><span data-stu-id="68c8a-138">Customize</span></span>

<span data-ttu-id="68c8a-139">組織のニーズに合わせて、ポリシーパッケージのポリシーの設定を必要に応じてカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="68c8a-139">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="68c8a-140">ポリシー設定に加えた変更は、パッケージを割り当てられたユーザーに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="68c8a-140">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="68c8a-141">ポリシーパッケージ内のポリシーの設定を編集するには、Microsoft Teams 管理センターでポリシーパッケージを選び、編集するポリシーの名前を選んで、[ **編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="68c8a-141">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="68c8a-142">ポリシーパッケージを割り当てると、パッケージのポリシーの設定を変更できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="68c8a-142">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="68c8a-143">詳細については、「 [ポリシーパッケージの](manage-policy-packages.md#customize-policies-in-a-policy-package)ポリシーをカスタマイズする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68c8a-143">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="68c8a-144">割り当てる</span><span class="sxs-lookup"><span data-stu-id="68c8a-144">Assign</span></span>

<span data-ttu-id="68c8a-145">ポリシーパッケージをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="68c8a-145">Assign the policy package to users.</span></span> <span data-ttu-id="68c8a-146">ポリシーパッケージを1人または複数のユーザーに割り当てるには、[ **ユーザーの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68c8a-146">To assign a policy package to one or multiple users, click **Manage users**.</span></span> <span data-ttu-id="68c8a-147">[PowerShell を使用](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation)して、ユーザーの大規模なバッチにポリシーパッケージを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="68c8a-147">You can also [use PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) to assign a policy package to large batches of users.</span></span> 

<span data-ttu-id="68c8a-148">Microsoft Teams 管理センターまたは PowerShell を使用してポリシーパッケージを割り当てる手順については、「 [ポリシーパッケージを割り当てる](manage-policy-packages.md#assign-a-policy-package)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="68c8a-148">For steps on how to assign a policy package using the Microsoft Teams admin center or PowerShell, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

![管理センターでポリシーパッケージを割り当てる方法のスクリーンショット](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="68c8a-150">ユーザーにポリシーが割り当てられていて、後で別のポリシーを割り当てると、最新の割り当てが優先されます。</span><span class="sxs-lookup"><span data-stu-id="68c8a-150">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

## <a name="related-topics"></a><span data-ttu-id="68c8a-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="68c8a-151">Related topics</span></span>

[<span data-ttu-id="68c8a-152">Teams でポリシー パッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="68c8a-152">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="68c8a-153">チームのユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="68c8a-153">Assign policies to your users in Teams</span></span>](assign-policies.md)
