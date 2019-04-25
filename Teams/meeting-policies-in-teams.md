---
title: 会議ポリシーを管理する
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.date: 04/18/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
f1keywords:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
description: Teams で会議のポリシー設定を管理する方法について説明します。
ms.openlocfilehash: 01d4ec8265c069d5fdbd6d8bb64ab89ec991956a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231815"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="1d605-103">Teams での会議ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="1d605-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="1d605-104">ミーティングのポリシーは、組織内のユーザーによってスケジュールされている会議の参加者をミーティングに使用可能な機能の制御に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1d605-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="1d605-105">ポリシーを作成し、変更を行い後、は、ポリシーに、ユーザーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1d605-105">After you create a policy and make your changes, you can then assign users to the policy.</span></span> 

<span data-ttu-id="1d605-106">既定では、グローバル (組織全体の既定値) をという名前のポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1d605-106">By default, a policy named Global (org-wide default) is created.</span></span> <span data-ttu-id="1d605-107">組織内のすべてのユーザー ポリシーが割り当てられますこの会議既定します。</span><span class="sxs-lookup"><span data-stu-id="1d605-107">All users in your organization will be assigned this meeting policy by default.</span></span> <span data-ttu-id="1d605-108">このポリシーに変更を加えるか、1 つまたは複数のカスタム ポリシーの作成にユーザーを割り当てるとします。</span><span class="sxs-lookup"><span data-stu-id="1d605-108">You can either make changes to this policy or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="1d605-109">カスタム ポリシーを作成するときを許可するまたはされない特定の機能、ユーザーが利用して、それらに適用する設定を持つ 1 つまたは複数のユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1d605-109">When you create a custom policy, you can allow or prevent certain features from being available to your users, and then assign it to one or more users who will have the settings applied to them.</span></span> 

## <a name="change-or-create-a-meeting-policy"></a><span data-ttu-id="1d605-110">変更するか、会議ポリシーを作成</span><span class="sxs-lookup"><span data-stu-id="1d605-110">Change or create a meeting policy</span></span>

<span data-ttu-id="1d605-111">**マイクロソフトのチーム管理センター**への移動を変更する会議ポリシーを作成、 > **会議** > **ミーティングのポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="1d605-111">To change or create a meeting policy, go to **Microsoft Teams admin center** > **Meetings** > **Meeting policies**.</span></span> <span data-ttu-id="1d605-112">リストからポリシーを選択するか、**新しいポリシー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d605-112">Select a policy from the list, or select **New policy**.</span></span> <span data-ttu-id="1d605-113">設定を選択し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d605-113">Choose your settings, and then select **Save**.</span></span>

<span data-ttu-id="1d605-114">たとえば、一連のユーザがあり、その会議を必要とする帯域幅の量を制限したいとします。</span><span class="sxs-lookup"><span data-stu-id="1d605-114">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="1d605-115">「帯域幅の制限」をという名前の新しいカスタム ポリシーを作成し、次の設定を無効にします。</span><span class="sxs-lookup"><span data-stu-id="1d605-115">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="1d605-116">[**ビデオのオーディオ &**。</span><span class="sxs-lookup"><span data-stu-id="1d605-116">Under **Audio & video**:</span></span>
- <span data-ttu-id="1d605-117">クラウドをオフに記録</span><span class="sxs-lookup"><span data-stu-id="1d605-117">Turn off cloud recording</span></span>
- <span data-ttu-id="1d605-118">ビデオを許可する IP をオフにします。</span><span class="sxs-lookup"><span data-stu-id="1d605-118">Turn off Allow IP video</span></span>

<span data-ttu-id="1d605-119">[**コンテンツの共有**をします。</span><span class="sxs-lookup"><span data-stu-id="1d605-119">Under **Content sharing**:</span></span>
- <span data-ttu-id="1d605-120">画面の共有モードを無効にします。</span><span class="sxs-lookup"><span data-stu-id="1d605-120">Disable screen sharing mode</span></span>
- <span data-ttu-id="1d605-121">ホワイト ボードをオフにします。</span><span class="sxs-lookup"><span data-stu-id="1d605-121">Turn off whiteboard</span></span>
- <span data-ttu-id="1d605-122">共有のメモをオフにします。</span><span class="sxs-lookup"><span data-stu-id="1d605-122">Turn off shared notes</span></span>

<span data-ttu-id="1d605-123">ユーザーにポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1d605-123">Then assign the policy to the users.</span></span>

> [!NOTE] 
> <span data-ttu-id="1d605-124">ユーザーには、一度に 1 つだけの会議ポリシーを割り当てることできます。</span><span class="sxs-lookup"><span data-stu-id="1d605-124">A user can be assigned only one meeting policy at a time.</span></span> 

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="1d605-125">会議ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="1d605-125">Assign a meeting policy to users</span></span>

<span data-ttu-id="1d605-126">1 人のユーザーにポリシーを適用する場合の左側のナビゲーション ウィンドウで**ユーザー**を選択し、ユーザーの表示名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d605-126">If you are applying the policy to one user, select **Users** on the left navigation pane, and then click the user's display name.</span></span> <span data-ttu-id="1d605-127">[ユーザーのページの [**割り当てポリシー**の**編集**を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d605-127">On the user's page, next to **Assigned policies**, select **Edit**.</span></span> <span data-ttu-id="1d605-128">**ユーザー ポリシーの編集**] ウィンドウの [**ミーティングのポリシー**]、[ボックスの一覧からミーティングのポリシーを選択し、し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d605-128">Then, in the **Edit user policies** pane, under **Meeting policy**, select the meeting policy from the drop-down list, and then select **Save**.</span></span> <span data-ttu-id="1d605-129">ユーザーの一覧からポリシーを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="1d605-129">You can also assign policies from the list of users.</span></span> <span data-ttu-id="1d605-130">これを行うには、ユーザーの表示名の左側に] をクリックしてユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="1d605-130">To do this, select the user by clicking to the left of the user's display name.</span></span> <span data-ttu-id="1d605-131">**設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d605-131">Select **Edit settings**.</span></span> <span data-ttu-id="1d605-132">**設定を編集**] ウィンドウの [**ミーティングのポリシー**]、[ボックスの一覧からポリシーを選択し、し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d605-132">Then, on the **Edit settings** pane, under **Meeting policy**, select the policy from the drop-down list, and then select **Save**.</span></span> 
 
<span data-ttu-id="1d605-133">複数のユーザーにポリシーを適用する場合、左側のナビゲーション ウィンドウで**ユーザー**を選択、ユーザー名の左側をクリックすると、各ユーザーを選択し、**設定の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d605-133">If you are applying a policy to more than one user, select **Users** on the left navigation pane, and then select each user by clicking to the left of the user name, and then click **Edit settings**.</span></span> <span data-ttu-id="1d605-134">**設定の編集**] ウィンドウの [**ミーティングのポリシー**]、[ボックスの一覧からポリシーを選択し、[**保存**します。</span><span class="sxs-lookup"><span data-stu-id="1d605-134">On the **Edit Settings** pane, under **Meeting policy**, select the policy from the drop-down list, and then select **Save**.</span></span>
 
<span data-ttu-id="1d605-135">割り当てることも会議ポリシーを 1 つまたは複数のユーザーとして次のように。</span><span class="sxs-lookup"><span data-stu-id="1d605-135">You can also assign a meeting policy to one or more users as follows:</span></span>

1. <span data-ttu-id="1d605-136">**マイクロソフトのチーム管理センター**を参照して > **会議** > **ミーティングのポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="1d605-136">Go to **Microsoft Teams admin center** > **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="1d605-137">ポリシーを選択するには、ポリシー名の左側にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d605-137">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="1d605-138">**ユーザーの管理**を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d605-138">Select **Manage users**.</span></span>
4. <span data-ttu-id="1d605-139">**ユーザーの管理**ウィンドウで、表示名、ユーザー名、ユーザーの検索、名を選択し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d605-139">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="1d605-140">追加するユーザーごとにこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="1d605-140">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="1d605-141">ユーザーの追加が完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d605-141">When you are finished adding users, select **Save**.</span></span>
 
> [!NOTE] 
> <span data-ttu-id="1d605-142">ユーザーがそれに割り当てられている場合は、ポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="1d605-142">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="1d605-143">まず、影響を受けるすべてのユーザーに別のポリシーを割り当てる必要があり、元のポリシーを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="1d605-143">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>
 
 
## <a name="user-policy-settings"></a><span data-ttu-id="1d605-144">ユーザー ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="1d605-144">User policy settings</span></span>

<span data-ttu-id="1d605-145">[**ミーティングのポリシー** ] ページで、既存のポリシーを選択した場合、または新しいポリシーを追加する**新しいポリシー**を選択するときは、次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="1d605-145">When you select an existing policy on the **Meeting policies** page or select **New policy** to add a new policy, you can configure the following settings.</span></span>

### <a name="new-meeting-policy-name-and-description"></a><span data-ttu-id="1d605-146">ポリシーの名前および説明の新しい会議出席</span><span class="sxs-lookup"><span data-stu-id="1d605-146">New meeting policy name and description</span></span>
   - <span data-ttu-id="1d605-147">**名**これは、[**ミーティングのポリシー** ] ページに表示されるポリシーの名前です。</span><span class="sxs-lookup"><span data-stu-id="1d605-147">**Name** This is the name of the policy that will appear on the **Meeting policies** page.</span></span> <span data-ttu-id="1d605-148">特殊文字または 64 文字より長くできません。</span><span class="sxs-lookup"><span data-stu-id="1d605-148">It can't contain special characters or be longer than 64 characters.</span></span> <span data-ttu-id="1d605-149">既存のポリシーの名前を変更できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1d605-149">Note that you can't change an existing policy's name.</span></span>
   - <span data-ttu-id="1d605-150">**説明**作成したポリシーのわかりやすい説明を追加できます。</span><span class="sxs-lookup"><span data-stu-id="1d605-150">**Description** You can put in a friendly description for the policy you create.</span></span> <span data-ttu-id="1d605-151">これは、ユーザーのグループにポリシーを割り当てる場合に役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="1d605-151">This will be helpful if you want to assign a policy to a group of users.</span></span>
::: zone-end 

<span data-ttu-id="1d605-152"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="1d605-152"></span></span>
### <a name="general"></a><span data-ttu-id="1d605-153">[全般]</span><span class="sxs-lookup"><span data-stu-id="1d605-153">General</span></span>
   - <span data-ttu-id="1d605-154">**チャンネルに対応できるようにします。** これを有効にすると、ミーティングに参加するユーザーを使用できるように即時の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1d605-154">**Allow Meet now in channels** Turning this on will allow the Meet Now feature to be available to users who join meetings.</span></span>
   - <span data-ttu-id="1d605-155">**Outlook アドインを許可** これをオンにすると、ポリシーに割り当てられたユーザーが、会議をスケジュールするときに、Outlook アドインを利用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="1d605-155">**Allow the Outlook add-in** Turning this on will let users assigned to the policy have the Outlook add-in available when they schedule meetings.</span></span>
   - <span data-ttu-id="1d605-156">**許可するチャネルの会議のスケジュール**これをオンにするには、チャネルの会議のスケジュールできるようなります。</span><span class="sxs-lookup"><span data-stu-id="1d605-156">**Allow channel meeting scheduling** Turning this on will allow Channel Meeting scheduling.</span></span>
   - <span data-ttu-id="1d605-157">**プライベート会議のスケジュール設定を許可** これをオンにすると、会議に参加するユーザーがプライベート会議のスケジュールを設定することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="1d605-157">**Allow scheduling private meetings** Turning this on will allow users that join a meeting to schedule private meetings.</span></span>

<span data-ttu-id="1d605-158"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="1d605-158"></span></span>

### <a name="audio--video"></a><span data-ttu-id="1d605-159">オーディオとビデオ</span><span class="sxs-lookup"><span data-stu-id="1d605-159">Audio & video</span></span>
   - <span data-ttu-id="1d605-160">**トランスクリプションを許可** これをオンにすると、ユーザーは会議のトランスクリプションを利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1d605-160">**Allow transcription** If you turn this on, transcription of the meeting will be available to users.</span></span>
   - <span data-ttu-id="1d605-161">**許可するクラウドの記録**これを有効にすると、レコーディングをクラウドに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="1d605-161">**Allow cloud recording** Turning this on will allow recordings to be saved in the cloud.</span></span>
   - <span data-ttu-id="1d605-162">**IP ビデオを許可** これをオンにすると、会議中に IP ビデオを使用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="1d605-162">**Allow IP video** Turning this on will allow IP videos during meetings.</span></span>
   - <span data-ttu-id="1d605-163">**メディア ビット レート (KB)** 会議用のビット レートを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="1d605-163">**Media bit rate (KBs)** You can set the bit rate for meetings.</span></span> <span data-ttu-id="1d605-164">既定値は 50 MB です。</span><span class="sxs-lookup"><span data-stu-id="1d605-164">The default is 50 MB.</span></span>

<span data-ttu-id="1d605-165"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="1d605-165"></span></span>

### <a name="content-sharing"></a><span data-ttu-id="1d605-166">コンテンツ共有</span><span class="sxs-lookup"><span data-stu-id="1d605-166">Content sharing</span></span>
   - <span data-ttu-id="1d605-167">**画面共有モード** 画面共有モードを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="1d605-167">**Screen sharing mode** You can select the screen sharing mode.</span></span> <span data-ttu-id="1d605-168">ここでは、ポリシーに割り当てられたユーザーが利用することができる会議で使用される画面のサイズになります。</span><span class="sxs-lookup"><span data-stu-id="1d605-168">This will be the size of the screen that will be used during a meeting that a user assigned with the policy can use.</span></span>
   - <span data-ttu-id="1d605-169">**参加者が制御を付与したり要求したりすることを許可** これにより、会議のすべての参加者が画面共有の制御を付与したり要求したりすることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="1d605-169">**Allow a participant to give or request control** This allows all participants in a meeting to give and request control of screen sharing.</span></span>
   - <span data-ttu-id="1d605-170">**外部の参加者が制御を付与したり要求したりすることを許可** これにより、画面が共有されているときに外部の参加者 (お客様の組織に属していないユーザー) が会議の制御を付与したり要求したりすることが可能になります。</span><span class="sxs-lookup"><span data-stu-id="1d605-170">**Allow an external participant to give or request control** This allows an external (someone not part of your organziation) participant to give and request control of a meeting when the screen is being shared.</span></span>
   - <span data-ttu-id="1d605-171">**PowerPoint 共有を許可** これをオンにすると、会議をスケジュール設定するユーザーが会議中に PowerPoint スライド デッキを共有することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="1d605-171">**Allow PowerPoint sharing** If you turn this on, users that schedule meetings can share PowerPoint slide decks during a meeting.</span></span>
   - <span data-ttu-id="1d605-172">**ホワイトボードを許可** これをオンにすると、会議の参加者が会議中にホワイトボードを利用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="1d605-172">**Allow whiteboard** If you turn this on, the whiteboard will be available to meeting participants during a meeting.</span></span>
   - <span data-ttu-id="1d605-173">**共有メモを許可** これをオンにすると、会議の参加者が会議中にホワイトボードを利用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="1d605-173">**Allow shared notes** If you turn this on, shared notes will be available to meeting participants during a meeting.</span></span>

<span data-ttu-id="1d605-174"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="1d605-174"></span></span>

### <a name="participants--guests"></a><span data-ttu-id="1d605-175">参加者とゲスト</span><span class="sxs-lookup"><span data-stu-id="1d605-175">Participants & guests</span></span>
   - <span data-ttu-id="1d605-176">**会議を開始するのにはダイヤルインを許可する人**オンまたはオフは、携帯電話を使用して会議を開始するにダイヤルするために認証されていないユーザーを許可する場合にできます。</span><span class="sxs-lookup"><span data-stu-id="1d605-176">**Allow people that dial in to start a meeting** You can turn on or off if you want to let people who haven't been authenticated because they dialed in using their phone to start a meeting.</span></span>
   - <span data-ttu-id="1d605-177">**自動的に人を認める**決定のどのような参加者のタイプが自動的にこのユーザーによって開催されるミーティングに追加されます。</span><span class="sxs-lookup"><span data-stu-id="1d605-177">**Automatically admit people** Determines what types of participants will automatically be added to meetings organized by this user.</span></span> <span data-ttu-id="1d605-178">ミーティング ロビーのすべての外部ユーザーを配置するが、すぐにミーティングに参加する会社のすべてのユーザーを許可する場合 **、組織内のすべてのユーザー**に設定します。</span><span class="sxs-lookup"><span data-stu-id="1d605-178">Set this to **Everyone in your organization** if you would like meetings to place every external user in the lobby but allow all users in the company to join the meeting immediately.</span></span> <span data-ttu-id="1d605-179">既定で匿名ユーザーを許可したい場合に、[**全員**にこれを設定します。</span><span class="sxs-lookup"><span data-stu-id="1d605-179">Set this to **Everyone** if you'd like to admit anonymous users by default.</span></span> <span data-ttu-id="1d605-180">会議への参加、社内のユーザーと同じようにもロビーに入っている他のすべての外部ユーザーのフェデレーション ユーザーを許可する場合 **、組織とフェデレーション組織内のすべてのユーザー**に設定します。</span><span class="sxs-lookup"><span data-stu-id="1d605-180">Set this to **Everyone in your organization and federated organizations** if you would like meetings to allow federated users to join like your company's users, but place all other external users in a lobby.</span></span>
   - <span data-ttu-id="1d605-181">**ロビーをバイパスするユーザー ダイヤルインできるようにします。** ロビーをバイパスし、ミーティングに参加する携帯電話を使用してダイヤルするユーザーを許可する場合オンまたはオフを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="1d605-181">**Allow dial-in users to bypass the lobby** You can turn on or off if you want to let people who dialed in using their phone to bypass the lobby and join the meeting.</span></span>
   - <span data-ttu-id="1d605-182">**ロビーの設定をオーバーライドするのには、[開催者**ミーティングの開催者が会議にユーザーを許可するのにはロビーの設定を無視するこの設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1d605-182">**Allow organizers to override lobby settings** Turn this setting on to let meeting organizers disregard the lobby settings to admit users to meetings.</span></span>
   - <span data-ttu-id="1d605-183">**個人の会議で対応できるようにします。** 会議が開始する前にチャットを使用して個別に対応する会議の出席者を許可するこの設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1d605-183">**Allow Meet now in private meetings** Turn this setting on to allow meeting attendees to meet privately via chat before the meeting begins.</span></span> 
   - <span data-ttu-id="1d605-184">**ライブ キャプションを有効にします。** 会議中に、サポートされている言語でキャプションを表示するには、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1d605-184">**Enable live captions** Enable this setting to display captions in supported languages during a meeting.</span></span> 
   - <span data-ttu-id="1d605-185">**会議でチャットを許可します。** ミーティング中にチャットを許可するようにこの設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1d605-185">**Allow chat in meetings** Enable this setting to permit chats during a meeting.</span></span> <span data-ttu-id="1d605-186">これは、会話を中断させたくないですが、ユーザーの質問があるか、討論の際に、[ハイパーリンク] または [メモを挿入する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="1d605-186">This is helpful if users have questions or want to insert a hyperlink or note during a discussion, but they don't want to interrupt the conversation.</span></span>

[<span data-ttu-id="1d605-187">記事の全文</span><span class="sxs-lookup"><span data-stu-id="1d605-187">Full article</span></span>](meeting-policies-in-teams.md)

### <a name="related-topics"></a><span data-ttu-id="1d605-188">関連トピック</span><span class="sxs-lookup"><span data-stu-id="1d605-188">Related topics</span></span>
[<span data-ttu-id="1d605-189">チームでのメッセージングのポリシー</span><span class="sxs-lookup"><span data-stu-id="1d605-189">Messaging policies in Teams</span></span>](messaging-policies-in-teams.md)
