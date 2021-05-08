---
title: TeamsとSkype相互運用性
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
description: 組織内のユーザーとコンシューマー (コンシューマー) Teamsユーザーの間の相互運用Skypeについて説明します。
localization_priority: Normal
ms.openlocfilehash: e3203c03043dbcdb04370cf3aa26b435fad4a728
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093957"
---
# <a name="teams-and-skype-interoperability"></a><span data-ttu-id="7a86a-103">TeamsとSkype相互運用性</span><span class="sxs-lookup"><span data-stu-id="7a86a-103">Teams and Skype interoperability</span></span>

<span data-ttu-id="7a86a-104">この記事では、アプリケーションとアプリケーション (コンシューマー) の間の相互運用Microsoft Teams Skypeについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7a86a-104">This article gives you an overview of the interoperability capabilities between Microsoft Teams and Skype (Consumer).</span></span> <span data-ttu-id="7a86a-105">ユーザーとTeamsユーザー Skypeを通じて通信する方法と、適用される管理者コントロールについて学習します。</span><span class="sxs-lookup"><span data-stu-id="7a86a-105">Learn how Teams users and Skype users can communicate through chats and calls and the admin controls that apply.</span></span>

<span data-ttu-id="7a86a-106">Teams組織内のユーザーは、メール アドレスを使用して、Skypeユーザーとチャットや通話を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7a86a-106">Teams users in your organization can chat with and call Skype users by using their email address and vice versa.</span></span>

- <span data-ttu-id="7a86a-107">Teamsユーザーは、1 対 1 のテキスト専用会話または音声/ビデオ通話を検索して開始Skypeできます。</span><span class="sxs-lookup"><span data-stu-id="7a86a-107">Teams users can search for and start a one-on-one text-only conversation or an audio/video call with a Skype user.</span></span>
- <span data-ttu-id="7a86a-108">Skypeユーザーは、1 対 1 のテキスト専用会話または音声/ビデオ通話を検索して開始Teamsできます。</span><span class="sxs-lookup"><span data-stu-id="7a86a-108">Skype users can search for and start a one-on-one text-only conversation or an audio/video call with a Teams user.</span></span>

<span data-ttu-id="7a86a-109">これらの機能は、デスクトップ、Web、モバイル (Android および iOS) クライアントで、Teams と Skype。</span><span class="sxs-lookup"><span data-stu-id="7a86a-109">These capabilities are available on the desktop, web, and mobile (Android and iOS) clients for both Teams and Skype.</span></span> <span data-ttu-id="7a86a-110">最適なエクスペリエンスを実現するには、バージョン 8.58 Skypeを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7a86a-110">For an optimal experience, we recommend Skype version 8.58 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="7a86a-111">このTeamsで説明する Skype と Skype の相互運用機能は、GCC、GCC High、DOD のデプロイ、またはプライベート クラウド環境では使用できません。</span><span class="sxs-lookup"><span data-stu-id="7a86a-111">The Teams and Skype interop capabilities discussed in this article aren't available in GCC, GCC High, or DOD deployments, or in private cloud environments.</span></span>

## <a name="chat-and-calling-experience"></a><span data-ttu-id="7a86a-112">チャットと通話のエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="7a86a-112">Chat and calling experience</span></span>

<span data-ttu-id="7a86a-113">チャットと通話エクスペリエンスの概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7a86a-113">Here's an overview of the chat and calling experience.</span></span>

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a><span data-ttu-id="7a86a-114">Teamsユーザーがチャットを開始するか、他のユーザーと通話Skypeする</span><span class="sxs-lookup"><span data-stu-id="7a86a-114">Teams user starts a chat or call with a Skype user</span></span>

<span data-ttu-id="7a86a-115">Teamsユーザーは、新しいチャットSkype検索バーにメール アドレスを入力して、ユーザーを検索できます。</span><span class="sxs-lookup"><span data-stu-id="7a86a-115">Teams users can search for a Skype user by typing their email address in a new chat or in the search bar.</span></span>  <span data-ttu-id="7a86a-116">次Teamsユーザーは、検索結果Skypeユーザーを選択して、チャットを開始したり、チャットを呼び出したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="7a86a-116">The Teams user can then select the Skype user in the search results to start a chat or call with them.</span></span>

<span data-ttu-id="7a86a-117">ユーザー Skype検索結果に表示しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="7a86a-117">A Skype user may choose not to appear in search results.</span></span> <span data-ttu-id="7a86a-118">この場合、ユーザーは Teams の検索結果に表示されTeamsユーザーは検索結果を見つけ出せしません。</span><span class="sxs-lookup"><span data-stu-id="7a86a-118">In this case, they won't show up in the search results in Teams and Teams users won't be able to find them.</span></span>

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a><span data-ttu-id="7a86a-119">Skypeユーザーが他のユーザーとチャットまたは通話をTeamsする</span><span class="sxs-lookup"><span data-stu-id="7a86a-119">Skype user starts a chat or call with a Teams user</span></span>

<span data-ttu-id="7a86a-120">Skypeユーザーは、自分のメール アドレスを使用して、Teamsを検索し、チャットを開始できます。</span><span class="sxs-lookup"><span data-stu-id="7a86a-120">Skype users can search for and start a chat with a Teams user by using their email address.</span></span> <span data-ttu-id="7a86a-121">ユーザー Teams、Skype ユーザーから新しいメッセージを受け取り、返信する前に最初にメッセージを受け入れる必要があるという通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7a86a-121">The Teams user is notified that they have a new message from a Skype user, and has to first accept the message before they can reply to it.</span></span>

- <span data-ttu-id="7a86a-122">ユーザーが [Teams] を選択した場合、会話は受け入れ、両方のユーザーがチャットし、互いに通話できます。</span><span class="sxs-lookup"><span data-stu-id="7a86a-122">If the Teams user selects **Accept**, the conversation is accepted, and both users can chat and call each other.</span></span>
- <span data-ttu-id="7a86a-123">ユーザーが Teams を選択すると、会話はブロックされ、そのユーザーからの後続のメッセージと呼び出Skypeブロックされます。</span><span class="sxs-lookup"><span data-stu-id="7a86a-123">If the Teams user selects **Block**, the conversation is blocked, and subsequent messages and calls from that Skype user are blocked.</span></span>
- <span data-ttu-id="7a86a-124">ユーザーが Teams を選択した場合、メッセージは Teams に表示され、ユーザーは会話を受け入れるかブロックするか判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7a86a-124">If the Teams user selects **View messages**, the message is displayed in Teams, which helps the user decide whether to accept or block the conversation.</span></span>

> [!NOTE]
> <span data-ttu-id="7a86a-125">Skype for Business から Teams にアップグレードし、ユーザーが Teams のみモードの場合は、Skype ユーザーから Teams ユーザーへのチャットと呼び出しが Teams に配信されます。</span><span class="sxs-lookup"><span data-stu-id="7a86a-125">If you upgraded from Skype for Business to Teams and your users are in Teams Only mode, chats and calls from Skype users to Teams users are delivered to Teams.</span></span> <span data-ttu-id="7a86a-126">ユーザーが諸島モードの場合、チャットや通話は、SkypeからTeamsに配信Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="7a86a-126">If your users are in Islands mode, chats and calls from Skype users to Teams users are delivered to Skype for Business.</span></span>

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a><span data-ttu-id="7a86a-127">Teamsユーザーをブロックまたはブロック解除Skypeする</span><span class="sxs-lookup"><span data-stu-id="7a86a-127">Teams user blocks or unblocks a Skype user</span></span>

<span data-ttu-id="7a86a-128">ユーザーはTeams Skype ユーザーからの最初の会話要求を受け入れるかブロックした後、いつでもそのユーザーをブロックまたはブロック解除できます。</span><span class="sxs-lookup"><span data-stu-id="7a86a-128">After a Teams user accepts or blocks the initial conversation request from a Skype user, they can choose to block or unblock that person at any time.</span></span> <span data-ttu-id="7a86a-129">この操作は、会話またはユーザーのプライバシー設定 (Teams) で行Teams。</span><span class="sxs-lookup"><span data-stu-id="7a86a-129">They can do this either in the conversation or in their privacy settings in Teams.</span></span> <span data-ttu-id="7a86a-130">Skypeユーザーは、ブロックされているのを知りません。</span><span class="sxs-lookup"><span data-stu-id="7a86a-130">Skype users won't know that they've been blocked.</span></span>

<span data-ttu-id="7a86a-131">ブロックSkype他のユーザー、および Teams ユーザーがブロックした公衆交換電話網 (PSTN) 電話番号と共に、Teams のユーザーのブロックされた連絡先リストに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="7a86a-131">Blocked Skype users, along with other people and public switched telephone network (PSTN) phone numbers that a Teams user has blocked, are listed on the user's blocked contact list in Teams.</span></span>

## <a name="limitations"></a><span data-ttu-id="7a86a-132">制限事項</span><span class="sxs-lookup"><span data-stu-id="7a86a-132">Limitations</span></span>

- <span data-ttu-id="7a86a-133">会話はテキスト専用です。</span><span class="sxs-lookup"><span data-stu-id="7a86a-133">Conversations are text-only.</span></span> <span data-ttu-id="7a86a-134">つまり、リッチな書式設定、@mentions、絵文字、またはネイティブのチャット エクスペリエンスで使用できるその他のチャット[機能Teamsはありません](native-chat-for-external-users.md)。</span><span class="sxs-lookup"><span data-stu-id="7a86a-134">This means that there's no rich formatting, @mentions, emojis, or other any of the other chat features that are available in a [native Teams chat experience](native-chat-for-external-users.md).</span></span>
- <span data-ttu-id="7a86a-135">会話は 1 対 1 のみです。</span><span class="sxs-lookup"><span data-stu-id="7a86a-135">Conversations are one-on-one only.</span></span> <span data-ttu-id="7a86a-136">グループ チャットはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7a86a-136">Group chats aren't supported.</span></span>
- <span data-ttu-id="7a86a-137">TeamsユーザーとSkypeユーザーが互いにプレゼンスを表示できない。</span><span class="sxs-lookup"><span data-stu-id="7a86a-137">Teams users and Skype users can't see each other's presence.</span></span>
- <span data-ttu-id="7a86a-138">ユーザー ID Skype電話番号を使用してSkypeユーザーを検索する機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7a86a-138">Searching for Skype users by using their Skype ID or phone number isn't supported.</span></span>
- <span data-ttu-id="7a86a-139">Skypeユーザーは、別のユーザーの番号、代理人の番号、または公衆交換電話網 (PSTN) 番号への転送を設定した Teams ユーザーに通話を発信できない。</span><span class="sxs-lookup"><span data-stu-id="7a86a-139">Skype users can't call Teams users who set up call forwarding to another user's number, a delegate's number, or a Public Switched Telephone Network (PSTN) number.</span></span>  <span data-ttu-id="7a86a-140">ボイスメールだけがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="7a86a-140">Only voicemail is supported.</span></span>
- <span data-ttu-id="7a86a-141">相互運用のエスカレーション、グループ通話、会議はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7a86a-141">Interop escalation, group calls, and meetings aren't supported.</span></span>
- <span data-ttu-id="7a86a-142">代理人がユーザーに代わって Skypeを呼び出す機能Teamsサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7a86a-142">The ability for a delegate to call a Skype user on behalf of a Teams user isn't supported.</span></span>
- <span data-ttu-id="7a86a-143">チャットでの画面共有はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7a86a-143">Screen sharing with chat isn't supported.</span></span>

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a><span data-ttu-id="7a86a-144">ユーザーがTeamsユーザーと通信できるかどうかをSkypeする</span><span class="sxs-lookup"><span data-stu-id="7a86a-144">Set whether Teams users can communicate with Skype users</span></span>

<span data-ttu-id="7a86a-145">管理者は、Microsoft Teams 管理センターまたは PowerShell を使用して外部アクセス設定を設定し、組織内の Teams ユーザーが Skype ユーザーと通信できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="7a86a-145">As an admin, you use the Microsoft Teams admin center or PowerShell to set external access settings to control whether Teams users in your organization can communicate with Skype users.</span></span> <span data-ttu-id="7a86a-146">既定では、この機能は新しいテナントに対して有効になっています。</span><span class="sxs-lookup"><span data-stu-id="7a86a-146">By default, this capability is turned on for new tenants.</span></span> <span data-ttu-id="7a86a-147">ただし、ドメインでまだ使用できない場合は、次の DNS SRV レコードを IT 管理者が構成する必要があります (_sipfederationtls.contoso.com など)。</span><span class="sxs-lookup"><span data-stu-id="7a86a-147">However, there's a prerequisite that the following DNS SRV record needs to be configured by the IT Admin if not already available for your domain, for example _sipfederationtls.contoso.com.</span></span>  

<span data-ttu-id="7a86a-148">**サービス**: sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="7a86a-148">**Service**: sipfederationtls</span></span><br/>
<span data-ttu-id="7a86a-149">**プロトコル**: TCP</span><span class="sxs-lookup"><span data-stu-id="7a86a-149">**Protocol**: TCP</span></span><br/>
<span data-ttu-id="7a86a-150">**優先度**: 100</span><span class="sxs-lookup"><span data-stu-id="7a86a-150">**Priority**: 100</span></span><br/>
<span data-ttu-id="7a86a-151">**重** み: 1</span><span class="sxs-lookup"><span data-stu-id="7a86a-151">**Weight**: 1</span></span><br/>
<span data-ttu-id="7a86a-152">**ポート**: 5061</span><span class="sxs-lookup"><span data-stu-id="7a86a-152">**Port**: 5061</span></span><br/>
<span data-ttu-id="7a86a-153">**ターゲット**: sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7a86a-153">**Target**: sipfed.online.lync.com</span></span>

<span data-ttu-id="7a86a-154">Skype for Business から Teams にアップグレードした場合、Skype for Business 管理センターで構成した外部通信設定は、Teams に移行されます。</span><span class="sxs-lookup"><span data-stu-id="7a86a-154">If you upgraded from Skype for Business to Teams, the external communications settings that you configured in the Skype for Business admin center are migrated to Teams.</span></span>

### <a name="in-the-microsoft-teams-admin-center"></a><span data-ttu-id="7a86a-155">Microsoft Teams 管理センターで</span><span class="sxs-lookup"><span data-stu-id="7a86a-155">In the Microsoft Teams admin center</span></span>

<span data-ttu-id="7a86a-156">管理センター Microsoft Teams、組織全体の設定 [外部アクセス] に移動し、[ユーザーは他のユーザーと通信Skype  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="7a86a-156">In the Microsoft Teams admin center, go to **Org-wide settings** > **External access**, and then turn on **Users can communicate with Skype users**.</span></span> <span data-ttu-id="7a86a-157">この設定と他の外部アクセス設定を構成する方法の詳細なガイダンスについては、「外部アクセスの管理」を参照[Teams。](./manage-external-access.md#allow-or-block-domains)</span><span class="sxs-lookup"><span data-stu-id="7a86a-157">For step-by-step guidance on how to configure this and other external access settings, see [Manage external access in Teams](./manage-external-access.md#allow-or-block-domains).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="7a86a-158">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="7a86a-158">Using PowerShell</span></span>

<span data-ttu-id="7a86a-159">以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7a86a-159">Do the following:</span></span> 
1. <span data-ttu-id="7a86a-160">[Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)コマンドレットを パラメーターと共に使用して、Teamsユーザーと通信できるかどうか ```EnablePublicCloudAccess``` Skypeします。</span><span class="sxs-lookup"><span data-stu-id="7a86a-160">Use the [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) cmdlet together with the ```EnablePublicCloudAccess``` parameter to control whether Teams users can communicate with Skype users.</span></span> <span data-ttu-id="7a86a-161">パラメーターを に設定すると ```true``` 、ユーザー Teamsユーザーと通信Skypeできます。</span><span class="sxs-lookup"><span data-stu-id="7a86a-161">Setting the parameter to ```true``` allows Teams users to communicate with Skype users.</span></span> <span data-ttu-id="7a86a-162">パラメーターを使用して ```EnablePublicCloudAudioVideoAccess``` 、音声/ビデオ通話を有効/無効にできます。</span><span class="sxs-lookup"><span data-stu-id="7a86a-162">You can use the ```EnablePublicCloudAudioVideoAccess``` parameter to enable/disable audio/video calls.</span></span>

2. <span data-ttu-id="7a86a-163">[Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider)コマンドレットを パラメーター を に設定して、Teamsユーザーと通信Skype ```Provider``` ```"WindowsLive"``` します。</span><span class="sxs-lookup"><span data-stu-id="7a86a-163">Use the [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet together with the ```Provider``` parameter set to ```"WindowsLive"``` so that Teams users can communicate with Skype users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7a86a-164">関連トピック</span><span class="sxs-lookup"><span data-stu-id="7a86a-164">Related topics</span></span>

- [<span data-ttu-id="7a86a-165">Teams で外部アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="7a86a-165">Manage external access in Teams</span></span>](manage-external-access.md)
- [<span data-ttu-id="7a86a-166">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="7a86a-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)