---
title: Microsoft Teams でフィードバックポリシーを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: msedliak
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: フィードバックポリシーを使用して、組織内の Teams ユーザーがチームに関するフィードバックを Microsoft に送信できるかどうかを制御する方法について説明します。
ms.openlocfilehash: 3c9d05a3003906377447ee119b8cfc9bd137db81
ms.sourcegitcommit: f26bb86d38c3b45a82e6d77c5aa521360a81ee9b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2019
ms.locfileid: "35540954"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="26830-103">Microsoft Teams でフィードバックポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="26830-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="26830-104">ユーザーは、チームクライアントに\*\*\*\* > **フィードバック**を送信していただくことで、チームに関するコメントや提案を Microsoft に送信できます。</span><span class="sxs-lookup"><span data-stu-id="26830-104">Users can send comments and suggestions about Teams to Microsoft by going to **Help** > **Give feedback** in the Teams clients.</span></span> <span data-ttu-id="26830-105">チームのエクスペリエンスを継続的に改善しており、このフィードバックを使用してチームの改善に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="26830-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

![Teams の [フィードバックの提供] オプションのスクリーンショット](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="26830-107">**フィードバック**を送信して送信されるデータは、"顧客データ" または "個人データ" と見なされる情報など、Office 365 契約の下で "サポートデータ" と見なされます。</span><span class="sxs-lookup"><span data-stu-id="26830-107">Data sent through **Give feedback** is considered as "Support Data" under your Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="26830-108">ユーザーがチームに関するフィードバックを Microsoft に送信できるようにするかどうかを設定する</span><span class="sxs-lookup"><span data-stu-id="26830-108">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="26830-109">管理者は、組織内のユーザーがチームに関するフィードバックを Microsoft に送信できるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="26830-109">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft.</span></span> <span data-ttu-id="26830-110">既定では、組織内のすべてのユーザーにグローバル (組織全体の既定) ポリシーが自動的に割り当てられ、その機能はポリシーで有効になります。</span><span class="sxs-lookup"><span data-stu-id="26830-110">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the feature is enabled in the policy.</span></span> <span data-ttu-id="26830-111">例外とは、教育機関向けの Teams であり、学生のためにこの機能が有効になっており、無効になっています。</span><span class="sxs-lookup"><span data-stu-id="26830-111">The exception is Teams for Education, where the feature is enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="26830-112">グローバルポリシーを編集するか、カスタムポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="26830-112">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="26830-113">ユーザーにカスタムポリシーが割り当てられている場合は、そのポリシーがユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="26830-113">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="26830-114">ユーザーにカスタムポリシーが割り当てられていない場合は、グローバルポリシーがユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="26830-114">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="26830-115">グローバルポリシーを編集するか、ポリシーを割り当てると、変更が有効になるまで最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="26830-115">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

<span data-ttu-id="26830-116">たとえば、組織内のすべてのユーザーが、トレーニングの新入業者を除き、フィードバックを送信することを許可する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="26830-116">Say, for example, you want to allow all users in your organization to send feedback except for new hires in training.</span></span> <span data-ttu-id="26830-117">このシナリオでは、ユーザー設定のポリシーを作成して、この機能を無効にして新しい採用者に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="26830-117">In this scenario, you create a custom policy to turn off the feature and assign it to new hires.</span></span> <span data-ttu-id="26830-118">組織内の他のすべてのユーザーは、この機能が有効になっているグローバルポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="26830-118">All other users in your organization get the global policy with the feature turned on.</span></span>  

<span data-ttu-id="26830-119">**新しい-Csteamsbackpolicy**コマンドレットを使用して、カスタムポリシーを作成し、それを1人以上のユーザーまたはユーザーのグループ (セキュリティグループ、配布グループなど) に割り当てるために、**許可-Csteamsフィードバックポリシー**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="26830-119">You use the **New-CsTeamsFeedbackPolicy** cmdlet to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span> 

<span data-ttu-id="26830-120">ポリシーを割り当てられたユーザーがフィードバックを送信できるようにするには、 **Userinitiatedmode**パラメーターを**enabled**に設定します。</span><span class="sxs-lookup"><span data-stu-id="26830-120">Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="26830-121">パラメーターを [**無効**] に設定すると、この機能は無効になり、ポリシーを割り当てられたユーザーにはフィードバックを送信するオプションが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="26830-121">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="26830-122">ユーザー設定のフィードバックポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="26830-122">Create a custom feedback policy</span></span>

<span data-ttu-id="26830-123">この例では、新入社員フィードバックポリシーというフィードバックポリシーを作成し、フィードバックを提供する機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="26830-123">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback.</span></span>

```
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a><span data-ttu-id="26830-124">ユーザー設定のフィードバックポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="26830-124">Assign a custom feedback policy</span></span>

### <a name="assign-a-custom-feedback-policy-to-a-user"></a><span data-ttu-id="26830-125">ユーザーにカスタムフィードバックポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="26830-125">Assign a custom feedback policy to a user</span></span>

<span data-ttu-id="26830-126">この例では、新入社員フィードバックポリシーという名前のカスタムポリシーを user1 という名前のユーザーに割り当てています。</span><span class="sxs-lookup"><span data-stu-id="26830-126">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a><span data-ttu-id="26830-127">ユーザー設定のフィードバックポリシーをグループ内のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="26830-127">Assign a custom feedback policy to users in a group</span></span>

<span data-ttu-id="26830-128">ユーザー設定のフィードバックポリシーは、既に指定されている複数のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="26830-128">You may want to assign a custom feedback policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="26830-129">たとえば、セキュリティグループ内のすべてのユーザーにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="26830-129">For example, you may want to assign a policy to all users in a security group.</span></span>

<span data-ttu-id="26830-130">この例では、新入社員フィードバックポリシーというカスタムフィードバックポリシーを、Contoso の新入社員グループのすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="26830-130">In this example, we assign a custom feedback policy called New Hire Feedback Policy to all users in the Contoso New Hires group.</span></span>  

<span data-ttu-id="26830-131">特定のグループの GroupObjectId を取得します。</span><span class="sxs-lookup"><span data-stu-id="26830-131">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
<span data-ttu-id="26830-132">指定したグループのメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="26830-132">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="26830-133">グループ内のすべてのユーザーを特定のフィードバックポリシーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="26830-133">Assign all users in the group to a particular feedback policy.</span></span> <span data-ttu-id="26830-134">この例では、新入社員フィードバックポリシーが追加されています。</span><span class="sxs-lookup"><span data-stu-id="26830-134">In this example, it's New Hire Feedback Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="26830-135">グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="26830-135">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="26830-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="26830-136">Related topics</span></span>

- [<span data-ttu-id="26830-137">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="26830-137">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)