---
title: Teams でのユーザーのプレゼンス
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Teams のプレゼンス状態、およびプレゼンス機能の管理設定について説明します。
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f14aeaf83862cbdd695eb6ec4646d8da81a0c5b
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369212"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="96b3d-103">Teams でのユーザーのプレゼンス</span><span class="sxs-lookup"><span data-stu-id="96b3d-103">User presence in Teams</span></span>

<span data-ttu-id="96b3d-104">プレゼンスは、Microsoft Teams (および Microsoft 365 または Office 365 全体) のユーザーのプロファイルの一部であり、ユーザーの現在の可用性と他のユーザーの状態を示します。</span><span class="sxs-lookup"><span data-stu-id="96b3d-104">Presence is part of a user's profile in Microsoft Teams (and throughout Microsoft 365 or Office 365) that indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="96b3d-105">既定では、組織内で Teams を使用しているすべてのユーザーは、他のユーザーがオンラインの場合、(ほぼリアルタイムで) 確認できます。</span><span class="sxs-lookup"><span data-stu-id="96b3d-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

<span data-ttu-id="96b3d-106">Outlook での Teams のプレゼンスは、Outlook 2013 デスクトップ版アプリ以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="96b3d-106">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

 > [!Note]
 > <span data-ttu-id="96b3d-107">さまざまなプラットフォームの Teams ユーザープロファイルの詳細については、「 [プラットフォームごとの teams の機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96b3d-107">For details about Teams user profiles on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="96b3d-108">Teams でのプレゼンス状態</span><span class="sxs-lookup"><span data-stu-id="96b3d-108">Presence states in Teams</span></span>

|<span data-ttu-id="96b3d-109">ユーザーが設定</span><span class="sxs-lookup"><span data-stu-id="96b3d-109">User configured</span></span>|<span data-ttu-id="96b3d-110">アプリが設定</span><span class="sxs-lookup"><span data-stu-id="96b3d-110">App configured</span></span>|
|:--- |:---|
| ![塗りつぶした緑のチェックマークは、連絡可能な状態を示す](media/Presence_Available.png) <span data-ttu-id="96b3d-112">連絡可能</span><span class="sxs-lookup"><span data-stu-id="96b3d-112">Available</span></span>|![塗りつぶした緑のチェックマークは、連絡可能な状態を示す](media/Presence_Available.png) <span data-ttu-id="96b3d-114">連絡可能</span><span class="sxs-lookup"><span data-stu-id="96b3d-114">Available</span></span>|
|| ![緑枠のチェックマークは、連絡可能な外出中の状態を示す](media/Presence_Available_OOF.png) <span data-ttu-id="96b3d-116">連絡可能、外出中</span><span class="sxs-lookup"><span data-stu-id="96b3d-116">Available, Out of Office</span></span> |
|  ![塗りつぶした赤い丸は、取り込み中を示す](media/Presence_Busy.png) <span data-ttu-id="96b3d-118">取り込み中</span><span class="sxs-lookup"><span data-stu-id="96b3d-118">Busy</span></span> |  ![塗りつぶした赤い丸は、取り込み中を示す](media/Presence_Busy.png) <span data-ttu-id="96b3d-120">取り込み中</span><span class="sxs-lookup"><span data-stu-id="96b3d-120">Busy</span></span>  |
|| ![塗りつぶした赤い丸は、通話のための取り込み中を示す](media/Presence_Busy.png) <span data-ttu-id="96b3d-122">通話中</span><span class="sxs-lookup"><span data-stu-id="96b3d-122">On a call</span></span>|
|| ![塗りつぶした赤い丸は、会議のための取り込み中を示す](media/Presence_Busy.png) <span data-ttu-id="96b3d-124">会議中</span><span class="sxs-lookup"><span data-stu-id="96b3d-124">In a meeting</span></span> |
|| ![赤枠の丸は、取り込み中を示す](media/Presence_Busy_OOF.png) <span data-ttu-id="96b3d-126">通話中、外出中</span><span class="sxs-lookup"><span data-stu-id="96b3d-126">On a call, out of office</span></span>|
|  ![白線の入った赤い丸は、応答不可を示す](media/Presence_DND.png) <span data-ttu-id="96b3d-128">応答不可</span><span class="sxs-lookup"><span data-stu-id="96b3d-128">Do not disturb</span></span> ||
|| ![白線の入った赤い丸は、発表中を示す](media/Presence_DND.png) <span data-ttu-id="96b3d-130">発表中</span><span class="sxs-lookup"><span data-stu-id="96b3d-130">Presenting</span></span>|
|| ![白線の入った赤い丸は、フォーカスを示す](media/Presence_DND.png) <span data-ttu-id="96b3d-132">フォーカス</span><span class="sxs-lookup"><span data-stu-id="96b3d-132">Focusing</span></span>|
| ![黄色の時計アイコンは、退席中を示す](media/Presence_Away.png) <span data-ttu-id="96b3d-134">退席中</span><span class="sxs-lookup"><span data-stu-id="96b3d-134">Away</span></span>| ![黄色の時計アイコンは、退席中を示す](media/Presence_Away.png) <span data-ttu-id="96b3d-136">退席中</span><span class="sxs-lookup"><span data-stu-id="96b3d-136">Away</span></span>|
|| <span data-ttu-id="96b3d-137">![黄色の時計アイコンは、退席中を示す*前回の退席中表示](media/Presence_Away.png)時刻\*</span><span class="sxs-lookup"><span data-stu-id="96b3d-137">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![黄色の時計アイコンは、一時退席中を示す](media/Presence_Away.png) <span data-ttu-id="96b3d-139">一時退席中</span><span class="sxs-lookup"><span data-stu-id="96b3d-139">Be right back</span></span>| |
|![X マーク付き灰色の丸は、オフラインを示す](media/Presence_Offline.png) <span data-ttu-id="96b3d-141">オフラインとして表示する</span><span class="sxs-lookup"><span data-stu-id="96b3d-141">Appear offline</span></span> | ![X マーク付き灰色の丸は、オフラインを示す](media/Presence_Offline.png) <span data-ttu-id="96b3d-143">オフライン</span><span class="sxs-lookup"><span data-stu-id="96b3d-143">Offline</span></span>| |
|| ![灰色枠の丸は、状態不明を示す](media/Presence_Unknown.png) <span data-ttu-id="96b3d-145">状態不明</span><span class="sxs-lookup"><span data-stu-id="96b3d-145">Status unknown</span></span>|
|| ![矢印付き紫色の丸は、外出中を示す](media/Presence_OOF.png) <span data-ttu-id="96b3d-147">外出中</span><span class="sxs-lookup"><span data-stu-id="96b3d-147">Out of Office</span></span>|
|||

<span data-ttu-id="96b3d-148">アプリで構成されたプレゼンス状態は、ユーザーアクティビティ (利用可能、退席中)、Outlook の予定表の状態 (会議中)、または Teams アプリの状態 (通話中、発表中) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="96b3d-148">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span> <span data-ttu-id="96b3d-149">予定表に基づいてフォーカスモードになっている場合は、チームでのユーザーの表示状態に注目されますが、他の製品では [応答不可] として表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="96b3d-149">Note that when you are in focus mode based on your calendar, Focusing will be the state people see in Teams, but it will display as Do not disturb in other products.</span></span>

<span data-ttu-id="96b3d-150">コンピューターをロックした場合、またはコンピューターがアイドルまたはスリープモードに切り替わったときに、現在のプレゼンス状態が "退席中" に変わります。</span><span class="sxs-lookup"><span data-stu-id="96b3d-150">Your current presence state changes to Away when you lock your computer or when your computer enters idle or sleep mode.</span></span> <span data-ttu-id="96b3d-151">モバイルデバイスでは、Teams アプリがバックグラウンドにあるときは、プレゼンス状態が [退席中] に変わります。</span><span class="sxs-lookup"><span data-stu-id="96b3d-151">On a mobile device, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="96b3d-152">プレゼンス状態に関係なく、ユーザーは、Teams で送信されたすべてのチャット メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="96b3d-152">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="96b3d-153">他者がメッセージを送信したときにユーザーがオフラインだった場合は、次回ユーザーがオンラインになったときに Teams にチャット メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="96b3d-153">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="96b3d-154">ユーザー状態が [応答不可] に設定されている場合でも、ユーザーはチャットメッセージを受信しますが、バナー通知は表示されません。</span><span class="sxs-lookup"><span data-stu-id="96b3d-154">If a user state is set to Do not disturb, the user will still receive chat messages, but banner notifications aren't displayed.</span></span>

<span data-ttu-id="96b3d-155">ユーザーは、[応答不可] (着信通話がボイスメールに転送される) を除くすべてのプレゼンス状態で通話を受信します。</span><span class="sxs-lookup"><span data-stu-id="96b3d-155">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="96b3d-156">受信者が発信者をブロックした場合、通話は配信されず、発信者には受信者のプレゼンスが「オフライン」と表示されます。</span><span class="sxs-lookup"><span data-stu-id="96b3d-156">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="96b3d-157">ユーザーを優先順位の高いアクセス リストに追加するには、Teams の **[設定]** > **[プライバシー]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="96b3d-157">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="96b3d-158">ユーザーの状態が [応答不可] に設定されている場合でも、アクセス権が与えられているユーザーに連絡できます。</span><span class="sxs-lookup"><span data-stu-id="96b3d-158">People who have priority access can contact the user even when the user's status is set to Do not disturb.</span></span>

## <a name="user-configured-states-expiration"></a><span data-ttu-id="96b3d-159">ユーザー構成状態の有効期限</span><span class="sxs-lookup"><span data-stu-id="96b3d-159">User configured states expiration</span></span>
<span data-ttu-id="96b3d-160">ユーザーが特定のプレゼンス状態を選択すると、アプリのアクティビティの更新に優先します。</span><span class="sxs-lookup"><span data-stu-id="96b3d-160">When a user selects a specific presence state, it takes precedence over any app activity update.</span></span> <span data-ttu-id="96b3d-161">たとえば、ユーザーが [応答不可] に設定した場合は、会議に出席したか、電話に応答しても、プレゼンスが [応答不可] のままになります。</span><span class="sxs-lookup"><span data-stu-id="96b3d-161">For example, if a user sets herself as Do not disturb, her presence will remain as Do not disturb even if she attends a meeting or answers a call.</span></span>

<span data-ttu-id="96b3d-162">ユーザーによって構成された状態には、一定期間後に関連しない可能性のある状態が表示されないようにするため、Teams に既定の有効期限の設定があります。</span><span class="sxs-lookup"><span data-stu-id="96b3d-162">User configured states have default expiration settings in Teams, in order to prevent users from displaying a status that may not be relevant after a period of time.</span></span>

|<span data-ttu-id="96b3d-163">ユーザーが構成した状態</span><span class="sxs-lookup"><span data-stu-id="96b3d-163">User configured state</span></span>|<span data-ttu-id="96b3d-164">既定の有効期限</span><span class="sxs-lookup"><span data-stu-id="96b3d-164">Default expiration</span></span>|
|:--- |:---|
| <span data-ttu-id="96b3d-165">取り込み中</span><span class="sxs-lookup"><span data-stu-id="96b3d-165">Busy</span></span>|<span data-ttu-id="96b3d-166">1日</span><span class="sxs-lookup"><span data-stu-id="96b3d-166">1 day</span></span>|
| <span data-ttu-id="96b3d-167">応答不可</span><span class="sxs-lookup"><span data-stu-id="96b3d-167">Do not disturb</span></span>|<span data-ttu-id="96b3d-168">1日</span><span class="sxs-lookup"><span data-stu-id="96b3d-168">1 day</span></span>|
| <span data-ttu-id="96b3d-169">ユーザー</span><span class="sxs-lookup"><span data-stu-id="96b3d-169">Others</span></span>|<span data-ttu-id="96b3d-170">7日</span><span class="sxs-lookup"><span data-stu-id="96b3d-170">7 days</span></span>|
|||

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="96b3d-171">Skype for Business と Teams の管理設定の比較</span><span class="sxs-lookup"><span data-stu-id="96b3d-171">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="96b3d-172">Skype for Business と Teams では、次の管理設定が異なります。</span><span class="sxs-lookup"><span data-stu-id="96b3d-172">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="96b3d-173">Teams では、組織内ユーザーに対してプレゼンス共有が常に有効になります。</span><span class="sxs-lookup"><span data-stu-id="96b3d-173">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="96b3d-174">プライバシー (プレゼンスを表示できるユーザーを定義する) 構成は、Teams では利用できません。</span><span class="sxs-lookup"><span data-stu-id="96b3d-174">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="96b3d-175">すべてのユーザー (フェデレーション サービスを含む) とのプレゼンス共有は、Teams ユーザーに対して常に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="96b3d-175">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="96b3d-176">連絡先リスト (Skype for Business に含まれている場合) は、**[チャット] > [連絡先]** または **[通話] > [連絡先]** で表示できます。</span><span class="sxs-lookup"><span data-stu-id="96b3d-176">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="96b3d-177">クライアントの「応答不可」と「重要な連絡先」機能は、Teams ユーザーに対して常に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="96b3d-177">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="96b3d-178">カレンダー (不在およびその他のカレンダー情報を含む) は、Teams が Outlook と統合されている場合、ユーザーに対して常に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="96b3d-178">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="96b3d-179">組織で Skype for Business を使用している場合は、*[最終ログイン]* または *[退席中]* インジケータ―が、Teams ユーザーに対して常に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="96b3d-179">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="96b3d-180">Teams 管理者がこれらの設定をカスタマイズする機能は、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="96b3d-180">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="96b3d-181">Skype for Business との共存</span><span class="sxs-lookup"><span data-stu-id="96b3d-181">Coexistence with Skype for Business</span></span>

<span data-ttu-id="96b3d-182">組織で Skype for business も使用している場合の Teams のプレゼンス機能の詳細については、「[Skype for Business との共存](coexistence-chat-calls-presence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96b3d-182">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
