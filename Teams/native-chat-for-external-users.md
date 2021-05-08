---
title: 外部 (フェデレーション) ユーザーのネイティブ チャット エクスペリエンスMicrosoft Teams
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
description: 両方のユーザーが TeamsOnly アップグレード モードTeamsの外部アクセス (フェデレーション) ユーザーのネイティブ Microsoft Teams チャット エクスペリエンスについて学習します。
ms.openlocfilehash: 02bf09a7623079eb207ffca1b122bc03bf07c5c8
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240463"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="db533-103">外部 (フェデレーション) ユーザーのネイティブ チャット エクスペリエンスMicrosoft Teams</span><span class="sxs-lookup"><span data-stu-id="db533-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>

<span data-ttu-id="db533-104">ユーザーがMicrosoft Teams (フェデレーション) ユーザーとチャットしている場合、チャット エクスペリエンスはテキストに制限されます。</span><span class="sxs-lookup"><span data-stu-id="db533-104">When a Microsoft Teams user is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="db533-105">ただし、Teams ユーザーと別の組織のユーザーの両方が TeamsOnly アップグレード モードの場合は、リッチフォーマット、@mentions、その他のチャット機能を含む "ネイティブ Teams チャット エクスペリエンス" を使用できます。</span><span class="sxs-lookup"><span data-stu-id="db533-105">However, if both your Teams user and the person in another organization are in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="db533-106">ネイティブ Teams他の組織のユーザーとのチャットは、1 対 1 のチャットにのみ制限されます。</span><span class="sxs-lookup"><span data-stu-id="db533-106">Native Teams chats with people in other organizations are limited to 1:1 chats only.</span></span>

<span data-ttu-id="db533-107">他の組織のユーザーのネイティブ チャット エクスペリエンスは、すべてのテナントTeamsオンになりますが、すべてのユーザーが資格を持っているというのではありません。</span><span class="sxs-lookup"><span data-stu-id="db533-107">The native chat experience for people in other organizations is turned on for all Teams tenants, but not all people are eligible.</span></span> <span data-ttu-id="db533-108">ネイティブ チャット エクスペリエンスを提供するには、送信者と受信者の両方を TeamsOnly アップグレード モード用に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db533-108">To be offered a native chat experience, both the sender and receiver need to be configured for TeamsOnly upgrade mode.</span></span> <span data-ttu-id="db533-109">アップグレード ポリシーの詳細については、「共存とアップグレードの設定 [」を参照してください](setting-your-coexistence-and-upgrade-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="db533-109">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="db533-110">外部アクセス ユーザーの機能の一覧を表示するには、Teamsとゲスト アクセスの比較に関する[ページを参照してください](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。</span><span class="sxs-lookup"><span data-stu-id="db533-110">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="db533-111">ネイティブ チャットに参加しているかどうかは、どうすれば知るのですか?</span><span class="sxs-lookup"><span data-stu-id="db533-111">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="db533-112">チャット内のテキストを他の組織のユーザーとのみ交換できる場合は、標準の外部アクセス (フェデレーション) チャットに参加しています。</span><span class="sxs-lookup"><span data-stu-id="db533-112">If you can only exchange text in your chat with people in other organizations, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="db533-113">書式設定、@mentions、絵文字など、その他のチャット機能がある場合は、ネイティブチャットTeamsしています。</span><span class="sxs-lookup"><span data-stu-id="db533-113">If you've got other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat.</span></span> 

<span data-ttu-id="db533-114">Teamsは、他の組織のユーザーのアップグレード モードを定期的にチェックし、TeamsOnly アップグレード モードで Teams を実行しているユーザーを見つけたら、ネイティブ Teams チャットに切り替えて元のチャットをロックするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="db533-114">Teams periodically checks the upgrade mode for people in other organizations and, when it finds an them running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="db533-115">ネイティブ チャットに切り替Teams、Teams 2 つの会話は結合しません。</span><span class="sxs-lookup"><span data-stu-id="db533-115">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="db533-116">代わりに、両方のチャットがチャット フィードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="db533-116">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="db533-117">新しいネイティブ チャットTeamsアクティブですが、古いテキスト専用チャットはロックされています。</span><span class="sxs-lookup"><span data-stu-id="db533-117">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="db533-118">ユーザーが [のみ] モードTeams場合は、どうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="db533-118">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="db533-119">他の組織のユーザーとネイティブ Teams チャットを行っている場合、そのうちの 1 人が TeamsOnly アップグレード モードから切り替わると、Teams はネイティブ Teams チャットをロックし、制限付きテキスト専用チャットのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="db533-119">If you were having a native Teams chat with people in other organizations and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="db533-120">ネイティブ チャットを続行Teamsされます。</span><span class="sxs-lookup"><span data-stu-id="db533-120">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="db533-121">ネイティブ のチャットを読Teams、そこで会話を続けはまだできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="db533-121">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="db533-122">このTeams古いテキスト専用チャットを見つけた場合、そのチャットは復活します。</span><span class="sxs-lookup"><span data-stu-id="db533-122">If Teams finds an old text-only chat with this person, it'll revive that chat.</span></span> <span data-ttu-id="db533-123">それ以外のTeams、新しいテキスト専用チャットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="db533-123">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="db533-124">関連トピック</span><span class="sxs-lookup"><span data-stu-id="db533-124">Related topics</span></span>

[<span data-ttu-id="db533-125">Teams で外部アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="db533-125">Manage external access in Teams</span></span>](manage-external-access.md)
