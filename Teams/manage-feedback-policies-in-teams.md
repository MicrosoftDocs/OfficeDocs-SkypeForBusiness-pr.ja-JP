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
ms.openlocfilehash: b489e574a1d1c2a2b1ac5faf69626e997dbbfaa9
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938486"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="d19c5-103">Microsoft Teams でフィードバックポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="d19c5-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="d19c5-104">組織内のユーザーは、teams に関するフィードバックを Microsoft に送信することができます。これは、チームのデスクトップと web クライアントの中から直接行っていることです。</span><span class="sxs-lookup"><span data-stu-id="d19c5-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="d19c5-105">チームのエクスペリエンスを継続的に改善しており、このフィードバックを使用してチームの改善に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="d19c5-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

<span data-ttu-id="d19c5-106">**フィードバックの提供機能**</span><span class="sxs-lookup"><span data-stu-id="d19c5-106">**The Give feedback feature**</span></span>

<span data-ttu-id="d19c5-107">ユーザーは、チームでフィードバックを送信する**ために、** チームに関するコメントや提案をお送りし  >  **Give feedback**ます。</span><span class="sxs-lookup"><span data-stu-id="d19c5-107">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="d19c5-108">**フィードバック**を送信して送信されるデータは、Microsoft 365 または Office 365 契約の下では、"顧客データ" または "個人データ" と見なされる情報を含む "サポートデータ" と見なされます。</span><span class="sxs-lookup"><span data-stu-id="d19c5-108">Data sent through **Give feedback** is considered as "Support Data" under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![Teams の [フィードバックの提供] オプションのスクリーンショット](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="d19c5-110">**調査**</span><span class="sxs-lookup"><span data-stu-id="d19c5-110">**Surveys**</span></span>

<span data-ttu-id="d19c5-111">また、ユーザーはチームとのエクスペリエンスを評価し、その評価についての詳細を送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="d19c5-111">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="d19c5-112">このポップアップアンケートは、チームのユーザーに対して表示されます。</span><span class="sxs-lookup"><span data-stu-id="d19c5-112">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="d19c5-113">ユーザーが通知の [**フィードバック**の送信] をクリックすると、アンケートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d19c5-113">When a user clicks **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![Teams でのアンケート通知とフォームのスクリーンショット](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="d19c5-115">ユーザーがチームに関するフィードバックを Microsoft に送信できるようにするかどうかを設定する</span><span class="sxs-lookup"><span data-stu-id="d19c5-115">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="d19c5-116">管理者として、組織内のユーザーが**フィードバック**を送信し、アンケートを受けるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="d19c5-116">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="d19c5-117">既定では、組織内のすべてのユーザーにグローバル (組織全体の既定) ポリシーが自動的に割り当てられ、ポリシーで**フィードバックの提供**機能とアンケートが有効になります。</span><span class="sxs-lookup"><span data-stu-id="d19c5-117">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="d19c5-118">この例外は、学生に対して機能が有効になっており、学生に対して無効になっている、教育機関向けの Teams です。</span><span class="sxs-lookup"><span data-stu-id="d19c5-118">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="d19c5-119">グローバル ポリシーを編集するか、カスタム ポリシーを作成して割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="d19c5-119">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="d19c5-120">グローバルポリシーを編集するか、カスタムポリシーを割り当てると、変更が有効になるまでに数時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="d19c5-120">After you edit the global policy or assign a custom policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="d19c5-121">たとえば、組織内のすべてのユーザーが**フィードバック**を送信してフィードバックを受け取り、トレーニングの新入団体以外のアンケートを受けることができるようにします。</span><span class="sxs-lookup"><span data-stu-id="d19c5-121">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="d19c5-122">このシナリオでは、ユーザー設定のポリシーを作成して、両方の機能を無効にし、新しい採用者に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d19c5-122">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="d19c5-123">組織内の他のすべてのユーザーは、この機能を有効にしたグローバルポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="d19c5-123">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="d19c5-124">フィードバックポリシーは、PowerShell を使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="d19c5-124">You manage feedback policies by using PowerShell.</span></span> <span data-ttu-id="d19c5-125">*[この](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)* コマンド**レットを使用して**、カスタムポリシーを作成します。これは、1人以上のユーザーまたはユーザーのグループ (セキュリティグループ、配布グループなど) に割り当てるために、ユーザー設定のポリシーと**Grant-csteamsフィードバックポリシー**コマンドレットを作成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="d19c5-125">Use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span>

<span data-ttu-id="d19c5-126">機能を無効にして有効にするには、次のパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="d19c5-126">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="d19c5-127">**フィードバック**を送信: ポリシーを割り当てられたユーザーがフィードバックを提供できるように、 **Userinitiatedmode**パラメーターを**enabled**に設定します。</span><span class="sxs-lookup"><span data-stu-id="d19c5-127">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="d19c5-128">パラメーターを [**無効**] に設定すると、この機能は無効になり、ポリシーを割り当てられたユーザーにはフィードバックを送信するオプションが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="d19c5-128">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="d19c5-129">**アンケート**: ポリシーを割り当てられたユーザーがアンケートを受けることができるように、 **receiveSurveysMode**パラメーターを**enabled**に設定します。</span><span class="sxs-lookup"><span data-stu-id="d19c5-129">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="d19c5-130">ユーザーにアンケートを受け取り、オプトインすることを許可するには、パラメーターを**Enableduseroverride**に設定します。</span><span class="sxs-lookup"><span data-stu-id="d19c5-130">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="d19c5-131">Teams では、ユーザーは [**設定**のプライバシー] に移動し  >  **Privacy**て、アンケートに参加するかどうかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="d19c5-131">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="d19c5-132">パラメーターを [**無効**] に設定すると、この機能は無効になり、ポリシーを割り当てられたユーザーはアンケートを受けることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="d19c5-132">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="d19c5-133">ユーザー設定のフィードバックポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="d19c5-133">Create a custom feedback policy</span></span>

<span data-ttu-id="d19c5-134">この例では、新入社員フィードバックポリシーというフィードバックポリシーを作成し **、フィードバックとアンケートを通じて**フィードバックを提供する機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d19c5-134">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a><span data-ttu-id="d19c5-135">ユーザーにカスタムフィードバックポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="d19c5-135">Assign a custom feedback policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="d19c5-136">この例では、新入社員フィードバックポリシーという名前のカスタムポリシーを user1 という名前のユーザーに割り当てています。</span><span class="sxs-lookup"><span data-stu-id="d19c5-136">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a><span data-ttu-id="d19c5-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="d19c5-137">Related topics</span></span>

- [<span data-ttu-id="d19c5-138">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="d19c5-138">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="d19c5-139">チームのユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="d19c5-139">Assign policies to your users in Teams</span></span>](assign-policies.md)