---
title: Microsoft Teams でフィードバック ポリシーを管理する
author: cichur
ms.author: v-cichur
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
description: フィードバック ポリシーを使用して、組織内の Teams ユーザーが Teams に関するフィードバックを Microsoft に送信できるかどうかを制御する方法について説明します。
ms.openlocfilehash: e2415204650ce47f875e432f062fd4a5e0438cd6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804697"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="06d40-103">Microsoft Teams でフィードバック ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="06d40-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="06d40-104">組織内のユーザーは、Teams に関するフィードバックを Microsoft に送信できます。Teams デスクトップおよび Web クライアント内から直接、Microsoft の取り組みについてお知らせします。</span><span class="sxs-lookup"><span data-stu-id="06d40-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="06d40-105">Teams のエクスペリエンスは継続的に改善され、このフィードバックを使用して Teams の改善に努めしています。</span><span class="sxs-lookup"><span data-stu-id="06d40-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

> [!NOTE]
> <span data-ttu-id="06d40-106">フィードバック ポリシーは、GCC、GCC High、DOD 展開では利用できません。</span><span class="sxs-lookup"><span data-stu-id="06d40-106">Feedback policies aren't available in GCC, GCC High, or DOD deployments.</span></span>

<span data-ttu-id="06d40-107">**フィードバックを送信する機能**</span><span class="sxs-lookup"><span data-stu-id="06d40-107">**The Give feedback feature**</span></span>

<span data-ttu-id="06d40-108">ユーザーは、Teams でフィードバックを送信する方法にアクセスして、Teams に関するコメントや提案  >  **を** 送信できます。</span><span class="sxs-lookup"><span data-stu-id="06d40-108">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="06d40-109">フィードバックを送信したデータは、Microsoft 365 または Office 365 契約に基く "サポート データ" と見なされます。その他の方法で "顧客データ" または "個人データ" と見なされる情報を含む。</span><span class="sxs-lookup"><span data-stu-id="06d40-109">Data sent through **Give feedback** is considered as "Support Data" under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![Teams の [フィードバックの送信] オプションのスクリーンショット](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="06d40-111">**アンケート**</span><span class="sxs-lookup"><span data-stu-id="06d40-111">**Surveys**</span></span>

<span data-ttu-id="06d40-112">また、ユーザーは Teams でのエクスペリエンスを評価し、評価に関する詳細を送信できます。</span><span class="sxs-lookup"><span data-stu-id="06d40-112">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="06d40-113">このポップアップ アンケートは、Teams でユーザーに対してときおり表示されます。</span><span class="sxs-lookup"><span data-stu-id="06d40-113">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="06d40-114">ユーザーが [通知 **にフィードバックを** 送信する] をクリックすると、アンケートが表示され、完了します。</span><span class="sxs-lookup"><span data-stu-id="06d40-114">When a user clicks **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![Teams のアンケートの通知とフォームのスクリーンショット](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="06d40-116">ユーザーが Teams に関するフィードバックを Microsoft に送信できるかどうかを設定する</span><span class="sxs-lookup"><span data-stu-id="06d40-116">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="06d40-117">管理者は、組織内のユーザーがフィードバックを送信して Teams に関するフィードバックを Microsoftに送信できるかどうか、およびユーザーがアンケートを受け取ったかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="06d40-117">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="06d40-118">既定では、組織内のすべてのユーザーにグローバル (組織全体の既定) ポリシーが自動的に割り当て、ポリシーで [フィードバックの送信] 機能とアンケートが有効になります。</span><span class="sxs-lookup"><span data-stu-id="06d40-118">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="06d40-119">ただし、教師に対して機能が有効になり、学生に対して無効になっている Teams for Education は例外です。</span><span class="sxs-lookup"><span data-stu-id="06d40-119">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="06d40-120">グローバル ポリシーを編集するか、カスタム ポリシーを作成して割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="06d40-120">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="06d40-121">グローバル ポリシーを編集するか、カスタム ポリシーを割り当てると、変更が有効なまで数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="06d40-121">After you edit the global policy or assign a custom policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="06d40-122">たとえば、トレーニングの新入社員を除き、組織内のすべてのユーザーがフィードバックを送信し、アンケートを受け取る場合を許可するとします。</span><span class="sxs-lookup"><span data-stu-id="06d40-122">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="06d40-123">このシナリオでは、両方の機能をオフにし、新入社員に割り当てるカスタム ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="06d40-123">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="06d40-124">組織内の他のすべてのユーザーは、機能が有効になっているグローバル ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="06d40-124">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="06d40-125">PowerShell を使用してフィードバック ポリシーを管理します。</span><span class="sxs-lookup"><span data-stu-id="06d40-125">You manage feedback policies by using PowerShell.</span></span> <span data-ttu-id="06d40-126">カスタム ポリシーと **Grant-CsTeamsFeedbackPolicy** コマンドレットを作成して、セキュリティ グループや配布グループなどの 1 つ以上のユーザーまたはユーザー グループに割り当てるには **、New-CsTeamsFeedbackPolicy** コマンドレットを使用します。このコマンドレットを使用します。 *[](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*</span><span class="sxs-lookup"><span data-stu-id="06d40-126">Use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span>

<span data-ttu-id="06d40-127">機能をオフにし、有効にする場合は、次のパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="06d40-127">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="06d40-128">**フィードバックの送信**: ポリシーが割り当てられているユーザーがフィードバックを提供するために **、userInitiatedMode** パラメーターを有効に設定します。</span><span class="sxs-lookup"><span data-stu-id="06d40-128">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="06d40-129">パラメーターを無効に **設定すると** 、機能が無効になり、ポリシーが割り当てられているユーザーにはフィードバックを送信するオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="06d40-129">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="06d40-130">**アンケート**: **receiveSurveysMode** パラメーターを有効に設定して、ポリシーが割り当てられているユーザーがアンケートを受け取るのを許可します。</span><span class="sxs-lookup"><span data-stu-id="06d40-130">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="06d40-131">ユーザーにアンケートを受け取ってオプトアウトを許可するには、パラメーターを **enabledUserOverride に設定します**。</span><span class="sxs-lookup"><span data-stu-id="06d40-131">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="06d40-132">Teams では、ユーザーは [**設定のプライバシー**] に移動し、アンケートに参加  >  するかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="06d40-132">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="06d40-133">パラメーターを無効に **設定すると** 、機能が無効になり、ポリシーが割り当てられているユーザーはアンケートを受け取らできなくなります。</span><span class="sxs-lookup"><span data-stu-id="06d40-133">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="06d40-134">カスタム フィードバック ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="06d40-134">Create a custom feedback policy</span></span>

<span data-ttu-id="06d40-135">この例では、新入社員フィードバック ポリシーと呼ばれるフィードバック ポリシーを作成し、フィードバックとアンケートを使用してフィードバックを送信する **機能をオフ** にします。</span><span class="sxs-lookup"><span data-stu-id="06d40-135">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a><span data-ttu-id="06d40-136">ユーザーにカスタム フィードバック ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="06d40-136">Assign a custom feedback policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="06d40-137">この例では、user1 という名前のユーザーに新入社員フィードバック ポリシーというカスタム ポリシーを割り当てします。</span><span class="sxs-lookup"><span data-stu-id="06d40-137">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a><span data-ttu-id="06d40-138">関連トピック</span><span class="sxs-lookup"><span data-stu-id="06d40-138">Related topics</span></span>

- [<span data-ttu-id="06d40-139">Teams PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="06d40-139">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="06d40-140"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="06d40-140">Assign policies to your users in Teams</span></span>](assign-policies.md)