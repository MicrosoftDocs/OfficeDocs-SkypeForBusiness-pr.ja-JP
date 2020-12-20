---
title: Teams でのユーザーのプレゼンス
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: チームのプレゼンス状態とプレゼンス機能の管理設定について学習します。
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: ff5a13d6b31527138b71d2ad3b2387f827933eda
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616951"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="cfde8-103">Teams でのユーザーのプレゼンス</span><span class="sxs-lookup"><span data-stu-id="cfde8-103">User presence in Teams</span></span>

<span data-ttu-id="cfde8-104">プレゼンスは、Microsoft Teams (および Microsoft 365 または Office 365 全体) のユーザー プロフィールの一部です。</span><span class="sxs-lookup"><span data-stu-id="cfde8-104">Presence is part of a user's profile in Microsoft Teams (and throughout Microsoft 365 or Office 365).</span></span> <span data-ttu-id="cfde8-105">プレゼンスは、ユーザーが現在の連絡可能かどうか、またそのユーザーの状態を他のユーザーに示します。</span><span class="sxs-lookup"><span data-stu-id="cfde8-105">Presence indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="cfde8-106">既定では、組織内で Teams を使用しているすべてのユーザーは、他のユーザーがオンラインの場合、(ほぼリアルタイムで) 確認できます。</span><span class="sxs-lookup"><span data-stu-id="cfde8-106">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span> <span data-ttu-id="cfde8-107">モバイルでページを更新すると、Web バージョンとデスクトップ バージョンでプレゼンスがリアルタイムで更新されます。</span><span class="sxs-lookup"><span data-stu-id="cfde8-107">Presence is updated in real time on the web and desktop versions when you refresh the page on mobile.</span></span>

 > [!Note]
 > <span data-ttu-id="cfde8-108">別のプラットフォームでの Teams のユーザー プロフィールについての詳細は、 [プラットフォームごとの Teams の機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfde8-108">For details about Teams user profiles on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="cfde8-109">Teams でのプレゼンス状態</span><span class="sxs-lookup"><span data-stu-id="cfde8-109">Presence states in Teams</span></span>

|<span data-ttu-id="cfde8-110">ユーザーが設定</span><span class="sxs-lookup"><span data-stu-id="cfde8-110">User configured</span></span>|<span data-ttu-id="cfde8-111">アプリが設定</span><span class="sxs-lookup"><span data-stu-id="cfde8-111">App configured</span></span>|
|:--- |:---|
| ![塗りつぶした緑のチェックマークは、連絡可能な状態を示す](media/Presence_Available.png) <span data-ttu-id="cfde8-113">連絡可能</span><span class="sxs-lookup"><span data-stu-id="cfde8-113">Available</span></span>|![塗りつぶした緑のチェックマークは、連絡可能な状態を示す](media/Presence_Available.png) <span data-ttu-id="cfde8-115">連絡可能</span><span class="sxs-lookup"><span data-stu-id="cfde8-115">Available</span></span>|
|| ![緑枠のチェックマークは、連絡可能な外出中の状態を示す](media/Presence_Available_OOF.png) <span data-ttu-id="cfde8-117">連絡可能、外出中。</span><span class="sxs-lookup"><span data-stu-id="cfde8-117">Available, Out of Office.</span></span> <span data-ttu-id="cfde8-118">注: 「外出中」は、ユーザーが「自動返信」を設定した期間に自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="cfde8-118">Note: Out of office is automatically set for the periods of time where the user sets "automatic replies".</span></span> <span data-ttu-id="cfde8-119">ユーザーがこれらの期間中にアプリを使用している場合、「外出中、連絡可能」などの二重のプレゼンスが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="cfde8-119">If the user is using the app during these periods of time, a dual presence might be shown, such as "Out of office, available".</span></span> |
|  ![塗りつぶした赤い丸は、取り込み中を示す](media/Presence_Busy.png) <span data-ttu-id="cfde8-121">取り込み中</span><span class="sxs-lookup"><span data-stu-id="cfde8-121">Busy</span></span> |  ![塗りつぶした赤い丸は、取り込み中を示す](media/Presence_Busy.png) <span data-ttu-id="cfde8-123">取り込み中</span><span class="sxs-lookup"><span data-stu-id="cfde8-123">Busy</span></span>  |
|| ![塗りつぶした赤い丸は、通話のための取り込み中を示す](media/Presence_Busy.png) <span data-ttu-id="cfde8-125">通話中</span><span class="sxs-lookup"><span data-stu-id="cfde8-125">In a call</span></span>|
|| ![塗りつぶした赤い丸は、会議のための取り込み中を示す](media/Presence_Busy.png) <span data-ttu-id="cfde8-127">会議中</span><span class="sxs-lookup"><span data-stu-id="cfde8-127">In a meeting</span></span> |
|| ![赤枠の丸は、取り込み中を示す](media/Presence_Busy_OOF.png) <span data-ttu-id="cfde8-129">通話中、外出中</span><span class="sxs-lookup"><span data-stu-id="cfde8-129">On a call, out of office</span></span>|
|  ![白線の入った赤い丸は、応答不可を示す](media/Presence_DND.png) <span data-ttu-id="cfde8-131">応答不可</span><span class="sxs-lookup"><span data-stu-id="cfde8-131">Do not disturb</span></span> ||
|| ![白線の入った赤い丸は、発表中を示す](media/Presence_DND.png) <span data-ttu-id="cfde8-133">発表中</span><span class="sxs-lookup"><span data-stu-id="cfde8-133">Presenting</span></span>|
|| ![白線の入った赤い丸は、フォーカスを示す](media/Presence_DND.png) <span data-ttu-id="cfde8-135">フォーカス中。</span><span class="sxs-lookup"><span data-stu-id="cfde8-135">Focusing.</span></span> <span data-ttu-id="cfde8-136">フォーカスは、ユーザーがカレンダーの MyAnalytics / Insights でフォーカス時間をスケジュールしたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfde8-136">Focus happens when the users schedule focus time in MyAnalytics/Insights in their calendars.</span></span>|
| ![黄色の時計アイコンは、退席中を示す](media/Presence_Away.png) <span data-ttu-id="cfde8-138">退席中</span><span class="sxs-lookup"><span data-stu-id="cfde8-138">Away</span></span>| ![黄色の時計アイコンは、退席中を示す](media/Presence_Away.png) <span data-ttu-id="cfde8-140">退席中</span><span class="sxs-lookup"><span data-stu-id="cfde8-140">Away</span></span>|
|| <span data-ttu-id="cfde8-141">![黄色の時計アイコンは、退席中を示す *前回の退席中表示](media/Presence_Away.png)時刻\*</span><span class="sxs-lookup"><span data-stu-id="cfde8-141">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![黄色の時計アイコンは、一時退席中を示す](media/Presence_Away.png) <span data-ttu-id="cfde8-143">一時退席中</span><span class="sxs-lookup"><span data-stu-id="cfde8-143">Be right back</span></span>| |
|![X マーク付き灰色の丸、オフラインを示す](media/Presence_Offline.png) <span data-ttu-id="cfde8-145">オフライン表示</span><span class="sxs-lookup"><span data-stu-id="cfde8-145">Appear offline</span></span>|![X マーク付き灰色の丸、オフラインを示す](media/Presence_Offline.png) <span data-ttu-id="cfde8-147">オフライン。</span><span class="sxs-lookup"><span data-stu-id="cfde8-147">Offline.</span></span>  <span data-ttu-id="cfde8-148">ユーザーがどのデバイスにも数分間ログインしていない場合、ユーザーはオフラインとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfde8-148">When users aren't logged in on any of their devices for a few minutes, they appear offline.</span></span> | |
|| ![灰色枠の丸は、状態不明を示す](media/Presence_Unknown.png) <span data-ttu-id="cfde8-150">状態不明</span><span class="sxs-lookup"><span data-stu-id="cfde8-150">Status unknown</span></span>|
|| ![矢印付き紫色の丸、外出中を示す](media/Presence_OOF.png) <span data-ttu-id="cfde8-152">外出中。</span><span class="sxs-lookup"><span data-stu-id="cfde8-152">Out of Office.</span></span> <span data-ttu-id="cfde8-153">自動応答が設定されている場合、外出中が使用されます。</span><span class="sxs-lookup"><span data-stu-id="cfde8-153">Out of Office is used when an automatic reply is set.</span></span> <span data-ttu-id="cfde8-154">(Outlook でのみ利用可能です。)</span><span class="sxs-lookup"><span data-stu-id="cfde8-154">(Available in Outlook only.)</span></span> |
|||

<span data-ttu-id="cfde8-155">アプリで構成されたプレゼンス状態は、ユーザーのアクティビティ (連絡可能、退席中)、Outlook カレンダーの状態 (会議中)、Teams アプリの状態 (通話中、発表中) などに基づいています。</span><span class="sxs-lookup"><span data-stu-id="cfde8-155">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span> <span data-ttu-id="cfde8-156">カレンダーに基づいてフォーカス モードになっている場合、**フォーカ** スは Teams で表示される状態になります。</span><span class="sxs-lookup"><span data-stu-id="cfde8-156">When you're in focus mode based on your calendar, **Focusing** will be the state people see in Teams.</span></span> <span data-ttu-id="cfde8-157">フォーカス モードは、他の製品では **応答不可** と表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfde8-157">Focus mode will display as **Do not disturb** in other products.</span></span>

<span data-ttu-id="cfde8-158">コンピューターをロックするか、コンピューターがアイドル モードまたはスリープ モードに入ると、現在のプレゼンス状態が [退席中] に変わります。</span><span class="sxs-lookup"><span data-stu-id="cfde8-158">Your current presence state changes to Away when you lock your computer or when your computer enters idle or sleep mode.</span></span> <span data-ttu-id="cfde8-159">モバイル端末では、Teams アプリがバックグラウンドにあるときはいつでも、プレゼンス状態が [退席中] に変わります。</span><span class="sxs-lookup"><span data-stu-id="cfde8-159">On a mobile device, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="cfde8-160">プレゼンス状態に関係なく、ユーザーは、Teams で送信されたすべてのチャット メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="cfde8-160">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="cfde8-161">他者がメッセージを送信したときにユーザーがオフラインだった場合は、次回ユーザーがオンラインになったときに Teams にチャット メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfde8-161">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="cfde8-162">ユーザーの状態が [応答不可] に設定されている場合、ユーザーは引き続きチャットメッセージを受信しますが、バナー通知は表示されません。</span><span class="sxs-lookup"><span data-stu-id="cfde8-162">If a user state is set to Do not disturb, the user will still receive chat messages, but banner notifications aren't displayed.</span></span>

<span data-ttu-id="cfde8-163">ユーザーは、「応答不可」状態 (着信呼び出しがボイスメールに配信される) を除き、すべてのプレゼンス状態で通話を受信します。</span><span class="sxs-lookup"><span data-stu-id="cfde8-163">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="cfde8-164">受信者が発信者をブロックした場合、通話は配信されず、発信者には受信者のプレゼンスが「オフライン」と表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfde8-164">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="cfde8-165">ユーザーを優先順位の高いアクセス リストに追加するには、Teams の **[設定]** > **[プライバシー]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="cfde8-165">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="cfde8-166">ユーザーのステータスが「応答不可」状態に設定されている場合でも、優先アクセス権が付与されている発信者は、ユーザーと連絡を取ることができます。</span><span class="sxs-lookup"><span data-stu-id="cfde8-166">People who have priority access can contact the user even when the user's status is set to Do not disturb.</span></span>

### <a name="dual-presence"></a><span data-ttu-id="cfde8-167">デュアル プレゼンス</span><span class="sxs-lookup"><span data-stu-id="cfde8-167">Dual presence</span></span>

  <span data-ttu-id="cfde8-168">ほとんどのユーザーにとってプレゼンスが機能する方法は、カレンダーのイベントまたは通話などのデバイス イベントに基づきます。</span><span class="sxs-lookup"><span data-stu-id="cfde8-168">The way presence works for most users is motivated by the events in the calendar or device events, such as a call.</span></span> <span data-ttu-id="cfde8-169">ユーザーは、有効期限のある状態を手動で設定することにより、UI でこのステータスを上書きできます。</span><span class="sxs-lookup"><span data-stu-id="cfde8-169">The user can override this status in the UI by manually setting states, which have some expiration time.</span></span>

## <a name="user-configured-states-expiration"></a><span data-ttu-id="cfde8-170">ユーザーが設定した状態の有効期限</span><span class="sxs-lookup"><span data-stu-id="cfde8-170">User configured states expiration</span></span>

<span data-ttu-id="cfde8-171">ユーザーが特定のプレゼンス状態を選択すると、アプリ アクティビティの更新よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="cfde8-171">When a user selects a specific presence state, it takes precedence over any app activity update.</span></span> <span data-ttu-id="cfde8-172">たとえば、ユーザーが自分自身を「応答不可」と設定した場合、会議に出席したり電話に応答したりしても、その存在は「応答不可」のままになります。</span><span class="sxs-lookup"><span data-stu-id="cfde8-172">For example, if a user sets herself as Do not disturb, her presence will remain as Do not disturb even if she attends a meeting or answers a call.</span></span>

<span data-ttu-id="cfde8-173">ユーザーが構成した状態には、一定期間後に関連性がない可能性のあるステータスがユーザーに表示されないようにするために、Teams に既定の有効期限設定があります。</span><span class="sxs-lookup"><span data-stu-id="cfde8-173">User configured states have default expiration settings in Teams, in order to prevent users from displaying a status that may not be relevant after a period of time.</span></span>

|<span data-ttu-id="cfde8-174">ユーザーが設定した状態</span><span class="sxs-lookup"><span data-stu-id="cfde8-174">User configured state</span></span>|<span data-ttu-id="cfde8-175">既定の有効期限</span><span class="sxs-lookup"><span data-stu-id="cfde8-175">Default expiration</span></span>|
|:--- |:---|
| <span data-ttu-id="cfde8-176">多忙</span><span class="sxs-lookup"><span data-stu-id="cfde8-176">Busy</span></span>|<span data-ttu-id="cfde8-177">1 日</span><span class="sxs-lookup"><span data-stu-id="cfde8-177">1 day</span></span>|
| <span data-ttu-id="cfde8-178">応答不可</span><span class="sxs-lookup"><span data-stu-id="cfde8-178">Do not disturb</span></span>|<span data-ttu-id="cfde8-179">1 日</span><span class="sxs-lookup"><span data-stu-id="cfde8-179">1 day</span></span>|
| <span data-ttu-id="cfde8-180">その他</span><span class="sxs-lookup"><span data-stu-id="cfde8-180">Others</span></span>|<span data-ttu-id="cfde8-181">7 日間</span><span class="sxs-lookup"><span data-stu-id="cfde8-181">7 days</span></span>|
|||

> [!NOTE]
> <span data-ttu-id="cfde8-182">ユーザーは、プレゼンスの期間を手動で構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="cfde8-182">A user can also configure manually a duration for her presence.</span></span> <span data-ttu-id="cfde8-183">たとえば、ユーザーは自分を明日の朝までオフラインで表示するように設定できます。</span><span class="sxs-lookup"><span data-stu-id="cfde8-183">For instance, a user can set herself as Appear offline until tomorrow morning.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="cfde8-184">Skype for Business と Teams の管理設定の比較</span><span class="sxs-lookup"><span data-stu-id="cfde8-184">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="cfde8-185">Skype for Business と Teams では、次の管理設定が異なります。</span><span class="sxs-lookup"><span data-stu-id="cfde8-185">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="cfde8-186">Teams では、組織内ユーザーに対してプレゼンス共有が常に有効になります。</span><span class="sxs-lookup"><span data-stu-id="cfde8-186">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="cfde8-187">プライバシー (プレゼンスを表示できるユーザーを定義する場所) の構成は、Teams では使用できません。</span><span class="sxs-lookup"><span data-stu-id="cfde8-187">Privacy (where you define who can see presence) configuration isn't available in Teams.</span></span>
- <span data-ttu-id="cfde8-188">すべてのユーザー (フェデレーション サービスを含む) とのプレゼンス共有は、Teams ユーザーに対して常に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="cfde8-188">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="cfde8-189">連絡先リスト (Skype for Business に含まれている場合) は、**[チャット] > [連絡先]** または **[通話] > [連絡先]** で表示できます。</span><span class="sxs-lookup"><span data-stu-id="cfde8-189">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="cfde8-190">クライアントの「応答不可」と「重要な連絡先」機能は、Teams ユーザーに対して常に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="cfde8-190">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="cfde8-191">カレンダー (不在およびその他のカレンダー情報を含む) は、Teams が Outlook と統合されている場合、ユーザーに対して常に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="cfde8-191">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="cfde8-192">組織で Skype for Business を使用している場合は、*[最終ログイン]* または *[退席中]* インジケータ―が、Teams ユーザーに対して常に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="cfde8-192">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="cfde8-193">Teams 管理者がこれらの設定をカスタマイズする機能は、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="cfde8-193">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="admin-settings-in-teams-compared-to-microsoft-outlook"></a><span data-ttu-id="cfde8-194">Microsoft Outlook と Teams の管理設定の比較</span><span class="sxs-lookup"><span data-stu-id="cfde8-194">Admin settings in Teams compared to Microsoft Outlook</span></span>

<span data-ttu-id="cfde8-195">Outlook でのチームのプレゼンスは、Outlook 2013 デスクトップ アプリ以降で、同じ組織内の連絡先に対してサポートされます。</span><span class="sxs-lookup"><span data-stu-id="cfde8-195">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later for contacts in the same organization.</span></span>

<span data-ttu-id="cfde8-196">ユーザー アカウントのアップグレード モード ポリシーが TeamsOnly に設定されている場合、Outlook はチームと通信してプレゼンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="cfde8-196">If the upgrade mode policy of the user account is set to TeamsOnly, Outlook talks to Teams to get presence.</span></span> <span data-ttu-id="cfde8-197">ユーザーアカウントが TeamsOnly に設定されていない場合、Outlook は Skype for Business と通信します。</span><span class="sxs-lookup"><span data-stu-id="cfde8-197">If the user account isn't set to TeamsOnly, then Outlook talks to Skype for Business.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="cfde8-198">Skype for Business との共存</span><span class="sxs-lookup"><span data-stu-id="cfde8-198">Coexistence with Skype for Business</span></span>

<span data-ttu-id="cfde8-199">組織で Skype for business も使用している場合の Teams のプレゼンス機能の詳細については、「[Skype for Business との共存](coexistence-chat-calls-presence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfde8-199">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses Skype for Business.</span></span>
