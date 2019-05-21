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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.messagingpolicies.overview
description: メッセージングポリシーと、それらを使用して Teams でチャットメッセージを制御する方法について説明します。
ms.openlocfilehash: 74baed2a51f1a03ee29238da1795c67601e30ae0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298059"
---
# <a name="manage-messaging-policies-in-teams"></a><span data-ttu-id="32a4d-103">Teams のメッセージング ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="32a4d-103">Manage messaging policies in Teams</span></span>

<!--- Add zone marker here--->

<span data-ttu-id="32a4d-104">メッセージングポリシーを使って、Microsoft Teams のユーザーが利用できるチャットおよびチャネルのメッセージング機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="32a4d-104">Messaging policies are used to control which chat and channel messaging features are available to users in Microsoft Teams.</span></span> <span data-ttu-id="32a4d-105">自動的に作成される既定のポリシーを使用するか、組織内のユーザー用に1つまたは複数のカスタムメッセージポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-105">You can use the default policy that is created automatically or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="32a4d-106">ポリシーを作成したら、組織内のユーザーまたはユーザーのグループに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-106">After you create a policy, you can assign it to a user or group of users in your organization.</span></span>

<span data-ttu-id="32a4d-107">既定では、Global (org wide default) という名前のポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-107">By default, a policy named Global (org-wide default) is created.</span></span> <span data-ttu-id="32a4d-108">組織内のすべてのユーザーには、既定でこのメッセージングポリシーが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-108">All users in your organization will be assigned this messaging policy by default.</span></span> <span data-ttu-id="32a4d-109">このポリシーを変更するか、1つ以上のカスタムポリシーを作成し、ユーザーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-109">You can either make changes to this policy or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="32a4d-110">カスタムポリシーを作成するときに、特定の機能がユーザーに対して利用可能になることを許可または禁止し、設定を適用する必要がある1人以上のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-110">When you create a custom policy, you can allow or prevent certain features from being available to your users and then assign it to one or more users who will need the settings applied to them.</span></span> 

## <a name="change-or-create-a-messaging-policy"></a><span data-ttu-id="32a4d-111">メッセージングポリシーを変更または作成する</span><span class="sxs-lookup"><span data-stu-id="32a4d-111">Change or create a messaging policy</span></span>

<span data-ttu-id="32a4d-112">Microsoft Teams 管理センターでは、管理者の資格情報でhttp://admin.teams.microsoft.com)サインインし、左側のナビゲーションウィンドウで [**メッセージングポリシー** ] を選ぶことにより、メッセージポリシーを簡単に管理できます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-112">You can easily manage messaging policies in the Microsoft Teams admin center (http://admin.teams.microsoft.com) by signing in with administrator credentials and choosing **Messaging policies** in the left navigation pane.</span></span> <span data-ttu-id="32a4d-113">組織の既存の既定のメッセージポリシーを編集するには、[**グローバル (組織全体の既定)** ] 行を選択し、変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-113">To edit the existing default messaging policy for your organization, select the **Global (Org-wide default)** row, and then make your changes.</span></span> <span data-ttu-id="32a4d-114">新しいカスタムメッセージポリシーを作成するには、[**新しいポリシー**] を選び、新しいポリシーに名前を付けて、設定を選びます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-114">To create a new custom messaging policy, select **New policy**, give the new policy a name, and then select your settings.</span></span> <span data-ttu-id="32a4d-115">完了したら、[**保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-115">Choose **Save** when you are done.</span></span>

<span data-ttu-id="32a4d-116">たとえば、送信されたメッセージが削除されたり、変更されたりしないようにする必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="32a4d-116">For example, say you want to make sure that sent messages aren't deleted or altered.</span></span> <span data-ttu-id="32a4d-117">"送信済みメッセージの保持" という名前の新しいカスタムポリシーを作成して、次の設定をオフにします。</span><span class="sxs-lookup"><span data-stu-id="32a4d-117">You would create a new custom policy named "Retain sent messages" and turn off the following settings:</span></span>

- <span data-ttu-id="32a4d-118">所有者が送信したメッセージを削除できる</span><span class="sxs-lookup"><span data-stu-id="32a4d-118">Owners can delete sent messages</span></span>
- <span data-ttu-id="32a4d-119">送信したメッセージを削除できるユーザー</span><span class="sxs-lookup"><span data-stu-id="32a4d-119">Users can delete sent messages</span></span>
- <span data-ttu-id="32a4d-120">送信したメッセージをユーザーが編集できるようにする</span><span class="sxs-lookup"><span data-stu-id="32a4d-120">Users can edit sent messages</span></span>

<span data-ttu-id="32a4d-121">次に、ポリシーをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-121">Then assign the policy to the users.</span></span>

> [!NOTE] 
> <span data-ttu-id="32a4d-122">ユーザーには、一度に1つのメッセージポリシーのみを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-122">A user can only be assigned one messaging policy at a time.</span></span>
 
## <a name="assign-a-messaging-policy-to-a-user"></a><span data-ttu-id="32a4d-123">ユーザーにメッセージングポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="32a4d-123">Assign a messaging policy to a user</span></span>

<span data-ttu-id="32a4d-124">カスタムメッセージングポリシーを作成した場合、そのポリシーがユーザーに割り当てられているユーザーに対してのみアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="32a4d-124">If you create a custom messaging policy, it will only be active for a user if the policy is assigned to the user.</span></span> <span data-ttu-id="32a4d-125">ユーザーにカスタムポリシーを割り当てるには、Microsoft Teams 管理センターに移動し、左側のナビゲーションウィンドウで [**ユーザー** ] を選び、ポリシーを割り当てるユーザーを選びます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-125">To assign a custom policy to a user, go to the Microsoft Teams admin center, choose **Users** in the left navigation pane, and select the user you want to assign the policy to.</span></span> <span data-ttu-id="32a4d-126">ユーザーのページで、[**割り当てられたポリシー**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="32a4d-126">On the user's page, choose **Edit** next to **Assigned policies**.</span></span> <span data-ttu-id="32a4d-127">次に、[**ユーザーポリシーの編集**] ウィンドウの [**メッセージポリシー**] で、ドロップダウンリストからメッセージポリシーを選び、[**保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-127">Then, in the **Edit user policies** pane, under **Messaging policy**, select the messaging policy from the drop-down list, and select **Save**.</span></span> <span data-ttu-id="32a4d-128">また、ユーザーの一覧から設定を編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-128">You can also edit settings from the list of users.</span></span> <span data-ttu-id="32a4d-129">そのためには、ユーザーの表示名の左側をクリックしてユーザーを選びます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-129">To do this, select the user by clicking to the left of the user's display name.</span></span> <span data-ttu-id="32a4d-130">[**設定の編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-130">Select **Edit settings**.</span></span> <span data-ttu-id="32a4d-131">次に、[**設定の編集**] ウィンドウの [**メッセージポリシー**] で、ドロップダウンリストからポリシーを選び、[**保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-131">Then, on the **Edit settings** pane, under **Messaging policy**, select the policy from the drop-down list and then select **Save**.</span></span>

<span data-ttu-id="32a4d-132">複数のユーザーにポリシーを適用する場合は、ユーザー名の左側をクリックし、[**設定の編集**] を選択して、各ユーザーを選びます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-132">If you are applying a policy to more than one user, select each of the users by clicking to the left of the user name, and then select **Edit settings**.</span></span> <span data-ttu-id="32a4d-133">[**設定の編集**] ウィンドウの [**メッセージポリシー**] で、ドロップダウンリストからポリシーを選び、[**保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-133">On the **Edit Settings** pane, under **Messaging policy**, select the policy from the drop-down list and then select **Save**.</span></span>

<span data-ttu-id="32a4d-134">また、次のように、1人または複数のユーザーにメッセージングポリシーを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-134">You can also assign a messaging policy to one or more users as follows:</span></span>

1. <span data-ttu-id="32a4d-135">**Microsoft Teams 管理センター** > の**メッセージングポリシー**に移動します。</span><span class="sxs-lookup"><span data-stu-id="32a4d-135">Go to **Microsoft Teams admin center** > **Messaging policies**.</span></span>
2. <span data-ttu-id="32a4d-136">ポリシー名の左側をクリックして、ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="32a4d-136">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="32a4d-137">[**ユーザーの管理**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-137">Select **Manage users**.</span></span>
4. <span data-ttu-id="32a4d-138">[**ユーザーの管理**] ウィンドウで、[表示名] または [ユーザー名] でユーザーを検索し、名前を選択して [**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="32a4d-138">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="32a4d-139">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="32a4d-139">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="32a4d-140">ユーザーの追加が完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="32a4d-140">When you are finished adding users, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="32a4d-141">ポリシーは、ユーザーに割り当てられている場合は削除できません。</span><span class="sxs-lookup"><span data-stu-id="32a4d-141">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="32a4d-142">最初に、影響を受けるすべてのユーザーに別のポリシーを割り当てる必要があります。その後、元のポリシーを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-142">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a><span data-ttu-id="32a4d-143">メッセージングポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="32a4d-143">Messaging policy settings</span></span>

<span data-ttu-id="32a4d-144">グローバルメッセージポリシーを変更したり、新しいカスタムポリシーを作成するには、次の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="32a4d-144">Use the following settings to change the global messaging policy or create a new custom policy:</span></span>

- <span data-ttu-id="32a4d-145">**所有者が送信したメッセージを削除できる** この設定を使用して、ユーザーがチャットで送信したメッセージを所有者が削除できるようにします。</span><span class="sxs-lookup"><span data-stu-id="32a4d-145">**Owners can delete sent messages**  Use this setting to let owners delete messages that users sent in chat.</span></span>
- <span data-ttu-id="32a4d-146">**送信したメッセージを削除できるユーザー**この設定を使用して、ユーザーがチャットで送信したメッセージを削除できるようにします。</span><span class="sxs-lookup"><span data-stu-id="32a4d-146">**Users can delete sent messages** Use this setting to let users delete messages that they sent in chat.</span></span>
- <span data-ttu-id="32a4d-147">**送信したメッセージをユーザーが編集できるようにする**この設定を使用して、ユーザーがチャットで送信したメッセージを編集できるようにします。</span><span class="sxs-lookup"><span data-stu-id="32a4d-147">**Users can edit sent messages** Use this setting to let users edit the messages that they sent in chat.</span></span>
- <span data-ttu-id="32a4d-148">開封済み**メッセージ**この設定を使用して、開封確認メッセージをユーザーが制御するか、すべてのユーザーに対して有効にするか、無効にするかを指定します。</span><span class="sxs-lookup"><span data-stu-id="32a4d-148">**Read receipts** Use this setting to specify whether read receipts are user controlled, enabled for everyone, or disabled.</span></span>
<span data-ttu-id="32a4d-149"><a name="bkchat"> </a></span><span class="sxs-lookup"><span data-stu-id="32a4d-149"></span></span>

- <span data-ttu-id="32a4d-150">**チャット** 組織内のユーザーが Teams アプリを使って他のユーザーとチャットできるようにする場合は、この設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="32a4d-150">**Chat**  Turn this setting on if you want users in your organization to be able to use the Teams app to chat with other people.</span></span>
- <span data-ttu-id="32a4d-151">**スレッドで Giphy を使用する** これを有効にすると、ユーザーは他のユーザーとのチャット会話に Giphy を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-151">**Use Giphys in conversations**  If you turn this on, users can include Giphys in chat conversations with other people.</span></span> <span data-ttu-id="32a4d-152">Giphy は、ユーザーがアニメーション GIF ファイルを検索および共有することができる、オンライン データベースおよび検索エンジンです。</span><span class="sxs-lookup"><span data-stu-id="32a4d-152">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="32a4d-153">各 Giphy にはコンテンツ評価が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="32a4d-153">Each Giphy is assigned a content rating.</span></span>
- <span data-ttu-id="32a4d-154">**Giphy コンテンツの評価**</span><span class="sxs-lookup"><span data-stu-id="32a4d-154">**Giphy content rating**</span></span> 
    - <span data-ttu-id="32a4d-155">**制限なし**これは、コンテンツの評価に関係なく、ユーザーがチャットに Giphy を挿入できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="32a4d-155">**No restriction** This means that your users will be able to insert any Giphy in chats regardless of the content rating.</span></span>
    - <span data-ttu-id="32a4d-156">**モデレート** これは、ユーザーが Giphy をチャットに挿入できるようにすることを意味しますが、成人向けコンテンツからは適度に制限されます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-156">**Moderate**  This means that your users will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
    - <span data-ttu-id="32a4d-157">**Strict** これは、ユーザーがチャットに Giphy を挿入できることを意味しますが、成人向けコンテンツからは厳密に制限されています。</span><span class="sxs-lookup"><span data-stu-id="32a4d-157">**Strict**  This means that your users will be able to insert Giphys in chats, but will be strictly restricted from adult content.</span></span>
- <span data-ttu-id="32a4d-158">**会話で Memes を使う**これを有効にすると、ユーザーは他のユーザーとのチャット会話にメンバーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-158">**Use Memes in conversations** If you turn this on, users can include Memes in chat conversations with other people.</span></span> 
- <span data-ttu-id="32a4d-159">**会話でステッカーを使用する**これを有効にすると、ユーザーはチャットの会話に他のユーザーとのステッカーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-159">**Use Stickers in conversations** If you turn this on, users can include Stickers in chat conversations with other people.</span></span>
- <span data-ttu-id="32a4d-160">**URL プレビューを許可する**メッセージで自動 URL プレビューのオンとオフを切り替えるには、この設定を使います。</span><span class="sxs-lookup"><span data-stu-id="32a4d-160">**Allow URL previews** Use this setting to turn automatic URL previewing on or off in messages.</span></span>
- <span data-ttu-id="32a4d-161">**ユーザーにメッセージの翻訳を許可する**この設定をオンにすると、ユーザーは Office 365 の個人の言語設定で指定された言語に Teams のメッセージを自動的に翻訳できるようになります。</span><span class="sxs-lookup"><span data-stu-id="32a4d-161">**Allow users to translate messages** Turn this setting on to let users automatically translate Teams messages into the language specified by their personal language settings for Office 365.</span></span>
- <span data-ttu-id="32a4d-162">**メッセージの表示にイマーシブリーダーを許可する**この設定をオンにして、ユーザーが Microsoft イマーシブリーダーのメッセージを表示できるようにします。</span><span class="sxs-lookup"><span data-stu-id="32a4d-162">**Allow immersive reader for viewing messages** Turn this setting on to let users view messages in Microsoft Immersive Reader.</span></span> <span data-ttu-id="32a4d-163">イマーシブリーダーは、テキストの読みやすさを向上させるための全画面閲覧のエクスペリエンスを提供する学習ツールです。</span><span class="sxs-lookup"><span data-stu-id="32a4d-163">Immersive Reader is a learning tool that provides a full screen reading experience to increase readability of text.</span></span>
- <span data-ttu-id="32a4d-164">**ユーザーは優先度通知を送信できます**これを有効にすると、ユーザーは優先度通知を使用するメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-164">**Users can send priority notifications** If you turn this on, users can send a message that uses priority notifications.</span></span> <span data-ttu-id="32a4d-165">優先度通知は、20分の間、またはメッセージが受信され、受信者がメッセージを受信して、メッセージが適切なタイミングで処理される可能性を最大化するまで、ユーザーに繰り返し通知します。</span><span class="sxs-lookup"><span data-stu-id="32a4d-165">Priority notifications notify users repeatedly for a period of 20 minutes or until messages are picked up and read by the recipient, maximizing the likelihood that the message is picked up and acted upon in a timely manner.</span></span>
- <span data-ttu-id="32a4d-166">**音声メッセージの作成**</span><span class="sxs-lookup"><span data-stu-id="32a4d-166">**Voice message creation**</span></span> 
    - <span data-ttu-id="32a4d-167">**チャットとチャネルで許可**つまり、ユーザはボイスメッセージをチャットとチャネルの両方に残しておくことができます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-167">**Allowed in chats and channels** This means that users can leave voice messages in both chats and channels.</span></span>
    - <span data-ttu-id="32a4d-168">**チャットで許可されている**つまり、ユーザーは音声メッセージをチャットに残すことができますが、チャネルではそのままにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="32a4d-168">**Allowed in chats only** This means that users can leave voice messages in chats, but not in channels.</span></span>
    - <span data-ttu-id="32a4d-169">**無効**つまり、ユーザはチャットやチャンネルでボイスメッセージを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="32a4d-169">**Disabled** This means that users cannot create voice messages in chats or channels.</span></span>  
- <span data-ttu-id="32a4d-170">**モバイルデバイスでは、最近のチャットの上にお気に入りのチャンネルを表示**この設定を有効にすると、ユーザーがスクロールする必要がないように、お気に入りのチャネルをモバイルデバイスの画面の上部に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-170">**On mobile devices, display favorite channels above recent chats** Enable this setting to move favorite channels to the top of the mobile device screen so that a user doesn't need to scroll to find them.</span></span> 
- <span data-ttu-id="32a4d-171">**グループチャットからユーザーを削除することをユーザーに許可**するこの設定をオンにして、ユーザーがグループチャットから他のユーザーを削除できるようにします。</span><span class="sxs-lookup"><span data-stu-id="32a4d-171">**Allow a user to remove users from a group chat** Turn this setting on to let a user remove other users from a group chat.</span></span> <span data-ttu-id="32a4d-172">この機能を使用すると、チャット履歴を失うことなく、少人数のグループとチャットを続けることができます。</span><span class="sxs-lookup"><span data-stu-id="32a4d-172">This feature lets you continue a chat with a smaller group of people without losing the chat history.</span></span>

### <a name="related-topics"></a><span data-ttu-id="32a4d-173">関連トピック</span><span class="sxs-lookup"><span data-stu-id="32a4d-173">Related topics</span></span>
[<span data-ttu-id="32a4d-174">Teams での会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="32a4d-174">Meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
