---
title: 'Lync Server 2013: Lync 対応電話での通話を使用する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Call Me At with a Lync-enabled phone
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56470326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d4b117970cec1e40b4d18928f82bc0cf2831eb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744227"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a><span data-ttu-id="6b794-102">Lync 対応電話および Lync Server 2013 での [折り返し] の使用</span><span class="sxs-lookup"><span data-stu-id="6b794-102">Using Call Me At with a Lync-enabled phone and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b794-103">_**最終更新日:** 2013-08-09_</span><span class="sxs-lookup"><span data-stu-id="6b794-103">_**Topic Last Modified:** 2013-08-09_</span></span>

<span data-ttu-id="6b794-104">Lync の [折り返し先] 機能を使うと、ユーザーは携帯電話、"陸"、または公衆交換電話網 (PSTN) に接続されたその他のデバイスを使って、会議のオーディオ部分に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="6b794-104">The Call Me At feature in Lync provides a way for users to join the audio portion of a conference by using a cell phone, “land line,” or other device connected to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="6b794-105">Lync を使用して会議に参加しようとすると、通常、[**音声会議**への参加方法] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b794-105">When you attempt to join a meeting by using Lync, you will typically be presented with the **Join Meeting Audio** dialog box:</span></span>

<span data-ttu-id="6b794-106">![Lync を使用して会議の音声ウィンドウのスクリーンショットに参加する](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Lync を使用して会議の音声ウィンドウのスクリーンショットに参加する")</span><span class="sxs-lookup"><span data-stu-id="6b794-106">![Use Lync to join meeting audio window screenshot](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Use Lync to join meeting audio window screenshot")</span></span>

<span data-ttu-id="6b794-107">[**折り返し**先] を選択した場合は、ドロップダウンリストから電話番号を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="6b794-107">If you select **Call me at**, you can then pick a phone number from the dropdown list.</span></span> <span data-ttu-id="6b794-108">Lync Server 2013 は、選択した電話番号に電話をかけ、その電話を使って会議のオーディオ部分に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="6b794-108">Lync Server 2013 will place a phone call to the selected number, and you can then use that phone to participate in the audio portion of the conference.</span></span>

<span data-ttu-id="6b794-109">ドロップダウンリストには、[ **Lync-オプション**] ダイアログボックスの [**電話**] タブで入力した電話番号 (携帯電話、自宅電話、その他の電話用) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b794-109">The dropdown list is populated by the phone numbers (for mobile phone, home phone, or other phone) that you have entered on the **Phones** tab in the **Lync – Options** dialog box:</span></span>

<span data-ttu-id="6b794-110">![Lync Phone のセットアップオプションのスクリーンショット](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync Phone のセットアップオプションのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="6b794-110">![Lync Phones set up options screenshot](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync Phones set up options screenshot")</span></span>

<span data-ttu-id="6b794-111">[電話] タブで電話番号を入力していない場合**は、ドロップ**ダウンボックスに使用できる番号はありません。</span><span class="sxs-lookup"><span data-stu-id="6b794-111">If you have not entered any phone numbers on the **Phones** tab then you will not have any numbers available in the dropdown box.</span></span> <span data-ttu-id="6b794-112">ただし、いつでも [**新しい番号**] をクリックして、必要な電話番号に Lync Server でダイヤルアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="6b794-112">However, you can always click **New Number** and have Lync Server dial out to any phone number you wish:</span></span>

<span data-ttu-id="6b794-113">![Lync 会議の音声通話ウィンドウのスクリーンショット](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync 会議の音声通話ウィンドウのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="6b794-113">![Lync join meeting audio call me window screenshot](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync join meeting audio call me window screenshot")</span></span>

<span data-ttu-id="6b794-114">[折り返し先] 機能は、意図したとおりに使用するために、Lync Server で PSTN 電話番号を呼び出すことによって、非常にうまく機能します。</span><span class="sxs-lookup"><span data-stu-id="6b794-114">The Call Me At feature works extremely well provided that you use it in the way it was intended: by having Lync Server call a PSTN phone number.</span></span> <span data-ttu-id="6b794-115">ただし、lync が有効なエンドポイント (たとえば、会議室の電話など) で通話を発信するように Lync Server に依頼した場合は、最適なエクスペリエンスを実現することはできません。</span><span class="sxs-lookup"><span data-stu-id="6b794-115">However, you can run into a less-than-optimal experience if you ask Lync Server to call you at a Lync-enabled endpoint (for example, a phone in a conference room).</span></span> <span data-ttu-id="6b794-116">以下に、発生する可能性のある問題と、その問題を回避する2つの方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6b794-116">Following is the issue you might run into, as well as two ways to work around the problem.</span></span>

<span data-ttu-id="6b794-117">まず、Lync 対応電話の電話番号を使用して [着信] 機能を提供すると、次のような処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="6b794-117">To begin, here’s what happens when you provide the Call Me At feature with the phone number of a Lync-enabled phone.</span></span> <span data-ttu-id="6b794-118">Ken Myer が、lync server が有効な電話番号である1-206-555-1219 で電話を受けて会議に参加しようとしているとします。</span><span class="sxs-lookup"><span data-stu-id="6b794-118">Suppose Ken Myer tries to join a meeting by having Lync Server call him at 1-206-555-1219, a Lync Server-enabled phone number.</span></span> <span data-ttu-id="6b794-119">Ken は最初に会議に接続されますが、数分の Lync によってメッセージの着信が完了しなかった**か、終了**したため、ken が会議から削除されたと表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b794-119">Ken will initially be connected to the meeting, but after a few seconds Lync will display the message **Call was not completed or has ended**, and Ken will appear to have been dropped from the meeting:</span></span>

<span data-ttu-id="6b794-120">![Lync の通話会議ウィンドウのスクリーンショット](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Lync の通話会議ウィンドウのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="6b794-120">![Screen shot of Lync call conferencing window](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Screen shot of Lync call conferencing window")</span></span>

<span data-ttu-id="6b794-121">ただし、Lync 会話ウィンドウに不一致があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6b794-121">Notice, however, that there is a discrepancy within the Lync conversation window.</span></span> <span data-ttu-id="6b794-122">Ken Myer は、[**参加者**] の見出しの下に表示される唯一の名前です。</span><span class="sxs-lookup"><span data-stu-id="6b794-122">Ken Myer is the only name listed under the **Participants** heading.</span></span> <span data-ttu-id="6b794-123">ただし、ウィンドウのタイトルバーに表示されている場合は、会議に合計4人の参加者が含まれていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="6b794-123">However, if you look in the title bar of the window, you’ll see that the conference contains a total of 4 participants.</span></span>

<span data-ttu-id="6b794-124">同様に、他の電話会議参加者の会話ウィンドウを見ると、Ken Myer はどこにも表示されません。</span><span class="sxs-lookup"><span data-stu-id="6b794-124">Likewise, if you look in the conversation window of any of the other conference participants you will not see Ken Myer listed anywhere:</span></span>

<span data-ttu-id="6b794-125">![Lync 参加者リストウィンドウのスクリーンショット](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync 参加者リストウィンドウのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="6b794-125">![Lync participant list window screenshot](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync participant list window screenshot")</span></span>

<span data-ttu-id="6b794-126">同時に、Ken Myer は Lync 対応の電話を使って通話の音声部分に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="6b794-126">And yet, at the same time, Ken Myer will be able to participate in the audio portion of the call by using his Lync-enabled phone.</span></span> <span data-ttu-id="6b794-127">[折り返し先] 機能は実際には動作していますが、ユーザーエクスペリエンスが最適ではありません。</span><span class="sxs-lookup"><span data-stu-id="6b794-127">The Call Me At feature has actually worked, but the user experience is less than optimal.</span></span>

<span data-ttu-id="6b794-128">この問題を回避するには、少なくとも2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="6b794-128">There are at least two ways to work around this problem.</span></span> <span data-ttu-id="6b794-129">この方法 (Ken Myer など) で既に会議に参加している場合は、別のモダリティを利用することで問題を解決できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6b794-129">If you have already joined a conference in this fashion (like Ken Myer did), you can typically resolve the issue by engaging in a different modality.</span></span> <span data-ttu-id="6b794-130">たとえば、インスタントメッセージを送信すると、会話ウィンドウには、自分自身を含むすべての会議参加者が表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="6b794-130">For example, if you send an instant message the conversation window will now show all the conference participants, including yourself:</span></span>

<span data-ttu-id="6b794-131">![Lync の会話と参加者リストのスクリーンショット](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync の会話と参加者リストのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="6b794-131">![Lync conversation and participant list screenshot](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync conversation and participant list screenshot")</span></span>

<span data-ttu-id="6b794-132">この時点で、予期される方法で会議に参加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6b794-132">At this point you should be able to participate in the meeting in the expected fashion.</span></span>

<span data-ttu-id="6b794-133">または、会議への参加方法を変更することで、この問題を完全に回避することもできます。</span><span class="sxs-lookup"><span data-stu-id="6b794-133">Alternatively, you can avoid this issue altogether by changing the way you join the meeting.</span></span> <span data-ttu-id="6b794-134">Lync server が有効になっている電話に Lync Server から通話を発信する必要がある場合は、まず、音声接続なしで会議に参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b794-134">If you need to have Lync Server call a Lync Server-enabled phone, you should begin by joining the meeting without an audio connection.</span></span> <span data-ttu-id="6b794-135">そのためには、[音声会議への参加方法] ダイアログボックスが表示されているときに、[音声を使用しない] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6b794-135">To do that, select Don’t join audio when presented with the Join Meeting Audio dialog box:</span></span>

<span data-ttu-id="6b794-136">![Lync が会議の音声ウィンドウに参加しない](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync が会議の音声ウィンドウに参加しない")</span><span class="sxs-lookup"><span data-stu-id="6b794-136">![Lync don't join meeting audio window screenshot](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync don't join meeting audio window screenshot")</span></span>

<span data-ttu-id="6b794-137">会議への接続が正常に完了すると、Lync サーバー対応電話を "招待" して会議に参加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6b794-137">After you have successfully connected to the meeting, you can now “invite” the Lync Server-enabled phone to join the meeting as well.</span></span> <span data-ttu-id="6b794-138">そのためには、ユーザーアイコンの上にマウスポインターを置き、[**他の人を招待**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b794-138">To do that, place the mouse over the People icon and then click **Invite More People**:</span></span>

<span data-ttu-id="6b794-139">![Lync の「その他の参加者の招待」ウィンドウのスクリーンショット](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync の「その他の参加者の招待」ウィンドウのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="6b794-139">![Lync invite more participants window screenshot](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync invite more participants window screenshot")</span></span>

<span data-ttu-id="6b794-140">これにより、[ **IM の送信**] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b794-140">That will bring up the **Send an IM** dialog box.</span></span> <span data-ttu-id="6b794-141">ダイアログボックスのタイトルを無視します (実際にはインスタントメッセージを送信していません)。次に、Lync 対応電話の電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="6b794-141">Ignore the dialog box title (you’re not actually sending an instant message) and type the phone number of the Lync-enabled phone:</span></span>

<span data-ttu-id="6b794-142">![[IM の送信] ダイアログボックスのスクリーンショット](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "[IM の送信] ダイアログボックスのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="6b794-142">![Send an IM dialog box screenshot](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Send an IM dialog box screenshot")</span></span>

<span data-ttu-id="6b794-143">[ **OK**] をクリックすると、Lync Server はダイアログボックスに入力された番号に電話をかけます。</span><span class="sxs-lookup"><span data-stu-id="6b794-143">After you click **OK**, Lync Server will call the number entered in the dialog box.</span></span> <span data-ttu-id="6b794-144">接続が確立されると、Lync 対応の電話を通じて完全なオーディオ機能を利用できるようになり、会議リスト全体を表示して操作できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6b794-144">When the connection is made, you will have full audio capabilities through the Lync-enabled phone, and you will be able to see and interact with the full conference roster.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

