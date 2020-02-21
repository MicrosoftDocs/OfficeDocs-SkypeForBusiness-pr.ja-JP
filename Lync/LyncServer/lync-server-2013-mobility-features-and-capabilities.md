---
title: 'Lync Server 2013: モビリティの特徴と機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c534aa912e2564f8a8934aafa75bc52b76600795
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a><span data-ttu-id="fda15-102">Lync Server 2013 のモビリティ機能</span><span class="sxs-lookup"><span data-stu-id="fda15-102">Mobility features and capabilities in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fda15-103">_**トピックの最終更新日:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="fda15-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="fda15-104">Lync Server 2013 の累積的な更新プログラムで導入されたモビリティ機能: 2 月2013は Lync 2010 Mobile および Lync 2013 Mobile クライアント機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="fda15-104">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2010 Mobile and Lync 2013 Mobile clients functionality.</span></span> <span data-ttu-id="fda15-105">Lync Server 2013 Mobility Service を展開すると、ユーザーはサポートされている Apple iOS、Android、Windows Phone、または Nokia Symbian モバイルデバイスを使用して、インスタントメッセージの送受信、連絡先の表示、プレゼンスの表示などのアクティビティを実行できます。</span><span class="sxs-lookup"><span data-stu-id="fda15-105">When you deploy the Lync Server 2013 Mobility Service, users can use supported Apple iOS, Android, and Windows Phone, or Nokia Symbian mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="fda15-106">また、クリックして会議に参加、勤務先から通話、同一番号接続、ボイス メール、不在着信など、モバイル デバイスでいくつかのエンタープライズ VoIP 機能がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="fda15-106">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="fda15-107">Lync Server 2013 の累積的な更新プログラムで導入された新機能: 2 月2013には、会議の出席者のボイスオーバー IP (VoIP) 機能とビデオ (.H) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fda15-107">New features introduced in the Cumulative Updates for Lync Server 2013: February 2013 include Voice over IP (VoIP) capability and video (H.264) for meeting attendee.</span></span>

<span data-ttu-id="fda15-108">Lync Server 2013 の累積的な更新プログラムで導入されたモビリティ機能: 2 月2013は Lync 2013 Mobile クライアント機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="fda15-108">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2013 Mobile client functionality.</span></span> <span data-ttu-id="fda15-109">Lync Server 2013 の累積的な更新プログラム: 2 月2013統合コミュニケーション Web API または UCWA。</span><span class="sxs-lookup"><span data-stu-id="fda15-109">The Cumulative Updates for Lync Server 2013: February 2013 install Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="fda15-110">UCWA は、Lync 2013 モバイルクライアントに使用されるコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="fda15-110">UCWA is the component used for Lync 2013 Mobile clients.</span></span> <span data-ttu-id="fda15-111">Lync Server 2013 では、Mcx が Lync 2010 モバイルクライアントに使用されます。</span><span class="sxs-lookup"><span data-stu-id="fda15-111">In Lync Server 2013, Mcx is used for Lync 2010 Mobile clients.</span></span> <span data-ttu-id="fda15-112">Lync Server 2013 の累積的な更新プログラム: 2 月2013は、mobility services の新しいエントリポイントとして UCWA を導入します。</span><span class="sxs-lookup"><span data-stu-id="fda15-112">Cumulative Updates for Lync Server 2013: February 2013 introduce UCWA as the new entry point for mobility services.</span></span> <span data-ttu-id="fda15-113">Lync Server 2013 は、Lync Server 2010:11 月2011の累積的な更新プログラムで導入された Mobility Service (Mcx) を同時に実装し、Lync 2010 Mobile のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="fda15-113">Lync Server 2013 concurrently implements the Mobility Service (Mcx), introduced in the Cumulative Updates for Lync Server 2010: November 2011, and provides support for Lync 2010 Mobile.</span></span> <span data-ttu-id="fda15-114">Lync Server 2013 の累積的な更新プログラム (2 月 2013) を展開する場合、ユーザーはサポートされている Apple iOS、Android、および Windows Phone モバイルデバイスを使用して、次のような操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="fda15-114">When you deploy the Cumulative Updates for Lync Server 2013: February 2013, users can use supported Apple iOS, Android, and Windows Phone mobile devices to perform such activities as:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fda15-115">Mobility Service でサポートされている機能 (Lync Server 2010 の累積的な更新プログラム):11 月2011は、(Mcx) で示されています。</span><span class="sxs-lookup"><span data-stu-id="fda15-115">Features supported by the Mobility Service from the Cumulative Updates for Lync Server 2010: November 2011 are noted with (Mcx).</span></span> <span data-ttu-id="fda15-116">リストされているすべての機能は、Lync Server 2013 の累積的な更新プログラムで導入された、UCWA でサポートされています (2013 年2月)。</span><span class="sxs-lookup"><span data-stu-id="fda15-116">All listed features are supported by the UCWA, introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

  - <span data-ttu-id="fda15-117">インスタントメッセージを送受信する (Mcx)</span><span class="sxs-lookup"><span data-stu-id="fda15-117">Send and receive instant messages (Mcx)</span></span>

  - <span data-ttu-id="fda15-118">プレゼンスの表示 (Mcx)</span><span class="sxs-lookup"><span data-stu-id="fda15-118">View presence (Mcx)</span></span>

  - <span data-ttu-id="fda15-119">連絡先を表示する (Mcx)</span><span class="sxs-lookup"><span data-stu-id="fda15-119">View contacts (Mcx)</span></span>

  - <span data-ttu-id="fda15-120">クリックして会議に参加する (Mcx)</span><span class="sxs-lookup"><span data-stu-id="fda15-120">Click to join a conference (Mcx)</span></span>

  - <span data-ttu-id="fda15-121">勤務先から通話 (Mcx)</span><span class="sxs-lookup"><span data-stu-id="fda15-121">Call via work (Mcx)</span></span>

  - <span data-ttu-id="fda15-122">単一番号のリーチ (Mcx)</span><span class="sxs-lookup"><span data-stu-id="fda15-122">Single number reach (Mcx)</span></span>

  - <span data-ttu-id="fda15-123">ボイスメール (Mcx)</span><span class="sxs-lookup"><span data-stu-id="fda15-123">Voice mail (Mcx)</span></span>

  - <span data-ttu-id="fda15-124">不在着信通知 (Mcx)</span><span class="sxs-lookup"><span data-stu-id="fda15-124">Missed call notification (Mcx)</span></span>

  - <span data-ttu-id="fda15-125">ボイス オーバー IP (VoIP)</span><span class="sxs-lookup"><span data-stu-id="fda15-125">Voice over IP (VoIP)</span></span>

  - <span data-ttu-id="fda15-126">出席者のビデオ (.H)</span><span class="sxs-lookup"><span data-stu-id="fda15-126">Attendee video (H.264)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fda15-127">Lync 2010 Mobile には、Nokia Symbian デバイス用のクライアントが用意されています。</span><span class="sxs-lookup"><span data-stu-id="fda15-127">Lync 2010 Mobile provided a client for Nokia Symbian devices.</span></span> <span data-ttu-id="fda15-128">Lync 2013 Mobile には、Nokia Symbian ベースのデバイスのクライアントはありません。</span><span class="sxs-lookup"><span data-stu-id="fda15-128">Lync 2013 Mobile will not have a client for Nokia Symbian-based devices.</span></span>



</div>

<span data-ttu-id="fda15-129">Apple iPad ユーザーは強化機能を利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="fda15-129">Apple iPad users will have access to enhanced capabilities.</span></span> <span data-ttu-id="fda15-130">音声通話を使用して会議に参加した後、iPad ユーザーは、会議内でアップロードされた Microsoft PowerPoint プレゼンテーションを表示したり、アプリケーションやデスクトップを共有したり、会議参加者リストを表示したり、その他のコンテンツタイプの通知を受信したりできます。が会議内で共有されている。</span><span class="sxs-lookup"><span data-stu-id="fda15-130">After joining a meeting by using audio call back, an iPad user will be able to view uploaded Microsoft PowerPoint presentations within a meeting, share applications and desktops, view the meeting participant list, and receive notifications of other content types that are being shared within the meeting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="fda15-131">1つの番号がある場合、ユーザーは勤務先番号にダイヤルされた携帯電話の通話を受信します。</span><span class="sxs-lookup"><span data-stu-id="fda15-131">With single number reach, a user receives calls on a mobile phone that were dialed to the work number.</span></span> <span data-ttu-id="fda15-132">[勤務先から通話] を使用すると、ユーザーは携帯電話番号ではなく勤務先電話番号を使用して Lync Mobile クライアントからの発信通話を配置します。</span><span class="sxs-lookup"><span data-stu-id="fda15-132">With Call via Work, the user places an outbound call from the Lync Mobile client by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="fda15-133">ダイヤルアウトの場合、クライアントは Mcx または UCWA (Lync Mobile バージョンに基づいて) に要求を送信して、それらの呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="fda15-133">With dial-out, the client sends a request to Mcx or UCWA (based on the Lync Mobile version) to make the call for them.</span></span> <span data-ttu-id="fda15-134">サーバーは通話を開始し、ユーザーに電話をかけ直します。</span><span class="sxs-lookup"><span data-stu-id="fda15-134">The server initiates the call and then calls the user back on the mobile phone.</span></span> <span data-ttu-id="fda15-135">ユーザーが応答すると、サーバーは相手をダイヤルして通話を完了します。</span><span class="sxs-lookup"><span data-stu-id="fda15-135">When the user answers, the server completes the call by dialing the other party.</span></span> <span data-ttu-id="fda15-136">通話による通話を使用することで、ユーザーは通話中に作業の id を維持することができます。つまり、通話受信者は発信者の携帯電話番号を表示せず、発信者が発信通話料金を発生させないようにします。</span><span class="sxs-lookup"><span data-stu-id="fda15-136">By using Call via Work, users can maintain their work identity during a call, which means that the call recipient does not see the caller's mobile number, and the caller avoids incurring outbound calling charges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="fda15-137">すべてのモバイル デバイスですべての機能がまったく同じように動作するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="fda15-137">Not all features work exactly the same on all mobile devices.</span></span> <span data-ttu-id="fda15-138">モバイルデバイスでサポートされている機能の詳細については、 <A href="https://go.microsoft.com/fwlink/p/?linkid=234777">https://go.microsoft.com/fwlink/p/?LinkId=234777</A>「」のモバイルクライアントの比較表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fda15-138">For details about features supported on mobile devices, see the Mobile Client Comparison Tables at <A href="https://go.microsoft.com/fwlink/p/?linkid=234777">https://go.microsoft.com/fwlink/p/?LinkId=234777</A>.</span></span> <span data-ttu-id="fda15-139">サポートされているデバイスとオペレーティングシステムの詳細については、「 <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for mobile clients In Lync Server 2013</A>」の「要件」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fda15-139">For details about supported devices and operating systems, see the requirements topics under <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for mobile clients in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="fda15-140">Lync Server 2013 自動検出機能を使用すると、モバイルアプリケーションは、ユーザーが自分のデバイス設定に Url を手動で入力する必要なく、Lync Server 2013 Web サービスを自動的に検索できます。</span><span class="sxs-lookup"><span data-stu-id="fda15-140">When you use the Lync Server 2013 Autodiscover feature, mobile applications can automatically locate Lync Server 2013 Web Services without requiring users to manually enter the URLs in their device settings.</span></span> <span data-ttu-id="fda15-141">URL をモバイル デバイスの設定に手動で入力することも、主にトラブルシューティングの目的でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="fda15-141">Manually entering URLs in mobile device settings is also supported, primarily for troubleshooting purposes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fda15-142">Mcx および UCWA は補完的なサービスで、両方とも、Lync 2010 Mobile および Lync 2013 モバイルクライアントをサポートするために展開されています。</span><span class="sxs-lookup"><span data-stu-id="fda15-142">The Mcx and UCWA are complimentary services and both are deployed to support Lync 2010 Mobile and Lync 2013 Mobile clients.</span></span> <span data-ttu-id="fda15-143">Lync 2013 Mobile は Lync Server 2010 の展開にサインインできません。</span><span class="sxs-lookup"><span data-stu-id="fda15-143">Lync 2013 Mobile will not be able to sign in to Lync Server 2010 deployments.</span></span> <span data-ttu-id="fda15-144">Lync 2010 Mobile および Lync 2013 Mobile は、lync Server 2013 の累積的な更新プログラムで Lync Server 2013 展開を使用できるようになります。 2 2013 月適用。</span><span class="sxs-lookup"><span data-stu-id="fda15-144">Lync 2010 Mobile and Lync 2013 Mobile will be able to use a Lync Server 2013 deployment with the Cumulative Updates for Lync Server 2013: February 2013 applied.</span></span>



</div>

<span data-ttu-id="fda15-145">モビリティ機能では、バックグラウンドで実行されているアプリケーションをサポートしないモバイル デバイス用のプッシュ通知\*\* もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="fda15-145">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="fda15-146">プッシュ通知は、モバイル アプリケーションが非アクティブなときに発生したイベントについてモバイル デバイスに送信される通知です。</span><span class="sxs-lookup"><span data-stu-id="fda15-146">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span> <span data-ttu-id="fda15-147">たとえば、不在着信したインスタントメッセージング (IM) の招待には、プッシュ通知が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="fda15-147">For example, a missed instant messaging (IM) invitation can result in a push notification.</span></span>

<span data-ttu-id="fda15-148">Mcx、UCWA、自動検出サービス、およびプッシュ通知のサポートは、Lync Server 2013 で提供されます。</span><span class="sxs-lookup"><span data-stu-id="fda15-148">Mcx, UCWA, Autodiscover Service, and support for push notifications are provided in Lync Server 2013.</span></span> <span data-ttu-id="fda15-149">Lync Server 2013 の累積的な更新プログラム (2013 年2月) でのモビリティエントリポイントの導入において、クライアントの機能、機能、および UCWA の使用が更新されました。</span><span class="sxs-lookup"><span data-stu-id="fda15-149">Updated client features, capabilities, and the use of UCWA as the mobility entry point are introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

