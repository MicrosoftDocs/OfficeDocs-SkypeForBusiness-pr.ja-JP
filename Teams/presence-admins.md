---
title: Teams でのユーザーのプレゼンス
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Teams のプレゼンスに関する管理者向けの情報です。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e0d7ef2fa7ae12f660bf6b77ba7c45a8c49ab10
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863198"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="becfd-103">Teams でのユーザーのプレゼンス</span><span class="sxs-lookup"><span data-stu-id="becfd-103">User presence in Teams</span></span>

<span data-ttu-id="becfd-104">プレゼンスは、Microsoft Teams (および Office 365 全体) のユーザーのプロファイルの一部であり、ユーザーの現在の可用性と他のユーザーの状態を示します。</span><span class="sxs-lookup"><span data-stu-id="becfd-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) that indicates the user’s current availability and status to other users.</span></span> <span data-ttu-id="becfd-105">既定では、他のユーザーがオンラインで利用できる場合、チームを使っているすべてのユーザーに (ほぼリアルタイムで) 表示できます。</span><span class="sxs-lookup"><span data-stu-id="becfd-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="becfd-106">ユーザーを [**Teams のみ**] モードに移動した後に Skype for Business クライアントをアンインストールすると、Outlook および Office アプリでプレゼンスが機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="becfd-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="becfd-107">プレゼンスは Teams では正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="becfd-107">Presence works fine in Teams.</span></span> <span data-ttu-id="becfd-108">回避策: Outlook (および他の Office アプリ) でプレゼンスを表示させるには、Teams を [**Teams のみ**] モードで実行している場合であっても、Skype for Business をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="becfd-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="becfd-109">Microsoft はこの問題を把握しており、現在修正に向けて取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="becfd-109">Microsoft is aware of this problem and is working on a fix.</span></span>

<span data-ttu-id="becfd-110">Outlook での Teams のプレゼンスは、Outlook 2013 デスクトップ版アプリ以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="becfd-110">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="becfd-111">Teams のプレゼンス状態</span><span class="sxs-lookup"><span data-stu-id="becfd-111">Presence states in Teams</span></span>

<span data-ttu-id="becfd-112">Teams で利用できるユーザーのプレゼンス状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="becfd-112">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="becfd-113">ユーザー構成済み</span><span class="sxs-lookup"><span data-stu-id="becfd-113">User configured</span></span>|<span data-ttu-id="becfd-114">構成済みのアプリ</span><span class="sxs-lookup"><span data-stu-id="becfd-114">App configured</span></span>|
|:--- |:---|
| ![正常に機能していることを示す緑色のチェックマーク](media/Presence_Available.png) <span data-ttu-id="becfd-116">利用可能</span><span class="sxs-lookup"><span data-stu-id="becfd-116">Available</span></span>|![正常に機能していることを示す緑色のチェックマーク](media/Presence_Available.png) <span data-ttu-id="becfd-118">利用可能</span><span class="sxs-lookup"><span data-stu-id="becfd-118">Available</span></span>|
|| ![使用可能な oof を示す緑のチェックマークを開く](media/Presence_Available_OOF.png) <span data-ttu-id="becfd-120">利用可能、外出中</span><span class="sxs-lookup"><span data-stu-id="becfd-120">Available, Out of Office</span></span> |
|  ![赤い丸で塗りつぶし、取り込み中](media/Presence_Busy.png) <span data-ttu-id="becfd-122">少ない</span><span class="sxs-lookup"><span data-stu-id="becfd-122">Busy</span></span> |  ![赤い丸で塗りつぶし、取り込み中](media/Presence_Busy.png) <span data-ttu-id="becfd-124">少ない</span><span class="sxs-lookup"><span data-stu-id="becfd-124">Busy</span></span>  |
|| !["通話中" であることを示す赤色の丸](media/Presence_Busy.png) <span data-ttu-id="becfd-126">通話中</span><span class="sxs-lookup"><span data-stu-id="becfd-126">On a call</span></span>|
|| ![赤い丸で囲まれるので、会議中に取り込み中であることを示します。](media/Presence_Busy.png) <span data-ttu-id="becfd-128">会議中</span><span class="sxs-lookup"><span data-stu-id="becfd-128">In a meeting</span></span> |
|| ![赤い丸で囲まれる、取り込み中であることを示す](media/Presence_Busy_OOF.png) <span data-ttu-id="becfd-130">通話中、外出中</span><span class="sxs-lookup"><span data-stu-id="becfd-130">On a call, out of office</span></span>|
|  ![白の丸で囲まれた赤い円。 [応答不可] を示します。](media/Presence_DND.png) <span data-ttu-id="becfd-132">応答不可</span><span class="sxs-lookup"><span data-stu-id="becfd-132">Do not disturb</span></span> ||
|| ![赤い円に白線を付け、プレゼンテーションを示します。](media/Presence_DND.png) <span data-ttu-id="becfd-134">発表</span><span class="sxs-lookup"><span data-stu-id="becfd-134">Presenting</span></span>|
|| ![赤の丸 (白の線) は、フォーカスがあることを示します。](media/Presence_DND.png) <span data-ttu-id="becfd-136">焦点</span><span class="sxs-lookup"><span data-stu-id="becfd-136">Focusing</span></span>|
| ![黄色の時計アイコン。退席中であることを示します。](media/Presence_Away.png) <span data-ttu-id="becfd-138">位置</span><span class="sxs-lookup"><span data-stu-id="becfd-138">Away</span></span>| ![黄色の時計アイコン。退席中であることを示します。](media/Presence_Away.png) <span data-ttu-id="becfd-140">位置</span><span class="sxs-lookup"><span data-stu-id="becfd-140">Away</span></span>|
|| <span data-ttu-id="becfd-141">![黄色の時計アイコン。 [](media/Presence_Away.png)最終版]*が表示さ*れていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="becfd-141">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![黄色の時計アイコン。退席中として表示されます。](media/Presence_Away.png) <span data-ttu-id="becfd-143">一時退席中</span><span class="sxs-lookup"><span data-stu-id="becfd-143">Be right back</span></span>| |
|| ![黄色の時計アイコン、[退席中]、[勤務停止]](media/Presence_Away.png)  <span data-ttu-id="becfd-145">業務時間外</span><span class="sxs-lookup"><span data-stu-id="becfd-145">Off Work</span></span>|
|| ![灰色の丸と x (x、オフラインを示す)](media/Presence_Offline.png) <span data-ttu-id="becfd-147">で</span><span class="sxs-lookup"><span data-stu-id="becfd-147">Offline</span></span> |
|| ![灰色の円を開く、状態が不明であることを示す](media/Presence_Unknown.png) <span data-ttu-id="becfd-149">状態不明</span><span class="sxs-lookup"><span data-stu-id="becfd-149">Status unknown</span></span>|
||![四角で囲まれた赤い円を開き、ブロックされていることを示します。](media/Presence_Blocked.png) <span data-ttu-id="becfd-151">ブロックされました</span><span class="sxs-lookup"><span data-stu-id="becfd-151">Blocked</span></span> |
|| ![矢印付き紫色の円は、外出中であることを示します。](media/Presence_OOF.png) <span data-ttu-id="becfd-153">外出中</span><span class="sxs-lookup"><span data-stu-id="becfd-153">Out of Office</span></span>|
|||
 
<span data-ttu-id="becfd-154">ユーザーは、現在のプレゼンス状態をいくつかのオプションに手動で設定することができ、その状態は他のすべてのユーザーに反映されます。</span><span class="sxs-lookup"><span data-stu-id="becfd-154">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="becfd-155">その他のユーザーのプレゼンス情報も自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="becfd-155">More user presence details are also automatically updated.</span></span> <span data-ttu-id="becfd-156">変更は、ユーザーのアクティビティ (利用可能、退席中)、Outlook の予定表の状態 (会議中)、またはチームアプリの状態 (通話中、発表中) に基づいて、一覧でインデントされた状態に基づいて行われます。</span><span class="sxs-lookup"><span data-stu-id="becfd-156">The changes are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span> <span data-ttu-id="becfd-157">現在のプレゼンス状態が [退席中] にリセットされるまでの15分間のアイドル時間のタイムアウトがあります。</span><span class="sxs-lookup"><span data-stu-id="becfd-157">There's a 15-minute inactivity timeout, after which a current presence state is reset to Away.</span></span>

<span data-ttu-id="becfd-158">ユーザーには、プレゼンス状態に関係なく、すべてのチャットメッセージが Teams で送信されます。</span><span class="sxs-lookup"><span data-stu-id="becfd-158">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="becfd-159">他のユーザーがメッセージを送信したときにユーザーがオフラインになっている場合は、次回ユーザーがオンラインになったときに、Teams にチャットメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="becfd-159">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="becfd-160">ユーザーが [応答不可] 状態にある場合でも、ユーザーはチャットメッセージを受け取りますが、バナー通知は表示されません。</span><span class="sxs-lookup"><span data-stu-id="becfd-160">If a user is in a Do Not Disturb state, the user will still get chat messages but a banner notification won't be displayed.</span></span>

<span data-ttu-id="becfd-161">ユーザーは、[応答不可] 状態 (着信通話がボイスメールに配信される) を除き、すべてのプレゼンス状態で通話を受信します。</span><span class="sxs-lookup"><span data-stu-id="becfd-161">Users receive calls in all presence states except for Do Not Disturb states, in which incoming calls are delivered to their voicemail.</span></span> <span data-ttu-id="becfd-162">受信者が発信者をブロックした場合、通話は配信されず、発信者には受信者のプレゼンスがオフラインとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="becfd-162">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="becfd-163">ユーザーを優先順位の高いアクセスリストに追加するには、Teams の [**設定** > ]**プライバシー**に移動します。</span><span class="sxs-lookup"><span data-stu-id="becfd-163">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="becfd-164">ユーザーが [応答不可] の状態にある場合でも、アクセス権が付与されているユーザーに連絡できます。</span><span class="sxs-lookup"><span data-stu-id="becfd-164">People who have priority access can contact the user even when the user is in a Do Not Disturb state.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="becfd-165">Skype for Business と比較した場合のチームの管理設定</span><span class="sxs-lookup"><span data-stu-id="becfd-165">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="becfd-166">Skype for Business の次の管理設定は、Teams では異なります。</span><span class="sxs-lookup"><span data-stu-id="becfd-166">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="becfd-167">Teams では、組織内のユーザーに対してプレゼンス共有が常に有効になります。</span><span class="sxs-lookup"><span data-stu-id="becfd-167">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="becfd-168">プライバシー (プレゼンスを表示できるユーザーを定義した場合) 構成は Teams では利用できません。</span><span class="sxs-lookup"><span data-stu-id="becfd-168">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="becfd-169">すべてのユーザー (フェデレーションサービスを含む) とのプレゼンスの共有は、Teams のユーザーに対して常に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="becfd-169">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="becfd-170">連絡先リスト (Skype for Business に含まれている場合) は、**チャット >** の [連絡先] または [ **> の連絡先**への通話] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="becfd-170">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="becfd-171">クライアントが応答不可であり、チーム内のユーザーに対して画期的な機能が常に有効になります。</span><span class="sxs-lookup"><span data-stu-id="becfd-171">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="becfd-172">予定表 (不在およびその他の予定表情報が含まれています) は、Teams が Outlook と統合されている場合、ユーザーに対して常に有効になります。</span><span class="sxs-lookup"><span data-stu-id="becfd-172">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="becfd-173">組織で Skype for Business が使用されている場合、[*最終表示*または*退席後*の状態の後、チームのユーザーは常に有効になります。</span><span class="sxs-lookup"><span data-stu-id="becfd-173">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="becfd-174">チーム管理者がこれらの設定をカスタマイズできるかどうかは、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="becfd-174">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="becfd-175">Skype for Business と共存する</span><span class="sxs-lookup"><span data-stu-id="becfd-175">Coexistence with Skype for Business</span></span>

<span data-ttu-id="becfd-176">組織で Skype for business を使用している場合の Teams の機能の詳細については、「 [skype For business との共存](coexistence-chat-calls-presence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="becfd-176">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
