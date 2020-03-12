---
title: 学校の大規模なユーザーセットにポリシーを割り当てる
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: saragava,karsmith
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: バッチポリシーの割り当てを使用して、リモート学校 (teleschool、tele) の目的で、教育機関の多数のユーザーにポリシーを割り当てる方法について説明します。
f1keywords: ''
ms.openlocfilehash: 79c36aa0e2a7a2d310756d052b8962daeaa38634
ms.sourcegitcommit: a34a827dfdad05b281e2e5ec5a80fc4e67fc89e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604304"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="2c273-103">学校の大規模なユーザーセットにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="2c273-103">Assign policies to large sets of users in your school</span></span>

<span data-ttu-id="2c273-104">学生や教師が Microsoft Teams のさまざまな機能にアクセスできるようにする必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="2c273-104">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="2c273-105">ライセンスの種類によって組織内のユーザーをすばやく特定し、適切なポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2c273-105">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="2c273-106">このチュートリアルでは、[バッチポリシーの割り当て](assign-policies.md#assign-a-policy-to-a-batch-of-users)を使用して、会議ポリシーを一括してユーザーに割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c273-106">This tutorial shows you how to use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy to users in bulk.</span></span>

<span data-ttu-id="2c273-107">ユーザーは、カスタムポリシーを作成して割り当てることがない限り、チームポリシーの種類に対してグローバル (組織全体の既定の) ポリシーを自動的に取得することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2c273-107">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="2c273-108">学生の人口は、多くの場合、多くの場合、最も制限の厳しいユーザーであるため、次の手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2c273-108">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="2c273-109">グローバル (組織全体の既定) ポリシーを編集して適用し、学生の機能を制限します。</span><span class="sxs-lookup"><span data-stu-id="2c273-109">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span> 
- <span data-ttu-id="2c273-110">プライベートチャットや会議のスケジュールなどのコア機能を利用できるようにするカスタムポリシーを作成し、そのポリシーをスタッフや教師に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2c273-110">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>

<span data-ttu-id="2c273-111">グローバルポリシーは、ユーザー設定のポリシーを作成して、それをスタッフや教師に割り当てるまで、学校のすべてのユーザーに適用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2c273-111">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="2c273-112">このチュートリアルでは、学生がグローバル会議ポリシーを取得し、PowerShell を使用して、EducatorMeetingPolicy という名前のカスタム会議ポリシーを一括して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2c273-112">In this tutorial, students will get the Global meeting policy and we use PowerShell to assign a custom meeting policy named EducatorMeetingPolicy to staff and educators in bulk.</span></span> <span data-ttu-id="2c273-113">このグローバルポリシーを編集して学生の会議の設定を変更し、スタッフや教師の会議の動作を定義するカスタムポリシーを作成していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="2c273-113">We assume that you've edited the Global policy to tailor meeting settings for students and created a custom policy that defines the meeting experience for staff and educators.</span></span>

![Teams 管理センターの [会議のポリシー] ページのスクリーンショット](media/edu-batch-policy-assignment.png)

<span data-ttu-id="2c273-115">次の手順に従って、ユーザー設定の会議ポリシーをまとめて割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2c273-115">Follow these steps to assign a custom meeting policy to staff and educators in bulk.</span></span>

## <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="2c273-116">Azure AD PowerShell for Graph モジュールと Teams PowerShell モジュールに接続する</span><span class="sxs-lookup"><span data-stu-id="2c273-116">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="2c273-117">この記事の手順を実行する前に、Graph モジュール用の Azure AD PowerShell (割り当てられているライセンスによってユーザーを識別する) と Microsoft Teams PowerShell モジュール (これらのユーザーにポリシーを割り当てる) をインストールして接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c273-117">Before you perform the steps in this article, you'll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="2c273-118">Graph モジュール用 Azure AD PowerShell にインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="2c273-118">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="2c273-119">昇格された Windows PowerShell コマンドプロンプト (管理者として Windows PowerShell を実行) を開き、次のコマンドを実行して、Azure Active Directory PowerShell for Graph モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="2c273-119">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module -Name AzureAD
```

<span data-ttu-id="2c273-120">Azure AD に接続するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="2c273-120">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="2c273-121">メッセージが表示されたら、管理者の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="2c273-121">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="2c273-122">詳細については、「 [Graph の Azure Active Directory PowerShell で接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c273-122">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="2c273-123">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="2c273-123">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="2c273-124">[Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams)をインストールするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="2c273-124">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="2c273-125">バージョン1.0.5 以降をインストールしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2c273-125">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="2c273-126">Teams に接続してセッションを開始するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="2c273-126">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```
<span data-ttu-id="2c273-127">メッセージが表示されたら、Azure AD への接続に使用したのと同じ管理者資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="2c273-127">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

## <a name="identify-your-users"></a><span data-ttu-id="2c273-128">ユーザーを特定する</span><span class="sxs-lookup"><span data-stu-id="2c273-128">Identify your users</span></span>

<span data-ttu-id="2c273-129">最初に、次を実行して、ライセンスの種類別にスタッフと教師を特定します。</span><span class="sxs-lookup"><span data-stu-id="2c273-129">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="2c273-130">これは、組織で使用されている Sku を示します。</span><span class="sxs-lookup"><span data-stu-id="2c273-130">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="2c273-131">次に、教職員の SKU が割り当てられているスタッフと教師を特定することができます。</span><span class="sxs-lookup"><span data-stu-id="2c273-131">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureADSubscribedSku
```

```powershell
$skus = Get-AzureADSubscribedSku
```

<span data-ttu-id="2c273-132">戻り値:</span><span class="sxs-lookup"><span data-stu-id="2c273-132">Which returns:</span></span>

```
ObjectId                                                                  SkuPartNumber      SkuId
--------                                                                  -------------      -----
ee1a846c-79e9-4bc3-9189-011ca89be890_e97c048c-37a4-45fb-ab50-022fbf07a370 M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
ee1a846c-79e9-4bc3-9189-011ca89be890_46c119d4-0379-4a9d-85e4-97c66d3f909e M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="2c273-133">この例では、教職員ライセンスの SkuId が "e97c048c-37a4-45fb-ab50-922fbf07a370" であることが出力されます。</span><span class="sxs-lookup"><span data-stu-id="2c273-133">In this example, the output shows that the Faculty license SkuId is "e97c048c-37a4-45fb-ab50-922fbf07a370".</span></span>

> [!NOTE]
> <span data-ttu-id="2c273-134">教育機関の sku と SKU Id の一覧については、「[教育機関向けリファレンス](sku-reference-edu.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2c273-134">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="2c273-135">次に、このライセンスを所有しているユーザーを特定し、それらをすべてまとめて収集するために、次の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="2c273-135">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object (($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370")
```

## <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="2c273-136">ポリシーをまとめて割り当てる</span><span class="sxs-lookup"><span data-stu-id="2c273-136">Assign a policy in bulk</span></span>

<span data-ttu-id="2c273-137">次に、適切なポリシーをユーザーにまとめて割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2c273-137">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="2c273-138">ポリシーの割り当てまたは更新ができるユーザーの最大数は、一度に2万です。</span><span class="sxs-lookup"><span data-stu-id="2c273-138">The maximum number of users for which you can assign or update policies is 20,000 at a time.</span></span> <span data-ttu-id="2c273-139">たとえば、2万のスタッフと教師を超えている場合は、複数のバッチを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c273-139">For example, if you have more than 20,000 staff and educators, you'll need to submit multiple batches.</span></span>

<span data-ttu-id="2c273-140">次を実行して、EducatorMeetingPolicy という名前の会議ポリシーを、スタッフと教師に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2c273-140">Run the following to assign the meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="2c273-141">TeamsMessagingPolicy などの別のポリシータイプを一括で割り当てるには、割り当てるポリシーと```PolicyType``` ```PolicyName```ポリシー名に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c273-141">To assign a different policy type in bulk, like TeamsMessagingPolicy, you'll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

## <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="2c273-142">一括割り当ての状態を取得する</span><span class="sxs-lookup"><span data-stu-id="2c273-142">Get the status of a bulk assignment</span></span>

<span data-ttu-id="2c273-143">各一括割り当てでは、操作 ID が返されます。この ID を使用して、ポリシー割り当ての進捗状況を追跡したり、発生する可能性のあるエラーを特定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="2c273-143">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="2c273-144">たとえば、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="2c273-144">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="2c273-145">バッチ処理の各ユーザーの割り当て状態を表示するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="2c273-145">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="2c273-146">各ユーザーの詳細が```UserState```プロパティに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2c273-146">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

## <a name="assign-a-policy-in-bulk-if-you-have-more-than-20000-users"></a><span data-ttu-id="2c273-147">2万を超えるユーザーがいる場合にポリシーを一括で割り当てる</span><span class="sxs-lookup"><span data-stu-id="2c273-147">Assign a policy in bulk if you have more than 20,000 users</span></span>

<span data-ttu-id="2c273-148">まず、次の手順を実行して、所有しているスタッフと教師の数を確認します。</span><span class="sxs-lookup"><span data-stu-id="2c273-148">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="2c273-149">ユーザー Id のリスト全体を指定する代わりに、次のようにして最初の2万を指定し、その後に次の2万を実行します。</span><span class="sxs-lookup"><span data-stu-id="2c273-149">Instead of providing the whole list of user IDs, run the following to specify the first 20,000, and then the next 20,000, and so on.</span></span>

```powershell
Assign-CsPolicy -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identities $faculty[0..19999].ObjectId
```

<span data-ttu-id="2c273-150">ユーザー Id の範囲は、すべてのユーザーのリストに到達するまで変更できます。</span><span class="sxs-lookup"><span data-stu-id="2c273-150">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="2c273-151">たとえば、最初の```$faculty[0..19999```バッチに対しては enter ```$faculty[20000..39999``` 、2番目```$faculty[40000..59999```のバッチには、3番目のバッチに対してを使用します。</span><span class="sxs-lookup"><span data-stu-id="2c273-151">For example, enter ```$faculty[0..19999``` for the first batch, use ```$faculty[20000..39999``` for the second batch, enter ```$faculty[40000..59999``` for the third batch, and so on.</span></span>

## <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="2c273-152">ユーザーに割り当てられているポリシーを取得する</span><span class="sxs-lookup"><span data-stu-id="2c273-152">Get the policies assigned to a user</span></span>

<span data-ttu-id="2c273-153">特定のユーザーに割り当てられているすべてのポリシーを表示するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="2c273-153">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="2c273-154">次の例は、hannah@contoso.com に割り当てられているポリシーを取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2c273-154">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="2c273-155">FAQ</span><span class="sxs-lookup"><span data-stu-id="2c273-155">FAQ</span></span>

<span data-ttu-id="2c273-156">**学生、スタッフ、および教師であるすべてのユーザーが、自動的に割り当てられるライセンスを取得するようにします。どうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="2c273-156">**I want to make sure that all users that are students, staff, and educators automatically get licenses assigned. How can I do that?**</span></span>

<span data-ttu-id="2c273-157">Teams 製品チームは、セキュリティグループへのポリシーの割り当てをサポートする作業を行っています。</span><span class="sxs-lookup"><span data-stu-id="2c273-157">The Teams product team is doing work to support assigning policies to security groups.</span></span> <span data-ttu-id="2c273-158">この時点で、学生と教師のグループを作成し、そのグループに適切なポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="2c273-158">At that time, you'll be able to create groups for your students and teachers, and then the appropriate policies to those groups.</span></span> <span data-ttu-id="2c273-159">明示的なユーザーの割り当て (このチュートリアルで割り当てたポリシーなど) により、グループから継承されたポリシーが上書きされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2c273-159">Note that explicit user assignments (such as the policies that you've assigned using this tutorial) will override policies inherited from a group.</span></span> <span data-ttu-id="2c273-160">この機能がサポートされている場合は、ポリシーの割り当てをグループに使用する方法と、継承したグループポリシーを確実に取得できるようにユーザーを更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c273-160">When this feature is supported, we'll provide more instructions on how to use policy assignment to groups and update your users to ensure they get the inherited group policies.</span></span>

<span data-ttu-id="2c273-161">**私はチームの PowerShell については詳しくありません。詳細情報はどこで入手できますか?**</span><span class="sxs-lookup"><span data-stu-id="2c273-161">**I'm not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="2c273-162">「 [Teams Powershell の概要](teams-powershell-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2c273-162">See [Teams Powershell overview](teams-powershell-overview.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2c273-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c273-163">Related topics</span></span>

- [<span data-ttu-id="2c273-164">ユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="2c273-164">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="2c273-165">新規-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="2c273-165">New-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="2c273-166">Get-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="2c273-166">Get-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="2c273-167">CsUserPolicyAssignment を取得する</span><span class="sxs-lookup"><span data-stu-id="2c273-167">Get-CsUserPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)