---
title: Microsoft Teams でフィードバック ポリシーを管理する
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: heprecel
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
description: 組織内の Teams ユーザーが Teams に関するフィードバックを Microsoft に送信できるかどうかを制御するフィードバック ポリシーの使用方法について説明します。
ms.openlocfilehash: 66f14467e66456f244664a8273e0ff962297c05f
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656723"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="f40a7-103">Microsoft Teams でフィードバック ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="f40a7-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="f40a7-104">組織内のユーザーは、Teams デスクトップおよび Web クライアントから直接、Teams に関するフィードバックを Microsoft に送信できます。</span><span class="sxs-lookup"><span data-stu-id="f40a7-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="f40a7-105">Microsoft は、Teams エクスペリエンスを継続的に向上しており、このフィードバックを使用して Teams を改善しています。</span><span class="sxs-lookup"><span data-stu-id="f40a7-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

> [!NOTE]
> <span data-ttu-id="f40a7-106">フィードバック ポリシーは、GCC、GCC High、DOD の展開では使用できません。</span><span class="sxs-lookup"><span data-stu-id="f40a7-106">Feedback policies aren't available in GCC, GCC High, or DOD deployments.</span></span>

<span data-ttu-id="f40a7-107">**[フィードバックの送信] 機能**</span><span class="sxs-lookup"><span data-stu-id="f40a7-107">**The Give feedback feature**</span></span>

<span data-ttu-id="f40a7-108">ユーザーは、Teams で **[ヘルプ]** > **[フィードバックの送信]** の順に移動し、Teams に関するコメントや提案を送信できます。</span><span class="sxs-lookup"><span data-stu-id="f40a7-108">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="f40a7-109">**[フィードバックの送信]** を通じて送信されたデータは、Microsoft 365 または Office 365 契約の「サポート データ」とみなされます。これには、「顧客データ」または「個人データ」と見なされる情報も含まれます。</span><span class="sxs-lookup"><span data-stu-id="f40a7-109">Data sent through **Give feedback** is considered as "Support Data" under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![Teams の [フィードバックの送信] のスクリーンショット](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="f40a7-111">**アンケート**</span><span class="sxs-lookup"><span data-stu-id="f40a7-111">**Surveys**</span></span>

<span data-ttu-id="f40a7-112">ユーザーはまた、Teams でのエクスペリエンスを評価し、評価に関する詳細を送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="f40a7-112">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="f40a7-113">このポップアップ アンケートは、[Teams] に随時表示されます。</span><span class="sxs-lookup"><span data-stu-id="f40a7-113">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="f40a7-114">ユーザーが通知で **[フィードバックの** 提供] を選択すると、アンケートが表示され、完了します。</span><span class="sxs-lookup"><span data-stu-id="f40a7-114">When a user selects **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![アンケートの通知とフォームのTeams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="f40a7-116">ユーザーが Teams に関するフィードバックを Microsoft に送信できるかどうかを設定する</span><span class="sxs-lookup"><span data-stu-id="f40a7-116">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="f40a7-117">管理者は、組織内のユーザーが **[フィードバックの送信]** で Microsoft に Teams に関するフィードバックを送信できるかどうか、およびアンケートを受信できるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="f40a7-117">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="f40a7-118">既定では、組織内のすべてのユーザーにグローバル (組織全体の既定) ポリシーが自動的に割り当て、ポリシーで [フィードバックの提供] 機能とアンケートが有効になります。</span><span class="sxs-lookup"><span data-stu-id="f40a7-118">By default, all users in your organization are automatically assigned the global (Org-wide default) policy, and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="f40a7-119">例外は、Teams for Education で、この機能は教師に対しては有効になっていますが、生徒に対しては無効になっています。</span><span class="sxs-lookup"><span data-stu-id="f40a7-119">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="f40a7-120">グローバル ポリシーを編集するか、カスタム ポリシーを作成して割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="f40a7-120">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="f40a7-121">グローバル ポリシーを編集するか、カスタム ポリシーを割り当てた後、変更が反映されるまでに数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f40a7-121">After you edit the global policy or assign a custom policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="f40a7-122">たとえば、組織内のすべてのユーザーが **[フィードバックの送信]** でフィードバックを送信し、トレーニング中の新入社員を除いてアンケートを受信できるようにしたいとします。</span><span class="sxs-lookup"><span data-stu-id="f40a7-122">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="f40a7-123">このシナリオでは、両方の機能をオフにして新入社員に割り当てるカスタム ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f40a7-123">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="f40a7-124">組織内の他のすべてのユーザーは、機能をオンにした状態でグローバル ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="f40a7-124">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="f40a7-125">フィードバック ポリシーは、PowerShell を使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="f40a7-125">You manage feedback policies by using PowerShell.</span></span> <span data-ttu-id="f40a7-126">**New-CsTeamsFeedbackPolicy** コマンドレット (*[](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)* こちら) を使用して、カスタム ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f40a7-126">Use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy.</span></span> <span data-ttu-id="f40a7-127">セキュリティ グループや配布グループなど、1 つ以上のユーザーまたはユーザー グループに割り当てるには **、Grant-CsTeamsFeedbackPolicy** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f40a7-127">Use the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span> <span data-ttu-id="f40a7-128">**Set-CsTeamsFeedbackPolicy を使用して、特定** のフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="f40a7-128">Use **Set-CsTeamsFeedbackPolicy** to set specific flags.</span></span>

<span data-ttu-id="f40a7-129">機能をオフまたはオンにするには、次のパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="f40a7-129">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="f40a7-130">**フィードバックの送信**: **userInitiatedMode** パラメーターを **[有効]** に設定して、ポリシーが割り当てられているユーザーがフィードバックを送信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f40a7-130">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="f40a7-131">パラメーターを **[無効]** に設定すると、機能がオフになり、ポリシーが割り当てられているユーザーにはフィードバックを送信するオプションが表示されません。</span><span class="sxs-lookup"><span data-stu-id="f40a7-131">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="f40a7-132">**アンケート**: **receiveSurveysMode** パラメーターを **[有効]** に設定して、ポリシーが割り当てられているユーザーがアンケートを受信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f40a7-132">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="f40a7-133">ユーザーがアンケートを受信して受け取らないことができるようにするには、パラメーターを **enabledUserOverride** に設定します。</span><span class="sxs-lookup"><span data-stu-id="f40a7-133">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="f40a7-134">Teams では、**[設定]** > **[プライバシー]** の順に移動し、アンケートに参加するかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="f40a7-134">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="f40a7-135">パラメーターを **[無効]** に設定すると、機能がオフになり、ポリシーが割り当てられているユーザーはアンケートを受信できません。</span><span class="sxs-lookup"><span data-stu-id="f40a7-135">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>
 - <span data-ttu-id="f40a7-136">**Email**: **AllowEmailCollection フラグを使用して、** 電子メール フィールドを追加します。</span><span class="sxs-lookup"><span data-stu-id="f40a7-136">**Email**: Use the **AllowEmailCollection** flag to add an email field.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="f40a7-137">カスタム フィードバック ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="f40a7-137">Create a custom feedback policy</span></span>

<span data-ttu-id="f40a7-138">この例では、[新入社員向けフィードバック ポリシー] というフィードバック ポリシーを作成し、**[フィードバックの送信]** およびアンケートでフィードバックを送信する機能をオフにします。</span><span class="sxs-lookup"><span data-stu-id="f40a7-138">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a><span data-ttu-id="f40a7-139">ユーザーにカスタムのフィードバック ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="f40a7-139">Assign a custom feedback policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="f40a7-140">この例では、user1 という名前のユーザーに [新入社員向けフィードバック ポリシー] という名前のカスタム ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f40a7-140">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a><span data-ttu-id="f40a7-141">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f40a7-141">Related topics</span></span>

- [<span data-ttu-id="f40a7-142">Teams PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="f40a7-142">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="f40a7-143"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="f40a7-143">Assign policies to your users in Teams</span></span>](assign-policies.md)
