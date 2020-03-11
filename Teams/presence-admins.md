---
title: Teams でのユーザーのプレゼンス
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Teams でのプレゼンスに関する管理者向け情報。
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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863198"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="1d3da-103">Teams でのユーザーのプレゼンス</span><span class="sxs-lookup"><span data-stu-id="1d3da-103">User presence in Teams</span></span>

<span data-ttu-id="1d3da-104">プレゼンスは、Microsoft Teams (および Office 365 全体) のユーザーのプロファイルの一部であり、ユーザーの現在の空き状況や状態を他のユーザーに示します。</span><span class="sxs-lookup"><span data-stu-id="1d3da-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) that indicates the user’s current availability and status to other users.</span></span> <span data-ttu-id="1d3da-105">既定では、組織内で Teams を使用しているすべてのユーザーは、他のユーザーがオンラインの場合、(ほぼリアルタイムで) 確認できます。</span><span class="sxs-lookup"><span data-stu-id="1d3da-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d3da-106">ユーザーを [**Teams のみ**] モードに移動した後に Skype for Business クライアントをアンインストールすると、Outlook および Office アプリでプレゼンスが機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="1d3da-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="1d3da-107">プレゼンスは Teams では正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="1d3da-107">Presence works fine in Teams.</span></span> <span data-ttu-id="1d3da-108">回避策: Outlook (および他の Office アプリ) でプレゼンスを表示させるには、Teams を [**Teams のみ**] モードで実行している場合であっても、Skype for Business をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d3da-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="1d3da-109">Microsoft はこの問題を把握しており、現在修正に向けて取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="1d3da-109">Microsoft is aware of this problem and is working on a fix.</span></span>

<span data-ttu-id="1d3da-110">Outlook での Teams のプレゼンスは、Outlook 2013 デスクトップ版アプリ以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1d3da-110">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="1d3da-111">Teams でのプレゼンス状態</span><span class="sxs-lookup"><span data-stu-id="1d3da-111">Presence states in Teams</span></span>

<span data-ttu-id="1d3da-112">Teams で利用できるユーザーのプレゼンス状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1d3da-112">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="1d3da-113">ユーザーが設定</span><span class="sxs-lookup"><span data-stu-id="1d3da-113">User configured</span></span>|<span data-ttu-id="1d3da-114">アプリが設定</span><span class="sxs-lookup"><span data-stu-id="1d3da-114">App configured</span></span>|
|:--- |:---|
| ![塗りつぶした緑のチェックマークは、連絡可能な状態を示す](media/Presence_Available.png) <span data-ttu-id="1d3da-116">連絡可能</span><span class="sxs-lookup"><span data-stu-id="1d3da-116">Available</span></span>|![塗りつぶした緑のチェックマークは、連絡可能な状態を示す](media/Presence_Available.png) <span data-ttu-id="1d3da-118">連絡可能</span><span class="sxs-lookup"><span data-stu-id="1d3da-118">Available</span></span>|
|| ![緑枠のチェックマークは、連絡可能な外出中の状態を示す](media/Presence_Available_OOF.png) <span data-ttu-id="1d3da-120">連絡可能、外出中</span><span class="sxs-lookup"><span data-stu-id="1d3da-120">Available, Out of Office</span></span> |
|  ![塗りつぶした赤い丸は、取り込み中を示す](media/Presence_Busy.png) <span data-ttu-id="1d3da-122">取り込み中</span><span class="sxs-lookup"><span data-stu-id="1d3da-122">Busy</span></span> |  ![塗りつぶした赤い丸は、取り込み中を示す](media/Presence_Busy.png) <span data-ttu-id="1d3da-124">取り込み中</span><span class="sxs-lookup"><span data-stu-id="1d3da-124">Busy</span></span>  |
|| ![塗りつぶした赤い丸は、通話のための取り込み中を示す](media/Presence_Busy.png) <span data-ttu-id="1d3da-126">通話中</span><span class="sxs-lookup"><span data-stu-id="1d3da-126">On a call</span></span>|
|| ![塗りつぶした赤い丸は、会議のための取り込み中を示す](media/Presence_Busy.png) <span data-ttu-id="1d3da-128">会議中</span><span class="sxs-lookup"><span data-stu-id="1d3da-128">In a meeting</span></span> |
|| ![赤枠の丸は、取り込み中を示す](media/Presence_Busy_OOF.png) <span data-ttu-id="1d3da-130">通話中、外出中</span><span class="sxs-lookup"><span data-stu-id="1d3da-130">On a call, out of office</span></span>|
|  ![白線の入った赤い丸は、応答不可を示す](media/Presence_DND.png) <span data-ttu-id="1d3da-132">応答不可</span><span class="sxs-lookup"><span data-stu-id="1d3da-132">Do not disturb</span></span> ||
|| ![白線の入った赤い丸は、発表中を示す](media/Presence_DND.png) <span data-ttu-id="1d3da-134">発表中</span><span class="sxs-lookup"><span data-stu-id="1d3da-134">Presenting</span></span>|
|| ![白線の入った赤い丸は、フォーカスを示す](media/Presence_DND.png) <span data-ttu-id="1d3da-136">フォーカス</span><span class="sxs-lookup"><span data-stu-id="1d3da-136">Focusing</span></span>|
| ![黄色の時計アイコンは、退席中を示す](media/Presence_Away.png) <span data-ttu-id="1d3da-138">退席中</span><span class="sxs-lookup"><span data-stu-id="1d3da-138">Away</span></span>| ![黄色の時計アイコンは、退席中を示す](media/Presence_Away.png) <span data-ttu-id="1d3da-140">退席中</span><span class="sxs-lookup"><span data-stu-id="1d3da-140">Away</span></span>|
|| <span data-ttu-id="1d3da-141">![黄色の時計アイコンは、退席中を示す*前回の退席中表示](media/Presence_Away.png)時刻\*</span><span class="sxs-lookup"><span data-stu-id="1d3da-141">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![黄色の時計アイコンは、一時退席中を示す](media/Presence_Away.png) <span data-ttu-id="1d3da-143">一時退席中</span><span class="sxs-lookup"><span data-stu-id="1d3da-143">Be right back</span></span>| |
|| ![黄の時計アイコンは、退席中、業務時間外を示す](media/Presence_Away.png)  <span data-ttu-id="1d3da-145">業務時間外</span><span class="sxs-lookup"><span data-stu-id="1d3da-145">Off Work</span></span>|
|| ![X マーク付き灰色の丸は、オフラインを示す](media/Presence_Offline.png) <span data-ttu-id="1d3da-147">オフライン</span><span class="sxs-lookup"><span data-stu-id="1d3da-147">Offline</span></span> |
|| ![灰色枠の丸は、状態不明を示す](media/Presence_Unknown.png) <span data-ttu-id="1d3da-149">状態不明</span><span class="sxs-lookup"><span data-stu-id="1d3da-149">Status unknown</span></span>|
||![斜線の入った赤枠の丸は、ブロックされたことを示す](media/Presence_Blocked.png) <span data-ttu-id="1d3da-151">ブロックされました</span><span class="sxs-lookup"><span data-stu-id="1d3da-151">Blocked</span></span> |
|| ![矢印付き紫色の丸は、外出中を示す](media/Presence_OOF.png) <span data-ttu-id="1d3da-153">外出中</span><span class="sxs-lookup"><span data-stu-id="1d3da-153">Out of Office</span></span>|
|||
 
<span data-ttu-id="1d3da-154">ユーザーは、現在のプレゼンス状態をいくつかのオプションから手動で設定できます。その状態が他のすべてのユーザーに対して表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d3da-154">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="1d3da-155">ユーザーのプレゼンスの他の詳細情報も自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="1d3da-155">More user presence details are also automatically updated.</span></span> <span data-ttu-id="1d3da-156">ユーザーのアクティビティ (連絡可能、退席中)、Outlook カレンダーの状態 (会議中)、Teams アプリの状態 (通話中、発表中) などに基づいて、このリストの右側の状態に変更されます。</span><span class="sxs-lookup"><span data-stu-id="1d3da-156">The changes are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span> <span data-ttu-id="1d3da-157">15 分間休止状態が続くとタイムアウトが発生し、現在のプレゼンス状態は「退席中」にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="1d3da-157">There's a 15-minute inactivity timeout, after which a current presence state is reset to Away.</span></span>

<span data-ttu-id="1d3da-158">プレゼンス状態に関係なく、ユーザーは、Teams で送信されたすべてのチャット メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="1d3da-158">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="1d3da-159">他者がメッセージを送信したときにユーザーがオフラインだった場合は、次回ユーザーがオンラインになったときに Teams にチャット メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d3da-159">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="1d3da-160">「応答不可」状態にある場合でもユーザーはチャット メッセージを受信できますが、バナー通知は表示されません。</span><span class="sxs-lookup"><span data-stu-id="1d3da-160">If a user is in a Do Not Disturb state, the user will still get chat messages but a banner notification won't be displayed.</span></span>

<span data-ttu-id="1d3da-161">ユーザーは、「応答不可」状態 (着信呼び出しがボイスメールに配信される) を除き、すべてのプレゼンス状態で通話を受信します。</span><span class="sxs-lookup"><span data-stu-id="1d3da-161">Users receive calls in all presence states except for Do Not Disturb states, in which incoming calls are delivered to their voicemail.</span></span> <span data-ttu-id="1d3da-162">受信者が発信者をブロックした場合、通話は配信されず、発信者には受信者のプレゼンスが「オフライン」と表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d3da-162">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="1d3da-163">ユーザーを優先順位の高いアクセス リストに追加するには、Teams の **[設定]** > **[プライバシー]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="1d3da-163">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="1d3da-164">ユーザーが「応答不可」状態にある場合でも、優先アクセス権が付与されている発信者は、ユーザーと連絡を取ることができます。</span><span class="sxs-lookup"><span data-stu-id="1d3da-164">People who have priority access can contact the user even when the user is in a Do Not Disturb state.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="1d3da-165">Skype for Business と Teams の管理設定の比較</span><span class="sxs-lookup"><span data-stu-id="1d3da-165">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="1d3da-166">Skype for Business と Teams では、次の管理設定が異なります。</span><span class="sxs-lookup"><span data-stu-id="1d3da-166">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="1d3da-167">Teams では、組織内ユーザーに対してプレゼンス共有が常に有効になります。</span><span class="sxs-lookup"><span data-stu-id="1d3da-167">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="1d3da-168">プライバシー (プレゼンスを表示できるユーザーを定義する) 構成は、Teams では利用できません。</span><span class="sxs-lookup"><span data-stu-id="1d3da-168">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="1d3da-169">すべてのユーザー (フェデレーション サービスを含む) とのプレゼンス共有は、Teams ユーザーに対して常に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="1d3da-169">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="1d3da-170">連絡先リスト (Skype for Business に含まれている場合) は、**[チャット] > [連絡先]** または **[通話] > [連絡先]** で表示できます。</span><span class="sxs-lookup"><span data-stu-id="1d3da-170">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="1d3da-171">クライアントの「応答不可」と「重要な連絡先」機能は、Teams ユーザーに対して常に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="1d3da-171">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="1d3da-172">カレンダー (不在およびその他のカレンダー情報を含む) は、Teams が Outlook と統合されている場合、ユーザーに対して常に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="1d3da-172">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="1d3da-173">組織で Skype for Business を使用している場合は、*[最終ログイン]* または *[退席中]* インジケータ―が、Teams ユーザーに対して常に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="1d3da-173">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="1d3da-174">Teams 管理者がこれらの設定をカスタマイズする機能は、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1d3da-174">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="1d3da-175">Skype for Business との共存</span><span class="sxs-lookup"><span data-stu-id="1d3da-175">Coexistence with Skype for Business</span></span>

<span data-ttu-id="1d3da-176">組織で Skype for business も使用している場合の Teams のプレゼンス機能の詳細については、「[Skype for Business との共存](coexistence-chat-calls-presence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d3da-176">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
