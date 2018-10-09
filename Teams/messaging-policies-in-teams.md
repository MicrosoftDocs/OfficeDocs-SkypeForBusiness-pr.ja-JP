---
title: チーム内のポリシーをメッセージングは何でしょうか。
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
ms.openlocfilehash: 7b9cb8a6a5c30806d44f5056e4dee0de79823841
ms.sourcegitcommit: c6b62a64d198fe18ae53cf849d125c5143053456
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2018
ms.locfileid: "25453795"
---
# <a name="what-are-messaging-policies-in-teams"></a><span data-ttu-id="725fd-103">チーム内のポリシーをメッセージングは何でしょうか。</span><span class="sxs-lookup"><span data-stu-id="725fd-103">What are Messaging policies in Teams?</span></span>

<span data-ttu-id="725fd-104">メッセージング ポリシーは、マイクロソフトのチームのユーザーに利用するチャットとチャネルのメッセージング機能を制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="725fd-104">Messaging policies are used to control which chat and channel messaging features are available to users in Microsoft Teams.</span></span> <span data-ttu-id="725fd-105">作成されるか、組織内の 1 つまたは複数のカスタム メッセージング ポリシーを作成する既定のポリシーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="725fd-105">You can use the default policy that is created or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="725fd-106">ポリシーを作成したら、割り当てる、ユーザーまたはユーザー グループ、組織内。</span><span class="sxs-lookup"><span data-stu-id="725fd-106">After you create a policy, you will assign it a user or groups of users in your organization.</span></span>

<span data-ttu-id="725fd-107">チーム管理センターのポリシーを簡単に管理することができます (http://admin.teams.microsoft.com)管理者の資格情報でログインし、左側のナビゲーションで**メッセージング ポリシー** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="725fd-107">Policies can be easily managed in the Teams Admin Center (http://admin.teams.microsoft.com) by logging in with administrator credentials and clicking **Messaging Policies** in the left navigation.</span></span> <span data-ttu-id="725fd-108">組織の既存の既定のポリシーを編集するには、**グローバル (組織全体の既定値)** 行を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="725fd-108">To edit the existing default policy for your organization, select the **Global (Org-wide default)** row and click **Edit**.</span></span> <span data-ttu-id="725fd-109">新しいメッセージング ポリシーを作成するには、**新しいポリシー**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="725fd-109">To create a new messaging policy, click **New policy**.</span></span>

![チームでのメッセージングのポリシー](media/messaging-policies.png)

<span data-ttu-id="725fd-111">使用可能なポリシーの設定を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="725fd-111">The available settings for the policy are described below:</span></span> 

- <span data-ttu-id="725fd-112">**所有者は、送信済みメッセージを削除できます。** 所有者のユーザーがチャットで送信されるメッセージの削除をできるようにするのにには、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="725fd-112">**Owners can delete sent messages**  Use this setting to let owners delete messages that users send in chat.</span></span>
- <span data-ttu-id="725fd-113">**ユーザーが送信したメッセージを削除できます。** ユーザーがチャットで、送信するメッセージを削除できるようにするのにには、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="725fd-113">**Users can delete sent messages** Use this setting to let users delete messages that they send in chat.</span></span>
- <span data-ttu-id="725fd-114">**ユーザーが送信したメッセージを編集できます。** チャットで送信したメッセージを編集できるようにするのにには、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="725fd-114">**Users can edit sent messages** Use this setting to let users edit the messages that they send in chat.</span></span>
- <span data-ttu-id="725fd-115">**開封**ユーザー制御、すべてのユーザーに対して有効または無効には、この設定を指定するかどうかの開封済みメッセージを使用します。</span><span class="sxs-lookup"><span data-stu-id="725fd-115">**Read receipts** Use this setting to specify whether read receipts are user controlled, enabled for everyone, or disabled.</span></span>
- <span data-ttu-id="725fd-116">**チャット** チームのアプリケーションを使用して、他のユーザーとチャットすることができる、組織内のユーザーをする場合は、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="725fd-116">**Chat**  Turn this setting on if you want users in your organization to be able to use the Teams app to chat with other people.</span></span>
- <span data-ttu-id="725fd-117">**会話に Giphys を使用** これをオンにした場合、ユーザーは、他の人とチャットで会話 Giphys を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="725fd-117">**Use Giphys in conversations**  If you turn this on, users can include Giphys in chat conversations with other people.</span></span> <span data-ttu-id="725fd-118">Giphy は、オンライン データベースと検索エンジンを検索し、アニメーション GIF ファイルを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="725fd-118">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="725fd-119">各 Giphy は、コンテンツの格付けを割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="725fd-119">Each Giphy is assigned a content rating.</span></span>
- <span data-ttu-id="725fd-120">**Giphy コンテンツの規制**</span><span class="sxs-lookup"><span data-stu-id="725fd-120">**Giphy content rating**</span></span> 
    - <span data-ttu-id="725fd-121">**制限なし**これは、できることを意味、ユーザーがコンテンツの規制とは無関係にチャットのすべての Giphys を挿入します。</span><span class="sxs-lookup"><span data-stu-id="725fd-121">**No restriction** This means that your users will be able to insert all Giphys in chats regardless of the content rating.</span></span>
    - <span data-ttu-id="725fd-122">**中程度** つまり、ユーザーがチャットで Giphys を挿入するのにはできるようになりますが、成人向けコンテンツからやや制限されます。</span><span class="sxs-lookup"><span data-stu-id="725fd-122">**Moderate**  This means that your users will be able to insert Giphys in chats but will be moderately restricted from adult content.</span></span>
    - <span data-ttu-id="725fd-123">**厳密です** つまり、ユーザーがチャットで Giphys を挿入するのにはできるようになりますが、成人向けコンテンツから厳密に制限されます。</span><span class="sxs-lookup"><span data-stu-id="725fd-123">**Strict**  This means that your users will be able to insert Giphys in chats but will be strictly restricted from adult content.</span></span>
- <span data-ttu-id="725fd-124">**会話に Memes を使用**これをオンにした場合、ユーザーは、他の人とチャットで会話 Memes を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="725fd-124">**Use Memes in conversations** If you turn this on, users can include Memes in chat conversations with other people.</span></span> 
- <span data-ttu-id="725fd-125">**会話での使用のステッカー**これをオンにした場合、ユーザーは、他の人とチャットで会話ステッカーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="725fd-125">**Use Stickers in conversations** If you turn this on, users can include Stickers in chat conversations with other people.</span></span>
- <span data-ttu-id="725fd-126">**許可する URL のプレビュー**自動 URL でのプレビュー オン/オフ メッセージを有効にするのにには、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="725fd-126">**Allow URL previews** Use this setting to turn automatic URL previewing on or off in messages.</span></span>
- <span data-ttu-id="725fd-127">**ユーザーがメッセージを変換できるようにします。** 自動的にチームのメッセージを Office 365 の場合は、その個人の言語設定で指定された言語に翻訳できるようにするのにはこの設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="725fd-127">**Allow users to translate messages** Turn this setting on to let users automatically translate Teams messages into the language specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="725fd-128">カスタム メッセージング ポリシーを作成した場合にのみアクティブになるユーザーのポリシーがユーザーに割り当てられている場合。</span><span class="sxs-lookup"><span data-stu-id="725fd-128">If you have created a custom Messaging policy, it will only be active for a user if that policy is assigned to a user.</span></span>  <span data-ttu-id="725fd-129">チームの管理センターのユーザーにカスタム ポリシーを割り当てるには左側のナビゲーションで**ユーザー**をクリックして、ポリシーを割り当てるユーザーを選択して、[**割り当てポリシー**の**編集**を選択し。</span><span class="sxs-lookup"><span data-stu-id="725fd-129">To assign a custom policy to a user in the Teams Admin Center, click **Users** in the left navigation, select the user you want to assign the policy to, and then choose **Edit** under **Assigned Policies**.</span></span>

### <a name="related-topics"></a><span data-ttu-id="725fd-130">関連トピック</span><span class="sxs-lookup"><span data-stu-id="725fd-130">Related topics</span></span>
[<span data-ttu-id="725fd-131">チームでミーティングのポリシー</span><span class="sxs-lookup"><span data-stu-id="725fd-131">Meeting policies in Teams</span></span>](meeting-policies-in-teams.md)