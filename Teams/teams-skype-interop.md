---
title: チームと Skype の相互運用性
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: 組織内の Teams ユーザーと Skype (コンシューマー) ユーザーとの相互運用性機能について説明します。
localization_priority: Normal
ms.openlocfilehash: b05724f7ddb860d4b135fad5834ea851403c1490
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "47766901"
---
# <a name="teams-and-skype-interoperability"></a><span data-ttu-id="0ab9a-103">チームと Skype の相互運用性</span><span class="sxs-lookup"><span data-stu-id="0ab9a-103">Teams and Skype interoperability</span></span>

<span data-ttu-id="0ab9a-104">この記事では、Microsoft Teams と Skype (コンシューマー) との間の相互運用性機能の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-104">This article gives you an overview of the interoperability capabilities between Microsoft Teams and Skype (Consumer).</span></span> <span data-ttu-id="0ab9a-105">チームのユーザーと Skype ユーザーが、チャットや通話、および適用される管理コントロールによってコミュニケーションを行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-105">Learn how Teams users and Skype users can communicate through chats and calls and the admin controls that apply.</span></span>

<span data-ttu-id="0ab9a-106">組織内の Teams ユーザーは、自分のメールアドレスを使って Skype のユーザーとチャットしたり、その逆に通話したりできます。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-106">Teams users in your organization can chat with and call Skype users by using their email address and vice versa.</span></span>

- <span data-ttu-id="0ab9a-107">Teams ユーザーは、1対1のテキストのみの会話、または Skype ユーザーとの音声/ビデオ通話を検索して開始することができます。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-107">Teams users can search for and start a one-on-one text-only conversation or an audio/video call with a Skype user.</span></span>
- <span data-ttu-id="0ab9a-108">Skype ユーザは、1対1のテキストのみの会話、または Teams ユーザとの音声/ビデオ通話を検索して開始することができます。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-108">Skype users can search for and start a one-on-one text-only conversation or an audio/video call with a Teams user.</span></span>

<span data-ttu-id="0ab9a-109">これらの機能は、Teams と Skype の両方のデスクトップ、web、モバイル (Android および iOS) クライアントで利用できます。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-109">These capabilities are available on the desktop, web, and mobile (Android and iOS) clients for both Teams and Skype.</span></span> <span data-ttu-id="0ab9a-110">最適なエクスペリエンスを実現するには、Skype バージョン8.58 以降をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-110">For an optimal experience, we recommend Skype version 8.58 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="0ab9a-111">この記事で説明されているチームおよび Skype 相互運用機能は、GCC、GCC 高、または DOD の展開やプライベートクラウド環境では使用できません。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-111">The Teams and Skype interop capabilities discussed in this article aren't available in GCC, GCC High, or DOD deployments, or in private cloud environments.</span></span>

## <a name="chat-and-calling-experience"></a><span data-ttu-id="0ab9a-112">チャットと通話のエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="0ab9a-112">Chat and calling experience</span></span>

<span data-ttu-id="0ab9a-113">チャットと通話のエクスペリエンスの概要を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-113">Here's an overview of the chat and calling experience.</span></span>

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a><span data-ttu-id="0ab9a-114">Teams ユーザーが Skype ユーザーとのチャットまたは通話を開始する</span><span class="sxs-lookup"><span data-stu-id="0ab9a-114">Teams user starts a chat or call with a Skype user</span></span>

<span data-ttu-id="0ab9a-115">Teams ユーザーは、新しいチャットまたは検索バーに自分のメールアドレスを入力して、Skype ユーザーを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-115">Teams users can search for a Skype user by typing their email address in a new chat or in the search bar.</span></span>  <span data-ttu-id="0ab9a-116">チームユーザは、検索結果で Skype ユーザを選択して、チャットまたは通話を開始できます。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-116">The Teams user can then select the Skype user in the search results to start a chat or call with them.</span></span>

<span data-ttu-id="0ab9a-117">Skype ユーザは、検索結果に表示されないように選択できます。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-117">A Skype user may choose not to appear in search results.</span></span> <span data-ttu-id="0ab9a-118">この場合、チームの検索結果には表示されず、Teams ユーザーはそれらを見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-118">In this case, they won't show up in the search results in Teams and Teams users won't be able to find them.</span></span>

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a><span data-ttu-id="0ab9a-119">Skype ユーザが Teams ユーザとチャットまたは通話を開始</span><span class="sxs-lookup"><span data-stu-id="0ab9a-119">Skype user starts a chat or call with a Teams user</span></span>

<span data-ttu-id="0ab9a-120">Skype ユーザは、自分のメールアドレスを使って、チームユーザとのチャットを検索して開始することができます。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-120">Skype users can search for and start a chat with a Teams user by using their email address.</span></span> <span data-ttu-id="0ab9a-121">チームユーザには、Skype ユーザからの新しいメッセージがあることが通知され、最初にメッセージを受信しないと返信できません。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-121">The Teams user is notified that they have a new message from a Skype user, and has to first accept the message before they can reply to it.</span></span>

- <span data-ttu-id="0ab9a-122">Teams ユーザーが [ **承諾**] を選択すると、会話が承諾され、両方のユーザーがチャットして通話を発信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-122">If the Teams user selects **Accept**, the conversation is accepted, and both users can chat and call each other.</span></span>
- <span data-ttu-id="0ab9a-123">Teams ユーザーが **ブロック**を選択した場合、会話はブロックされ、その後の Skype ユーザからのメッセージや通話はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-123">If the Teams user selects **Block**, the conversation is blocked, and subsequent messages and calls from that Skype user are blocked.</span></span>
- <span data-ttu-id="0ab9a-124">Teams ユーザーが [ **メッセージの表示**] を選択すると、そのメッセージが teams に表示され、ユーザーはその会話を承認またはブロックするかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-124">If the Teams user selects **View messages**, the message is displayed in Teams, which helps the user decide whether to accept or block the conversation.</span></span>

> [!NOTE]
> <span data-ttu-id="0ab9a-125">Skype for Business から Teams にアップグレードして、ユーザーが Teams のみモードの場合は、Skype ユーザーから Teams ユーザーへのチャットや通話が Teams に配信されます。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-125">If you upgraded from Skype for Business to Teams and your users are in Teams Only mode, chats and calls from Skype users to Teams users are delivered to Teams.</span></span> <span data-ttu-id="0ab9a-126">ユーザが諸島モードになっている場合は、Skype ユーザから Teams ユーザへのチャットや通話が Skype for Business に配信されます。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-126">If your users are in Islands mode, chats and calls from Skype users to Teams users are delivered to Skype for Business.</span></span>

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a><span data-ttu-id="0ab9a-127">Teams ユーザーが Skype ユーザーをブロックまたはブロック解除する</span><span class="sxs-lookup"><span data-stu-id="0ab9a-127">Teams user blocks or unblocks a Skype user</span></span>

<span data-ttu-id="0ab9a-128">チームのユーザーが Skype ユーザーからの最初の会話要求を承諾またはブロックした後は、そのユーザーはいつでもブロックまたはブロック解除することができます。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-128">After a Teams user accepts or blocks the initial conversation request from a Skype user, they can choose to block or unblock that person at any time.</span></span> <span data-ttu-id="0ab9a-129">この操作は、会話または Teams のプライバシー設定で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-129">They can do this either in the conversation or in their privacy settings in Teams.</span></span> <span data-ttu-id="0ab9a-130">Skype ユーザは、ブロックされていることを認識できません。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-130">Skype users won't know that they've been blocked.</span></span>

<span data-ttu-id="0ab9a-131">ブロックされた Skype ユーザーと、他のユーザー、および Teams ユーザーがブロックした公衆交換電話網 (PSTN) 電話番号は、チームのユーザーのブロックされた連絡先リストに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-131">Blocked Skype users, along with other people and public switched telephone network (PSTN) phone numbers that a Teams user has blocked, are listed on the user's blocked contact list in Teams.</span></span>

## <a name="limitations"></a><span data-ttu-id="0ab9a-132">伴う</span><span class="sxs-lookup"><span data-stu-id="0ab9a-132">Limitations</span></span>

- <span data-ttu-id="0ab9a-133">会話はテキストのみです。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-133">Conversations are text-only.</span></span> <span data-ttu-id="0ab9a-134">これは、ネイティブな [書式設定]、[@mentions]、[絵文字] などの他のチャット機能がないことを意味します。これは、 [ネイティブのチームチャットエクスペリエンス](native-chat-for-external-users.md)で利用できます。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-134">This means that there's no rich formatting, @mentions, emojis, or other any of the other chat features that are available in a [native Teams chat experience](native-chat-for-external-users.md).</span></span>
- <span data-ttu-id="0ab9a-135">会話は1対1でのみ行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-135">Conversations are one-on-one only.</span></span> <span data-ttu-id="0ab9a-136">グループチャットはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-136">Group chats aren't supported.</span></span>
- <span data-ttu-id="0ab9a-137">Teams ユーザーと Skype ユーザーは、互いのプレゼンスを見ることはできません。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-137">Teams users and Skype users can't see each other's presence.</span></span>
- <span data-ttu-id="0ab9a-138">Skype ID または電話番号を使用して Skype ユーザを検索することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-138">Searching for Skype users by using their Skype ID or phone number isn't supported.</span></span>
- <span data-ttu-id="0ab9a-139">Skype ユーザは、他のユーザの番号、代理人の番号、公衆交換電話網 (PSTN) 番号への通話転送を設定した Teams ユーザとは通話できません。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-139">Skype users can't call Teams users who set up call forwarding to another user's number, a delegate's number, or a Public Switched Telephone Network (PSTN) number.</span></span>  <span data-ttu-id="0ab9a-140">ボイスメールのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-140">Only voicemail is supported.</span></span>
- <span data-ttu-id="0ab9a-141">相互運用エスカレーション、グループ通話、会議はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-141">Interop escalation, group calls, and meetings aren't supported.</span></span>
- <span data-ttu-id="0ab9a-142">Teams ユーザの代理として、代理人が Skype ユーザに通話を発信する機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-142">The ability for a delegate to call a Skype user on behalf of a Teams user isn't supported.</span></span>
- <span data-ttu-id="0ab9a-143">チャットでの画面共有はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-143">Screen sharing with chat isn't supported.</span></span>

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a><span data-ttu-id="0ab9a-144">チームユーザーが Skype ユーザーと通信できるかどうかを設定する</span><span class="sxs-lookup"><span data-stu-id="0ab9a-144">Set whether Teams users can communicate with Skype users</span></span>

<span data-ttu-id="0ab9a-145">管理者は、Microsoft Teams 管理センターまたは PowerShell を使用して外部アクセス設定を設定し、組織内の Teams ユーザーが Skype ユーザーと通信できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-145">As an admin, you use the Microsoft Teams admin center or PowerShell to set external access settings to control whether Teams users in your organization can communicate with Skype users.</span></span> <span data-ttu-id="0ab9a-146">既定では、新しいテナントではこの機能が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-146">By default, this capability is turned on for new tenants.</span></span>

<span data-ttu-id="0ab9a-147">Skype for Business から Teams にアップグレードした場合、Skype for Business 管理センターで構成した外部通信設定が Teams に移行されます。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-147">If you upgraded from Skype for Business to Teams, the external communications settings that you configured in the Skype for Business admin center are migrated to Teams.</span></span>

### <a name="in-the-microsoft-teams-admin-center"></a><span data-ttu-id="0ab9a-148">Microsoft Teams 管理センターで</span><span class="sxs-lookup"><span data-stu-id="0ab9a-148">In the Microsoft Teams admin center</span></span>

<span data-ttu-id="0ab9a-149">Microsoft Teams 管理センターで、[**組織全体の設定**] の [外部アクセス] に移動し、[  >  **External access\*\*\*\*ユーザーが Skype ユーザーと通信できるよう**にする] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-149">In the Microsoft Teams admin center, go to **Org-wide settings** > **External access**, and then turn on **Users can communicate with Skype users**.</span></span> <span data-ttu-id="0ab9a-150">このような外部アクセス設定を構成する方法については、「 [Teams で外部アクセスを管理](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-150">For step-by-step guidance on how to configure this and other external access settings, see [Manage external access in Teams](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="0ab9a-151">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="0ab9a-151">Using PowerShell</span></span>

<span data-ttu-id="0ab9a-152">パラメーターと共に [CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) コマンドレットを使用して、 ```EnablePublicCloudAccess``` Teams ユーザーが Skype ユーザーと通信できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-152">Use the [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) cmdlet together with the ```EnablePublicCloudAccess``` parameter to control whether Teams users can communicate with Skype users.</span></span> <span data-ttu-id="0ab9a-153">```true```チームユーザーが Skype ユーザーと通信できるようにパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-153">Setting the parameter to ```true``` allows Teams users to communicate with Skype users.</span></span> <span data-ttu-id="0ab9a-154">このパラメーターを使って、 ```EnablePublicCloudAudioVideoAccess``` 音声/ビデオ通話を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="0ab9a-154">You can use the ```EnablePublicCloudAudioVideoAccess``` parameter to enable/disable audio/video calls.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0ab9a-155">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0ab9a-155">Related topics</span></span>

- [<span data-ttu-id="0ab9a-156">Teams で外部アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="0ab9a-156">Manage external access in Teams</span></span>](manage-external-access.md)
- [<span data-ttu-id="0ab9a-157">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="0ab9a-157">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
