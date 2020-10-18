---
title: 'Lync Server 2013: Lync が有効な電話での通話の使用'
description: 'Lync Server 2013: Lync が有効な電話での通話を使用しています。'
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
ms.openlocfilehash: 7fd7855e45132b133c78230e7f8769bdab897140
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580423"
---
# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a><span data-ttu-id="8b18d-103">Lync が有効な電話および Lync Server 2013 での Call Me の使用</span><span class="sxs-lookup"><span data-stu-id="8b18d-103">Using Call Me At with a Lync-enabled phone and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b18d-104">_**トピックの最終更新日:** 2013-08-09_</span><span class="sxs-lookup"><span data-stu-id="8b18d-104">_**Topic Last Modified:** 2013-08-09_</span></span>

<span data-ttu-id="8b18d-105">Lync の [私に連絡] 機能を使用すると、ユーザーは、携帯電話、"陸 line"、または公衆交換電話網 (PSTN) に接続されたその他のデバイスを使用して、電話会議の音声部分に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="8b18d-105">The Call Me At feature in Lync provides a way for users to join the audio portion of a conference by using a cell phone, “land line,” or other device connected to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="8b18d-106">Lync を使用して会議に参加しようとすると、通常、[ **ミーティング音声に参加** ] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8b18d-106">When you attempt to join a meeting by using Lync, you will typically be presented with the **Join Meeting Audio** dialog box:</span></span>

<span data-ttu-id="8b18d-107">![Lync を使用して会議の音声ウィンドウのスクリーンショットを参加させる](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Lync を使用して会議の音声ウィンドウのスクリーンショットを参加させる")</span><span class="sxs-lookup"><span data-stu-id="8b18d-107">![Use Lync to join meeting audio window screenshot](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Use Lync to join meeting audio window screenshot")</span></span>

<span data-ttu-id="8b18d-108">[電話 **での通話**] を選択した場合は、ドロップダウンリストから電話番号を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="8b18d-108">If you select **Call me at**, you can then pick a phone number from the dropdown list.</span></span> <span data-ttu-id="8b18d-109">Lync Server 2013 は、選択された番号に電話を掛けて、その電話を使用して会議の音声部分に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="8b18d-109">Lync Server 2013 will place a phone call to the selected number, and you can then use that phone to participate in the audio portion of the conference.</span></span>

<span data-ttu-id="8b18d-110">ドロップダウンリストには、[ **Lync –のオプション**] ダイアログボックスの [**電話**] タブに入力した電話番号 (携帯電話、自宅電話番号、またはその他の電話番号) が設定されます。</span><span class="sxs-lookup"><span data-stu-id="8b18d-110">The dropdown list is populated by the phone numbers (for mobile phone, home phone, or other phone) that you have entered on the **Phones** tab in the **Lync – Options** dialog box:</span></span>

<span data-ttu-id="8b18d-111">![Lync Phone セットアップオプションのスクリーンショット](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync Phone セットアップオプションのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="8b18d-111">![Lync Phones set up options screenshot](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync Phones set up options screenshot")</span></span>

<span data-ttu-id="8b18d-112">[ **電話] タブに** 電話番号が入力されていない場合は、ドロップダウンボックスで使用可能な番号はありません。</span><span class="sxs-lookup"><span data-stu-id="8b18d-112">If you have not entered any phone numbers on the **Phones** tab then you will not have any numbers available in the dropdown box.</span></span> <span data-ttu-id="8b18d-113">ただし、[ **新しい番号** ] をいつでもクリックして、Lync Server から必要な電話番号にダイヤルアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="8b18d-113">However, you can always click **New Number** and have Lync Server dial out to any phone number you wish:</span></span>

<span data-ttu-id="8b18d-114">![Lync 参加ミーティング音声呼び出しウィンドウのスクリーンショット](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync 参加ミーティング音声呼び出しウィンドウのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="8b18d-114">![Lync join meeting audio call me window screenshot](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync join meeting audio call me window screenshot")</span></span>

<span data-ttu-id="8b18d-115">この機能は、Lync Server で PSTN 電話番号を呼び出すことによって、意図したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="8b18d-115">The Call Me At feature works extremely well provided that you use it in the way it was intended: by having Lync Server call a PSTN phone number.</span></span> <span data-ttu-id="8b18d-116">ただし、lync が有効なエンドポイント (たとえば、会議室の電話など) で Lync Server に電話をかけようとすると、最適化された機能を実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="8b18d-116">However, you can run into a less-than-optimal experience if you ask Lync Server to call you at a Lync-enabled endpoint (for example, a phone in a conference room).</span></span> <span data-ttu-id="8b18d-117">次に、発生する可能性のある問題と、この問題を回避するための2つの方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8b18d-117">Following is the issue you might run into, as well as two ways to work around the problem.</span></span>

<span data-ttu-id="8b18d-118">まず、Lync が有効になっている電話機の電話番号を使用して、[通話] 機能を提供すると、次のような処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="8b18d-118">To begin, here’s what happens when you provide the Call Me At feature with the phone number of a Lync-enabled phone.</span></span> <span data-ttu-id="8b18d-119">Ken Myer が lync server が有効な電話番号である1-206-555-1219 で Lync Server に電話をかけることによって、会議に参加しようとしているとします。</span><span class="sxs-lookup"><span data-stu-id="8b18d-119">Suppose Ken Myer tries to join a meeting by having Lync Server call him at 1-206-555-1219, a Lync Server-enabled phone number.</span></span> <span data-ttu-id="8b18d-120">最初は Ken が会議に接続されていますが、数秒の Lync がメッセージ **呼び出しを完了または終了**した後に、ken が会議から削除されたように見えます。</span><span class="sxs-lookup"><span data-stu-id="8b18d-120">Ken will initially be connected to the meeting, but after a few seconds Lync will display the message **Call was not completed or has ended**, and Ken will appear to have been dropped from the meeting:</span></span>

<span data-ttu-id="8b18d-121">![Lync 通話会議ウィンドウのスクリーンショット](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Lync 通話会議ウィンドウのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="8b18d-121">![Screen shot of Lync call conferencing window](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Screen shot of Lync call conferencing window")</span></span>

<span data-ttu-id="8b18d-122">ただし、Lync 会話ウィンドウに不一致があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8b18d-122">Notice, however, that there is a discrepancy within the Lync conversation window.</span></span> <span data-ttu-id="8b18d-123">Ken Myer は、[ **参加者** ] の見出しの下に表示される唯一の名前です。</span><span class="sxs-lookup"><span data-stu-id="8b18d-123">Ken Myer is the only name listed under the **Participants** heading.</span></span> <span data-ttu-id="8b18d-124">ただし、ウィンドウのタイトルバーを見ると、会議に合計4人の参加者が含まれていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="8b18d-124">However, if you look in the title bar of the window, you’ll see that the conference contains a total of 4 participants.</span></span>

<span data-ttu-id="8b18d-125">同様に、他のいずれかの会議参加者の [会話] ウィンドウを表示しても、Ken Myer がどこにも表示されません。</span><span class="sxs-lookup"><span data-stu-id="8b18d-125">Likewise, if you look in the conversation window of any of the other conference participants you will not see Ken Myer listed anywhere:</span></span>

<span data-ttu-id="8b18d-126">![Lync 参加者リストウィンドウのスクリーンショット](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync 参加者リストウィンドウのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="8b18d-126">![Lync participant list window screenshot](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync participant list window screenshot")</span></span>

<span data-ttu-id="8b18d-127">それと同時に、Ken Myer は Lync が有効な電話機を使用して通話の音声部分に参加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8b18d-127">And yet, at the same time, Ken Myer will be able to participate in the audio portion of the call by using his Lync-enabled phone.</span></span> <span data-ttu-id="8b18d-128">この機能は実際には動作していますが、ユーザーの利便性は最適ではありません。</span><span class="sxs-lookup"><span data-stu-id="8b18d-128">The Call Me At feature has actually worked, but the user experience is less than optimal.</span></span>

<span data-ttu-id="8b18d-129">この問題を回避する方法は、少なくとも2つあります。</span><span class="sxs-lookup"><span data-stu-id="8b18d-129">There are at least two ways to work around this problem.</span></span> <span data-ttu-id="8b18d-130">この方法 (Ken Myer did など) で既に電話会議に参加している場合は、通常は別のモダリティを使用して問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="8b18d-130">If you have already joined a conference in this fashion (like Ken Myer did), you can typically resolve the issue by engaging in a different modality.</span></span> <span data-ttu-id="8b18d-131">たとえば、インスタントメッセージを送信すると、[会話] ウィンドウには、自分を含むすべての電話会議の参加者が表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="8b18d-131">For example, if you send an instant message the conversation window will now show all the conference participants, including yourself:</span></span>

<span data-ttu-id="8b18d-132">![Lync の会話と参加者リストのスクリーンショット](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync の会話と参加者リストのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="8b18d-132">![Lync conversation and participant list screenshot](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync conversation and participant list screenshot")</span></span>

<span data-ttu-id="8b18d-133">この時点で、必要な方法で会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="8b18d-133">At this point you should be able to participate in the meeting in the expected fashion.</span></span>

<span data-ttu-id="8b18d-134">または、会議への参加方法を変更することによって、この問題を完全に回避できます。</span><span class="sxs-lookup"><span data-stu-id="8b18d-134">Alternatively, you can avoid this issue altogether by changing the way you join the meeting.</span></span> <span data-ttu-id="8b18d-135">Lync Server が有効な電話機を Lync Server で呼び出す必要がある場合は、まず音声接続を使用せずに会議に参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b18d-135">If you need to have Lync Server call a Lync Server-enabled phone, you should begin by joining the meeting without an audio connection.</span></span> <span data-ttu-id="8b18d-136">そのためには、[ミーティング音声に参加する] ダイアログボックスが表示されたときに、[オーディオに参加しない] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8b18d-136">To do that, select Don’t join audio when presented with the Join Meeting Audio dialog box:</span></span>

<span data-ttu-id="8b18d-137">![Lync が会議の音声ウィンドウのスクリーンショットに参加しない](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync が会議の音声ウィンドウのスクリーンショットに参加しない")</span><span class="sxs-lookup"><span data-stu-id="8b18d-137">![Lync don't join meeting audio window screenshot](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync don't join meeting audio window screenshot")</span></span>

<span data-ttu-id="8b18d-138">会議への接続が正常に完了すると、Lync Server が有効になっている電話を会議に参加させることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="8b18d-138">After you have successfully connected to the meeting, you can now “invite” the Lync Server-enabled phone to join the meeting as well.</span></span> <span data-ttu-id="8b18d-139">そのためには、マウスを People アイコンの上に置き、[ **他のユーザーを招待**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8b18d-139">To do that, place the mouse over the People icon and then click **Invite More People**:</span></span>

<span data-ttu-id="8b18d-140">![Lync invite [その他の参加者の追加] ウィンドウのスクリーンショット](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync invite [その他の参加者の追加] ウィンドウのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="8b18d-140">![Lync invite more participants window screenshot](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync invite more participants window screenshot")</span></span>

<span data-ttu-id="8b18d-141">を選択すると、[ **IM の送信** ] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8b18d-141">That will bring up the **Send an IM** dialog box.</span></span> <span data-ttu-id="8b18d-142">ダイアログボックスのタイトル (実際にはインスタントメッセージを送信しない) を無視して、Lync が有効な電話の電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="8b18d-142">Ignore the dialog box title (you’re not actually sending an instant message) and type the phone number of the Lync-enabled phone:</span></span>

<span data-ttu-id="8b18d-143">![IM ダイアログボックスのスクリーンショットを送信する](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "IM ダイアログボックスのスクリーンショットを送信する")</span><span class="sxs-lookup"><span data-stu-id="8b18d-143">![Send an IM dialog box screenshot](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Send an IM dialog box screenshot")</span></span>

<span data-ttu-id="8b18d-144">[ **OK]** をクリックすると、ダイアログボックスに入力した番号が Lync Server によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8b18d-144">After you click **OK**, Lync Server will call the number entered in the dialog box.</span></span> <span data-ttu-id="8b18d-145">接続が確立されると、Lync が有効になっている電話から完全な音声機能が提供されるようになり、会議の完全な一覧を表示して操作できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8b18d-145">When the connection is made, you will have full audio capabilities through the Lync-enabled phone, and you will be able to see and interact with the full conference roster.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

