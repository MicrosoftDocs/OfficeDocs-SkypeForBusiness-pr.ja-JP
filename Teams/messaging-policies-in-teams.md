---
title: Teams でメッセージング ポリシーを管理する
ms.author: lolaj
author: lolajacobsen
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.messagingpolicies.overview
- seo-marvel-apr2020
description: この記事では、メッセージングポリシーと、それらを使用して Teams でチャットメッセージングを制御する方法について説明します。
ms.openlocfilehash: c29697c8ec4d235ed232616e34590351bea59e9e
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2020
ms.locfileid: "45042979"
---
# <a name="manage-messaging-policies-in-teams"></a><span data-ttu-id="1dc3b-103">Teams でメッセージング ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="1dc3b-103">Manage messaging policies in Teams</span></span>

<!--- Add zone marker here--->

<span data-ttu-id="1dc3b-104">メッセージング ポリシーを使用して、Microsoft Teams のユーザーが、チャットおよびチャネルのどのメッセージング機能を使用できるかを制御します。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-104">Messaging policies are used to control which chat and channel messaging features are available to users in Microsoft Teams.</span></span> <span data-ttu-id="1dc3b-105">自動的に作成されるグローバル (組織全体の既定) ポリシーを使用するか、またはカスタムメッセージングポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-105">You can use the global (Org-wide default) policy that's created automatically or create and assign custom messaging policies.</span></span>

<span data-ttu-id="1dc3b-106">カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-106">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="1dc3b-107">グローバルポリシーの設定を編集するか、1つまたは複数のカスタムポリシーを作成して割り当てることで、必要な機能を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-107">You can edit the settings in the global policy or create and assign one or more custom policies to turn on or turn off the features that you want.</span></span>

## <a name="create-a-custom-messaging-policy"></a><span data-ttu-id="1dc3b-108">カスタムメッセージングポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="1dc3b-108">Create a custom messaging policy</span></span>

1. <span data-ttu-id="1dc3b-109">Microsoft Teams 管理センターの左のナビゲーションで、[**メッセージングポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-109">In the left navigation of the Microsoft Teams admin center, go to **Messaging policies**.</span></span>
2. <span data-ttu-id="1dc3b-110">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-110">Click **Add**.</span></span>
3. <span data-ttu-id="1dc3b-111">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-111">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="1dc3b-112">目的の設定を選びます。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-112">Choose the settings that you want.</span></span>
5. <span data-ttu-id="1dc3b-113">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-113">Click **Save**.</span></span>

<span data-ttu-id="1dc3b-114">たとえば、送信したメッセージが削除されたり、変更されたりしないようにしたいとします。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-114">For example, say you want to make sure that sent messages aren't deleted or altered.</span></span> <span data-ttu-id="1dc3b-115">"送信済みメッセージの保持" という名前の新しいカスタムポリシーを作成し、次の設定をオフにします。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-115">Create a new custom policy named "Retain sent messages" and turn off the following settings:</span></span>

- <span data-ttu-id="1dc3b-116">所有者が送信したメッセージを削除できます</span><span class="sxs-lookup"><span data-stu-id="1dc3b-116">Owners can delete sent messages</span></span>
- <span data-ttu-id="1dc3b-117">ユーザーは送信済みメッセージを削除できます</span><span class="sxs-lookup"><span data-stu-id="1dc3b-117">Users can delete sent messages</span></span>
- <span data-ttu-id="1dc3b-118">ユーザーが送信したメッセージを編集できます</span><span class="sxs-lookup"><span data-stu-id="1dc3b-118">Users can edit sent messages</span></span>

<span data-ttu-id="1dc3b-119">次に、ポリシーをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-119">Then assign the policy to users.</span></span>

## <a name="edit-a-messaging-policy"></a><span data-ttu-id="1dc3b-120">メッセージングポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="1dc3b-120">Edit a messaging policy</span></span>

<span data-ttu-id="1dc3b-121">グローバルポリシーは、作成した任意のカスタムポリシーで編集できます。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-121">You can edit the global policy an any custom policies that you create.</span></span> 

1. <span data-ttu-id="1dc3b-122">Microsoft Teams 管理センターの左のナビゲーションで、[**メッセージングポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-122">In the left navigation of the Microsoft Teams admin center, go to **Messaging policies**.</span></span>
2. <span data-ttu-id="1dc3b-123">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-123">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="1dc3b-124">ここで、必要な変更を行います。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-124">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="1dc3b-125">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-125">Click **Save**.</span></span>

## <a name="assign-a-custom-messaging-policy-to-users"></a><span data-ttu-id="1dc3b-126">ユーザーにカスタムメッセージングポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1dc3b-126">Assign a custom messaging policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="1dc3b-127">ユーザーに割り当てることができるメッセージング ポリシーは一度に 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-127">A user can only be assigned one messaging policy at a time.</span></span>

> [!NOTE]
> <span data-ttu-id="1dc3b-128">ユーザーが割り当てられているポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-128">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="1dc3b-129">影響を受けるすべてのユーザーにまず異なるポリシーを割り当ててから、元のポリシーを削除できます。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-129">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a><span data-ttu-id="1dc3b-130">メッセージング ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="1dc3b-130">Messaging policy settings</span></span>

<span data-ttu-id="1dc3b-131">次に、構成できるメッセージングポリシーの設定を示します。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-131">Here are the messaging policy settings that you can configure.</span></span>

- <span data-ttu-id="1dc3b-132">**所有者が送信したメッセージを削除できます** この設定を使用して、ユーザーがチャットで送信したメッセージを所有者が削除できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-132">**Owners can delete sent messages**  Use this setting to let owners delete messages that users sent in chat.</span></span>
- <span data-ttu-id="1dc3b-133">**ユーザーが送信したメッセージを削除できます** この設定を使用して、ユーザーがチャットで送信したメッセージを削除できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-133">**Users can delete sent messages** Use this setting to let users delete messages that they sent in chat.</span></span>
- <span data-ttu-id="1dc3b-134">**ユーザーが送信したメッセージを編集できます** この設定を使用して、ユーザーがチャットで送信したメッセージを編集できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-134">**Users can edit sent messages** Use this setting to let users edit the messages that they sent in chat.</span></span>
- <span data-ttu-id="1dc3b-135">**開封確認** 開封確認を使うと、チャット メッセージの送信者は、1:1 の受信者および 20 人以下のグループ チャットによってメッセージが開封された場合に通知を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-135">**Read receipts** Read receipts allow the sender of a chat message to be notified when their message was read by the recipient in 1:1 and group chats 20 people or less.</span></span> <span data-ttu-id="1dc3b-136">メッセージの開封確認によって、メッセージが開封されたかどうかが明確になり、チームのコミュニケーションが向上します。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-136">Message read receipts remove uncertainly about whether a message was read, and improve team communication.</span></span> <span data-ttu-id="1dc3b-137">開封確認は電子情報開示レポートでは収集されません。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-137">Please note that read receipts are not captured in eDiscovery reporting.</span></span>  
    - <span data-ttu-id="1dc3b-138">**ユーザーによる制御** これは、ユーザーが開封確認の有効/無効を設定できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-138">**User controlled** This means that users get to decide if they want read receipts ON or OFF.</span></span> <span data-ttu-id="1dc3b-139">このアプリでの既定の設定は有効です。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-139">Default setting within the app is ON.</span></span> <span data-ttu-id="1dc3b-140">ユーザーは無効にできます。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-140">Users can then turn it OFF.</span></span>
    - <span data-ttu-id="1dc3b-141">**すべてのユーザーに対して有効 (On for everyone)** テナントのすべてのユーザーでこの機能が有効になります。無効にするオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-141">**On for everyone** This means everyone in the tenant will have the feature ON with no option to turn it off.</span></span> <span data-ttu-id="1dc3b-142">**[すべてのユーザーに対して有効 (On for everyone)]** 設定を使用する場合、テナント全体の確認メッセージを設定する唯一の方法は、テナント全体用に 1 つのメッセージング ポリシー (「グローバル (組織全体の既定値)」という名前の既定ポリシー) を設定するか、テナントのすべてのメッセージング ポリシーで確認メッセージに関して同じ設定を使用するという方法のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-142">Be aware that when using the **On for everyone** setting, the only way to set receipts for the whole tenant is either to have only one messaging policy for the whole tenant (the default policy named "Global (Org-wide Default)") or to have all messaging policies in the tenant use the same settings for receipts.</span></span> <span data-ttu-id="1dc3b-143">**[すべてのユーザーに対して有効 (On for everyone)]** が有効になっている場合に、開封確認機能が最大の効果を発揮します。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-143">The read receipts feature is most effective when the feature is enabled to **On for everyone**.</span></span>
    - <span data-ttu-id="1dc3b-144">**すべてのユーザーに対して無効 (Off for everyone)** これは、機能が無効で、テナント内でだれも開封確認を利用することも、有効にすることもできないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-144">**Off for everyone** This means the feature is disabled and no one in the tenant has read receipts nor can they turn it on.</span></span>
<span data-ttu-id="1dc3b-145"><a name="bkchat"> </a></span><span class="sxs-lookup"><span data-stu-id="1dc3b-145"><a name="bkchat"> </a></span></span>

- <span data-ttu-id="1dc3b-146">**チャット** 組織内のユーザーが Teams アプリを使用して他のユーザーとチャットできるようにする場合は、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-146">**Chat**  Turn this setting on if you want users in your organization to be able to use the Teams app to chat with other people.</span></span>
- <span data-ttu-id="1dc3b-147">**会話で Giphys を使用** 有効にすると、ユーザーは他のユーザーとのチャット会話に Giphys を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-147">**Use Giphys in conversations**  If you turn this on, users can include Giphys in chat conversations with other people.</span></span> <span data-ttu-id="1dc3b-148">Giphy は、ユーザーがアニメーション GIF ファイルを検索および共有することができる、オンライン データベースおよび検索エンジンです。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-148">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="1dc3b-149">各 Giphy にはコンテンツ評価が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-149">Each Giphy is assigned a content rating.</span></span>
- <span data-ttu-id="1dc3b-150">**Giphy コンテンツの評価**</span><span class="sxs-lookup"><span data-stu-id="1dc3b-150">**Giphy content rating**</span></span>
    - <span data-ttu-id="1dc3b-151">**制限なし** ユーザーは、コンテンツの評価にかかわらず、チャットに任意の Giphy を挿入できます。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-151">**No restriction** This means that your users will be able to insert any Giphy in chats regardless of the content rating.</span></span>
    - <span data-ttu-id="1dc3b-152">**中レベル** ユーザーは、Giphy をチャットに挿入することができますが、成人向けコンテンツの挿入についてはある程度制限されます。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-152">**Moderate**  This means that your users will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
    - <span data-ttu-id="1dc3b-153">**高レベル** ユーザーは、Giphy をチャットに挿入することができますが、成人向けコンテンツの挿入については厳格に制限されます。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-153">**Strict**  This means that your users will be able to insert Giphys in chats, but will be strictly restricted from adult content.</span></span>
- <span data-ttu-id="1dc3b-154">**会議で Memes を使用** 有効にすると、ユーザーは他のユーザーとのチャット会話に Memes を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-154">**Use Memes in conversations** If you turn this on, users can include Memes in chat conversations with other people.</span></span>
- <span data-ttu-id="1dc3b-155">**会話でステッカーを使用** 有効にすると、ユーザーは他のユーザーとのチャット会話にステッカーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-155">**Use Stickers in conversations** If you turn this on, users can include Stickers in chat conversations with other people.</span></span>
- <span data-ttu-id="1dc3b-156">**URL のプレビューを許可する** この設定を使用すると、メッセージでの URL の自動プレビューの有効/無効を切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-156">**Allow URL previews** Use this setting to turn automatic URL previewing on or off in messages.</span></span>
- <span data-ttu-id="1dc3b-157">**ユーザーにメッセージの翻訳を許可する**この設定をオンにすると、ユーザーは Microsoft 365 または Office 365 の個人の言語設定で指定された言語に Teams のメッセージを自動的に翻訳できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-157">**Allow users to translate messages** Turn this setting on to let users automatically translate Teams messages into the language specified by their personal language settings for Microsoft 365 or Office 365.</span></span>
- <span data-ttu-id="1dc3b-158">**イマーシブ リーダーにメッセージの表示を許可します** この設定を有効にすると、Microsoft イマーシブ リーダーでユーザーはメッセージを表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-158">**Allow immersive reader for viewing messages** Turn this setting on to let users view messages in Microsoft Immersive Reader.</span></span> <span data-ttu-id="1dc3b-159">イマーシブ リーダーは、テキストの読みやすさを向上させるための全画面閲覧エクスペリエンスを備えた学習ツールです。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-159">Immersive Reader is a learning tool that provides a full screen reading experience to increase readability of text.</span></span>
- <span data-ttu-id="1dc3b-160">**優先度通知を使って緊急メッセージを送信する**これを有効にすると、ユーザーは[優先度通知](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462)を使ってメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-160">**Send urgent messages using priority notifications** If you turn this on, users can send messages using [priority notifications](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462).</span></span> <span data-ttu-id="1dc3b-161">優先度通知は、2分間隔で20分間、または*緊急*とマークされているメッセージが受信者によって受信され、メッセージが適切なタイミングで処理される可能性を最大化するまで、ユーザーに通知されます。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-161">Priority notifications notify users every 2 minutes for a period of 20 minutes or until messages that are marked as *urgent* are picked up and read by the recipient, maximizing the likelihood that the message is acted upon in a timely manner.</span></span>
- <span data-ttu-id="1dc3b-162">**オーディオメッセージの作成**</span><span class="sxs-lookup"><span data-stu-id="1dc3b-162">**Audio message creation**</span></span> 
  > [!Important]
  > <span data-ttu-id="1dc3b-163">音声メッセージは、電子情報開示レポートではキャプチャされません。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-163">Audio messages are not captured in eDiscovery reporting.</span></span>
    - <span data-ttu-id="1dc3b-164">**チャットとチャネルで許可** ユーザーは音声メッセージをチャットとチャネルでそのままの状態にできます。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-164">**Allowed in chats and channels** This means that users can leave audio messages in both chats and channels.</span></span>
    - <span data-ttu-id="1dc3b-165">**チャットでのみ許可** ユーザーは音声メッセージをチャットでそのままの状態にできますが、チャネルでは許可されません。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-165">**Allowed in chats only** This means that users can leave audio messages in chats, but not in channels.</span></span>
    - <span data-ttu-id="1dc3b-166">**無効** ユーザーはチャットとチャネルのどちらにおいても音声メッセージを作成できません。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-166">**Disabled** This means that users cannot create audio messages in chats or channels.</span></span>  
- <span data-ttu-id="1dc3b-167">**モバイル デバイスで最近のチャットの上にお気に入りのチャネルを表示する** この設定を有効にすると、お気に入りのチャネルがモバイル デバイスの上部に移動し、ユーザーはスクロールしないでも確認できます。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-167">**On mobile devices, display favorite channels above recent chats** Enable this setting to move favorite channels to the top of the mobile device screen so that a user doesn't need to scroll to find them.</span></span>
- <span data-ttu-id="1dc3b-168">**ユーザーによるグループ チャットからのユーザーの削除を許可する** この設定を有効にすると、ユーザーはグループ チャットから他のユーザーを削除できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-168">**Allow a user to remove users from a group chat** Turn this setting on to let a user remove other users from a group chat.</span></span> <span data-ttu-id="1dc3b-169">この機能を使用すると、チャット履歴を失うことなく、グループ ユーザーの人数を減らしてチャットを続けることができます。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-169">This feature lets you continue a chat with a smaller group of people without losing the chat history.</span></span>
- <span data-ttu-id="1dc3b-170">**返信の候補を有効にする** チャットメッセージの返信の候補を有効にするには、この設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-170">**Enable suggested replies**  Turn this setting on to enable suggested replies for chat messages.</span></span>

> [!NOTE]
> <span data-ttu-id="1dc3b-171">Giphys などの一部の設定は、チームの所有者がチーム レベルで、プライベート チャネルの所有者がプライベート チャネル レベルでも構成できます。</span><span class="sxs-lookup"><span data-stu-id="1dc3b-171">Some of these settings, such using Giphys, can also be configured at the team level by team owners and at the private channel level by private channel owners.</span></span>

### <a name="related-topics"></a><span data-ttu-id="1dc3b-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="1dc3b-172">Related topics</span></span>

- [<span data-ttu-id="1dc3b-173">チームのユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1dc3b-173">Assign policies to your users in Teams</span></span>](assign-policies.md)
