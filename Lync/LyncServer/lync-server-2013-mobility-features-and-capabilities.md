---
title: 'Lync Server 2013: モビリティの機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e47a37acd45ed577b9ad730de39c79d4113c8f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a><span data-ttu-id="301b3-102">Lync Server 2013 のモビリティの機能</span><span class="sxs-lookup"><span data-stu-id="301b3-102">Mobility features and capabilities in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="301b3-103">_**最終更新日:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="301b3-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="301b3-104">Lync Server 2013 の累積更新プログラムで導入されたモバイル機能: 2 月2013は Lync 2010 Mobile および Lync 2013 モバイルクライアント機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="301b3-104">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2010 Mobile and Lync 2013 Mobile clients functionality.</span></span> <span data-ttu-id="301b3-105">Lync Server 2013 モビリティサービスを展開すると、サポートされている Apple iOS、Android、Windows Phone、Nokia Symbian モバイルデバイスを使って、インスタントメッセージの送受信、連絡先の表示、プレゼンスの表示などの操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="301b3-105">When you deploy the Lync Server 2013 Mobility Service, users can use supported Apple iOS, Android, and Windows Phone, or Nokia Symbian mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="301b3-106">さらに、モバイルデバイスでは、クリックして電話会議に参加したり、勤務先の電話による通話、ボイスメール、不在着信など、一部のエンタープライズ音声機能をサポートしたりします。</span><span class="sxs-lookup"><span data-stu-id="301b3-106">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="301b3-107">Lync Server 2013 の累積更新プログラムで導入された新機能: 2013 年2月電話には、会議出席者のためのボイスオーバー IP (VoIP) 機能とビデオ (.H) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="301b3-107">New features introduced in the Cumulative Updates for Lync Server 2013: February 2013 include Voice over IP (VoIP) capability and video (H.264) for meeting attendee.</span></span>

<span data-ttu-id="301b3-108">Lync Server 2013 の累積更新プログラムで導入されたモバイル機能: 2013 年2月のモバイルクライアントの機能が2013サポートされています。</span><span class="sxs-lookup"><span data-stu-id="301b3-108">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2013 Mobile client functionality.</span></span> <span data-ttu-id="301b3-109">Lync Server 2013 向けの累積的な更新プログラム: 年 2 2013 月ユニファイドコミュニケーションの Web API、または UCWA をインストールします。</span><span class="sxs-lookup"><span data-stu-id="301b3-109">The Cumulative Updates for Lync Server 2013: February 2013 install Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="301b3-110">UCWA は、Lync 2013 モバイルクライアントで使用されるコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="301b3-110">UCWA is the component used for Lync 2013 Mobile clients.</span></span> <span data-ttu-id="301b3-111">Lync Server 2013 では、Mcx が Lync 2010 モバイルクライアントで使用されます。</span><span class="sxs-lookup"><span data-stu-id="301b3-111">In Lync Server 2013, Mcx is used for Lync 2010 Mobile clients.</span></span> <span data-ttu-id="301b3-112">Lync Server 2013 の累積更新プログラム: 2013 年2月に、モビリティサービスの新しいエントリポイントとして UCWA が導入されています。</span><span class="sxs-lookup"><span data-stu-id="301b3-112">Cumulative Updates for Lync Server 2013: February 2013 introduce UCWA as the new entry point for mobility services.</span></span> <span data-ttu-id="301b3-113">Lync Server 2013 は、Lync Server 2010: 2011 年11月の累積更新プログラムで導入されたモビリティサービス (Mcx) を同時に実装し、Lync 2010 Mobile のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="301b3-113">Lync Server 2013 concurrently implements the Mobility Service (Mcx), introduced in the Cumulative Updates for Lync Server 2010: November 2011, and provides support for Lync 2010 Mobile.</span></span> <span data-ttu-id="301b3-114">Lync Server 2013 2013 の累積更新プログラムを展開する場合、ユーザーはサポートされている Apple iOS、Android、Windows Phone のモバイルデバイスを使用して、次のような操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="301b3-114">When you deploy the Cumulative Updates for Lync Server 2013: February 2013, users can use supported Apple iOS, Android, and Windows Phone mobile devices to perform such activities as:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="301b3-115">Lync Server 2010 の累積的な更新プログラムのモビリティサービスでサポートされている機能: 2011 年11月には、(Mcx) と記載されています。</span><span class="sxs-lookup"><span data-stu-id="301b3-115">Features supported by the Mobility Service from the Cumulative Updates for Lync Server 2010: November 2011 are noted with (Mcx).</span></span> <span data-ttu-id="301b3-116">リストされたすべての機能は、UCWA でサポートされます。 Lync Server 2013 の累積更新プログラムで導入されました。2013年2月。</span><span class="sxs-lookup"><span data-stu-id="301b3-116">All listed features are supported by the UCWA, introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

  - <span data-ttu-id="301b3-117">インスタントメッセージ (Mcx) を送受信する</span><span class="sxs-lookup"><span data-stu-id="301b3-117">Send and receive instant messages (Mcx)</span></span>

  - <span data-ttu-id="301b3-118">プレゼンスを表示する (Mcx)</span><span class="sxs-lookup"><span data-stu-id="301b3-118">View presence (Mcx)</span></span>

  - <span data-ttu-id="301b3-119">連絡先を表示する (Mcx)</span><span class="sxs-lookup"><span data-stu-id="301b3-119">View contacts (Mcx)</span></span>

  - <span data-ttu-id="301b3-120">クリックして会議に参加する (Mcx)</span><span class="sxs-lookup"><span data-stu-id="301b3-120">Click to join a conference (Mcx)</span></span>

  - <span data-ttu-id="301b3-121">職場での通話 (Mcx)</span><span class="sxs-lookup"><span data-stu-id="301b3-121">Call via work (Mcx)</span></span>

  - <span data-ttu-id="301b3-122">1つの番号への到達 (Mcx)</span><span class="sxs-lookup"><span data-stu-id="301b3-122">Single number reach (Mcx)</span></span>

  - <span data-ttu-id="301b3-123">ボイスメール (Mcx)</span><span class="sxs-lookup"><span data-stu-id="301b3-123">Voice mail (Mcx)</span></span>

  - <span data-ttu-id="301b3-124">不在着信通知 (Mcx)</span><span class="sxs-lookup"><span data-stu-id="301b3-124">Missed call notification (Mcx)</span></span>

  - <span data-ttu-id="301b3-125">ボイス オーバー IP (VoIP)</span><span class="sxs-lookup"><span data-stu-id="301b3-125">Voice over IP (VoIP)</span></span>

  - <span data-ttu-id="301b3-126">出席者のビデオ (H.264)</span><span class="sxs-lookup"><span data-stu-id="301b3-126">Attendee video (H.264)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="301b3-127">Lync 2010 Mobile では、Nokia Symbian デバイス用のクライアントが用意されています。</span><span class="sxs-lookup"><span data-stu-id="301b3-127">Lync 2010 Mobile provided a client for Nokia Symbian devices.</span></span> <span data-ttu-id="301b3-128">Lync 2013 Mobile には、Nokia Symbian ベースのデバイスのクライアントはありません。</span><span class="sxs-lookup"><span data-stu-id="301b3-128">Lync 2013 Mobile will not have a client for Nokia Symbian-based devices.</span></span>



</div>

<span data-ttu-id="301b3-129">Apple iPad ユーザーは、強化された機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="301b3-129">Apple iPad users will have access to enhanced capabilities.</span></span> <span data-ttu-id="301b3-130">音声通話を使用して会議に参加した後、iPad ユーザーは、会議中にアップロードされた Microsoft PowerPoint プレゼンテーションを表示したり、アプリケーションとデスクトップを共有したり、会議参加者リストを表示したり、他のコンテンツタイプの通知を受信したりすることができます。会議内で共有されている。</span><span class="sxs-lookup"><span data-stu-id="301b3-130">After joining a meeting by using audio call back, an iPad user will be able to view uploaded Microsoft PowerPoint presentations within a meeting, share applications and desktops, view the meeting participant list, and receive notifications of other content types that are being shared within the meeting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="301b3-131">1つの番号に到達すると、勤務先の電話番号にダイヤルされた携帯電話で着信を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="301b3-131">With single number reach, a user receives calls on a mobile phone that were dialed to the work number.</span></span> <span data-ttu-id="301b3-132">勤務先からの通話では、ユーザーは携帯電話番号ではなく勤務先の電話番号を使用して、Lync モバイルクライアントから発信通話を発信します。</span><span class="sxs-lookup"><span data-stu-id="301b3-132">With Call via Work, the user places an outbound call from the Lync Mobile client by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="301b3-133">ダイヤルアウトの場合、クライアントは Mcx または UCWA (Lync モバイルバージョンに基づく) に要求を送信して、通話を発信します。</span><span class="sxs-lookup"><span data-stu-id="301b3-133">With dial-out, the client sends a request to Mcx or UCWA (based on the Lync Mobile version) to make the call for them.</span></span> <span data-ttu-id="301b3-134">サーバーによって通話が開始され、携帯電話に発信されます。</span><span class="sxs-lookup"><span data-stu-id="301b3-134">The server initiates the call and then calls the user back on the mobile phone.</span></span> <span data-ttu-id="301b3-135">ユーザーが応答すると、相手にダイヤルすることによってサーバーが通話を完了します。</span><span class="sxs-lookup"><span data-stu-id="301b3-135">When the user answers, the server completes the call by dialing the other party.</span></span> <span data-ttu-id="301b3-136">勤務先から通話を使用することで、ユーザーは通話中に作業の id を保持することができます。つまり、通話の受信者には発信者の携帯電話番号が表示されず、発信者は発信通話料金を伴わなくなります。</span><span class="sxs-lookup"><span data-stu-id="301b3-136">By using Call via Work, users can maintain their work identity during a call, which means that the call recipient does not see the caller's mobile number, and the caller avoids incurring outbound calling charges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="301b3-137">すべての機能が、すべてのモバイルデバイスでまったく同じであるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="301b3-137">Not all features work exactly the same on all mobile devices.</span></span> <span data-ttu-id="301b3-138">モバイルデバイスでサポートされている機能の詳細については、 <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>のモバイルクライアントの比較表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="301b3-138">For details about features supported on mobile devices, see the Mobile Client Comparison Tables at <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>.</span></span> <span data-ttu-id="301b3-139">サポートされているデバイスとオペレーティングシステムの詳細については、「 <A href="lync-server-2013-planning-for-mobile-clients.md">Lync Server 2013 のモバイルクライアントの計画</A>」の要件に関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="301b3-139">For details about supported devices and operating systems, see the requirements topics under <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for mobile clients in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="301b3-140">Lync Server 2013 自動検出機能を使用すると、モバイルアプリケーションは、ユーザーがデバイスの設定で Url を手動で入力する必要なく、Lync Server 2013 Web サービスを自動的に見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="301b3-140">When you use the Lync Server 2013 Autodiscover feature, mobile applications can automatically locate Lync Server 2013 Web Services without requiring users to manually enter the URLs in their device settings.</span></span> <span data-ttu-id="301b3-141">モバイルデバイスの設定では、手動での Url の入力もサポートされます。主にトラブルシューティングを目的としています。</span><span class="sxs-lookup"><span data-stu-id="301b3-141">Manually entering URLs in mobile device settings is also supported, primarily for troubleshooting purposes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="301b3-142">Mcx と UCWA は、無料サービスであり、両方とも Lync 2010 Mobile および Lync 2013 モバイルクライアントをサポートするために展開されています。</span><span class="sxs-lookup"><span data-stu-id="301b3-142">The Mcx and UCWA are complimentary services and both are deployed to support Lync 2010 Mobile and Lync 2013 Mobile clients.</span></span> <span data-ttu-id="301b3-143">Lync 2013 Mobile では、Lync Server 2010 の展開にサインインすることはできません。</span><span class="sxs-lookup"><span data-stu-id="301b3-143">Lync 2013 Mobile will not be able to sign in to Lync Server 2010 deployments.</span></span> <span data-ttu-id="301b3-144">Lync 2010 Mobile および Lync 2013 Mobile では、lync server 2013 の累積更新プログラムで Lync Server 2013 の展開を使用できるようになります。2月2013適用されています。</span><span class="sxs-lookup"><span data-stu-id="301b3-144">Lync 2010 Mobile and Lync 2013 Mobile will be able to use a Lync Server 2013 deployment with the Cumulative Updates for Lync Server 2013: February 2013 applied.</span></span>



</div>

<span data-ttu-id="301b3-145">モビリティ機能では、バックグラウンドで実行されているアプリケーションをサポートしないモバイル デバイス用の*プッシュ通知*もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="301b3-145">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="301b3-146">プッシュ通知は、モバイル アプリケーションが非アクティブなときに発生したイベントについてモバイル デバイスに送信される通知です。</span><span class="sxs-lookup"><span data-stu-id="301b3-146">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span> <span data-ttu-id="301b3-147">たとえば、不在着信したインスタントメッセージング (IM) 招待は、プッシュ通知につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="301b3-147">For example, a missed instant messaging (IM) invitation can result in a push notification.</span></span>

<span data-ttu-id="301b3-148">Mcx、UCWA、自動検出サービス、およびプッシュ通知のサポートについては、「Lync Server 2013」をご利用ください。</span><span class="sxs-lookup"><span data-stu-id="301b3-148">Mcx, UCWA, Autodiscover Service, and support for push notifications are provided in Lync Server 2013.</span></span> <span data-ttu-id="301b3-149">更新されたクライアント機能、機能、および UCWA の使用は、モビリティーエントリポイントが Lync Server 2013 の累積更新プログラムで導入されています (2013 年2月)。</span><span class="sxs-lookup"><span data-stu-id="301b3-149">Updated client features, capabilities, and the use of UCWA as the mobility entry point are introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

