---
title: Teams のメッセージング ポリシーを管理する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.messagingpolicies.overview
description: メッセージング ポリシーとそれらを使用してメッセージング チームのチャットを制御する方法について説明します。
ms.openlocfilehash: f0dd52dac1bd2563a0ef5c500714ab63eeadf84d
ms.sourcegitcommit: ee3f79ce1b6da0885e1096f9fba894bcff1814da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2019
ms.locfileid: "33298454"
---
# <a name="manage-messaging-policies-in-teams"></a><span data-ttu-id="d34e2-103">Teams のメッセージング ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="d34e2-103">Manage messaging policies in Teams</span></span>

<!--- Add zone marker here--->

<span data-ttu-id="d34e2-104">メッセージング ポリシーは、マイクロソフトのチームのユーザーに利用するチャットとチャネルのメッセージング機能を制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d34e2-104">Messaging policies are used to control which chat and channel messaging features are available to users in Microsoft Teams.</span></span> <span data-ttu-id="d34e2-105">自動的に作成されるか、組織内の 1 つまたは複数のカスタム メッセージング ポリシーを作成する既定のポリシーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d34e2-105">You can use the default policy that is created automatically or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="d34e2-106">ポリシーを作成した後は、組織内ユーザーまたはユーザー グループに割り当てることが。</span><span class="sxs-lookup"><span data-stu-id="d34e2-106">After you create a policy, you can assign it to a user or group of users in your organization.</span></span>

<span data-ttu-id="d34e2-107">既定では、グローバル (組織全体の既定値) をという名前のポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d34e2-107">By default, a policy named Global (org-wide default) is created.</span></span> <span data-ttu-id="d34e2-108">組織内のすべてのユーザー ポリシーが割り当てられますこのメッセージ既定します。</span><span class="sxs-lookup"><span data-stu-id="d34e2-108">All users in your organization will be assigned this messaging policy by default.</span></span> <span data-ttu-id="d34e2-109">このポリシーに変更を加えるか、1 つまたは複数のカスタム ポリシーの作成にユーザーを割り当てるとします。</span><span class="sxs-lookup"><span data-stu-id="d34e2-109">You can either make changes to this policy or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="d34e2-110">カスタム ポリシーを作成するときにすることができますか、またはの特定の機能がユーザーに利用されることを防ぐして、それらに適用する設定する必要がある 1 つまたは複数のユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d34e2-110">When you create a custom policy, you can allow or prevent certain features from being available to your users and then assign it to one or more users who will need the settings applied to them.</span></span> 

## <a name="change-or-create-a-messaging-policy"></a><span data-ttu-id="d34e2-111">変更またはメッセージング ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d34e2-111">Change or create a messaging policy</span></span>

<span data-ttu-id="d34e2-112">マイクロソフトのチームの管理センターでのメッセージング ポリシーを簡単に管理することができます (http://admin.teams.microsoft.com)で管理者の資格情報を使用してサインインし、左側のナビゲーション ウィンドウで、**メッセージング ポリシー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d34e2-112">You can easily manage messaging policies in the Microsoft Teams admin center (http://admin.teams.microsoft.com) by signing in with administrator credentials and choosing **Messaging policies** in the left navigation pane.</span></span> <span data-ttu-id="d34e2-113">メッセージング ポリシーを組織の既存の既定値を編集するには、**グローバル (組織全体の既定値)** の行を選択し、変更してください。</span><span class="sxs-lookup"><span data-stu-id="d34e2-113">To edit the existing default messaging policy for your organization, select the **Global (Org-wide default)** row, and then make your changes.</span></span> <span data-ttu-id="d34e2-114">新しいカスタム メッセージング ポリシーを作成するには、**新しいポリシー**を選択、新しいポリシーの名前を入力しの設定。</span><span class="sxs-lookup"><span data-stu-id="d34e2-114">To create a new custom messaging policy, select **New policy**, give the new policy a name, and then select your settings.</span></span> <span data-ttu-id="d34e2-115">したら**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d34e2-115">Choose **Save** when you are done.</span></span>

<span data-ttu-id="d34e2-116">たとえば、することを確認するメッセージは削除または変更を送信したとします。</span><span class="sxs-lookup"><span data-stu-id="d34e2-116">For example, say you want to make sure that sent messages aren't deleted or altered.</span></span> <span data-ttu-id="d34e2-117">保存メッセージを送信」をという名前の新しいカスタム ポリシーを作成し、次の設定をオフにします。</span><span class="sxs-lookup"><span data-stu-id="d34e2-117">You would create a new custom policy named "Retain sent messages" and turn off the following settings:</span></span>

- <span data-ttu-id="d34e2-118">所有者は、送信済みメッセージを削除できます。</span><span class="sxs-lookup"><span data-stu-id="d34e2-118">Owners can delete sent messages</span></span>
- <span data-ttu-id="d34e2-119">ユーザーが送信したメッセージを削除できます。</span><span class="sxs-lookup"><span data-stu-id="d34e2-119">Users can delete sent messages</span></span>
- <span data-ttu-id="d34e2-120">ユーザーが送信したメッセージを編集できます。</span><span class="sxs-lookup"><span data-stu-id="d34e2-120">Users can edit sent messages</span></span>

<span data-ttu-id="d34e2-121">ユーザーにポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d34e2-121">Then assign the policy to the users.</span></span>

> [!NOTE] 
> <span data-ttu-id="d34e2-122">ユーザーのみ割り当てられますメッセージング ポリシーを 1 つずつ。</span><span class="sxs-lookup"><span data-stu-id="d34e2-122">A user can only be assigned one messaging policy at a time.</span></span>
 
## <a name="assign-a-messaging-policy-to-a-user"></a><span data-ttu-id="d34e2-123">メッセージング ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="d34e2-123">Assign a messaging policy to a user</span></span>

<span data-ttu-id="d34e2-124">カスタム メッセージング ポリシーを作成する場合にのみアクティブになるユーザーのポリシーがユーザーに割り当てられている場合。</span><span class="sxs-lookup"><span data-stu-id="d34e2-124">If you create a custom messaging policy, it will only be active for a user if the policy is assigned to the user.</span></span> <span data-ttu-id="d34e2-125">カスタム ポリシーをユーザーに割り当てるには、マイクロソフトのチーム管理センターに、左側のナビゲーション ウィンドウで、**ユーザー**の選択し、するようにポリシーを割り当てるユーザーを選択を移動します。</span><span class="sxs-lookup"><span data-stu-id="d34e2-125">To assign a custom policy to a user, go to the Microsoft Teams admin center, choose **Users** in the left navigation pane, and select the user you want to assign the policy to.</span></span> <span data-ttu-id="d34e2-126">ユーザーのページで、 **[割り当てポリシー**] の横の**編集**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d34e2-126">On the user's page, choose **Edit** next to **Assigned policies**.</span></span> <span data-ttu-id="d34e2-127">**ユーザー ポリシーの編集**ウィンドウで、**メッセージングのポリシー**では、ドロップ ダウン リストから、メッセージング ポリシーを選択し、**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d34e2-127">Then, in the **Edit user policies** pane, under **Messaging policy**, select the messaging policy from the drop-down list, and select **Save**.</span></span> <span data-ttu-id="d34e2-128">ユーザーの一覧から設定を編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="d34e2-128">You can also edit settings from the list of users.</span></span> <span data-ttu-id="d34e2-129">これを行うには、ユーザーの表示名の左側に] をクリックしてユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="d34e2-129">To do this, select the user by clicking to the left of the user's display name.</span></span> <span data-ttu-id="d34e2-130">**設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d34e2-130">Select **Edit settings**.</span></span> <span data-ttu-id="d34e2-131">**メッセージング ポリシー**での**設定を編集**ウィンドウにドロップ ダウン リストからポリシーを選択し、し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d34e2-131">Then, on the **Edit settings** pane, under **Messaging policy**, select the policy from the drop-down list and then select **Save**.</span></span>

<span data-ttu-id="d34e2-132">複数のユーザーにポリシーを適用する場合、ユーザー名の左側をクリックすると、各ユーザーを選択し、**設定を編集**します。</span><span class="sxs-lookup"><span data-stu-id="d34e2-132">If you are applying a policy to more than one user, select each of the users by clicking to the left of the user name, and then select **Edit settings**.</span></span> <span data-ttu-id="d34e2-133">[**設定の編集**ウィンドウで、**メッセージング ポリシー**では、ドロップ ダウン リストからポリシーを選択し、[**保存**します。</span><span class="sxs-lookup"><span data-stu-id="d34e2-133">On the **Edit Settings** pane, under **Messaging policy**, select the policy from the drop-down list and then select **Save**.</span></span>

<span data-ttu-id="d34e2-134">1 つまたは複数のユーザーに次のように、メッセージング ポリシーも割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d34e2-134">You can also assign a messaging policy to one or more users as follows:</span></span>

1. <span data-ttu-id="d34e2-135">**マイクロソフトのチーム管理センター**を参照して > **メッセージング ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="d34e2-135">Go to **Microsoft Teams admin center** > **Messaging policies**.</span></span>
2. <span data-ttu-id="d34e2-136">ポリシーを選択するには、ポリシー名の左側にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d34e2-136">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="d34e2-137">**ユーザーの管理**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d34e2-137">Select **Manage users**.</span></span>
4. <span data-ttu-id="d34e2-138">**ユーザーの管理**ウィンドウで、表示名、ユーザー名、ユーザーの検索、名を選択し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d34e2-138">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="d34e2-139">追加するユーザーごとにこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d34e2-139">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="d34e2-140">ユーザーの追加が完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d34e2-140">When you are finished adding users, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="d34e2-141">ユーザーがそれに割り当てられている場合は、ポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="d34e2-141">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="d34e2-142">まず、影響を受けるすべてのユーザーに別のポリシーを割り当てる必要があり、元のポリシーを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="d34e2-142">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a><span data-ttu-id="d34e2-143">メッセージングのポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="d34e2-143">Messaging policy settings</span></span>

<span data-ttu-id="d34e2-144">グローバル メッセージング ポリシーを変更するか、新しいカスタム ポリシーを作成するには、次の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="d34e2-144">Use the following settings to change the global messaging policy or create a new custom policy:</span></span>

- <span data-ttu-id="d34e2-145">**所有者は、送信済みメッセージを削除できます。** ユーザーをチャットで送信するメッセージを削除する所有者をできるようにするのにこの設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="d34e2-145">**Owners can delete sent messages**  Use this setting to let owners delete messages that users sent in chat.</span></span>
- <span data-ttu-id="d34e2-146">**ユーザーが送信したメッセージを削除できます。** チャットで送信されるメッセージを削除できるようにするのにには、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="d34e2-146">**Users can delete sent messages** Use this setting to let users delete messages that they sent in chat.</span></span>
- <span data-ttu-id="d34e2-147">**ユーザーが送信したメッセージを編集できます。** チャットで送信するメッセージを編集できるようにするのにには、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="d34e2-147">**Users can edit sent messages** Use this setting to let users edit the messages that they sent in chat.</span></span>
- <span data-ttu-id="d34e2-148">**開封**ユーザー制御、すべてのユーザーに対して有効または無効には、この設定を指定するかどうかの開封済みメッセージを使用します。</span><span class="sxs-lookup"><span data-stu-id="d34e2-148">**Read receipts** Use this setting to specify whether read receipts are user controlled, enabled for everyone, or disabled.</span></span>
<span data-ttu-id="d34e2-149"><a name="bkchat"> </a></span><span class="sxs-lookup"><span data-stu-id="d34e2-149"></span></span>

- <span data-ttu-id="d34e2-150">**チャット** チームのアプリケーションを使用して、他のユーザーとチャットすることができる、組織内のユーザーをする場合は、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d34e2-150">**Chat**  Turn this setting on if you want users in your organization to be able to use the Teams app to chat with other people.</span></span>
- <span data-ttu-id="d34e2-151">**会話に Giphys を使用** これをオンにした場合、ユーザーは、他の人とチャットで会話 Giphys を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d34e2-151">**Use Giphys in conversations**  If you turn this on, users can include Giphys in chat conversations with other people.</span></span> <span data-ttu-id="d34e2-152">Giphy は、ユーザーがアニメーション GIF ファイルを検索および共有することができる、オンライン データベースおよび検索エンジンです。</span><span class="sxs-lookup"><span data-stu-id="d34e2-152">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="d34e2-153">各 Giphy にはコンテンツ評価が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="d34e2-153">Each Giphy is assigned a content rating.</span></span>
- <span data-ttu-id="d34e2-154">**Giphy コンテンツの規制**</span><span class="sxs-lookup"><span data-stu-id="d34e2-154">**Giphy content rating**</span></span> 
    - <span data-ttu-id="d34e2-155">**制限なし**これは、できることを意味、ユーザーがコンテンツの規制に関係なくチャットで、Giphy を挿入します。</span><span class="sxs-lookup"><span data-stu-id="d34e2-155">**No restriction** This means that your users will be able to insert any Giphy in chats regardless of the content rating.</span></span>
    - <span data-ttu-id="d34e2-156">**中程度** つまり、ユーザーがチャット、Giphys を挿入するのにはできるようになりますが、成人向けコンテンツからやや制限されています。</span><span class="sxs-lookup"><span data-stu-id="d34e2-156">**Moderate**  This means that your users will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
    - <span data-ttu-id="d34e2-157">**厳密です** つまり、ユーザーがチャット、Giphys を挿入するのにはできるようになりますが、成人向けコンテンツから厳密に制限されます。</span><span class="sxs-lookup"><span data-stu-id="d34e2-157">**Strict**  This means that your users will be able to insert Giphys in chats, but will be strictly restricted from adult content.</span></span>
- <span data-ttu-id="d34e2-158">**会話に Memes を使用**これをオンにした場合、ユーザーは、他の人とチャットで会話 Memes を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d34e2-158">**Use Memes in conversations** If you turn this on, users can include Memes in chat conversations with other people.</span></span> 
- <span data-ttu-id="d34e2-159">**会話での使用のステッカー**これをオンにした場合、ユーザーは、他の人とチャットで会話ステッカーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d34e2-159">**Use Stickers in conversations** If you turn this on, users can include Stickers in chat conversations with other people.</span></span>
- <span data-ttu-id="d34e2-160">**許可する URL のプレビュー**自動 URL でのプレビュー オン/オフ メッセージを有効にするのにには、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="d34e2-160">**Allow URL previews** Use this setting to turn automatic URL previewing on or off in messages.</span></span>
- <span data-ttu-id="d34e2-161">**ユーザーがメッセージを変換できるようにします。** 自動的にチームのメッセージを Office 365 の場合は、その個人の言語設定で指定された言語に翻訳できるようにするのにはこの設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d34e2-161">**Allow users to translate messages** Turn this setting on to let users automatically translate Teams messages into the language specified by their personal language settings for Office 365.</span></span>
- <span data-ttu-id="d34e2-162">**メッセージを表示するための没入感のリーダーを許可します。** この設定を使用すると、ユーザーにメッセージを表示する Microsoft 没入感のリーダーでオンにします。</span><span class="sxs-lookup"><span data-stu-id="d34e2-162">**Allow immersive reader for viewing messages** Turn this setting on to let users view messages in Microsoft Immersive Reader.</span></span> <span data-ttu-id="d34e2-163">没入感のリーダーは、テキストの読みやすさを向上させる経験を読み取り、全画面表示を提供する学習ツールです。</span><span class="sxs-lookup"><span data-stu-id="d34e2-163">Immersive Reader is a learning tool that provides a full screen reading experience to increase readability of text.</span></span>
- <span data-ttu-id="d34e2-164">**ユーザーは優先順位の通知を送信できます。** これをオンにした場合、ユーザーは優先順位の通知を使用してメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="d34e2-164">**Users can send priority notifications** If you turn this on, users can send a message that uses priority notifications.</span></span> <span data-ttu-id="d34e2-165">優先度の通知では、20 分、またはメッセージが選択されるまでの期間の繰り返しユーザーを通知し、メッセージがピックアップし、適切なタイミングで処理されている可能性を最大化する、受信者に開封します。</span><span class="sxs-lookup"><span data-stu-id="d34e2-165">Priority notifications notify users repeatedly for a period of 20 minutes or until messages are picked up and read by the recipient, maximizing the likelihood that the message is picked up and acted upon in a timely manner.</span></span>
- <span data-ttu-id="d34e2-166">**音声メッセージの作成**</span><span class="sxs-lookup"><span data-stu-id="d34e2-166">**Voice message creation**</span></span> 
    - <span data-ttu-id="d34e2-167">**チャットやチャンネルの許可**これは、ユーザーがチャットとチャネルの両方で音声メッセージを残すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d34e2-167">**Allowed in chats and channels** This means that users can leave voice messages in both chats and channels.</span></span>
    - <span data-ttu-id="d34e2-168">**許可のチャットのみ**これは、ユーザーおくことができます音声メッセージのチャネルではなくですが、チャットなどのことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d34e2-168">**Allowed in chats only** This means that users can leave voice messages in chats, but not in channels.</span></span>
    - <span data-ttu-id="d34e2-169">**無効になっています。** つまり、ユーザーがチャットやチャンネルにボイス メッセージを作成できません。</span><span class="sxs-lookup"><span data-stu-id="d34e2-169">**Disabled** This means that users cannot create voice messages in chats or channels.</span></span>  
- <span data-ttu-id="d34e2-170">**、モバイル デバイスで、最近のチャットの上のお気に入りのチャンネルを表示します**ユーザーがそれらを見つけるまでスクロールする必要があるように、モバイル デバイスの画面の一番上にお気に入りのチャンネルを移動するには、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d34e2-170">**On mobile devices, display favorite channels above recent chats** Enable this setting to move favorite channels to the top of the mobile device screen so that a user doesn't need to scroll to find them.</span></span> 
- <span data-ttu-id="d34e2-171">**グループ チャット ユーザーを削除するユーザーを許可します。** ユーザーがグループ チャットから他のユーザーを削除するようにするのにはこの設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d34e2-171">**Allow a user to remove users from a group chat** Turn this setting on to let a user remove other users from a group chat.</span></span> <span data-ttu-id="d34e2-172">この機能を使用して、人の小さなグループでチャットをチャットの履歴を失うことがなく続行できます。</span><span class="sxs-lookup"><span data-stu-id="d34e2-172">This feature lets you continue a chat with a smaller group of people without losing the chat history.</span></span>

### <a name="related-topics"></a><span data-ttu-id="d34e2-173">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d34e2-173">Related topics</span></span>
[<span data-ttu-id="d34e2-174">Teams での会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="d34e2-174">Meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
