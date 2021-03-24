---
title: Microsoft Teams で発信者番号ポリシーを管理する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams で発信者番号ポリシーを使用および管理して、組織内の Teams ユーザーの発信者番号を変更またはブロックする方法について説明します。
ms.openlocfilehash: cd15245523cdc3f5fb3625a2b4cfdae4deebb7d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102783"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="0540c-103">Microsoft Teams で発信者番号ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="0540c-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="0540c-104">管理者は、Microsoft Teams で発信者番号ポリシーを使用して、発信者番号 (発信回線 ID とも呼ばれます) を変更またはブロックできます。</span><span class="sxs-lookup"><span data-stu-id="0540c-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="0540c-105">既定では、Teams ユーザーが PSTN 電話に電話をかけると、Teams ユーザーの電話番号が表示され、PSTN 発信者が Teams ユーザーに電話をかけると、PSTN 発信者の電話番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0540c-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="0540c-106">発信者番号ポリシーを使用すると、組織内の Teams ユーザーの代替電話番号を表示したり、着信番号が表示されないようにブロックしたりできます。</span><span class="sxs-lookup"><span data-stu-id="0540c-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="0540c-107">たとえば、ユーザーが電話をかけるときに、ユーザーの電話番号の代わりに組織の代表電話番号が表示されるように発信者番号を変更できます。</span><span class="sxs-lookup"><span data-stu-id="0540c-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="0540c-108">発信者番号ポリシーを管理するには、Microsoft Teams 管理センターで **[音声]** > **[発信者番号ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="0540c-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="0540c-109">グローバル (組織全体の既定) ポリシーを使用ことも、カスタム ポリシーを作成して割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="0540c-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="0540c-110">カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0540c-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="0540c-111">カスタム発信者番号ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="0540c-111">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="0540c-112">Microsoft Teams 管理センターの左側のナビゲーションで、**[音声]** > **[発信者番号ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="0540c-112">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="0540c-113">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0540c-113">Click **Add**.</span></span> <br>
<span data-ttu-id="0540c-114">![管理センターの新しい [発信者番号ポリシー] ページのスクリーン ショット](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="0540c-114">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="0540c-115">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="0540c-115">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="0540c-116">ここで、希望する設定を選びます。</span><span class="sxs-lookup"><span data-stu-id="0540c-116">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="0540c-117">**[着信した発信者番号をブロックする]**: この設定をオンにすると、着信した通話の発信者番号が表示されないようにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="0540c-117">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="0540c-118">**[発信者番号ポリシーの上書き]**: この設定をオンにすると、ユーザーは自分の番号が受信者に表示されるかどうかに関するポリシーの設定を上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="0540c-118">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="0540c-119">つまり、発信者番号を表示するかどうかをユーザー自身が選択できます。</span><span class="sxs-lookup"><span data-stu-id="0540c-119">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="0540c-120">詳細については、「[発信者番号のエンド ユーザー制御](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0540c-120">For more information, see [End user control of outbound caller ID](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="0540c-121">**[発信者番号を置換する]**: 次のいずれかを選択して、ユーザーに対して表示される発信者番号を設定します。</span><span class="sxs-lookup"><span data-stu-id="0540c-121">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="0540c-122">**[ユーザーの番号]**: ユーザーの番号を表示します。</span><span class="sxs-lookup"><span data-stu-id="0540c-122">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="0540c-123">**[サービス番号]**: サービス電話番号が発信者番号として表示されるように設定できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0540c-123">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="0540c-124">**[匿名]**: 発信者番号が [匿名] として表示されます。</span><span class="sxs-lookup"><span data-stu-id="0540c-124">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="0540c-125">**[発信者番号をこのサービス番号に置換する]**: ユーザーの発信者番号の代わりに使用するサービス番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="0540c-125">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="0540c-126">このオプションは、**[発信者番号を置換する]** で **[サービス番号]** を選択した場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="0540c-126">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="0540c-127">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0540c-127">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="0540c-128">発信者番号ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="0540c-128">Edit a caller ID policy</span></span>

<span data-ttu-id="0540c-129">グローバル ポリシー、または作成したカスタム ポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="0540c-129">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="0540c-130">Microsoft Teams 管理センターの左側のナビゲーションで、**[音声]** > **[発信者番号ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="0540c-130">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="0540c-131">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0540c-131">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="0540c-132">目的に合わせて設定を変更したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0540c-132">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="0540c-133">カスタム発信者番号ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="0540c-133">Assign a custom caller ID policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="0540c-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="0540c-134">Related topics</span></span>

[<span data-ttu-id="0540c-135">New-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="0540c-135">New-CsCallingLineIdentity</span></span>](/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="0540c-136"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="0540c-136">Assign policies to your users in Teams</span></span>](assign-policies.md)