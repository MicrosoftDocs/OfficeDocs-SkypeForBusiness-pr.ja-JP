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
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: ユーザーは、他のユーザーの状態メッセージの代理人として明示的に設定することができます。
ms.openlocfilehash: 56c0e9bd5394e738170130bab15803e5cb4d741c
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570360"
---
# <a name="message-delegation"></a><span data-ttu-id="726eb-103">メッセージの委任</span><span class="sxs-lookup"><span data-stu-id="726eb-103">Message delegation</span></span>

<span data-ttu-id="726eb-104">ユーザーは、状態を既に [退席中] または [応答不可] に設定して、カスタムテキストを指定できます。</span><span class="sxs-lookup"><span data-stu-id="726eb-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="726eb-105">メッセージの委任機能は、次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="726eb-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="726eb-106">ユーザーは、別のユーザーをテキスト状態メッセージの一部としてメンションして、相手に連絡したいユーザーがいないときに、@username メンションされたユーザーに連絡することを提案 @username ます。</span><span class="sxs-lookup"><span data-stu-id="726eb-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="726eb-107">代理人として割り当てられたユーザーには、代理人として任命されたことが通知されます。</span><span class="sxs-lookup"><span data-stu-id="726eb-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="726eb-108">最初のユーザーに連絡しようとしているユーザーは、指定されたデリゲートの上にマウスポインターを置くと、代わりに代理人に簡単にメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="726eb-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="726eb-109">これはクライアントでのユーザーによって開始されるプロセスであり、この機能を有効にするために管理者の関与は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="726eb-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="726eb-110">医療機関の委任使用シナリオ</span><span class="sxs-lookup"><span data-stu-id="726eb-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="726eb-111">*代理人を設定しない場合の使用例:* Franco のお店では、radiology 部門で通話を発信できます。</span><span class="sxs-lookup"><span data-stu-id="726eb-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="726eb-112">緊急の個人的な通話を受信していて、次の数時間の間に一歩離してください。</span><span class="sxs-lookup"><span data-stu-id="726eb-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="726eb-113">彼は、radiology department、Lena Ehrle の相手のうちの1人に、彼が休暇中に自分のことを説明するように求めています。</span><span class="sxs-lookup"><span data-stu-id="726eb-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="726eb-114">彼は、ポケットベルを使って、緊急のメッセージやポケットベルをリッスンしていて、現在の責任に加えて、ワトソン博士の代理として応答します。</span><span class="sxs-lookup"><span data-stu-id="726eb-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="726eb-115">チームの他のユーザーは、非公式の委任が行われていない可能性があり、患者の ensues に混乱を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="726eb-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="726eb-116">*代理人を設定する使用例:* Franco のお店では、radiology 部門で通話を発信できます。</span><span class="sxs-lookup"><span data-stu-id="726eb-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="726eb-117">緊急の個人的な通話を受信していて、次の数時間の間に一歩離してください。</span><span class="sxs-lookup"><span data-stu-id="726eb-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="726eb-118">彼は、radiology department、Lena Ehrle のいずれかのピアに連絡して、彼が休暇中の相手に向けて説明します。</span><span class="sxs-lookup"><span data-stu-id="726eb-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="726eb-119">自分のユーザー設定の状態メッセージを変更して、"今後数時間は利用できません" というメッセージが表示されるようにしました。</span><span class="sxs-lookup"><span data-stu-id="726eb-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="726eb-120">緊急対応の @DrEhrle に連絡してください。」</span><span class="sxs-lookup"><span data-stu-id="726eb-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="726eb-121">チームの他のユーザーは、あなたが Dr. it Cio に連絡しようとしているため、この委任が行われていることを認識しているため、現在はワトソン博士に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="726eb-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="726eb-122">患者の注意を ensues ことができます。</span><span class="sxs-lookup"><span data-stu-id="726eb-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="726eb-123">Teams クライアントでのユーザーの状態への共存モードの影響</span><span class="sxs-lookup"><span data-stu-id="726eb-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="726eb-124">管理者は、[状態メモ] と [委任によるメンション] の動作が、ユーザーの共存モードに依存することに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="726eb-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user’s co-existence mode.</span></span> <span data-ttu-id="726eb-125">このマトリックスは、次の可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="726eb-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="726eb-126">共存モード</span><span class="sxs-lookup"><span data-stu-id="726eb-126">Co-Existence Mode</span></span> | <span data-ttu-id="726eb-127">予期される動作</span><span class="sxs-lookup"><span data-stu-id="726eb-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="726eb-128">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="726eb-128">TeamsOnly</span></span> |<span data-ttu-id="726eb-129">ユーザーは、Teams からのみメモを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="726eb-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="726eb-130">ユーザーの Teams のメモは Teams & SfB に表示されます。</span><span class="sxs-lookup"><span data-stu-id="726eb-130">User’s Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="726eb-131">アイランド</span><span class="sxs-lookup"><span data-stu-id="726eb-131">Islands</span></span> | <span data-ttu-id="726eb-132">Teams でのユーザーのメモセットは、Teams でのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="726eb-132">User’s note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="726eb-133">Sfb でのみ表示される sfb でのユーザのメモセット</span><span class="sxs-lookup"><span data-stu-id="726eb-133">User’s note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="726eb-134">SfB \* モード</span><span class="sxs-lookup"><span data-stu-id="726eb-134">SfB\* modes</span></span> | <span data-ttu-id="726eb-135">ユーザーは、SfB からのみメモを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="726eb-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="726eb-136">ユーザーの SfB メモは、SfB & Teams で表示されます。</span><span class="sxs-lookup"><span data-stu-id="726eb-136">User’s SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="726eb-137">ユーザーは、チーム内のメモを設定できるのは、チームのモードが Teams s のみか、または諸島の場合のみです。</span><span class="sxs-lookup"><span data-stu-id="726eb-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="726eb-138">Skype for Business でのノートセットの表示</span><span class="sxs-lookup"><span data-stu-id="726eb-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="726eb-139">ノートが Skype for Business から設定されたことを示す視覚的な通知はありません。</span><span class="sxs-lookup"><span data-stu-id="726eb-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="726eb-140">Skype for Business では、状態メモに文字数の制限は適用されません。</span><span class="sxs-lookup"><span data-stu-id="726eb-140">Skype for Business doesn’t enforce a character limit on status notes.</span></span> <span data-ttu-id="726eb-141">Microsoft Teams では、Skype for Business からのメモセットの最初の280文字のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="726eb-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="726eb-142">メモの末尾にある省略記号 (...) は、切り捨てを示します。</span><span class="sxs-lookup"><span data-stu-id="726eb-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="726eb-143">Skype for Business では、ノートの有効期間をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="726eb-143">Skype for Business doesn’t support expiry times for notes.</span></span>

<span data-ttu-id="726eb-144">ユーザーが TeamsOnly モードにアップグレードされている場合、Skype for Business から Teams へのメモの移行はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="726eb-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="726eb-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="726eb-145">Related topics</span></span>

[<span data-ttu-id="726eb-146">Skype for Business と共存する</span><span class="sxs-lookup"><span data-stu-id="726eb-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
