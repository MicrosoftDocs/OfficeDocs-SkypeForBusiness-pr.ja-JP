---
title: Teams でメッセージング ポリシーを管理する
ms.author: serdars
author: SerdarSoysal
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
description: メッセージング ポリシーについて、および Teams でメッセージング ポリシーを使用してチャット メッセージングを制御する方法について取り上げます。
ms.openlocfilehash: 800bc37ee25c073d0702c519196620faa1faf92e
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574166"
---
# <a name="manage-messaging-policies-in-teams"></a><span data-ttu-id="873da-103">Teams でメッセージング ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="873da-103">Manage messaging policies in Teams</span></span>

<!--- Add zone marker here--->

<span data-ttu-id="873da-104">メッセージング ポリシーは、チャット内のユーザー (所有者とメンバー [)](assign-roles-permissions.md)が使用できるチャットおよびチャネル メッセージング機能を制御Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="873da-104">Messaging policies are used to control which chat and channel messaging features are available to [users (owners and members)](assign-roles-permissions.md) in Microsoft Teams.</span></span> <span data-ttu-id="873da-105">自動的に作成されるグローバル (組織全体の既定) ポリシーを使用するか、カスタム メッセージング ポリシーを作成して割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="873da-105">You can use the global (Org-wide default) policy that's created automatically or create and assign custom messaging policies.</span></span>

<span data-ttu-id="873da-106">カスタム ポリシーを作成して割り当てない限り、組織内のユーザーはグローバル ポリシーを自動的に取得します。</span><span class="sxs-lookup"><span data-stu-id="873da-106">Users in your organization will automatically get the global policy, unless you create and assign a custom policy.</span></span> <span data-ttu-id="873da-107">グローバル ポリシーの設定を編集するか、1 つ以上のカスタム ポリシーを作成して割り当て、必要な機能を有効またはオフにします。</span><span class="sxs-lookup"><span data-stu-id="873da-107">Edit the settings in the global policy or create and assign one or more custom policies to turn on or turn off the features that you want.</span></span>

## <a name="create-a-custom-messaging-policy"></a><span data-ttu-id="873da-108">カスタム メッセージング ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="873da-108">Create a custom messaging policy</span></span>

1. <span data-ttu-id="873da-109">管理センターの左側のMicrosoft Teams、[メッセージング ポリシー]**に移動します**。</span><span class="sxs-lookup"><span data-stu-id="873da-109">In the left navigation of the Microsoft Teams admin center, go to **Messaging policies**.</span></span>
2. <span data-ttu-id="873da-110">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="873da-110">Select **Add**.</span></span>
3. <span data-ttu-id="873da-111">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="873da-111">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="873da-112">希望する設定を選びます。</span><span class="sxs-lookup"><span data-stu-id="873da-112">Choose the settings that you want.</span></span>
5. <span data-ttu-id="873da-113">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="873da-113">Select **Save**.</span></span>

<span data-ttu-id="873da-114">たとえば、送信済みメッセージが削除または変更されていないとします。</span><span class="sxs-lookup"><span data-stu-id="873da-114">For example, you want to make sure that sent messages aren't deleted or altered.</span></span> <span data-ttu-id="873da-115">"送信メッセージを保持する" という名前の新しいカスタム ポリシーを作成し、次の設定をオフにします。</span><span class="sxs-lookup"><span data-stu-id="873da-115">Create a new custom policy named "Retain sent messages" and turn off the following settings:</span></span>

- <span data-ttu-id="873da-116">所有者が送信したメッセージを削除できます</span><span class="sxs-lookup"><span data-stu-id="873da-116">Owners can delete sent messages</span></span>
- <span data-ttu-id="873da-117">ユーザーは送信済みメッセージを削除できます</span><span class="sxs-lookup"><span data-stu-id="873da-117">Users can delete sent messages</span></span>
- <span data-ttu-id="873da-118">ユーザーが送信したメッセージを編集できます</span><span class="sxs-lookup"><span data-stu-id="873da-118">Users can edit sent messages</span></span>

<span data-ttu-id="873da-119">次に、ポリシーをユーザーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="873da-119">Then assign the policy to users.</span></span>

## <a name="edit-a-messaging-policy"></a><span data-ttu-id="873da-120">メッセージング ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="873da-120">Edit a messaging policy</span></span>

<span data-ttu-id="873da-121">グローバル ポリシーおよび作成したカスタム ポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="873da-121">You can edit the global policy and any custom policies that you create.</span></span>

1. <span data-ttu-id="873da-122">管理センターの左側のMicrosoft Teams、[メッセージング ポリシー]**に移動します**。</span><span class="sxs-lookup"><span data-stu-id="873da-122">In the left navigation of the Microsoft Teams admin center, go to **Messaging policies**.</span></span>
2. <span data-ttu-id="873da-123">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="873da-123">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>
3. <span data-ttu-id="873da-124">ここで、希望する変更を行います。</span><span class="sxs-lookup"><span data-stu-id="873da-124">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="873da-125">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="873da-125">Select **Save**.</span></span>

## <a name="assign-a-custom-messaging-policy-to-users"></a><span data-ttu-id="873da-126">カスタム メッセージング ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="873da-126">Assign a custom messaging policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="873da-127">ユーザーに割り当てることができるメッセージング ポリシーは一度に 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="873da-127">A user can only be assigned one messaging policy at a time.</span></span>

> [!NOTE]
> <span data-ttu-id="873da-128">ユーザーが割り当てられているポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="873da-128">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="873da-129">影響を受けるすべてのユーザーにまず異なるポリシーを割り当ててから、元のポリシーを削除できます。</span><span class="sxs-lookup"><span data-stu-id="873da-129">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a><span data-ttu-id="873da-130">メッセージング ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="873da-130">Messaging policy settings</span></span>

<span data-ttu-id="873da-131">構成できるメッセージング ポリシー設定を次に示します。</span><span class="sxs-lookup"><span data-stu-id="873da-131">Here are the messaging policy settings that you can configure.</span></span>

- <span data-ttu-id="873da-132">**所有者が送信したメッセージを削除できます** この設定を使用して、ユーザーがチャットで送信したメッセージを所有者が削除できるようにします。</span><span class="sxs-lookup"><span data-stu-id="873da-132">**Owners can delete sent messages**  Use this setting to let owners delete messages that users sent in chat.</span></span>
- <span data-ttu-id="873da-133">**ユーザーが送信したメッセージを削除できます** この設定を使用して、ユーザーがチャットで送信したメッセージを削除できるようにします。</span><span class="sxs-lookup"><span data-stu-id="873da-133">**Users can delete sent messages** Use this setting to let users delete messages that they sent in chat.</span></span>
- <span data-ttu-id="873da-134">**ユーザーが送信したメッセージを編集できます** この設定を使用して、ユーザーがチャットで送信したメッセージを編集できるようにします。</span><span class="sxs-lookup"><span data-stu-id="873da-134">**Users can edit sent messages** Use this setting to let users edit the messages that they sent in chat.</span></span>
- <span data-ttu-id="873da-135">**領収書の読み取り** 受信確認では、1:1 に受信者がメッセージを読み取り、20 人以下のグループ チャットを行った場合に、チャット メッセージの送信者に通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="873da-135">**Read receipts** Read receipts allow the sender of a chat message to be notified when their message was read by the recipient in 1:1 and group chats 20 people or fewer.</span></span> <span data-ttu-id="873da-136">メッセージの開封確認によって、メッセージが開封されたかどうかが明確になり、チームのコミュニケーションが向上します。</span><span class="sxs-lookup"><span data-stu-id="873da-136">Message read receipts remove uncertainly about whether a message was read, and improve team communication.</span></span> <span data-ttu-id="873da-137">電子情報開示レポートでは、読み取り確認メッセージはキャプチャされません。</span><span class="sxs-lookup"><span data-stu-id="873da-137">Read receipts aren't captured in eDiscovery reporting.</span></span>  
    - <span data-ttu-id="873da-138">**ユーザーによる制御** これは、ユーザーが開封確認の有効/無効を設定できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="873da-138">**User controlled** This means that users get to decide if they want read receipts ON or OFF.</span></span> <span data-ttu-id="873da-139">このアプリでの既定の設定は有効です。</span><span class="sxs-lookup"><span data-stu-id="873da-139">Default setting within the app is ON.</span></span> <span data-ttu-id="873da-140">ユーザーは無効にできます。</span><span class="sxs-lookup"><span data-stu-id="873da-140">Users can then turn it OFF.</span></span>
    - <span data-ttu-id="873da-141">**すべてのユーザーに対して有効 (On for everyone)** テナントのすべてのユーザーでこの機能が有効になります。無効にするオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="873da-141">**On for everyone** This means everyone in the tenant will have the feature ON with no option to turn it off.</span></span> <span data-ttu-id="873da-142">[全員に対してオン] 設定を使用する場合、テナント全体に対して 1 つのメッセージング ポリシー (既定のポリシー "グローバル (組織全体の既定)" という名前) のみを使用するか、テナント内のすべてのメッセージング ポリシーで受信確認に同じ設定を使用する方法があります。</span><span class="sxs-lookup"><span data-stu-id="873da-142">When using the **On for everyone** setting, the only way to set receipts for the whole tenant is either to have only one messaging policy for the whole tenant (the default policy named "Global (Org-wide Default)") or to have all messaging policies in the tenant use the same settings for receipts.</span></span> <span data-ttu-id="873da-143">**[すべてのユーザーに対して有効 (On for everyone)]** が有効になっている場合に、開封確認機能が最大の効果を発揮します。</span><span class="sxs-lookup"><span data-stu-id="873da-143">The read receipts feature is most effective when the feature is enabled to **On for everyone**.</span></span>
    - <span data-ttu-id="873da-144">**すべてのユーザーに対して無効 (Off for everyone)** これは、機能が無効で、テナント内でだれも開封確認を利用することも、有効にすることもできないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="873da-144">**Off for everyone** This means the feature is disabled and no one in the tenant has read receipts nor can they turn it on.</span></span>
<span data-ttu-id="873da-145"><a name="bkchat"> </a></span><span class="sxs-lookup"><span data-stu-id="873da-145"><a name="bkchat"> </a></span></span>

- <span data-ttu-id="873da-146">**チャット** 組織内のユーザーが Teams アプリを使用して他のユーザーとチャットできるようにする場合は、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="873da-146">**Chat**  Turn this setting on if you want users in your organization to be able to use the Teams app to chat with other people.</span></span>
- <span data-ttu-id="873da-147">**会話で Giphys を使用する**  Giphys を有効にした場合、ユーザーは他のユーザーとのチャット会話に Giphys を含めできます。</span><span class="sxs-lookup"><span data-stu-id="873da-147">**Use Giphys in conversations**  If you turn on Giphys, users can include Giphys in chat conversations with other people.</span></span> <span data-ttu-id="873da-148">Giphy は、ユーザーがアニメーション GIF ファイルを検索および共有することができる、オンライン データベースおよび検索エンジンです。</span><span class="sxs-lookup"><span data-stu-id="873da-148">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="873da-149">各 Giphy にはコンテンツ評価が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="873da-149">Each Giphy is assigned a content rating.</span></span> <span data-ttu-id="873da-150">この設定をオンに加えて、会話で Giphys を許可するには、オプションの接続エクスペリエンスを有効にする必要があります。 [](/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences)</span><span class="sxs-lookup"><span data-stu-id="873da-150">In addition to turning on this setting, you need to enable [Optional Connected Experiences](/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) to allow Giphys in conversations.</span></span>
- <span data-ttu-id="873da-151">**Gipsy コンテンツレーティング**</span><span class="sxs-lookup"><span data-stu-id="873da-151">**Gipsy content rating**</span></span>
    - <span data-ttu-id="873da-152">**制限なし** ユーザーは、コンテンツの評価にかかわらず、チャットに任意の Giphy を挿入できます。</span><span class="sxs-lookup"><span data-stu-id="873da-152">**No restriction** This means that your users will be able to insert any Giphy in chats regardless of the content rating.</span></span>
    - <span data-ttu-id="873da-153">**中レベル** ユーザーは、Giphy をチャットに挿入することができますが、成人向けコンテンツの挿入についてはある程度制限されます。</span><span class="sxs-lookup"><span data-stu-id="873da-153">**Moderate**  This means that your users will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
    - <span data-ttu-id="873da-154">**高レベル** ユーザーは、Giphy をチャットに挿入することができますが、成人向けコンテンツの挿入については厳格に制限されます。</span><span class="sxs-lookup"><span data-stu-id="873da-154">**Strict**  This means that your users will be able to insert Giphys in chats, but will be strictly restricted from adult content.</span></span>
- <span data-ttu-id="873da-155">**会話でミームを使用する** ミームを有効にした場合、ユーザーは他のユーザーとのチャット会話にミームを含めできます。</span><span class="sxs-lookup"><span data-stu-id="873da-155">**Use Memes in conversations** If you turn Memes on, users can include Memes in chat conversations with other people.</span></span>
- <span data-ttu-id="873da-156">\*\*会話でステッカーを使用する。</span><span class="sxs-lookup"><span data-stu-id="873da-156">\*\*Use Stickers in conversations.</span></span> <span data-ttu-id="873da-157">これを有効にした場合、ユーザーは他のユーザーとのチャット会話にステッカーを含めできます。</span><span class="sxs-lookup"><span data-stu-id="873da-157">If you turn this on, users can include Stickers in chat conversations with other people.</span></span>
- <span data-ttu-id="873da-158">**URL のプレビューを許可する** この設定を使用すると、メッセージでの URL の自動プレビューの有効/無効を切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="873da-158">**Allow URL previews** Use this setting to turn automatic URL previewing on or off in messages.</span></span>
- <span data-ttu-id="873da-159">**ユーザーにメッセージの翻訳を許可する** この設定をオンにすると、ユーザーは、Teams またはユーザーの個人の言語設定で指定された言語にメッセージを自動的Microsoft 365翻訳Office 365。</span><span class="sxs-lookup"><span data-stu-id="873da-159">**Allow users to translate messages** Turn this setting on to let users automatically translate Teams messages into the language specified by their personal language settings for Microsoft 365 or Office 365.</span></span>
- <span data-ttu-id="873da-160">**イマーシブ リーダーにメッセージの表示を許可します** この設定を有効にすると、Microsoft イマーシブ リーダーでユーザーはメッセージを表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="873da-160">**Allow immersive reader for viewing messages** Turn this setting on to let users view messages in Microsoft Immersive Reader.</span></span> <span data-ttu-id="873da-161">イマーシブ リーダーは、テキストの読みやすさを向上させるための全画面閲覧エクスペリエンスを備えた学習ツールです。</span><span class="sxs-lookup"><span data-stu-id="873da-161">Immersive Reader is a learning tool that provides a full screen reading experience to increase readability of text.</span></span>
- <span data-ttu-id="873da-162">**優先度通知を使用して緊急メッセージを送信する** これを有効にした場合、ユーザーは優先度通知 を使用して [メッセージを送信できます](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462)。</span><span class="sxs-lookup"><span data-stu-id="873da-162">**Send urgent messages using priority notifications** If you turn this on, users can send messages using [priority notifications](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462).</span></span> <span data-ttu-id="873da-163">優先度通知は、2 分ごとに 20 分間、または緊急とマークされたメッセージが受信者によって取得および読み上げされるまで、ユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="873da-163">Priority notifications notify users every 2 minutes for 20 minutes or until messages that are marked as *urgent* are picked up and read by the recipient.</span></span> <span data-ttu-id="873da-164">この機能は、メッセージが時に応じて処理される可能性を高めます。</span><span class="sxs-lookup"><span data-stu-id="873da-164">This feature increases the likelihood that the message is acted upon in a timely manner.</span></span>
- <span data-ttu-id="873da-165">**オーディオ メッセージの作成**</span><span class="sxs-lookup"><span data-stu-id="873da-165">**Audio message creation**</span></span>
  > [!Important]
  > <span data-ttu-id="873da-166">電子情報開示レポートでは、オーディオ メッセージはキャプチャされません。</span><span class="sxs-lookup"><span data-stu-id="873da-166">Audio messages are not captured in eDiscovery reporting.</span></span>
    - <span data-ttu-id="873da-167">**チャットとチャネルで許可** ユーザーは音声メッセージをチャットとチャネルでそのままの状態にできます。</span><span class="sxs-lookup"><span data-stu-id="873da-167">**Allowed in chats and channels** This means that users can leave audio messages in both chats and channels.</span></span>
    - <span data-ttu-id="873da-168">**チャットでのみ許可** ユーザーは音声メッセージをチャットでそのままの状態にできますが、チャネルでは許可されません。</span><span class="sxs-lookup"><span data-stu-id="873da-168">**Allowed in chats only** This means that users can leave audio messages in chats, but not in channels.</span></span>
    - <span data-ttu-id="873da-169">**無効** ユーザーはチャットとチャネルのどちらにおいても音声メッセージを作成できません。</span><span class="sxs-lookup"><span data-stu-id="873da-169">**Disabled** This means that users cannot create audio messages in chats or channels.</span></span>  
- <span data-ttu-id="873da-170">**モバイル デバイスで最近のチャットの上にお気に入りのチャネルを表示する** この設定を有効にすると、お気に入りのチャネルがモバイル デバイスの上部に移動し、ユーザーはスクロールしないでも確認できます。</span><span class="sxs-lookup"><span data-stu-id="873da-170">**On mobile devices, display favorite channels above recent chats** Enable this setting to move favorite channels to the top of the mobile device screen so that a user doesn't need to scroll to find them.</span></span>
- <span data-ttu-id="873da-171">**ユーザーによるグループ チャットからのユーザーの削除を許可する** この設定を有効にすると、ユーザーはグループ チャットから他のユーザーを削除できるようになります。</span><span class="sxs-lookup"><span data-stu-id="873da-171">**Allow a user to remove users from a group chat** Turn this setting on to let a user remove other users from a group chat.</span></span> <span data-ttu-id="873da-172">この機能を使用すると、チャット履歴を失うことなく、グループ ユーザーの人数を減らしてチャットを続けることができます。</span><span class="sxs-lookup"><span data-stu-id="873da-172">This feature lets you continue a chat with a smaller group of people without losing the chat history.</span></span>
- <span data-ttu-id="873da-173">**返信候補を有効にする**  この設定をオンにすると、チャット メッセージに対する返信候補が有効にされます。</span><span class="sxs-lookup"><span data-stu-id="873da-173">**Enable suggested replies**  Turn this setting on to enable suggested replies for chat messages.</span></span>
- <span data-ttu-id="873da-174">**チャットのアクセス許可ロール** この設定を使用して、ユーザーの教師ありチャット ロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="873da-174">**Chat permission role** Use this setting to define the supervised chat role of the user.</span></span>  <span data-ttu-id="873da-175">[監視付きチャット](supervise-chats-edu.md)の詳細をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="873da-175">Learn more about [supervised chat](supervise-chats-edu.md).</span></span>

> [!NOTE]
> <span data-ttu-id="873da-176">Giphys などの一部の設定は、チームの所有者がチーム レベルで、プライベート チャネルの所有者がプライベート チャネル レベルでも構成できます。</span><span class="sxs-lookup"><span data-stu-id="873da-176">Some of these settings, such using Giphys, can also be configured at the team level by team owners and at the private channel level by private channel owners.</span></span>

### <a name="related-topics"></a><span data-ttu-id="873da-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="873da-177">Related topics</span></span>

- [<span data-ttu-id="873da-178">グループ内のユーザーとグループにポリシーを割り当Teams</span><span class="sxs-lookup"><span data-stu-id="873da-178">Assign policies to users and groups in Teams</span></span>](assign-policies-users-and-groups.md)
- [<span data-ttu-id="873da-179">Microsoft Teams でチーム所有者とメンバーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="873da-179">Assign team owners and members in Microsoft Teams</span></span>](assign-roles-permissions.md)
