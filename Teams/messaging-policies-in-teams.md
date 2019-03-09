---
title: メッセージング ポリシーを管理する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.messagingpolicies.overview
- ms.teamsadmincenter.messagingpolicies.settings.chat
description: メッセージング ポリシーとそれらを使用してメッセージング チームのチャットを制御する方法について説明します。
ms.openlocfilehash: 69097888038699b8d30084598fcf411fe0f97dc2
ms.sourcegitcommit: f3b41e7abafc84571bd9e8267d41decc0fe78e4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "30494102"
---
# <a name="what-are-messaging-policies-in-teams"></a><span data-ttu-id="58809-103">Teams でのメッセージング ポリシーについて</span><span class="sxs-lookup"><span data-stu-id="58809-103">What are Messaging policies in Teams?</span></span>  

::: zone target="docs"
<span data-ttu-id="58809-104">メッセージング ポリシーは、マイクロソフトのチームのユーザーに利用するチャットとチャネルのメッセージング機能を制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="58809-104">Messaging policies are used to control which chat and channel messaging features are available to users in Microsoft Teams.</span></span> <span data-ttu-id="58809-105">作成されるか、組織内の 1 つまたは複数のカスタム メッセージング ポリシーを作成する既定のポリシーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="58809-105">You can use the default policy that is created or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="58809-106">ポリシーを作成したら、割り当てる、ユーザーまたはユーザー グループ、組織内。</span><span class="sxs-lookup"><span data-stu-id="58809-106">After you create a policy, you will assign it a user or groups of users in your organization.</span></span>

<span data-ttu-id="58809-107">マイクロソフトのチーム管理センターのポリシーを簡単に管理することができます (http://admin.teams.microsoft.com)管理者の資格情報でログインし、左側のナビゲーション ウィンドウで、**メッセージング ポリシー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="58809-107">Policies can be easily managed in the Microsoft Teams admin center (http://admin.teams.microsoft.com) by logging in with administrator credentials and choosing **Messaging Policies** in the left navigation pane.</span></span> 

![チームでのメッセージングのポリシー](media/messaging-policies-image1.png)

<span data-ttu-id="58809-109">組織の既存の既定のメッセージング ポリシーを編集するに**グローバル (組織全体の既定値)** の行をクリックし、変更してください。</span><span class="sxs-lookup"><span data-stu-id="58809-109">To edit the existing default Messaging policy for your organization, click the **Global (Org-wide default)** row, and then make your changes.</span></span> <span data-ttu-id="58809-110">新しいカスタム メッセージング ポリシーを作成するには、[**新しいポリシー** ] をクリックし、設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="58809-110">To create a new custom messaging policy, click **New policy** and select your settings.</span></span> <span data-ttu-id="58809-111">したら**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="58809-111">Choose **Save** when you are done.</span></span>

![チームでのメッセージングのポリシー設定](media/messaging-policies-image2.png)
::: zone-end  
::: zone target="chromeless"
<span data-ttu-id="58809-113">グローバル メッセージング ポリシーを変更するか、新しいカスタム ポリシーを作成するには、次の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="58809-113">Use the following settings to change the global Messaging policy or create a new custom policy:</span></span>

- <span data-ttu-id="58809-114">**所有者は、送信済みメッセージを削除できます。** ユーザーをチャットで送信するメッセージを削除する所有者をできるようにするのにこの設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="58809-114">**Owners can delete sent messages**  Use this setting to let owners delete messages that users sent in chat.</span></span>
- <span data-ttu-id="58809-115">**ユーザーが送信したメッセージを削除できます。** チャットで送信されるメッセージを削除できるようにするのにには、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="58809-115">**Users can delete sent messages** Use this setting to let users delete messages that they sent in chat.</span></span>
- <span data-ttu-id="58809-116">**ユーザーが送信したメッセージを編集できます。** チャットで送信するメッセージを編集できるようにするのにには、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="58809-116">**Users can edit sent messages** Use this setting to let users edit the messages that they sent in chat.</span></span>
- <span data-ttu-id="58809-117">**開封**ユーザー制御、すべてのユーザーに対して有効または無効には、この設定を指定するかどうかの開封済みメッセージを使用します。</span><span class="sxs-lookup"><span data-stu-id="58809-117">**Read receipts** Use this setting to specify whether read receipts are user controlled, enabled for everyone, or disabled.</span></span>

<span data-ttu-id="58809-118"><a name="bkchat"> </a></span><span class="sxs-lookup"><span data-stu-id="58809-118"></span></span>

- <span data-ttu-id="58809-119">**チャット** チームのアプリケーションを使用して、他のユーザーとチャットすることができる、組織内のユーザーをする場合は、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="58809-119">**Chat**  Turn this setting on if you want users in your organization to be able to use the Teams app to chat with other people.</span></span>
- <span data-ttu-id="58809-120">**会話に Giphys を使用** これをオンにした場合、ユーザーは、他の人とチャットで会話 Giphys を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="58809-120">**Use Giphys in conversations**  If you turn this on, users can include Giphys in chat conversations with other people.</span></span> <span data-ttu-id="58809-121">Giphy は、ユーザーがアニメーション GIF ファイルを検索および共有することができる、オンライン データベースおよび検索エンジンです。</span><span class="sxs-lookup"><span data-stu-id="58809-121">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="58809-122">各 Giphy にはコンテンツ評価が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="58809-122">Each Giphy is assigned a content rating.</span></span>
- <span data-ttu-id="58809-123">**Giphy コンテンツの規制**</span><span class="sxs-lookup"><span data-stu-id="58809-123">**Giphy content rating**</span></span> 
    - <span data-ttu-id="58809-124">**制限なし**これは、できることを意味、ユーザーがコンテンツの規制に関係なくチャットで、Giphy を挿入します。</span><span class="sxs-lookup"><span data-stu-id="58809-124">**No restriction** This means that your users will be able to insert any Giphy in chats regardless of the content rating.</span></span>
    - <span data-ttu-id="58809-125">**中程度** つまり、ユーザーがチャット、Giphys を挿入するのにはできるようになりますが、成人向けコンテンツからやや制限されています。</span><span class="sxs-lookup"><span data-stu-id="58809-125">**Moderate**  This means that your users will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
    - <span data-ttu-id="58809-126">**厳密です** つまり、ユーザーがチャット、Giphys を挿入するのにはできるようになりますが、成人向けコンテンツから厳密に制限されます。</span><span class="sxs-lookup"><span data-stu-id="58809-126">**Strict**  This means that your users will be able to insert Giphys in chats, but will be strictly restricted from adult content.</span></span>
- <span data-ttu-id="58809-127">**会話に Memes を使用**これをオンにした場合、ユーザーは、他の人とチャットで会話 Memes を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="58809-127">**Use Memes in conversations** If you turn this on, users can include Memes in chat conversations with other people.</span></span> 
- <span data-ttu-id="58809-128">**会話での使用のステッカー**これをオンにした場合、ユーザーは、他の人とチャットで会話ステッカーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="58809-128">**Use Stickers in conversations** If you turn this on, users can include Stickers in chat conversations with other people.</span></span>
- <span data-ttu-id="58809-129">**許可する URL のプレビュー**自動 URL でのプレビュー オン/オフ メッセージを有効にするのにには、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="58809-129">**Allow URL previews** Use this setting to turn automatic URL previewing on or off in messages.</span></span>
- <span data-ttu-id="58809-130">**ユーザーがメッセージを変換できるようにします。** 自動的にチームのメッセージを Office 365 の場合は、その個人の言語設定で指定された言語に翻訳できるようにするのにはこの設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="58809-130">**Allow users to translate messages** Turn this setting on to let users automatically translate Teams messages into the language specified by their personal language settings for Office 365.</span></span> 

[<span data-ttu-id="58809-131">記事の全文</span><span class="sxs-lookup"><span data-stu-id="58809-131">Full article</span></span>](messaging-policies-in-teams.md)
::: zone-end

::: zone target="docs"
<span data-ttu-id="58809-132">カスタム メッセージング ポリシーを作成した場合にのみアクティブになるユーザーのポリシーがユーザーに割り当てられている場合。</span><span class="sxs-lookup"><span data-stu-id="58809-132">If you have created a custom Messaging policy, it will only be active for a user if that policy is assigned to a user.</span></span> <span data-ttu-id="58809-133">マイクロソフト チームの管理センターのユーザーに割り当てるカスタム ポリシーには、左側のナビゲーションで**ユーザー**を選択をするようにポリシーを割り当てるユーザーを選択できます。</span><span class="sxs-lookup"><span data-stu-id="58809-133">To assign a custom policy to a user in the Microsoft Teams admin center, choose **Users** in the left navigation, and select the user you want to assign the policy to.</span></span> <span data-ttu-id="58809-134">ユーザーのページでは、**ポリシーの割り当て**] の横の**編集**を選択します。</span><span class="sxs-lookup"><span data-stu-id="58809-134">On the user's page, choose **Edit** next to **Assigned Policies**.</span></span>
::: zone-end

### <a name="related-topics"></a><span data-ttu-id="58809-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="58809-135">Related topics</span></span>
[<span data-ttu-id="58809-136">Teams での会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="58809-136">Meeting policies in Teams</span></span>](meeting-policies-in-teams.md)



