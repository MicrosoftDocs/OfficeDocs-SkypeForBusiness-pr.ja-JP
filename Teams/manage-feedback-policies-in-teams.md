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
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: フィードバックポリシーを使用して、組織内の Teams ユーザーがチームに関するフィードバックを Microsoft に送信できるかどうかを制御する方法について説明します。
ms.openlocfilehash: 70771f4a5e7c1376970ac3ac96cb9a4f822882a8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837547"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="9f259-103">Microsoft Teams でフィードバックポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="9f259-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="9f259-104">組織内のユーザーは、teams に関するフィードバックを Microsoft に送信することができます。これは、チームのデスクトップと web クライアントの中から直接行っていることです。</span><span class="sxs-lookup"><span data-stu-id="9f259-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="9f259-105">チームのエクスペリエンスを継続的に改善しており、このフィードバックを使用してチームの改善に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="9f259-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

<span data-ttu-id="9f259-106">**フィードバックの提供機能**</span><span class="sxs-lookup"><span data-stu-id="9f259-106">**The Give feedback feature**</span></span>

<span data-ttu-id="9f259-107">ユーザーは、チームで**フィードバック**を送信する**ために、** > チームに関するコメントや提案をお送りします。</span><span class="sxs-lookup"><span data-stu-id="9f259-107">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="9f259-108">**フィードバック**を送信して送信されるデータは、"顧客データ" または "個人データ" と見なされる情報など、Office 365 契約の下で "サポートデータ" と見なされます。</span><span class="sxs-lookup"><span data-stu-id="9f259-108">Data sent through **Give feedback** is considered as "Support Data" under your Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![Teams の [フィードバックの提供] オプションのスクリーンショット](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="9f259-110">**調査**</span><span class="sxs-lookup"><span data-stu-id="9f259-110">**Surveys**</span></span>

<span data-ttu-id="9f259-111">また、ユーザーはチームとのエクスペリエンスを評価し、その評価についての詳細を送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="9f259-111">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="9f259-112">このポップアップアンケートは、チームのユーザーに対して表示されます。</span><span class="sxs-lookup"><span data-stu-id="9f259-112">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="9f259-113">ユーザーが通知の [**フィードバック**の送信] をクリックすると、アンケートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9f259-113">When a user clicks **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![Teams でのアンケート通知とフォームのスクリーンショット](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="9f259-115">ユーザーがチームに関するフィードバックを Microsoft に送信できるようにするかどうかを設定する</span><span class="sxs-lookup"><span data-stu-id="9f259-115">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="9f259-116">管理者として、組織内のユーザーが**フィードバック**を送信し、アンケートを受けるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="9f259-116">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="9f259-117">既定では、組織内のすべてのユーザーにグローバル (組織全体の既定) ポリシーが自動的に割り当てられ、ポリシーで**フィードバックの提供**機能とアンケートが有効になります。</span><span class="sxs-lookup"><span data-stu-id="9f259-117">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="9f259-118">この例外は、学生に対して機能が有効になっており、学生に対して無効になっている、教育機関向けの Teams です。</span><span class="sxs-lookup"><span data-stu-id="9f259-118">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="9f259-119">グローバルポリシーを編集するか、カスタムポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="9f259-119">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="9f259-120">ユーザーにカスタムポリシーが割り当てられている場合は、そのポリシーがユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9f259-120">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="9f259-121">ユーザーにカスタムポリシーが割り当てられていない場合は、グローバルポリシーがユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9f259-121">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="9f259-122">グローバルポリシーを編集するか、ポリシーを割り当てると、変更が有効になるまで最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="9f259-122">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

<span data-ttu-id="9f259-123">たとえば、組織内のすべてのユーザーが**フィードバック**を送信してフィードバックを受け取り、トレーニングの新入団体以外のアンケートを受けることができるようにします。</span><span class="sxs-lookup"><span data-stu-id="9f259-123">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="9f259-124">このシナリオでは、ユーザー設定のポリシーを作成して、両方の機能を無効にし、新しい採用者に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="9f259-124">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="9f259-125">組織内の他のすべてのユーザーは、この機能を有効にしたグローバルポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="9f259-125">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="9f259-126">カスタムポリシーを作成するには、 *[次](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)* のコマンドレットを使用します。これは、カスタムポリシーを作成するために、1人以上のユーザーまたはユーザーのグループ (セキュリティグループ、配布グループなど) に割り当てるための、**許可-Csteamsフィードバックポリシー** **コマンドレットを**使用します。</span><span class="sxs-lookup"><span data-stu-id="9f259-126">You use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span>

<span data-ttu-id="9f259-127">機能を無効にして有効にするには、次のパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="9f259-127">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="9f259-128">**フィードバック**を送信: ポリシーを割り当てられたユーザーがフィードバックを提供できるように、 **Userinitiatedmode**パラメーターを**enabled**に設定します。</span><span class="sxs-lookup"><span data-stu-id="9f259-128">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="9f259-129">パラメーターを [**無効**] に設定すると、この機能は無効になり、ポリシーを割り当てられたユーザーにはフィードバックを送信するオプションが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="9f259-129">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="9f259-130">**アンケート**: ポリシーを割り当てられたユーザーがアンケートを受けることができるように、 **receiveSurveysMode**パラメーターを**enabled**に設定します。</span><span class="sxs-lookup"><span data-stu-id="9f259-130">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="9f259-131">ユーザーにアンケートを受け取り、オプトインすることを許可するには、パラメーターを**Enableduseroverride**に設定します。</span><span class="sxs-lookup"><span data-stu-id="9f259-131">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="9f259-132">Teams では、ユーザーは [**設定** > の**プライバシー** ] に移動して、アンケートに参加するかどうかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="9f259-132">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="9f259-133">パラメーターを [**無効**] に設定すると、この機能は無効になり、ポリシーを割り当てられたユーザーはアンケートを受けることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="9f259-133">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="9f259-134">ユーザー設定のフィードバックポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="9f259-134">Create a custom feedback policy</span></span>

<span data-ttu-id="9f259-135">この例では、新入社員フィードバックポリシーというフィードバックポリシーを作成し **、フィードバックとアンケートを通じて**フィードバックを提供する機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="9f259-135">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a><span data-ttu-id="9f259-136">ユーザー設定のフィードバックポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="9f259-136">Assign a custom feedback policy</span></span>

### <a name="assign-a-custom-feedback-policy-to-a-user"></a><span data-ttu-id="9f259-137">ユーザーにカスタムフィードバックポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="9f259-137">Assign a custom feedback policy to a user</span></span>

<span data-ttu-id="9f259-138">この例では、新入社員フィードバックポリシーという名前のカスタムポリシーを user1 という名前のユーザーに割り当てています。</span><span class="sxs-lookup"><span data-stu-id="9f259-138">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a><span data-ttu-id="9f259-139">ユーザー設定のフィードバックポリシーをグループ内のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="9f259-139">Assign a custom feedback policy to users in a group</span></span>

<span data-ttu-id="9f259-140">ユーザー設定のフィードバックポリシーは、既に指定されている複数のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="9f259-140">You may want to assign a custom feedback policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="9f259-141">たとえば、セキュリティグループ内のすべてのユーザーにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="9f259-141">For example, you may want to assign a policy to all users in a security group.</span></span>

<span data-ttu-id="9f259-142">この例では、新入社員フィードバックポリシーというカスタムフィードバックポリシーを、Contoso の新入社員グループのすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9f259-142">In this example, we assign a custom feedback policy called New Hire Feedback Policy to all users in the Contoso New Hires group.</span></span>  

<span data-ttu-id="9f259-143">特定のグループの GroupObjectId を取得します。</span><span class="sxs-lookup"><span data-stu-id="9f259-143">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
<span data-ttu-id="9f259-144">指定したグループのメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="9f259-144">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="9f259-145">グループ内のすべてのユーザーを特定のフィードバックポリシーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9f259-145">Assign all users in the group to a particular feedback policy.</span></span> <span data-ttu-id="9f259-146">この例では、新入社員フィードバックポリシーが追加されています。</span><span class="sxs-lookup"><span data-stu-id="9f259-146">In this example, it's New Hire Feedback Policy.</span></span>
```PowerShell
$members | ForEach-Object {Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="9f259-147">グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9f259-147">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9f259-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f259-148">Related topics</span></span>

- [<span data-ttu-id="9f259-149">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="9f259-149">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
