---
title: メッセージの委任
author: dstrome
ms.author: dstrome
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
description: "\"退席中\" 状態または \"応答不可\" 状態のユーザーが自分の状態メッセージで別のユーザーを代理として明示的に設定する方法について説明します。"
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5fea05e8f316117ae711cc9f00da752c45959f2e
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904739"
---
# <a name="message-delegation"></a><span data-ttu-id="ab199-103">メッセージの委任</span><span class="sxs-lookup"><span data-stu-id="ab199-103">Message delegation</span></span>

<span data-ttu-id="ab199-104">ユーザーは、明示的にステータスを [退席中] または [応答不可] に設定し、カスタム テキストを提供できます。</span><span class="sxs-lookup"><span data-stu-id="ab199-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="ab199-105">メッセージの委任機能は次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="ab199-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="ab199-106">ユーザーは、テキストのステータス メッセージの一部で @username に別のユーザーの名前をあげます。これは、連絡できない場合は、@username に名前をあげたユーザーに連絡することを示します。</span><span class="sxs-lookup"><span data-stu-id="ab199-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="ab199-107">代理人として指名されたユーザーには、指名されたことが通知されます。</span><span class="sxs-lookup"><span data-stu-id="ab199-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="ab199-108">最初のユーザーに連絡しようとしている人は、指名された代理人にカーソルを合わせると、代理人に簡単にメッセージを送ることができます。</span><span class="sxs-lookup"><span data-stu-id="ab199-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="ab199-109">これは、ユーザーによって開始されるクライアントのプロセスであり、この機能を有効にするために管理者に連絡する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ab199-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="ab199-110">医療機関における代理人の使用シナリオ</span><span class="sxs-lookup"><span data-stu-id="ab199-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="ab199-111">*代理人の設定を使用しない例:* Franco Piccio 先生は放射線科に電話をかけています。</span><span class="sxs-lookup"><span data-stu-id="ab199-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="ab199-112">彼は緊急の個人的な電話を受け、数時間現場から離れなければなりません。</span><span class="sxs-lookup"><span data-stu-id="ab199-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="ab199-113">彼は、放射線科の同僚である Lena Ehrle 先生に、自分がいない間、代わりに患者さんを診てほしいと依頼します。</span><span class="sxs-lookup"><span data-stu-id="ab199-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="ab199-114">彼は非公式にポケットベルを Ehrle 先生に渡します。Ehrle 先生は、自分の仕事をこなしながら、Piccio 先生の代わりにポケットベルの緊急メッセージと通知音を聞いて応答します。</span><span class="sxs-lookup"><span data-stu-id="ab199-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="ab199-115">チームの他のメンバーは、非公式の委任に気が付かず、患者さんの治療に混乱が生じるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="ab199-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="ab199-116">*代理人の設定を使用する例:* Franco Piccio 先生は放射線科に電話をかけています。</span><span class="sxs-lookup"><span data-stu-id="ab199-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="ab199-117">彼は緊急の個人的な電話を受け、数時間現場から離れなければなりません。</span><span class="sxs-lookup"><span data-stu-id="ab199-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="ab199-118">彼は、放射線科の同僚である Lena Ehrle 先生に、自分がいない間、代わりに患者さんを診てほしいと依頼します。</span><span class="sxs-lookup"><span data-stu-id="ab199-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="ab199-119">彼は自分のカスタム ステータス メッセージを変更して、「数時間現場から離れなければなりません。</span><span class="sxs-lookup"><span data-stu-id="ab199-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="ab199-120">緊急の場合は @DrEhrle に連絡してください。」のような内容を残します。</span><span class="sxs-lookup"><span data-stu-id="ab199-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="ab199-121">チームの他のメンバーは、Piccio 先生と連絡を取ろうとしたときに、委任があったことに気づきます。そのため、Ehrle 先生と連絡を取ることができます。</span><span class="sxs-lookup"><span data-stu-id="ab199-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="ab199-122">患者の治療に混乱がほとんど生じません。</span><span class="sxs-lookup"><span data-stu-id="ab199-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="ab199-123">Teams クライアントのユーザー ステータスに対する共存モードの影響</span><span class="sxs-lookup"><span data-stu-id="ab199-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="ab199-124">管理者は、[状態メモ] と [委任によるメンション] の動作が、ユーザーの共存モードに依存することに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab199-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user's co-existence mode.</span></span> <span data-ttu-id="ab199-125">このマトリックスは可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="ab199-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="ab199-126">共存モード</span><span class="sxs-lookup"><span data-stu-id="ab199-126">Co-Existence Mode</span></span> | <span data-ttu-id="ab199-127">正常な動作</span><span class="sxs-lookup"><span data-stu-id="ab199-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="ab199-128">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="ab199-128">TeamsOnly</span></span> |<span data-ttu-id="ab199-129">ユーザーは、Teams からのみメモを設定できます。</span><span class="sxs-lookup"><span data-stu-id="ab199-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="ab199-130">ユーザーの Teams のメモは Teams & SfB に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab199-130">User's Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="ab199-131">アイランド</span><span class="sxs-lookup"><span data-stu-id="ab199-131">Islands</span></span> | <span data-ttu-id="ab199-132">Teams でのユーザーのメモセットは、Teams でのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab199-132">User's note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="ab199-133">Sfb でのみ表示される sfb でのユーザのメモセット</span><span class="sxs-lookup"><span data-stu-id="ab199-133">User's note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="ab199-134">SfB\* モード</span><span class="sxs-lookup"><span data-stu-id="ab199-134">SfB\* modes</span></span> | <span data-ttu-id="ab199-135">ユーザーは、SfB からのみメモを設定できます。</span><span class="sxs-lookup"><span data-stu-id="ab199-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="ab199-136">ユーザーの SfB メモは、SfB & Teams で表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab199-136">User's SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="ab199-137">モードが TeamsOnly または アイランドの場合、ユーザーはメモを設定できます。</span><span class="sxs-lookup"><span data-stu-id="ab199-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="ab199-138">メモの Skype for Business での表示</span><span class="sxs-lookup"><span data-stu-id="ab199-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="ab199-139">メモが Skype for Business から設定されていることを視覚的に示すものはありません。</span><span class="sxs-lookup"><span data-stu-id="ab199-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="ab199-140">Skype for Business では、状態メモに文字数の制限は適用されません。</span><span class="sxs-lookup"><span data-stu-id="ab199-140">Skype for Business doesn't enforce a character limit on status notes.</span></span> <span data-ttu-id="ab199-141">Microsoft Teams は、Skype for Business からのメモ セットのうち最初の 280 文字のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="ab199-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="ab199-142">メモの最後にある省略記号 (…) は省略されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="ab199-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="ab199-143">Skype for Business では、ノートの有効期間をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="ab199-143">Skype for Business doesn't support expiry times for notes.</span></span>

<span data-ttu-id="ab199-144">ユーザーが TeamsOnly モードにアップグレードされている場合は、Skype for Business から Teams にメモを移行することはできません。</span><span class="sxs-lookup"><span data-stu-id="ab199-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ab199-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab199-145">Related topics</span></span>

[<span data-ttu-id="ab199-146">Skype for Business と共存する</span><span class="sxs-lookup"><span data-stu-id="ab199-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
