---
title: Teams でのユーザーのプレゼンス
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: 00ca1a2d7a00b4aa827cfb5a989e31b54b83fbeb
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "46803909"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="0ea7a-103">Teams でのユーザーのプレゼンス</span><span class="sxs-lookup"><span data-stu-id="0ea7a-103">User presence in Teams</span></span>

<span data-ttu-id="0ea7a-104">プレゼンスは、Microsoft Teams (および Microsoft 365 または Office 365 全体) のユーザーのプロファイルの一部であり、ユーザーの現在の可用性と他のユーザーの状態を示します。</span><span class="sxs-lookup"><span data-stu-id="0ea7a-104">Presence is part of a user's profile in Microsoft Teams (and throughout Microsoft 365 or Office 365) that indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="0ea7a-105">既定では、組織内で Teams を使用しているすべてのユーザーは、他のユーザーがオンラインの場合、(ほぼリアルタイムで) 確認できます。</span><span class="sxs-lookup"><span data-stu-id="0ea7a-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

<span data-ttu-id="0ea7a-106">Outlook での Teams のプレゼンスは、Outlook 2013 デスクトップ版アプリ以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0ea7a-106">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="0ea7a-107">Teams でのプレゼンス状態</span><span class="sxs-lookup"><span data-stu-id="0ea7a-107">Presence states in Teams</span></span>

|<span data-ttu-id="0ea7a-108">ユーザーが設定</span><span class="sxs-lookup"><span data-stu-id="0ea7a-108">User configured</span></span>|<span data-ttu-id="0ea7a-109">アプリが設定</span><span class="sxs-lookup"><span data-stu-id="0ea7a-109">App configured</span></span>|
|:--- |:---|
| ![塗りつぶした緑のチェックマークは、連絡可能な状態を示す](media/Presence_Available.png) <span data-ttu-id="0ea7a-111">連絡可能</span><span class="sxs-lookup"><span data-stu-id="0ea7a-111">Available</span></span>|![塗りつぶした緑のチェックマークは、連絡可能な状態を示す](media/Presence_Available.png) <span data-ttu-id="0ea7a-113">連絡可能</span><span class="sxs-lookup"><span data-stu-id="0ea7a-113">Available</span></span>|
|| ![緑枠のチェックマークは、連絡可能な外出中の状態を示す](media/Presence_Available_OOF.png) <span data-ttu-id="0ea7a-115">連絡可能、外出中</span><span class="sxs-lookup"><span data-stu-id="0ea7a-115">Available, Out of Office</span></span> |
|  ![塗りつぶした赤い丸は、取り込み中を示す](media/Presence_Busy.png) <span data-ttu-id="0ea7a-117">取り込み中</span><span class="sxs-lookup"><span data-stu-id="0ea7a-117">Busy</span></span> |  ![塗りつぶした赤い丸は、取り込み中を示す](media/Presence_Busy.png) <span data-ttu-id="0ea7a-119">取り込み中</span><span class="sxs-lookup"><span data-stu-id="0ea7a-119">Busy</span></span>  |
|| ![塗りつぶした赤い丸は、通話のための取り込み中を示す](media/Presence_Busy.png) <span data-ttu-id="0ea7a-121">通話中</span><span class="sxs-lookup"><span data-stu-id="0ea7a-121">On a call</span></span>|
|| ![塗りつぶした赤い丸は、会議のための取り込み中を示す](media/Presence_Busy.png) <span data-ttu-id="0ea7a-123">会議中</span><span class="sxs-lookup"><span data-stu-id="0ea7a-123">In a meeting</span></span> |
|| ![赤枠の丸は、取り込み中を示す](media/Presence_Busy_OOF.png) <span data-ttu-id="0ea7a-125">通話中、外出中</span><span class="sxs-lookup"><span data-stu-id="0ea7a-125">On a call, out of office</span></span>|
|  ![白線の入った赤い丸は、応答不可を示す](media/Presence_DND.png) <span data-ttu-id="0ea7a-127">応答不可</span><span class="sxs-lookup"><span data-stu-id="0ea7a-127">Do not disturb</span></span> ||
|| ![白線の入った赤い丸は、発表中を示す](media/Presence_DND.png) <span data-ttu-id="0ea7a-129">発表中</span><span class="sxs-lookup"><span data-stu-id="0ea7a-129">Presenting</span></span>|
|| ![白線の入った赤い丸は、フォーカスを示す](media/Presence_DND.png) <span data-ttu-id="0ea7a-131">フォーカス</span><span class="sxs-lookup"><span data-stu-id="0ea7a-131">Focusing</span></span>|
| ![黄色の時計アイコンは、退席中を示す](media/Presence_Away.png) <span data-ttu-id="0ea7a-133">退席中</span><span class="sxs-lookup"><span data-stu-id="0ea7a-133">Away</span></span>| ![黄色の時計アイコンは、退席中を示す](media/Presence_Away.png) <span data-ttu-id="0ea7a-135">退席中</span><span class="sxs-lookup"><span data-stu-id="0ea7a-135">Away</span></span>|
|| <span data-ttu-id="0ea7a-136">![黄色の時計アイコンは、退席中を示す*前回の退席中表示](media/Presence_Away.png)時刻\*</span><span class="sxs-lookup"><span data-stu-id="0ea7a-136">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![黄色の時計アイコンは、一時退席中を示す](media/Presence_Away.png) <span data-ttu-id="0ea7a-138">一時退席中</span><span class="sxs-lookup"><span data-stu-id="0ea7a-138">Be right back</span></span>| |
|| ![黄の時計アイコンは、退席中、業務時間外を示す](media/Presence_Away.png)  <span data-ttu-id="0ea7a-140">業務時間外</span><span class="sxs-lookup"><span data-stu-id="0ea7a-140">Off Work</span></span>|
|| ![X マーク付き灰色の丸は、オフラインを示す](media/Presence_Offline.png) <span data-ttu-id="0ea7a-142">オフライン</span><span class="sxs-lookup"><span data-stu-id="0ea7a-142">Offline</span></span> |
|| ![灰色枠の丸は、状態不明を示す](media/Presence_Unknown.png) <span data-ttu-id="0ea7a-144">状態不明</span><span class="sxs-lookup"><span data-stu-id="0ea7a-144">Status unknown</span></span>|
||![斜線の入った赤枠の丸は、ブロックされたことを示す](media/Presence_Blocked.png) <span data-ttu-id="0ea7a-146">ブロックされました</span><span class="sxs-lookup"><span data-stu-id="0ea7a-146">Blocked</span></span> |
|| ![矢印付き紫色の丸は、外出中を示す](media/Presence_OOF.png) <span data-ttu-id="0ea7a-148">外出中</span><span class="sxs-lookup"><span data-stu-id="0ea7a-148">Out of Office</span></span>|
|||

<span data-ttu-id="0ea7a-149">アプリで構成されたプレゼンス状態は、ユーザーアクティビティ (利用可能、退席中)、Outlook の予定表の状態 (会議中)、または Teams アプリの状態 (通話中、発表中) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="0ea7a-149">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span> <span data-ttu-id="0ea7a-150">予定表に基づくフォーカスモードになっている場合は、ユーザーが Teams で表示した状態で、他の製品で [応答不可] として表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0ea7a-150">Note that when you are in focus mode based on your calendar, Focusing will be the state people see in Teams but will show as Do not disturb in other products.</span></span>

<span data-ttu-id="0ea7a-151">コンピューターをロックするか、アイドルまたはスリープモードに入ると、現在のプレゼンス状態が「退席中」に変わります。</span><span class="sxs-lookup"><span data-stu-id="0ea7a-151">Your current presence state changes to Away when you lock your computer or when it enters idle or sleep mode.</span></span> <span data-ttu-id="0ea7a-152">モバイルでは、Teams アプリがバックグラウンドにあるときは、プレゼンス状態が [退席中] に変わります。</span><span class="sxs-lookup"><span data-stu-id="0ea7a-152">On mobile, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="0ea7a-153">プレゼンス状態に関係なく、ユーザーは、Teams で送信されたすべてのチャット メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="0ea7a-153">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="0ea7a-154">他者がメッセージを送信したときにユーザーがオフラインだった場合は、次回ユーザーがオンラインになったときに Teams にチャット メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ea7a-154">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="0ea7a-155">ユーザーが [応答不可] になっている場合でも、ユーザーはチャットメッセージを受け取りますが、バナー通知は表示されません。</span><span class="sxs-lookup"><span data-stu-id="0ea7a-155">If a user is in Do not disturb, the user will still get chat messages but banner notifications aren't displayed.</span></span>

<span data-ttu-id="0ea7a-156">ユーザーは、[応答不可] (着信通話がボイスメールに転送される) を除くすべてのプレゼンス状態で通話を受信します。</span><span class="sxs-lookup"><span data-stu-id="0ea7a-156">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="0ea7a-157">受信者が発信者をブロックした場合、通話は配信されず、発信者には受信者のプレゼンスが「オフライン」と表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ea7a-157">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="0ea7a-158">ユーザーを優先順位の高いアクセス リストに追加するには、Teams の **[設定]** > **[プライバシー]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ea7a-158">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="0ea7a-159">ユーザーが [応答不可] になっている場合でも、アクセス権が付与されているユーザーに連絡できます。</span><span class="sxs-lookup"><span data-stu-id="0ea7a-159">People who have priority access can contact the user even when the user is in Do not disturb.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="0ea7a-160">Skype for Business と Teams の管理設定の比較</span><span class="sxs-lookup"><span data-stu-id="0ea7a-160">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="0ea7a-161">Skype for Business と Teams では、次の管理設定が異なります。</span><span class="sxs-lookup"><span data-stu-id="0ea7a-161">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="0ea7a-162">Teams では、組織内ユーザーに対してプレゼンス共有が常に有効になります。</span><span class="sxs-lookup"><span data-stu-id="0ea7a-162">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="0ea7a-163">プライバシー (プレゼンスを表示できるユーザーを定義する) 構成は、Teams では利用できません。</span><span class="sxs-lookup"><span data-stu-id="0ea7a-163">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="0ea7a-164">すべてのユーザー (フェデレーション サービスを含む) とのプレゼンス共有は、Teams ユーザーに対して常に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="0ea7a-164">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="0ea7a-165">連絡先リスト (Skype for Business に含まれている場合) は、**[チャット] > [連絡先]** または **[通話] > [連絡先]** で表示できます。</span><span class="sxs-lookup"><span data-stu-id="0ea7a-165">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="0ea7a-166">クライアントの「応答不可」と「重要な連絡先」機能は、Teams ユーザーに対して常に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="0ea7a-166">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="0ea7a-167">カレンダー (不在およびその他のカレンダー情報を含む) は、Teams が Outlook と統合されている場合、ユーザーに対して常に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="0ea7a-167">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="0ea7a-168">組織で Skype for Business を使用している場合は、*[最終ログイン]* または *[退席中]* インジケータ―が、Teams ユーザーに対して常に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="0ea7a-168">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="0ea7a-169">Teams 管理者がこれらの設定をカスタマイズする機能は、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0ea7a-169">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="0ea7a-170">Skype for Business との共存</span><span class="sxs-lookup"><span data-stu-id="0ea7a-170">Coexistence with Skype for Business</span></span>

<span data-ttu-id="0ea7a-171">組織で Skype for business も使用している場合の Teams のプレゼンス機能の詳細については、「[Skype for Business との共存](coexistence-chat-calls-presence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ea7a-171">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
