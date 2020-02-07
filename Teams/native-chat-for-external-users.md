---
title: Microsoft Teams の外部 (フェデレーション) ユーザー向けのネイティブチャット操作
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: Microsoft Teams の外部アクセス (フェデレーション) ユーザー向けのネイティブなチームチャットエクスペリエンスについて説明します。この機能は、両方のユーザーが teams Sonly アップグレードモードを使用している外部ユーザー間で利用できます。
ms.openlocfilehash: 0d6f7ed00482ee68233b4d93cc101e9c820a6f14
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41832687"
---
<a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="81cb0-103">Microsoft Teams の外部 (フェデレーション) ユーザー向けのネイティブチャット操作</span><span class="sxs-lookup"><span data-stu-id="81cb0-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>
======================================

<span data-ttu-id="81cb0-104">Microsoft Teams ユーザーが外部 (フェデレーション) ユーザーとのチャットを行っている場合、チャットエクスペリエンスはテキストに制限されます。</span><span class="sxs-lookup"><span data-stu-id="81cb0-104">When a Microsoft Teams users is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="81cb0-105">ただし、Teams テナントと外部ユーザーの両方が Teams Sonly アップグレードモードである場合は、"ネイティブチームチャットエクスペリエンス" を使用できます。これには、リッチな書式設定、@mentions、その他のチャット機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="81cb0-105">However, if both your Teams tenant and that of the external user is in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="81cb0-106">つまり、組織内のユーザーと同じように、適切な外部ユーザーと同じ1:1 チームチャットエクスペリエンスを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="81cb0-106">In other words, you can have the same rich 1:1 Teams chat experience with eligible external users as you'd have with users in your organization.</span></span> <span data-ttu-id="81cb0-107">外部ユーザーとのネイティブチームチャットは、依然として1:1 のチャットに限定されます (外部ユーザーはグループチャットを行うことはできません)。</span><span class="sxs-lookup"><span data-stu-id="81cb0-107">Native Teams chats with external users are still limited to 1:1 chats only (external users can't do group chats).</span></span>

<span data-ttu-id="81cb0-108">外部ユーザー向けのネイティブチャット操作は、すべてのチームテナントで有効になっていますが、すべてのユーザーが対象になっているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="81cb0-108">The native chat experience for external users is turned on for all Teams tenants, but not all users are eligible.</span></span> <span data-ttu-id="81cb0-109">ネイティブチャットエクスペリエンスを提供するには、送信者と受信者の両方が、Teams のアップグレードモードを実行している Teams テナントに参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="81cb0-109">To be offered a native chat experience, both the sender and receiver need to be on a Teams tenant that's running the TeamsOnly upgrade mode.</span></span> <span data-ttu-id="81cb0-110">アップグレードポリシーの詳細については、「[共存の設定とアップグレードの設定](setting-your-coexistence-and-upgrade-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81cb0-110">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="81cb0-111">Teams の外部アクセスユーザーの機能の一覧については、「[外部とゲストのアクセスを比較](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81cb0-111">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="81cb0-112">自分がネイティブチャットであるかどうかを知る方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="81cb0-112">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="81cb0-113">チャット内のテキストを外部ユーザーとのみ交換できる場合は、標準の外部アクセス (フェデレーション) チャットを使用しています。</span><span class="sxs-lookup"><span data-stu-id="81cb0-113">If you can only exchange text in your chat with an external user, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="81cb0-114">書式設定、@mentions、絵文字など、その他のすべてのチャット機能を使用している場合は、ネイティブのチームとの間で、外部ユーザーとチャットしていることになります。</span><span class="sxs-lookup"><span data-stu-id="81cb0-114">If you've got all of the other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat with your external user.</span></span> 

<span data-ttu-id="81cb0-115">チームは定期的に外部ユーザーのアップグレードモードを確認します。チームは、Teams のアップグレードモードで Teams を実行している外部ユーザーを見つけたときに、ネイティブのチームチャットに切り替えて、元のチャットをロックするように求められます。</span><span class="sxs-lookup"><span data-stu-id="81cb0-115">Teams periodically checks the upgrade mode for external users and, when it finds an external user running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="81cb0-116">ネイティブなチームチャットに切り替えると、Teams では2つの会話が結合されません。</span><span class="sxs-lookup"><span data-stu-id="81cb0-116">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="81cb0-117">代わりに、チャットフィードに両方のチャットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="81cb0-117">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="81cb0-118">新しいネイティブチームチャットはアクティブですが、以前のテキストのみのチャットはロックされています。</span><span class="sxs-lookup"><span data-stu-id="81cb0-118">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="81cb0-119">ユーザーが Teams のみモードになっていない場合はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="81cb0-119">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="81cb0-120">ネイティブなチームで外部ユーザーとチャットしていて、どちらか一方が teams のアップグレードモードに切り替えられている場合、チームはネイティブのチームチャットをロックし、テキストのみのチャットを制限したリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="81cb0-120">If you were having a native Teams chat with an external user and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="81cb0-121">ネイティブの Teams チャットを続行することはできません。</span><span class="sxs-lookup"><span data-stu-id="81cb0-121">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="81cb0-122">ただし、ネイティブの Teams チャットを読むことはできますが、そこで会話を続けることはできません。</span><span class="sxs-lookup"><span data-stu-id="81cb0-122">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="81cb0-123">Teams では、この外部ユーザとのテキストのみのチャットが見つかると、そのチャットが使おうます。</span><span class="sxs-lookup"><span data-stu-id="81cb0-123">If Teams finds an old text-only chat with this external user, it'll revive that chat.</span></span> <span data-ttu-id="81cb0-124">それ以外の場合、チームは新しいテキストのみのチャットを作成します。</span><span class="sxs-lookup"><span data-stu-id="81cb0-124">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="81cb0-125">関連トピック</span><span class="sxs-lookup"><span data-stu-id="81cb0-125">Related topics</span></span>

[<span data-ttu-id="81cb0-126">Teams で外部アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="81cb0-126">Manage external access in Teams</span></span>](manage-external-access.md)
