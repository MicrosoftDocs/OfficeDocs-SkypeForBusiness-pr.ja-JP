---
title: チーム内のポリシーをメッセージングは何でしょうか。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.messagingpolicies.overview
description: メッセージング ポリシーとそれらを使用してメッセージング チームのチャットを制御する方法について説明します。
ms.openlocfilehash: ef252f958f08c75d0fcfb8af0a06aadf776d3668
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850918"
---
# <a name="what-are-messaging-policies-in-teams"></a><span data-ttu-id="07ea4-103">チーム内のポリシーをメッセージングは何でしょうか。</span><span class="sxs-lookup"><span data-stu-id="07ea4-103">What are Messaging policies in Teams?</span></span>

<span data-ttu-id="07ea4-104">メッセージング ポリシーは、どのようなチャットとチャネルのメッセージング機能は、チーム内のユーザーに利用可能な制御に使用されます。</span><span class="sxs-lookup"><span data-stu-id="07ea4-104">Messaging policies are used to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="07ea4-105">作成されるか、組織内の 1 つまたは複数のカスタム メッセージング ポリシーを作成する既定のポリシーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="07ea4-105">You can use the default policy that is created or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="07ea4-106">ポリシーを作成したら、割り当てる、ユーザーまたはユーザー グループ、組織内。</span><span class="sxs-lookup"><span data-stu-id="07ea4-106">After you create a policy, you will assign it a user or groups of users in your organization.</span></span>

- <span data-ttu-id="07ea4-107">**所有者は、送信済みメッセージを削除できます。** 所有者のユーザーがチャットで送信されるメッセージの削除をできるようにするのにには、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="07ea4-107">**Owners can delete sent messages**  Use this setting to let owners delete messages that users send in chat.</span></span>
- <span data-ttu-id="07ea4-108">**ユーザーが送信したメッセージを削除できます。** ユーザーがチャットで、送信するメッセージを削除できるようにするのにには、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="07ea4-108">**Users can delete sent messages** Use this setting to let users delete messages that they send in chat.</span></span>
- <span data-ttu-id="07ea4-109">**ユーザーが送信したメッセージを編集できます。** チャットで送信したメッセージを編集できるようにするのにには、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="07ea4-109">**Users can edit sent messages** Use this setting to let users edit their messages that they send in chat.</span></span>
- <span data-ttu-id="07ea4-110">**チャット** チームのアプリケーションを使用して、他のユーザーとチャットすることができる、組織内のユーザーをする場合は、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="07ea4-110">**Chat**  Turn this setting on if you want users in your organization to be able to use the Teams app to chat with other people.</span></span>
- <span data-ttu-id="07ea4-111">**会話に Giphys を使用** これをオンにした場合、ユーザーは、他の人とチャットで会話 Giphys を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="07ea4-111">**Use Giphys in conversations**  If you turn this on, users can include Giphys in chat conversations with other people.</span></span> <span data-ttu-id="07ea4-112">Giphy は、オンライン データベースと検索エンジンを検索し、アニメーション GIF ファイルを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="07ea4-112">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="07ea4-113">各 Giphy は、コンテンツの格付けを割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="07ea4-113">Each Giphy is assigned a content rating.</span></span>
- <span data-ttu-id="07ea4-114">**Giphy コンテンツの規制**</span><span class="sxs-lookup"><span data-stu-id="07ea4-114">**Giphy content rating**</span></span> 
    - <span data-ttu-id="07ea4-115">**制限なし**これは、できることを意味、ユーザーがチャットのすべての Giphys を挿入します。</span><span class="sxs-lookup"><span data-stu-id="07ea4-115">**No restriction** This means that your users will be able to insert all Giphys in chats.</span></span>
    - <span data-ttu-id="07ea4-116">**中程度** つまり、ユーザーはできるだけの挿入</span><span class="sxs-lookup"><span data-stu-id="07ea4-116">**Moderate**  This means that your users will be able only insert</span></span> 
    - <span data-ttu-id="07ea4-117">**厳密**</span><span class="sxs-lookup"><span data-stu-id="07ea4-117">**Strict**</span></span>
- <span data-ttu-id="07ea4-118">**会話に Memes を使用**これをオンにした場合、ユーザーは、他の人とチャットで会話 Memes を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="07ea4-118">**Use Memes in conversations** If you turn this on, users can include Memes in chat conversations with other people.</span></span> 
- <span data-ttu-id="07ea4-119">**会話での使用のステッカー**これをオンにした場合、ユーザーは、他の人とチャットで会話ステッカーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="07ea4-119">**Use Stickers in conversations** If you turn this on, users can include Stickers in chat conversations with other people.</span></span>


### <a name="related-topics"></a><span data-ttu-id="07ea4-120">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="07ea4-120">Related topics</span></span>
[<span data-ttu-id="07ea4-121">チームでミーティングのポリシー</span><span class="sxs-lookup"><span data-stu-id="07ea4-121">Meeting policies in Teams</span></span>](meeting-policies-in-teams.md)