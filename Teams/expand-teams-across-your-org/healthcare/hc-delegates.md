---
title: メッセージの委任
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: ユーザーは、他のユーザーの状態メッセージの代理人として明示的に設定することができます。
ms.openlocfilehash: be7092d2a68010d00a2d214f12bfe9011d44bbc5
ms.sourcegitcommit: 1786d4beccc8749e20709d2360d90e2bf7634925
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2019
ms.locfileid: "35119485"
---
# <a name="set-a-delegate-in-a-status-message"></a><span data-ttu-id="74af8-103">状態メッセージで代理人を設定する</span><span class="sxs-lookup"><span data-stu-id="74af8-103">Set a delegate in a status message</span></span>

<span data-ttu-id="74af8-104">ユーザーは、状態を既に [退席中] または [応答不可] に設定して、カスタムテキストを指定できます。</span><span class="sxs-lookup"><span data-stu-id="74af8-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="74af8-105">委任機能を使用すると、別のユーザーにテキスト状態メッセージの一部としてメンションを @username ことができます。また、それらのユーザーが連絡できるようにする場合は、代わりに、@username メンションされたユーザーに連絡することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="74af8-105">The delegation feature allows them to @username mention another user in part of a text status message, and suggest that while they are unavailable people who want to contact them contact the @username mentioned user instead.</span></span> <span data-ttu-id="74af8-106">他のユーザーに連絡してもらい、指定された代理人の上にカーソルを置いて、代わりに簡単にメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="74af8-106">Someone trying to contact them can then hover over the nominated delegate and easily message them instead.</span></span>  <span data-ttu-id="74af8-107">代理人として割り当てられたユーザーには、代理人として任命されたことが通知されます。</span><span class="sxs-lookup"><span data-stu-id="74af8-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>

<span data-ttu-id="74af8-108">これは、クライアントでのユーザーによって開始されるプロセスであり、管理者の関与は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="74af8-108">This is a user-initiated process in the client, and no Admin involvement is required.</span></span>

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="74af8-109">医療機関の委任使用シナリオ</span><span class="sxs-lookup"><span data-stu-id="74af8-109">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="74af8-110">*代理人を設定しない場合の使用例:* Franco のお店では、radiology 部門で通話を発信できます。</span><span class="sxs-lookup"><span data-stu-id="74af8-110">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="74af8-111">緊急の個人的な通話を受信していて、次の数時間の間に一歩離してください。</span><span class="sxs-lookup"><span data-stu-id="74af8-111">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="74af8-112">彼は、radiology department、Lena Ehrle の相手のうちの1人に、彼が休暇中に自分のことを説明するように求めています。</span><span class="sxs-lookup"><span data-stu-id="74af8-112">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="74af8-113">彼は、ポケットベルを使って、緊急のメッセージやポケットベルをリッスンしていて、現在の責任に加えて、ワトソン博士の代理として応答します。</span><span class="sxs-lookup"><span data-stu-id="74af8-113">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="74af8-114">チームの他のユーザーは、非公式の委任が行われていない可能性があり、患者の ensues に混乱を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="74af8-114">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="74af8-115">*代理人を設定する使用例:* Franco のお店では、radiology 部門で通話を発信できます。</span><span class="sxs-lookup"><span data-stu-id="74af8-115">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="74af8-116">緊急の個人的な通話を受信していて、次の数時間の間に一歩離してください。</span><span class="sxs-lookup"><span data-stu-id="74af8-116">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="74af8-117">彼は、radiology department、Lena Ehrle のいずれかのピアに連絡して、彼が休暇中の相手に向けて説明します。</span><span class="sxs-lookup"><span data-stu-id="74af8-117">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="74af8-118">自分のユーザー設定の状態メッセージを変更して、"今後数時間は利用できません" というメッセージが表示されるようにしました。</span><span class="sxs-lookup"><span data-stu-id="74af8-118">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="74af8-119">緊急対応の @DrEhrle に連絡してください。」</span><span class="sxs-lookup"><span data-stu-id="74af8-119">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="74af8-120">チームの他のユーザーは、あなたが Dr. it Cio に連絡しようとしているため、この委任が行われていることを認識しているため、現在はワトソン博士に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="74af8-120">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="74af8-121">患者の注意を ensues ことができます。</span><span class="sxs-lookup"><span data-stu-id="74af8-121">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="74af8-122">Teams クライアントでのユーザーの状態への共存モードの影響</span><span class="sxs-lookup"><span data-stu-id="74af8-122">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="74af8-123">管理者は、状態メモと委任メンションが一部のユーザーの共同のモードに依存することに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74af8-123">Admins should be aware that status notes and delegation mentions will depend partly on a user’s co-existence mode.</span></span> <span data-ttu-id="74af8-124">このマトリックスは、次の可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="74af8-124">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="74af8-125">共存モード</span><span class="sxs-lookup"><span data-stu-id="74af8-125">Co-Existence Mode</span></span> | <span data-ttu-id="74af8-126">予期される動作</span><span class="sxs-lookup"><span data-stu-id="74af8-126">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="74af8-127">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="74af8-127">TeamsOnly</span></span> |<span data-ttu-id="74af8-128">ユーザーは、Teams からのみメモを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="74af8-128">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="74af8-129">ユーザーの Teams のメモは Teams & SfB に表示されます。</span><span class="sxs-lookup"><span data-stu-id="74af8-129">User’s Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="74af8-130">アイランド</span><span class="sxs-lookup"><span data-stu-id="74af8-130">Islands</span></span> | <span data-ttu-id="74af8-131">Teams でのユーザーのメモセットは、Teams でのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="74af8-131">User’s note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="74af8-132">Sfb でのみ表示される sfb でのユーザのメモセット</span><span class="sxs-lookup"><span data-stu-id="74af8-132">User’s note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="74af8-133">SfB \* モード</span><span class="sxs-lookup"><span data-stu-id="74af8-133">SfB\* modes</span></span> | <span data-ttu-id="74af8-134">ユーザーは、SfB からのみメモを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="74af8-134">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="74af8-135">ユーザーの SfB メモは、SfB & Teams で表示されます。</span><span class="sxs-lookup"><span data-stu-id="74af8-135">User’s SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="74af8-136">ユーザーは、チーム内のメモを設定できるのは、チームのモードが Teams s のみか、または諸島の場合のみです。</span><span class="sxs-lookup"><span data-stu-id="74af8-136">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="74af8-137">Skype for Business でのノートセットの表示</span><span class="sxs-lookup"><span data-stu-id="74af8-137">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="74af8-138">ノートが Skype for Business から設定されたことを示す視覚的な通知はありません。</span><span class="sxs-lookup"><span data-stu-id="74af8-138">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="74af8-139">Skype for Business では、状態メモに文字数の制限は適用されません。</span><span class="sxs-lookup"><span data-stu-id="74af8-139">Skype for Business doesn’t enforce a character limit on status notes.</span></span> <span data-ttu-id="74af8-140">Microsoft Teams では、Skype for Business からのメモセットの最初の280文字のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="74af8-140">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="74af8-141">終端の省略記号 (...) は、切り捨てを示します。</span><span class="sxs-lookup"><span data-stu-id="74af8-141">An ellipse (…) at the end indicates truncation.</span></span>
  
<span data-ttu-id="74af8-142">Skype for Business では、ノートの有効期間をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="74af8-142">Skype for Business doesn’t support expiry times for notes.</span></span>

<span data-ttu-id="74af8-143">ユーザーが TeamsOnly モードにアップグレードされている場合、Skype for Business から Teams へのメモの移行はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="74af8-143">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="configure-allowing-clients-to-use-delegates"></a><span data-ttu-id="74af8-144">クライアントに代理人の使用を許可するように構成する</span><span class="sxs-lookup"><span data-stu-id="74af8-144">Configure allowing clients to use delegates</span></span>

<span data-ttu-id="74af8-145">この機能には、Microsoft Teams 管理センターでの構成または PowerShell の使用は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="74af8-145">This feature does not require configuration in Microsoft Teams admin center, or using PowerShell.</span></span> <span data-ttu-id="74af8-146">サポートされているテナントでは、チームクライアントで既定で利用できます。</span><span class="sxs-lookup"><span data-stu-id="74af8-146">In tenants that support it, it is available by default in the Teams client.</span></span>

## <a name="related-topics"></a><span data-ttu-id="74af8-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="74af8-147">Related topics</span></span>

[<span data-ttu-id="74af8-148">Skype for Business と共存する</span><span class="sxs-lookup"><span data-stu-id="74af8-148">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
