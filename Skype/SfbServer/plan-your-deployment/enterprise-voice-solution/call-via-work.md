---
title: Skype ビジネス サーバーの作業時間を使用して呼び出すのための計画
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: ビジネス サーバーの Skype の呼び出しを使用して作業の計画、できます Skype のビジネスとお使いの PBX 電話システムとの統合ユーザーは、PBX 電話を制御するビジネス用の Skype を使用できるようにします。
ms.openlocfilehash: 3a2452f732d55f305d91cee9cd2b940f7bb3c88e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207245"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="46231-103">Skype ビジネス サーバーの作業時間を使用して呼び出すのための計画</span><span class="sxs-lookup"><span data-stu-id="46231-103">Plan for Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="46231-104">ビジネス サーバーの Skype の呼び出しを使用して作業の計画、できます Skype のビジネスとお使いの PBX 電話システムとの統合ユーザーは、PBX 電話を制御するビジネス用の Skype を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="46231-104">Planning for Call Via Work in Skype for Business Server, which enables integration between Skype for Business and your PBX phone system, so that users can use Skype for Business to control their PBX phones.</span></span>
  
 <span data-ttu-id="46231-105">**作業の呼び出しで**は、ビジネス サーバー ビジネス ソリューションは、Skype を既存の PBX 電話システムと統合するための Skype の新機能です。</span><span class="sxs-lookup"><span data-stu-id="46231-105">**Call Via Work** is a new feature in Skype for Business Server which enables you to integrate your Skype for Business solution with your existing PBX phone systems.</span></span> <span data-ttu-id="46231-106">ビジネスでの展開、または外部のユーザーであっても、他のユーザーを呼び出す Skype の呼び出しを使用して有効になっているユーザーことができますをクリックします。</span><span class="sxs-lookup"><span data-stu-id="46231-106">A user enabled for Call Via Work can click in Skype for Business to call another user, either within your deployment or an external user.</span></span> <span data-ttu-id="46231-107">この通話は、ユーザーの PBX 電話を使用して実現されます。</span><span class="sxs-lookup"><span data-stu-id="46231-107">The call is completed using the user's PBX phone.</span></span> <span data-ttu-id="46231-108">これにより、PBX 電話を持つユーザーのビジネス会話の豊富な Skype のオーディオが含まれます。</span><span class="sxs-lookup"><span data-stu-id="46231-108">This enables a user with a PBX phone to include audio in their rich Skype for Business conversations.</span></span> <span data-ttu-id="46231-109">Lync Server のリモート呼び出しの以前のバージョンでは、コントロールは、Lync Server は PBX 電話を制御するユーザーを有効にする機能でした。</span><span class="sxs-lookup"><span data-stu-id="46231-109">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="46231-110">ビジネス サーバーの Skype は、この機能は作業時間を使用して呼び出しを交換済み。</span><span class="sxs-lookup"><span data-stu-id="46231-110">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>
  
<span data-ttu-id="46231-111">作業を使用して呼び出しが PBX 電話ユーザーは、次を有効に</span><span class="sxs-lookup"><span data-stu-id="46231-111">Call Via Work enables the following for PBX phone users</span></span>
  
- <span data-ttu-id="46231-112">PBX 電話で提供される音声を使用した、クリック通話操作。</span><span class="sxs-lookup"><span data-stu-id="46231-112">Click-to-call experience, with the audio provided through the PBX phone.</span></span>
    
- <span data-ttu-id="46231-113">存在、ユーザーの検索、および IM の統合-などの IM セッションの 2 つの作業の呼び出しを使用してユーザーに追加できますオーディオのセッションでは、PBX 電話を介して提供されるオーディオ。</span><span class="sxs-lookup"><span data-stu-id="46231-113">Presence, user search, and IM integration-- for example, two Call Via Work users in an IM session can add audio to their session, with the audio provided through the PBX phones.</span></span>
    
- <span data-ttu-id="46231-114">作業を使用して呼び出しの呼び出しに、IM、アプリケーション共有、およびファイル転送を追加する機能。</span><span class="sxs-lookup"><span data-stu-id="46231-114">The ability to add IM, application sharing, and file transfer to a Call Via Work call.</span></span>
    
- <span data-ttu-id="46231-115">ワンクリックでの会議参加機能</span><span class="sxs-lookup"><span data-stu-id="46231-115">One-click meeting join capability</span></span>
    
## <a name="how-it-works"></a><span data-ttu-id="46231-116">メカニズム</span><span class="sxs-lookup"><span data-stu-id="46231-116">How it works</span></span>

<span data-ttu-id="46231-117">作業の呼び出しを使用してユニファイド コミュニケーション Web API (UCWA) ように、使用して、バック ツー バック ユーザー エージェント (B2BUA)、PBX システムと、Skype のビジネス サーバー展開では、通信のコンピューターでサポートされているアプリケーション (csta によって実現) ゲートウェイが接続する必要はありません。PBX システムとビジネスのサーバーの Skype です。</span><span class="sxs-lookup"><span data-stu-id="46231-117">Call Via Work uses Unified Communications Web API (UCWA) as the back-to-back user agent (B2BUA) between the PBX system and your Skype for Business Server deployment, so that no computer-supported telecommunications application (CSTA) gateway is needed to connect Skype for Business Server with your PBX system.</span></span> <span data-ttu-id="46231-118">UCWA 携帯との接続と、web クライアントを有効にする Lync Server の以前のバージョンで導入されたサービスは、各フロント エンド サーバーに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="46231-118">UCWA is a service introduced in previous versions of Lync Server to enable connectivity with mobile and web clients, and is automatically installed on every Front End Server.</span></span>
  
### <a name="call-workflow-for-a-call-via-work-call"></a><span data-ttu-id="46231-119">作業を使用して呼び出しの呼び出しのワークフローを呼び出す</span><span class="sxs-lookup"><span data-stu-id="46231-119">Call workflow for a Call Via Work call</span></span>

<span data-ttu-id="46231-120">作業を使用して呼び出しを有効になっているユーザーが呼び出しを実行するビジネス サーバーの Skype を使用する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="46231-120">The following illustrates how a user enabled for Call Via Work can use the Skype for Business Server to make a call:</span></span>
  
!["勤務先から通話" の通話中のステップを示しています。まず、発信者が Skype for Business クライアントで誰かにクリックで発信し、次に、UCWA が発信者の電話を鳴らします。発信者が電話を取ると、受信者が呼び出されます](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. <span data-ttu-id="46231-123">ユーザーでは、ビジネスのクライアントに、Skype でユーザーを選択し、それらを呼び出すため、電話のアイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="46231-123">The user selects a user in their Skype for Business client, and clicks the phone icon to call them.</span></span> <span data-ttu-id="46231-124">または、IM 会話中にクリックして、セッションを共有しているユーザーに電話をかけます。</span><span class="sxs-lookup"><span data-stu-id="46231-124">Or, during an IM conversation, the user clicks to call the user they are having the session with.</span></span>
    
2. <span data-ttu-id="46231-125">電話をかけたユーザーの PBX 電話が呼び出しを開始します。</span><span class="sxs-lookup"><span data-stu-id="46231-125">The PBX phone of the user who placed the call starts to ring.</span></span> <span data-ttu-id="46231-126">この電話の発信者番号は、作業を使用して呼び出しの呼び出しを配置するすべてのユーザーの発信者番号の表示に設定したグローバルな電話番号を示しています。</span><span class="sxs-lookup"><span data-stu-id="46231-126">The caller ID for this phone shows a global phone number which you have set up to show in the caller ID of all users placing Call Via Work calls.</span></span> <span data-ttu-id="46231-127">このグローバル電話番号は、個人の電話に応じた実際の電話番号ではありません。</span><span class="sxs-lookup"><span data-stu-id="46231-127">This global phone number is not an actual phone number that corresponds to any one person's phone.</span></span> <span data-ttu-id="46231-128">これは、ユーザー自身が発信した電話であり、着信ではないことを同時に相手に知らせる視覚的信号です。</span><span class="sxs-lookup"><span data-stu-id="46231-128">Instead, it is a visual signal to let a user know that this is their own outgoing call, and not an incoming call happening at the same time.</span></span> <span data-ttu-id="46231-129">作業を通じて呼び出しを配置するときは、このグローバルな電話番号とその意味について、それらのユーザーを教育する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46231-129">When you deploy Call Via Work, you should educate those users about this global phone number and what it means.</span></span>
    
3. <span data-ttu-id="46231-130">電話をかけたユーザーは自分の PBX 電話を取ります。</span><span class="sxs-lookup"><span data-stu-id="46231-130">The user who placed the call picks up their PBX phone.</span></span> <span data-ttu-id="46231-131">ビジネス用の Skype は、呼び出し先に音声通話を開始します。</span><span class="sxs-lookup"><span data-stu-id="46231-131">Skype for Business then initiates the voice call to the callee.</span></span> 
    
4. <span data-ttu-id="46231-p107">呼び出し先が応答すると、音声通話が開始します。2 人のユーザーが既に IM セッションを開始している場合は、これを継続できます。</span><span class="sxs-lookup"><span data-stu-id="46231-p107">When the callee answers, the voice call begins. If the two users already had an IM session going, it can continue.</span></span>
    
### <a name="joining-a-conference-with-call-via-work"></a><span data-ttu-id="46231-134">"勤務先から通話" を使用した会議への参加</span><span class="sxs-lookup"><span data-stu-id="46231-134">Joining a Conference With Call Via Work</span></span>

<span data-ttu-id="46231-135">作業を使用して呼び出すユーザーは、会議 URL をクリックしてスケジュールされたミーティングに参加できます。</span><span class="sxs-lookup"><span data-stu-id="46231-135">A Call Via Work user can join a scheduled meeting by clicking the meeting URL.</span></span> <span data-ttu-id="46231-136">ビジネス用の Skype**に**メッセージが会議サービスは、ユーザーの PBX 電話をダイヤルするまで表示されます。</span><span class="sxs-lookup"><span data-stu-id="46231-136">Skype for Business then shows a **Dialing out to** message until the meeting service dials the user's PBX phone.</span></span> <span data-ttu-id="46231-137">作業を使用して呼び出すユーザーは、PBX 電話をピックアップし、ミーティングに参加します。</span><span class="sxs-lookup"><span data-stu-id="46231-137">The Call Via Work user then picks up the PBX phone and joins the meeting.</span></span>
  
<span data-ttu-id="46231-138">作業の呼び出しを使用してユーザーも使用できます**即時会議**のオプションでビジネス用の Skype Meet Now ミーティングを作成します。</span><span class="sxs-lookup"><span data-stu-id="46231-138">A Call Via Work user can also use the **Meet Now** option in Skype for Business to create Meet Now meetings.</span></span> <span data-ttu-id="46231-139">続いてユーザーに「**〜さんにダイヤルしています**」というメッセージが表示され、PBX 電話が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="46231-139">The user then sees the **Dialing out to** message, and the PBX phone rings.</span></span>
  
<span data-ttu-id="46231-140">作業の呼び出しを使用してユーザーもダイヤルイン会議にビジネスの Skype 内から会議ブリッジの番号を呼び出すことでできます。</span><span class="sxs-lookup"><span data-stu-id="46231-140">A Call Via Work user can also dial in to a meeting by calling the Conference Bridge number from within Skype for Business.</span></span> <span data-ttu-id="46231-141">会議 PIN が必要な場合、ユーザーはその PBX 電話を使用して、PIN を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46231-141">If a conference PIN is required, the user must use their PBX phone to input the PIN.</span></span>
  
### <a name="incoming-calls"></a><span data-ttu-id="46231-142">着信通話</span><span class="sxs-lookup"><span data-stu-id="46231-142">Incoming Calls</span></span>

<span data-ttu-id="46231-143">ユーザーに対して有効にすると作業時間を使用して呼び出すビジネス クライアントが同時に (ユーザーが設定する場合同時呼び出し) をリングのすべてのビジネス電話、PBX 電話ユーザーの Skype、Skype を受信します。</span><span class="sxs-lookup"><span data-stu-id="46231-143">When a user enabled for Call Via Work receives a Skype for Business call, the PBX phone and the user's Skype for Business clients all ring simultaneously (if the user has set up simultaneous ring).</span></span> <span data-ttu-id="46231-144">ユーザーは、PBX 電話をかけるか、ビジネスの通知を Skype で**受信を許可**] をクリックするか、呼び出しを受け入れることができます。</span><span class="sxs-lookup"><span data-stu-id="46231-144">The user can accept the call either by picking up the PBX phone or clicking **Accept** on the Skype for Business notification.</span></span> <span data-ttu-id="46231-145">ユーザーは、ビジネスの Skype を使用して呼び出しを受け入れる場合、Skype の呼び出しの「ビジネス」ウィンドウは開いたままです。</span><span class="sxs-lookup"><span data-stu-id="46231-145">If the user accepts the call using Skype for Business, the Skype for Business window for the call stays open.</span></span> <span data-ttu-id="46231-146">PBX 電話をかけることによって、ユーザーが呼び出しを受け入れると場合、ビジネスの通知ウィンドウの Skype を終了し、ビジネス セッションでは、PBX 電話で音声通話のみ Skype はありません。</span><span class="sxs-lookup"><span data-stu-id="46231-146">But if the user accepts the call by picking up the PBX phone, then the Skype for Business notification window closes and there is no Skype for Business session, only the voice call over the PBX phone.</span></span>
  
<span data-ttu-id="46231-147">作業時間を使用して呼び出しを有効になっているユーザーは、PBX 電話、PBX 電話が鳴るだけを受信します。</span><span class="sxs-lookup"><span data-stu-id="46231-147">When a user enabled for Call Via Work receives a PBX call, only the PBX phone rings.</span></span>
  
## <a name="limitations-of-call-via-work"></a><span data-ttu-id="46231-148">作業を使用して呼び出しの制限事項</span><span class="sxs-lookup"><span data-stu-id="46231-148">Limitations of Call Via Work</span></span>

<span data-ttu-id="46231-149">作業による呼び出しは、ほとんどのハードウェアの設定をする必要がありますが、すべてのエンタープライズ VoIP またはリモート通話コントロールで利用できる機能と比較して制限する音声ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="46231-149">Call Via Work is a voice solution that requires little hardware setup, but has limitations compared to the features available in full Enterprise Voice or remote call control.</span></span> <span data-ttu-id="46231-150">作業を使用して呼び出すには、次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="46231-150">Call Via Work has the following limitations:</span></span>
  
- <span data-ttu-id="46231-151">作業の呼び出しを使用してユーザーに作業を使用して呼び出すコールバック番号に自動転送が設定されて場合、このユーザーはユーザーの電話番号を会議に招待しようとしています。 招待状はユーザーがアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="46231-151">If a Call Via Work user has set up call forwarding to the Call Via Work callback number, and someone tries to invite this user to a meeting by the user's phone number, the invitation will not reach the user.</span></span> <span data-ttu-id="46231-152">参加者を会議に招待するには、電話番号ではなく名前をクリックするように、ユーザーに伝える必要があります。</span><span class="sxs-lookup"><span data-stu-id="46231-152">You should educate your users to invite participants to meetings by clicking the name, not the phone number.</span></span> 
    
- <span data-ttu-id="46231-153">911 機能が拡張され、悪意のある呼び出しのトレースは、作業時間を使用して呼び出しの呼び出し時に使用できません。</span><span class="sxs-lookup"><span data-stu-id="46231-153">Enhanced 911 capability and malicious call tracing are not available during Call Via Work calls.</span></span>
    
- <span data-ttu-id="46231-154">作業を使用して呼び出しが有効なユーザーは、委任、チーム呼び出し、または応答グループの機能を使用できません。</span><span class="sxs-lookup"><span data-stu-id="46231-154">Users enabled for Call Via Work cannot use the delegation, team call, or response group features.</span></span>
    
- <span data-ttu-id="46231-155">ユーザーの作業を使用して呼び出すは、ミュート、ミーティングを記録または通話のミュートを解除、保持または、電話を転送またはコール パークを使用するビジネス用の Skype を使用できません。</span><span class="sxs-lookup"><span data-stu-id="46231-155">Users of Call Via Work cannot use Skype for Business to record a meeting, mute or unmute the call, hold or transfer the call, or use call park.</span></span>
    
- <span data-ttu-id="46231-156">ユーザーは、PBX のボイスメール メッセージにアクセスするのに作業を使用して呼び出しを使用できません。</span><span class="sxs-lookup"><span data-stu-id="46231-156">Users cannot use Call Via Work to access their PBX voicemail messages.</span></span>
    
- <span data-ttu-id="46231-157">作業を使用して呼び出しのユーザーと音声通話、ビデオ、Powerpoint では、ホワイト ボードなどの通信や 1 つのメモを含む共同会議を開始したセッション エスカレートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="46231-157">Users of Call Via Work cannot escalate a session that started as a voice call to a collaborative meeting that includes communications such as video, Powerpoint, whiteboard, or One Note.</span></span>
    
- <span data-ttu-id="46231-158">ユーザーの作業を使用して呼び出すのでは、2 人の呼び出しをより多くのユーザーを追加できません。</span><span class="sxs-lookup"><span data-stu-id="46231-158">Users of Call Via Work cannot add more users to a 2-person call.</span></span>
    
- <span data-ttu-id="46231-159">卓上電話のペアリングまたは VDI プラグイン ペアリングをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="46231-159">No support for deskphone pairing or VDI plugin pairing.</span></span>
    
- <span data-ttu-id="46231-160">ユーザーは、または、呼び出しの PBX 電話を使用する (としない、Skype ウィンドウを使用してビジネス) は、呼び出しのログされません。</span><span class="sxs-lookup"><span data-stu-id="46231-160">If a user makes or answers a call using the PBX phone (and not using the Skype for Business window), there will be no log of the call.</span></span>
    
- <span data-ttu-id="46231-161">PBX システムが **REFER with Replaces** をサポートしていない場合は、次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="46231-161">If your PBX system does not support **REFER with Replaces**, the following behavior will happen.</span></span> <span data-ttu-id="46231-162">作業の呼び出しを使用して呼び出し、ユーザーは、PBX 電話から継続的な呼び出しを転送する場合、使用時に通話ウィンドウ非表示になりませんから、Skype をビジネスのウィンドウの。</span><span class="sxs-lookup"><span data-stu-id="46231-162">While on a Call Via Work call, if the user transfers the ongoing call from the PBX Phone, the call window will not disappear from their Skype for Business window.</span></span> <span data-ttu-id="46231-163">ユーザーが通話ウィンドウを閉じると、転送先との間の通話が終了します。</span><span class="sxs-lookup"><span data-stu-id="46231-163">If the user then closes the call window, the call between the transfer target and the transferee will end.</span></span> 
    
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="46231-164">作業を使用して呼び出すのための前提条件</span><span class="sxs-lookup"><span data-stu-id="46231-164">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="46231-165">作業による呼び出しですべてのユーザーを有効にするのには、場所にいくつかの前提条件が必要です。</span><span class="sxs-lookup"><span data-stu-id="46231-165">To enable any users for Call Via Work, you must have some pre-requisites in place.</span></span> <span data-ttu-id="46231-166">これらの必要条件の詳細については、作業時間を使用して呼び出すためのユーザーを有効にする方法の手順については、[展開の呼び出しを使用して作業ビジネス サーバー 2015 の Skype で](../../deploy/deploy-call-via-work.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46231-166">For more information on these prerequisites, and for steps on how to enable users for Call Via Work, see [Deploy Call Via Work in Skype for Business Server 2015](../../deploy/deploy-call-via-work.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="46231-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="46231-167">See also</span></span>

[<span data-ttu-id="46231-168">ビジネス用の Skype でのリモート通話コントロールの計画</span><span class="sxs-lookup"><span data-stu-id="46231-168">Plan for remote call control in Skype for Business</span></span>](remote-call-control.md)
  
[<span data-ttu-id="46231-169">Skype for Business Server 2015 での "勤務先から通話" の展開</span><span class="sxs-lookup"><span data-stu-id="46231-169">Deploy Call Via Work in Skype for Business Server 2015</span></span>](../../deploy/deploy-call-via-work.md)

