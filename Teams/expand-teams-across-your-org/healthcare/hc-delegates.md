---
title: メッセージの委任
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: ユーザーは、ステータス メッセージの代理人として別のユーザーを明示的に設定できます。
ms.openlocfilehash: ec1f590cad4ada605b4a487d982b3a2459ecb5f2
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827785"
---
# <a name="message-delegation"></a><span data-ttu-id="a64eb-103">メッセージの委任</span><span class="sxs-lookup"><span data-stu-id="a64eb-103">Message delegation</span></span>

<span data-ttu-id="a64eb-104">ユーザーは、明示的にステータスを [退席中] または [応答不可] に設定し、カスタム テキストを提供できます。</span><span class="sxs-lookup"><span data-stu-id="a64eb-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="a64eb-105">メッセージの委任機能は次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="a64eb-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="a64eb-106">ユーザーは、テキストのステータス メッセージの一部で @username に別のユーザーの名前をあげます。これは、連絡できない場合は、@username に名前をあげたユーザーに連絡することを示します。</span><span class="sxs-lookup"><span data-stu-id="a64eb-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="a64eb-107">代理人として指名されたユーザーには、指名されたことが通知されます。</span><span class="sxs-lookup"><span data-stu-id="a64eb-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="a64eb-108">最初のユーザーに連絡しようとしている人は、指名された代理人にカーソルを合わせると、代理人に簡単にメッセージを送ることができます。</span><span class="sxs-lookup"><span data-stu-id="a64eb-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="a64eb-109">これは、ユーザーによって開始されるクライアントのプロセスであり、この機能を有効にするために管理者に連絡する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a64eb-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="a64eb-110">医療機関における代理人の使用シナリオ</span><span class="sxs-lookup"><span data-stu-id="a64eb-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="a64eb-111">*代理人の設定を使用しない例:* Franco Piccio 先生は放射線科に電話をかけています。</span><span class="sxs-lookup"><span data-stu-id="a64eb-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="a64eb-112">彼は緊急の個人的な電話を受け、数時間現場から離れなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a64eb-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="a64eb-113">彼は、放射線科の同僚である Lena Ehrle 先生に、自分がいない間、代わりに患者さんを診てほしいと依頼します。</span><span class="sxs-lookup"><span data-stu-id="a64eb-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="a64eb-114">彼は非公式にポケットベルを Ehrle 先生に渡します。Ehrle 先生は、自分の仕事をこなしながら、Piccio 先生の代わりにポケットベルの緊急メッセージと通知音を聞いて応答します。</span><span class="sxs-lookup"><span data-stu-id="a64eb-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="a64eb-115">チームの他のメンバーは、非公式の委任に気が付かず、患者さんの治療に混乱が生じるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="a64eb-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="a64eb-116">*代理人の設定を使用する例:* Franco Piccio 先生は放射線科に電話をかけています。</span><span class="sxs-lookup"><span data-stu-id="a64eb-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="a64eb-117">彼は緊急の個人的な電話を受け、数時間現場から離れなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a64eb-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="a64eb-118">彼は、放射線科の同僚である Lena Ehrle 先生に、自分がいない間、代わりに患者さんを診てほしいと依頼します。</span><span class="sxs-lookup"><span data-stu-id="a64eb-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="a64eb-119">彼は自分のカスタム ステータス メッセージを変更して、「数時間現場から離れなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a64eb-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="a64eb-120">緊急の場合は @DrEhrle に連絡してください。」のような内容を残します。</span><span class="sxs-lookup"><span data-stu-id="a64eb-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="a64eb-121">チームの他のメンバーは、Piccio 先生と連絡を取ろうとしたときに、委任があったことに気づきます。そのため、Ehrle 先生と連絡を取ることができます。</span><span class="sxs-lookup"><span data-stu-id="a64eb-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="a64eb-122">患者の治療に混乱がほとんど生じません。</span><span class="sxs-lookup"><span data-stu-id="a64eb-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="a64eb-123">Teams クライアントのユーザー ステータスに対する共存モードの影響</span><span class="sxs-lookup"><span data-stu-id="a64eb-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="a64eb-124">管理者は、ステータスのメモと委任言及の動作がユーザーの共存モードに一部依存することに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a64eb-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user’s co-existence mode.</span></span> <span data-ttu-id="a64eb-125">このマトリックスは可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="a64eb-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="a64eb-126">共存モード</span><span class="sxs-lookup"><span data-stu-id="a64eb-126">Co-Existence Mode</span></span> | <span data-ttu-id="a64eb-127">正常な動作</span><span class="sxs-lookup"><span data-stu-id="a64eb-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="a64eb-128">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="a64eb-128">TeamsOnly</span></span> |<span data-ttu-id="a64eb-129">ユーザーは、Teams からのみメモを設定できます。</span><span class="sxs-lookup"><span data-stu-id="a64eb-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="a64eb-130">ユーザーの Teams メモは、Teams と SfB に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a64eb-130">User’s Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="a64eb-131">アイランド</span><span class="sxs-lookup"><span data-stu-id="a64eb-131">Islands</span></span> | <span data-ttu-id="a64eb-132">Teams で設定されたユーザーのメモは、Teams でのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a64eb-132">User’s note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="a64eb-133">SfB で設定されたユーザーのメモは、SfB でのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a64eb-133">User’s note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="a64eb-134">SfB\* モード</span><span class="sxs-lookup"><span data-stu-id="a64eb-134">SfB\* modes</span></span> | <span data-ttu-id="a64eb-135">ユーザーは、SfB からのみメモを設定できます。</span><span class="sxs-lookup"><span data-stu-id="a64eb-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="a64eb-136">ユーザーの SfB メモは、SfB と Teams に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a64eb-136">User’s SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="a64eb-137">モードが TeamsOnly または アイランドの場合、ユーザーはメモを設定できます。</span><span class="sxs-lookup"><span data-stu-id="a64eb-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="a64eb-138">メモの Skype for Business での表示</span><span class="sxs-lookup"><span data-stu-id="a64eb-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="a64eb-139">メモが Skype for Business から設定されていることを視覚的に示すものはありません。</span><span class="sxs-lookup"><span data-stu-id="a64eb-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="a64eb-140">Skype for Business のステータス メモに文字数の制限は適用されていません。</span><span class="sxs-lookup"><span data-stu-id="a64eb-140">Skype for Business doesn’t enforce a character limit on status notes.</span></span> <span data-ttu-id="a64eb-141">Microsoft Teams は、Skype for Business からのメモ セットのうち最初の 280 文字のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="a64eb-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="a64eb-142">メモの最後にある省略記号 (…) は省略されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="a64eb-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="a64eb-143">Skype for Business は、メモの有効期限をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a64eb-143">Skype for Business doesn’t support expiry times for notes.</span></span>

<span data-ttu-id="a64eb-144">ユーザーが TeamsOnly モードにアップグレードされている場合は、Skype for Business から Teams にメモを移行することはできません。</span><span class="sxs-lookup"><span data-stu-id="a64eb-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a64eb-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="a64eb-145">Related topics</span></span>

[<span data-ttu-id="a64eb-146">Skype for Business と共存する</span><span class="sxs-lookup"><span data-stu-id="a64eb-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
