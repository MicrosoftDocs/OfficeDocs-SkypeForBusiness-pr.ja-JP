---
title: Microsoft Teams の外部 (フェデレーション) ユーザー向けネイティブ チャット エクスペリエンス
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: 両方のユーザーが TeamsOnly アップグレード モードにある Microsoft Teams の外部アクセス (フェデレーション) ユーザーのネイティブ Teams チャット エクスペリエンスについて説明します。
ms.openlocfilehash: a06532ab4cd1d1c5ffe3f30d2a6036b2c34c716f
ms.sourcegitcommit: 5a39061c2156531f4b7f5f69eecf81a8c8b238d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2021
ms.locfileid: "52030117"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="756ad-103">Microsoft Teams の外部 (フェデレーション) ユーザー向けネイティブ チャット エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="756ad-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>

<span data-ttu-id="756ad-104">Microsoft Teams ユーザーが外部 (フェデレーション) ユーザーとチャットしている場合、チャット エクスペリエンスはテキストに制限されます。</span><span class="sxs-lookup"><span data-stu-id="756ad-104">When a Microsoft Teams user is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="756ad-105">ただし、Teams ユーザーと別の組織のユーザーの両方が TeamsOnly アップグレード モードの場合は、リッチ フォーマット、@mentions、その他のチャット機能を含む"ネイティブ Teams チャット エクスペリエンス" を使用できます。</span><span class="sxs-lookup"><span data-stu-id="756ad-105">However, if both your Teams user and the person in another organization are in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="756ad-106">他の組織のユーザーとのネイティブ Teams チャットは、1 対 1 のチャットにのみ制限されます。</span><span class="sxs-lookup"><span data-stu-id="756ad-106">Native Teams chats with people in other organizations are limited to 1:1 chats only.</span></span>

<span data-ttu-id="756ad-107">他の組織のユーザーのネイティブ チャット エクスペリエンスは、すべての Teams テナントで有効になりますが、すべてのユーザーが対象となるとは言えなかっています。</span><span class="sxs-lookup"><span data-stu-id="756ad-107">The native chat experience for people in other organizations is turned on for all Teams tenants, but not all people are eligible.</span></span> <span data-ttu-id="756ad-108">ネイティブ チャット エクスペリエンスを提供するには、送信者と受信者の両方を TeamsOnly アップグレード モード用に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="756ad-108">To be offered a native chat experience, both the sender and receiver need to be configured for TeamsOnly upgrade mode.</span></span> <span data-ttu-id="756ad-109">アップグレード ポリシーの詳細については、「共存とアップグレードの [設定の設定」を参照してください](setting-your-coexistence-and-upgrade-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="756ad-109">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="756ad-110">Teams の外部アクセス ユーザーの機能の一覧を表示するには、「外部アクセスとゲスト アクセスを比較する」 [を参照してください](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。</span><span class="sxs-lookup"><span data-stu-id="756ad-110">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="756ad-111">ネイティブ チャットに参加しているかどうかは、どうすれば分かるのか?</span><span class="sxs-lookup"><span data-stu-id="756ad-111">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="756ad-112">チャット内のテキストのみを他の組織のユーザーと交換できる場合は、標準の外部アクセス (フェデレーション) チャットに参加しています。</span><span class="sxs-lookup"><span data-stu-id="756ad-112">If you can only exchange text in your chat with people in other organizations, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="756ad-113">書式設定、@mentions、絵文字など、他のすべてのチャット機能がある場合は、ネイティブ Teams チャットに参加しています。</span><span class="sxs-lookup"><span data-stu-id="756ad-113">If you've got all of the other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat.</span></span> 

<span data-ttu-id="756ad-114">Teams は、他の組織のユーザーのアップグレード モードを定期的にチェックし、TeamsOnly アップグレード モードで Teams を実行しているチームを見つけたら、ネイティブの Teams チャットに切り替えて元のチャットをロックするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="756ad-114">Teams periodically checks the upgrade mode for people in other organizations and, when it finds an them running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="756ad-115">ネイティブの Teams チャットに切り替えても、Teams は 2 つの会話をマージしません。</span><span class="sxs-lookup"><span data-stu-id="756ad-115">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="756ad-116">代わりに、チャット フィードに両方のチャットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="756ad-116">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="756ad-117">新しいネイティブ Teams チャットはアクティブですが、古いテキスト専用チャットはロックされています。</span><span class="sxs-lookup"><span data-stu-id="756ad-117">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="756ad-118">ユーザーが Teams Only モードでなくなった場合は、どうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="756ad-118">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="756ad-119">他の組織のユーザーとネイティブ Teams チャットを行っている場合、そのうちの 1 人が TeamsOnly アップグレード モードから切り替わると、Teams はネイティブ Teams チャットをロックし、テキスト専用の制限付きチャットのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="756ad-119">If you were having a native Teams chat with people in other organizations and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="756ad-120">ネイティブ Teams チャットを続行できない。</span><span class="sxs-lookup"><span data-stu-id="756ad-120">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="756ad-121">ネイティブの Teams チャットは引き続き読み取り可能ですが、そこで会話を続行できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="756ad-121">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="756ad-122">Teams が、このユーザーと古いテキスト専用チャットを見つけた場合、そのチャットが再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="756ad-122">If Teams finds an old text-only chat with this person, it'll revive that chat.</span></span> <span data-ttu-id="756ad-123">それ以外の場合、Teams は新しいテキスト専用チャットを作成します。</span><span class="sxs-lookup"><span data-stu-id="756ad-123">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="756ad-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="756ad-124">Related topics</span></span>

[<span data-ttu-id="756ad-125">Teams で外部アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="756ad-125">Manage external access in Teams</span></span>](manage-external-access.md)
