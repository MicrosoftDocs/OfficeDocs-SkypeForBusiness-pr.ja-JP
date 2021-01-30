---
title: Microsoft Teams での外部 (フェデレーション) ユーザーのネイティブ チャットエクスペリエンス
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
description: 両方のユーザーが TeamsOnly アップグレード モードにある Microsoft Teams の外部アクセス (フェデレーション) ユーザー向けネイティブ Teams チャット エクスペリエンスについて説明します。
ms.openlocfilehash: df9e1e41992e105937deacf898833995cdfb7714
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055659"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="2ca2b-103">Microsoft Teams での外部 (フェデレーション) ユーザーのネイティブ チャットエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="2ca2b-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>

<span data-ttu-id="2ca2b-104">Microsoft Teams ユーザーが外部 (フェデレーション) ユーザーとチャットしている場合、チャットエクスペリエンスはテキストに制限されます。</span><span class="sxs-lookup"><span data-stu-id="2ca2b-104">When a Microsoft Teams user is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="2ca2b-105">ただし、Teams ユーザーと別の組織のユーザーの両方が TeamsOnly アップグレード モードの場合は、リッチフォーマット、@mentions、その他のチャット機能を含む "ネイティブ Teams チャット エクスペリエンス" を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2ca2b-105">However, if both your Teams user and the person in another organization is in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="2ca2b-106">つまり、組織内のユーザーと同じように、他の組織の対象ユーザーと同じリッチな 1 対 1 の Teams チャット エクスペリエンスを利用できます。</span><span class="sxs-lookup"><span data-stu-id="2ca2b-106">In other words, you can have the same rich 1:1 Teams chat experience with eligible people in other organizations as you'd have with users in your organization.</span></span> <span data-ttu-id="2ca2b-107">他の組織のユーザーとのネイティブ Teams チャットは、1 対 1 のチャットに制限されます。</span><span class="sxs-lookup"><span data-stu-id="2ca2b-107">Native Teams chats with people in other organizations are limited to 1:1 chats only.</span></span>

<span data-ttu-id="2ca2b-108">他の組織のユーザーのネイティブ チャットエクスペリエンスは、すべての Teams テナントに対して有効になりますが、すべてのユーザーが利用できるとは言えな。</span><span class="sxs-lookup"><span data-stu-id="2ca2b-108">The native chat experience for people in other organizations is turned on for all Teams tenants, but not all people are eligible.</span></span> <span data-ttu-id="2ca2b-109">ネイティブ チャットエクスペリエンスを提供するには、送信者と受信者の両方を TeamsOnly アップグレード モード用に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ca2b-109">To be offered a native chat experience, both the sender and receiver need to be configured for TeamsOnly upgrade mode.</span></span> <span data-ttu-id="2ca2b-110">アップグレード ポリシーの詳細については、「共存とアップグレード [の設定」を参照してください](setting-your-coexistence-and-upgrade-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="2ca2b-110">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="2ca2b-111">Teams で外部アクセス ユーザーの機能の一覧を表示するには、「外部アクセスとゲスト アクセスを比較する [」を参照してください](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。</span><span class="sxs-lookup"><span data-stu-id="2ca2b-111">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="2ca2b-112">ネイティブ チャットに参加しているかどうかは、どのように知る必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="2ca2b-112">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="2ca2b-113">チャット内のテキストを他の組織のユーザーとのみやり取りできる場合は、標準の外部アクセス (フェデレーション) チャットに参加しています。</span><span class="sxs-lookup"><span data-stu-id="2ca2b-113">If you can only exchange text in your chat with people in other organizations, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="2ca2b-114">書式設定、@mentions、絵文字など、他のすべてのチャット機能がある場合は、ネイティブの Teams チャットに参加しています。</span><span class="sxs-lookup"><span data-stu-id="2ca2b-114">If you've got all of the other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat.</span></span> 

<span data-ttu-id="2ca2b-115">Teams は、他の組織のユーザーのアップグレード モードを定期的にチェックし、TeamsOnly アップグレード モードで Teams を実行しているユーザーを見つけたら、ネイティブの Teams チャットに切り替えて元のチャットをロックするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2ca2b-115">Teams periodically checks the upgrade mode for people in other organizations and, when it finds an them running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="2ca2b-116">ネイティブの Teams チャットに切り替えても、Teams は 2 つの会話を結合しません。</span><span class="sxs-lookup"><span data-stu-id="2ca2b-116">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="2ca2b-117">代わりに、両方のチャットがチャット フィードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2ca2b-117">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="2ca2b-118">新しいネイティブ Teams チャットはアクティブですが、古いテキスト専用のチャットはロックされています。</span><span class="sxs-lookup"><span data-stu-id="2ca2b-118">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="2ca2b-119">ユーザーが Teams のみモードではなくなった場合は、どうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="2ca2b-119">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="2ca2b-120">他の組織のユーザーとネイティブの Teams チャットを行っている場合、そのうちの 1 人が TeamsOnly アップグレード モードから切り替わると、Teams はネイティブの Teams チャットをロックし、制限付きテキスト専用チャットのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="2ca2b-120">If you were having a native Teams chat with people in other organizations and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="2ca2b-121">ネイティブの Teams チャットを続行できない。</span><span class="sxs-lookup"><span data-stu-id="2ca2b-121">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="2ca2b-122">ネイティブの Teams チャットは引き続き読み取り可能ですが、そこで会話を続けはまだできます。</span><span class="sxs-lookup"><span data-stu-id="2ca2b-122">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="2ca2b-123">Teams が、このユーザーとの古いテキスト専用チャットを見つけた場合、そのチャットは復活します。</span><span class="sxs-lookup"><span data-stu-id="2ca2b-123">If Teams finds an old text-only chat with this person, it'll revive that chat.</span></span> <span data-ttu-id="2ca2b-124">それ以外の場合、Teams は新しいテキスト専用チャットを作成します。</span><span class="sxs-lookup"><span data-stu-id="2ca2b-124">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="2ca2b-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ca2b-125">Related topics</span></span>

[<span data-ttu-id="2ca2b-126">Teams で外部アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="2ca2b-126">Manage external access in Teams</span></span>](manage-external-access.md)
