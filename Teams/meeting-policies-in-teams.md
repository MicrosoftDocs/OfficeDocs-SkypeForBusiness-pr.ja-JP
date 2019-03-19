---
title: 会議ポリシーを管理する
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.date: 03/01/2019
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
ms.openlocfilehash: 344c45761ebbb326162d2c62b4fb8cac25f47645
ms.sourcegitcommit: 8e62025d630c511ffb0361b9643d46c762188102
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "30664717"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="4b2b4-103">Teams での会議ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="4b2b4-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="4b2b4-104">ミーティングのポリシーは、組織内のユーザーによってスケジュールされている会議の参加者をミーティングに使用可能な機能の制御に使用されます。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="4b2b4-105">ポリシーを作成して変更を行った後、ユーザーをポリシーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-105">After you create a policy and make your changes, you can then assign uses to the policy.</span></span> 

<span data-ttu-id="4b2b4-106">既定では、グローバル (組織全体の既定値) をという名前のポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-106">By default, a policy named Global (org-wide default) is created.</span></span> <span data-ttu-id="4b2b4-107">組織内のすべてのユーザー ポリシーが割り当てられますこの会議既定します。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-107">All users in your organization will be assigned this meeting policy by default.</span></span> <span data-ttu-id="4b2b4-108">このポリシーに変更を加えるか、1 つまたは複数のカスタム ポリシーの作成にユーザーを割り当てるとします。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-108">You can either make changes to this policy or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="4b2b4-109">カスタム ポリシーを作成するときはまたは許可するの特定の機能がユーザーに利用されることを防ぐし、それらに適用する設定を持つ 1 つまたは複数のユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-109">When you create a custom policy, you can allow or prevent certain features from being available to your users and then assign it to one or more users who will have the settings applied to them.</span></span> 

## <a name="change-or-create-a-meeting-policy"></a><span data-ttu-id="4b2b4-110">変更するか、会議ポリシーを作成</span><span class="sxs-lookup"><span data-stu-id="4b2b4-110">Change or create a meeting policy</span></span>

<span data-ttu-id="4b2b4-111">**マイクロソフトのチーム管理センター**への移動を変更する会議ポリシーを作成、 > **会議** > **ミーティングのポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-111">To change or create a meeting policy, go to **Microsoft Teams admin center** > **Meetings** > **Meeting policies**.</span></span> <span data-ttu-id="4b2b4-112">リストからポリシーを選択するか、**新しいポリシー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-112">Select a policy from the list, or select **New policy**.</span></span> <span data-ttu-id="4b2b4-113">設定を選択し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-113">Choose your settings, and then select **Save**.</span></span>

<span data-ttu-id="4b2b4-114">たとえば、一連のユーザがあり、その会議を必要とする帯域幅の量を制限したいとします。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-114">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="4b2b4-115">「帯域幅の制限」をという名前の新しいカスタム ポリシーを作成し、次の設定を無効にします。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-115">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="4b2b4-116">[**ビデオのオーディオ &**。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-116">Under **Audio & video**:</span></span>
- <span data-ttu-id="4b2b4-117">クラウドをオフに記録</span><span class="sxs-lookup"><span data-stu-id="4b2b4-117">Turn off cloud recording</span></span>
- <span data-ttu-id="4b2b4-118">ビデオを許可する IP をオフにします。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-118">Turn off Allow IP video</span></span>

<span data-ttu-id="4b2b4-119">[**コンテンツの共有**をします。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-119">Under **Content sharing**:</span></span>
- <span data-ttu-id="4b2b4-120">画面の共有モードを無効にします。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-120">Disable screen sharing mode</span></span>
- <span data-ttu-id="4b2b4-121">ホワイト ボードをオフにします。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-121">Turn off whiteboard</span></span>
- <span data-ttu-id="4b2b4-122">共有のメモをオフにします。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-122">Turn off shared notes</span></span>

<span data-ttu-id="4b2b4-123">ユーザーにポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-123">Then assign the policy to the users.</span></span>

> [!NOTE] 
> <span data-ttu-id="4b2b4-124">ユーザーには、一度に 1 つだけの会議ポリシーを割り当てることできます。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-124">A user can be assigned only one meeting policy at a time.</span></span> 

## <a name="assign-a-meeting-policy-to-a-user"></a><span data-ttu-id="4b2b4-125">会議ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="4b2b4-125">Assign a meeting policy to a user</span></span>

<span data-ttu-id="4b2b4-126">**マイクロソフトのチーム管理センター**にポリシーを割り当てるには、 > **のユーザー**です。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-126">To assign a policy, go to **Microsoft Teams admin center** > **Users**.</span></span> 
 
<span data-ttu-id="4b2b4-127">1 人のユーザーにポリシーを適用する場合は、ユーザーの表示名を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-127">If you are applying the policy to one user, select the user's display name.</span></span> <span data-ttu-id="4b2b4-128">**割り当てポリシー**] の横の**編集**を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-128">Next to **Assigned policies**, select **Edit**.</span></span> <span data-ttu-id="4b2b4-129">**ユーザー ポリシーの編集**] ウィンドウの [**ミーティングのポリシー**]、[ボックスの一覧からミーティングのポリシーを選択し、**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-129">Then, in the **Edit user policies** pane, under **Meeting policy**, select the meeting policy from the drop-down list, and select **Save**.</span></span> <span data-ttu-id="4b2b4-130">ユーザーの一覧から設定を編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-130">You can also edit settings from the list of users.</span></span> <span data-ttu-id="4b2b4-131">これを行うには、ユーザーの表示名の左側に] をクリックしてユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-131">To do this, select the user by clicking to the left of the user's display name.</span></span> <span data-ttu-id="4b2b4-132">**設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-132">Select **Edit settings**.</span></span> <span data-ttu-id="4b2b4-133">**設定を編集**] ウィンドウの [**ミーティングのポリシー**]、[ドロップダウン リストからポリシーを選択し、し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-133">Then, on the **Edit settings** pane, under **Meeting policy**, select the policy from the drop-down list and then select **Save**.</span></span> 
 
<span data-ttu-id="4b2b4-134">複数のユーザーにポリシーを適用する場合、ユーザー名の左側をクリックして選択する各ユーザーと**設定の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-134">If you are applying a policy to more than one user, select each of the users by clicking to the left of the user name, and then click **Edit settings**.</span></span> <span data-ttu-id="4b2b4-135">**設定の編集**] ウィンドウの [**ミーティングのポリシー**]、[ドロップダウン リストからポリシーを選択し、[**保存**します。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-135">On the **Edit Settings** pane, under **Meeting policy**, select the policy from the drop-down list and then select **Save**.</span></span>
 
<span data-ttu-id="4b2b4-136">これを行うには、**マイクロソフトのチーム管理センター** > **会議** >  **ミーティングのポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-136">You can also do this by going to **Microsoft Teams admin center** > **Meetings** >  **Meeting policies**.</span></span> <span data-ttu-id="4b2b4-137">ポリシーを選択し、**ユーザーの管理**を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-137">Select the policy and then select **Manage users**.</span></span> <span data-ttu-id="4b2b4-138">**ユーザーの管理**ウィンドウで、[ディスプレイ] または [ユーザー名でユーザーを検索しています。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-138">In the **Manage users** pane, search for the user by display or user name.</span></span> <span data-ttu-id="4b2b4-139">名前を選択し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-139">Select the name and select **Add**.</span></span> <span data-ttu-id="4b2b4-140">ユーザーの追加が完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-140">When you are finished adding users, select **Save**.</span></span>

> [!NOTE] 
> <span data-ttu-id="4b2b4-141">ユーザーがそれに割り当てられている場合は、ポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-141">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="4b2b4-142">まず、影響を受けるすべてのユーザーに別のポリシーを割り当てる必要があり、元のポリシーを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-142">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>
 
 
## <a name="user-policy-settings"></a><span data-ttu-id="4b2b4-143">ユーザー ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="4b2b4-143">User policy settings</span></span>

<span data-ttu-id="4b2b4-144">[**ミーティングのポリシー** ] ページで、既存のポリシーを選択した場合、または新しいポリシーを追加する**新しいポリシー**を選択するときは、次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-144">When you select an existing policy on the **Meeting policies** page or select **New policy** to add a new policy, you can configure the following settings.</span></span>

### <a name="new-meeting-policy-name-and-description"></a><span data-ttu-id="4b2b4-145">ポリシーの名前および説明の新しい会議出席</span><span class="sxs-lookup"><span data-stu-id="4b2b4-145">New meeting policy name and description</span></span>
   - <span data-ttu-id="4b2b4-146">**名**これは、[**ミーティングのポリシー** ] ページに表示されるポリシーの名前です。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-146">**Name** This is the name of the policy that will appear on the **Meeting policies** page.</span></span> <span data-ttu-id="4b2b4-147">特殊文字または 64 文字より長くできません。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-147">It can't contain special characters or be longer than 64 characters.</span></span> <span data-ttu-id="4b2b4-148">既存のポリシーの名前を変更できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-148">Note that you can't change an existing policy's name.</span></span>
   - <span data-ttu-id="4b2b4-149">**説明**作成したポリシーのわかりやすい説明を追加できます。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-149">**Description** You can put in a friendly description for the policy you create.</span></span> <span data-ttu-id="4b2b4-150">これは、ユーザーのグループにポリシーを割り当てる場合に役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-150">This will be helpful if you want to assign a policy to a group of users.</span></span>
::: zone-end 

<span data-ttu-id="4b2b4-151"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="4b2b4-151"></span></span>
### <a name="general"></a><span data-ttu-id="4b2b4-152">[全般]</span><span class="sxs-lookup"><span data-stu-id="4b2b4-152">General</span></span>
   - <span data-ttu-id="4b2b4-153">**会議の開始を許可** これをオンにすると、会議に参加するユーザーが [会議の開始] 機能を使用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-153">**Allow Meet Now** Turning this on will allow the Meet Now feature to be available to users that join meetings.</span></span>
   - <span data-ttu-id="4b2b4-154">**Outlook アドインを許可** これをオンにすると、ポリシーに割り当てられたユーザーが、会議をスケジュールするときに、Outlook アドインを利用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-154">**Allow the Outlook add-in** Turning this on will let users assigned to the policy have the Outlook add-in available when they schedule meetings.</span></span>
   - <span data-ttu-id="4b2b4-155">**チャネル会議のスケジュール設定を許可** これをオンにするとチャネル会議をスケジュール設定することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-155">**Allow Channel meeting scheduling** Turning this on will allow Channel Meeting scheduling.</span></span>
   - <span data-ttu-id="4b2b4-156">**プライベート会議のスケジュール設定を許可** これをオンにすると、会議に参加するユーザーがプライベート会議のスケジュールを設定することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-156">**Allow scheduling private meetings** Turning this on will allow users that join a meeting to schedule private meetings.</span></span>

<span data-ttu-id="4b2b4-157"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="4b2b4-157"></span></span>

### <a name="audio--video"></a><span data-ttu-id="4b2b4-158">オーディオとビデオ</span><span class="sxs-lookup"><span data-stu-id="4b2b4-158">Audio & video</span></span>
   - <span data-ttu-id="4b2b4-159">**トランスクリプションを許可** これをオンにすると、ユーザーは会議のトランスクリプションを利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-159">**Allow transcription** If you turn this on, transcription of the meeting will be available to users.</span></span>
   - <span data-ttu-id="4b2b4-160">**許可するクラウドの記録**これを有効にすると、レコーディングをクラウドに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-160">**Allow cloud recording** Turning this on will allow recordings to be saved in the cloud.</span></span>
   - <span data-ttu-id="4b2b4-161">**IP ビデオを許可** これをオンにすると、会議中に IP ビデオを使用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-161">**Allow IP video** Turning this on will allow IP videos during meetings.</span></span>
   - <span data-ttu-id="4b2b4-162">**メディア ビット レート (KB)** 会議用のビット レートを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-162">**Media bit rate (KBs)** You can set the bit rate for meetings.</span></span> <span data-ttu-id="4b2b4-163">既定値は 50 MB です。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-163">The default is 50 MB.</span></span>

<span data-ttu-id="4b2b4-164"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="4b2b4-164"></span></span>

### <a name="content-sharing"></a><span data-ttu-id="4b2b4-165">コンテンツ共有</span><span class="sxs-lookup"><span data-stu-id="4b2b4-165">Content sharing</span></span>
   - <span data-ttu-id="4b2b4-166">**画面共有モード** 画面共有モードを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-166">**Screen sharing mode** You can select the screen sharing mode.</span></span> <span data-ttu-id="4b2b4-167">ここでは、ポリシーに割り当てられたユーザーが利用することができる会議で使用される画面のサイズになります。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-167">This will be the size of the screen that will be used during a meeting that a user assigned with the policy can use.</span></span>
   - <span data-ttu-id="4b2b4-168">**参加者が制御を付与したり要求したりすることを許可** これにより、会議のすべての参加者が画面共有の制御を付与したり要求したりすることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-168">**Allow a participant to give or request control** This allows all participants in a meeting to give and request control of screen sharing.</span></span>
   - <span data-ttu-id="4b2b4-169">**外部の参加者が制御を付与したり要求したりすることを許可** これにより、画面が共有されているときに外部の参加者 (お客様の組織に属していないユーザー) が会議の制御を付与したり要求したりすることが可能になります。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-169">**Allow an external participant to give or request control** This allows an external (someone not part of your organziation) participant to give and request control of a meeting when the screen is being shared.</span></span>
   - <span data-ttu-id="4b2b4-170">**PowerPoint 共有を許可** これをオンにすると、会議をスケジュール設定するユーザーが会議中に PowerPoint スライド デッキを共有することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-170">**Allow PowerPoint sharing** If you turn this on, users that schedule meetings can share PowerPoint slide decks during a meeting.</span></span>
   - <span data-ttu-id="4b2b4-171">**ホワイトボードを許可** これをオンにすると、会議の参加者が会議中にホワイトボードを利用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-171">**Allow whiteboard** If you turn this on, the whiteboard will be available to meeting participants during a meeting.</span></span>
   - <span data-ttu-id="4b2b4-172">**共有メモを許可** これをオンにすると、会議の参加者が会議中にホワイトボードを利用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-172">**Allow shared notes** If you turn this on, shared notes will be available to meeting participants during a meeting.</span></span>

<span data-ttu-id="4b2b4-173"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="4b2b4-173"></span></span>

### <a name="participants--guests"></a><span data-ttu-id="4b2b4-174">参加者とゲスト</span><span class="sxs-lookup"><span data-stu-id="4b2b4-174">Participants & guests</span></span>
   - <span data-ttu-id="4b2b4-175">**会議を開始するのにはダイヤルインを許可する人**ユーザーに携帯電話を使用して会議を開始するにダイヤルしているために、認証されていないことを許可する場合は、オンまたはオフを有効にことができます。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-175">**Allow people that dial in to start a meeting** You can turn on or off if you want to let people that haven't been authenticated because they've dialed in using their phone to start a meeting.</span></span>
   - <span data-ttu-id="4b2b4-176">**自動的に人を認める**決定のどのような参加者のタイプが自動的にこのユーザーによって開催されるミーティングに追加されます。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-176">**Automatically admit people** Determines what types of participants will automatically be added to meetings organized by this user.</span></span> <span data-ttu-id="4b2b4-177">ミーティング ロビーのすべての外部ユーザーを配置するが、すぐにミーティングに参加する会社のすべてのユーザーを許可したい場合は、"組織内の全員] に設定します。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-177">Set this to "Everyone in organization" if you would like meetings to place every external user in the lobby but allow all users in the company to join the meeting immediately.</span></span> <span data-ttu-id="4b2b4-178">既定で匿名ユーザーを許可したい場合は、"Everyone"に設定します。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-178">Set this to "Everyone" if you'd like to admit anonymous users by default.</span></span> <span data-ttu-id="4b2b4-179">場合会議への参加、社内のユーザーと同じようにもロビーに入っている他のすべての外部ユーザーのフェデレーション ユーザーを許可するのには、everyone グループに、組織とフェデレーションの組織で設定します。</span><span class="sxs-lookup"><span data-stu-id="4b2b4-179">Set this to "Everyone in your organization and federated organizations" if you would like meetings to allow federated users to join like your company's users, but place all other external users in a lobby.</span></span>

[<span data-ttu-id="4b2b4-180">記事の全文</span><span class="sxs-lookup"><span data-stu-id="4b2b4-180">Full article</span></span>](meeting-policies-in-teams.md)

### <a name="related-topics"></a><span data-ttu-id="4b2b4-181">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b2b4-181">Related topics</span></span>
[<span data-ttu-id="4b2b4-182">チームでのメッセージングのポリシー</span><span class="sxs-lookup"><span data-stu-id="4b2b4-182">Messaging policies in Teams</span></span>](messaging-policies-in-teams.md)