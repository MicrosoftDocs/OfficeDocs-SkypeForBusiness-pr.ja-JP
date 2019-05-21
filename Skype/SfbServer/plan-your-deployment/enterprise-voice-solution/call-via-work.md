---
title: Skype for Business Server での勤務先での通話の計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: Skype for business Server を使った skype for business Server での通話の計画。 skype for business と PBX 電話システムとの統合を有効にし、ユーザーが Skype for Business を使用して PBX 電話を制御できるようにします。
ms.openlocfilehash: b2f0e57a33f6e194dc981b623a641850ed3c8de5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277028"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="47bbc-103">Skype for Business Server での勤務先での通話の計画</span><span class="sxs-lookup"><span data-stu-id="47bbc-103">Plan for Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="47bbc-104">Skype for business Server を使った skype for business Server での通話の計画。 skype for business と PBX 電話システムとの統合を有効にし、ユーザーが Skype for Business を使用して PBX 電話を制御できるようにします。</span><span class="sxs-lookup"><span data-stu-id="47bbc-104">Planning for Call Via Work in Skype for Business Server, which enables integration between Skype for Business and your PBX phone system, so that users can use Skype for Business to control their PBX phones.</span></span>
  
 <span data-ttu-id="47bbc-105">[勤務先での**通話**は、Skype For business Server の新機能です。 skype for business ソリューションと既存の PBX 電話システムとの統合を可能にします。</span><span class="sxs-lookup"><span data-stu-id="47bbc-105">**Call Via Work** is a new feature in Skype for Business Server which enables you to integrate your Skype for Business solution with your existing PBX phone systems.</span></span> <span data-ttu-id="47bbc-106">勤務先からの通話が有効になっているユーザーは、[Skype for Business] をクリックして、展開または外部ユーザーのいずれかで別のユーザーに電話をかけることができます。</span><span class="sxs-lookup"><span data-stu-id="47bbc-106">A user enabled for Call Via Work can click in Skype for Business to call another user, either within your deployment or an external user.</span></span> <span data-ttu-id="47bbc-107">この通話は、ユーザーの PBX 電話を使用して実現されます。</span><span class="sxs-lookup"><span data-stu-id="47bbc-107">The call is completed using the user's PBX phone.</span></span> <span data-ttu-id="47bbc-108">これにより、PBX 電話を使用するユーザーは、豊富な Skype for Business の会話に音声を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="47bbc-108">This enables a user with a PBX phone to include audio in their rich Skype for Business conversations.</span></span> <span data-ttu-id="47bbc-109">以前のバージョンの Lync Server リモート通話コントロールは、ユーザーが Lync Server を使って PBX 電話を制御できるようにする機能です。</span><span class="sxs-lookup"><span data-stu-id="47bbc-109">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="47bbc-110">Skype for Business Server では、この機能は勤務先からの通話に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="47bbc-110">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>
  
<span data-ttu-id="47bbc-111">勤務先での通話 PBX 電話のユーザーに対して次の機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="47bbc-111">Call Via Work enables the following for PBX phone users</span></span>
  
- <span data-ttu-id="47bbc-112">PBX 電話で提供される音声を使用した、クリック通話操作。</span><span class="sxs-lookup"><span data-stu-id="47bbc-112">Click-to-call experience, with the audio provided through the PBX phone.</span></span>
    
- <span data-ttu-id="47bbc-113">プレゼンス、ユーザー検索、IM の統合: たとえば、IM セッションで [勤務先] の2回の通話では、PBX 電話経由で提供されたオーディオを使って、そのセッションに音声を追加できます。</span><span class="sxs-lookup"><span data-stu-id="47bbc-113">Presence, user search, and IM integration-- for example, two Call Via Work users in an IM session can add audio to their session, with the audio provided through the PBX phones.</span></span>
    
- <span data-ttu-id="47bbc-114">通話に IM、アプリケーション共有、ファイル転送を追加する機能。</span><span class="sxs-lookup"><span data-stu-id="47bbc-114">The ability to add IM, application sharing, and file transfer to a Call Via Work call.</span></span>
    
- <span data-ttu-id="47bbc-115">ワンクリックでの会議参加機能</span><span class="sxs-lookup"><span data-stu-id="47bbc-115">One-click meeting join capability</span></span>
    
## <a name="how-it-works"></a><span data-ttu-id="47bbc-116">メカニズム</span><span class="sxs-lookup"><span data-stu-id="47bbc-116">How it works</span></span>

<span data-ttu-id="47bbc-117">[勤務先での通話] PBX システムと Skype for Business Server の展開の間のバックツーバックユーザーエージェント (B2BUA) としてユニファイドコミュニケーション Web API (UCWA) を使用します。これにより、コンピューターでサポートされている通信アプリケーション (CSTA) ゲートウェイは接続する必要がなくなります。お使いの PBX システムを搭載した Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="47bbc-117">Call Via Work uses Unified Communications Web API (UCWA) as the back-to-back user agent (B2BUA) between the PBX system and your Skype for Business Server deployment, so that no computer-supported telecommunications application (CSTA) gateway is needed to connect Skype for Business Server with your PBX system.</span></span> <span data-ttu-id="47bbc-118">UCWA は、モバイルおよび web クライアントとの接続を可能にするために、以前のバージョンの Lync Server で導入されたサービスであり、すべてのフロントエンドサーバーに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="47bbc-118">UCWA is a service introduced in previous versions of Lync Server to enable connectivity with mobile and web clients, and is automatically installed on every Front End Server.</span></span>
  
### <a name="call-workflow-for-a-call-via-work-call"></a><span data-ttu-id="47bbc-119">勤務先から通話のワークフローを呼び出す</span><span class="sxs-lookup"><span data-stu-id="47bbc-119">Call workflow for a Call Via Work call</span></span>

<span data-ttu-id="47bbc-120">次の例は、勤務先のユーザーが Skype for Business Server を使って通話を発信する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="47bbc-120">The following illustrates how a user enabled for Call Via Work can use the Skype for Business Server to make a call:</span></span>
  
!["勤務先から通話" の通話中のステップを示しています。まず、発信者が Skype for Business クライアントで誰かにクリックで発信し、次に、UCWA が発信者の電話を鳴らします。発信者が電話を取ると、受信者が呼び出されます](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. <span data-ttu-id="47bbc-123">ユーザーは、Skype for Business クライアントでユーザーを選択し、電話のアイコンをクリックして通話を発信します。</span><span class="sxs-lookup"><span data-stu-id="47bbc-123">The user selects a user in their Skype for Business client, and clicks the phone icon to call them.</span></span> <span data-ttu-id="47bbc-124">または、IM 会話中にクリックして、セッションを共有しているユーザーに電話をかけます。</span><span class="sxs-lookup"><span data-stu-id="47bbc-124">Or, during an IM conversation, the user clicks to call the user they are having the session with.</span></span>
    
2. <span data-ttu-id="47bbc-125">電話をかけたユーザーの PBX 電話が呼び出しを開始します。</span><span class="sxs-lookup"><span data-stu-id="47bbc-125">The PBX phone of the user who placed the call starts to ring.</span></span> <span data-ttu-id="47bbc-126">この電話の発信者番号は、[勤務先] で通話を発信しているすべてのユーザーの発信者番号認識に設定したグローバル電話番号を示しています。</span><span class="sxs-lookup"><span data-stu-id="47bbc-126">The caller ID for this phone shows a global phone number which you have set up to show in the caller ID of all users placing Call Via Work calls.</span></span> <span data-ttu-id="47bbc-127">このグローバル電話番号は、個人の電話に応じた実際の電話番号ではありません。</span><span class="sxs-lookup"><span data-stu-id="47bbc-127">This global phone number is not an actual phone number that corresponds to any one person's phone.</span></span> <span data-ttu-id="47bbc-128">これは、ユーザー自身が発信した電話であり、着信ではないことを同時に相手に知らせる視覚的信号です。</span><span class="sxs-lookup"><span data-stu-id="47bbc-128">Instead, it is a visual signal to let a user know that this is their own outgoing call, and not an incoming call happening at the same time.</span></span> <span data-ttu-id="47bbc-129">職場で通話を展開する場合は、このグローバル電話番号とその意味についてユーザーを教育する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bbc-129">When you deploy Call Via Work, you should educate those users about this global phone number and what it means.</span></span>
    
3. <span data-ttu-id="47bbc-130">電話をかけたユーザーは自分の PBX 電話を取ります。</span><span class="sxs-lookup"><span data-stu-id="47bbc-130">The user who placed the call picks up their PBX phone.</span></span> <span data-ttu-id="47bbc-131">次に、Skype for Business から呼び出し先への音声通話が開始されます。</span><span class="sxs-lookup"><span data-stu-id="47bbc-131">Skype for Business then initiates the voice call to the callee.</span></span> 
    
4. <span data-ttu-id="47bbc-p107">呼び出し先が応答すると、音声通話が開始します。2 人のユーザーが既に IM セッションを開始している場合は、これを継続できます。</span><span class="sxs-lookup"><span data-stu-id="47bbc-p107">When the callee answers, the voice call begins. If the two users already had an IM session going, it can continue.</span></span>
    
### <a name="joining-a-conference-with-call-via-work"></a><span data-ttu-id="47bbc-134">"勤務先から通話" を使用した会議への参加</span><span class="sxs-lookup"><span data-stu-id="47bbc-134">Joining a Conference With Call Via Work</span></span>

<span data-ttu-id="47bbc-135">職場ユーザーからの通話は、会議の URL をクリックして、スケジュールされた会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="47bbc-135">A Call Via Work user can join a scheduled meeting by clicking the meeting URL.</span></span> <span data-ttu-id="47bbc-136">Skype for Business は、会議サービスがユーザーの PBX 電話にダイヤルするまで、メッセージ**へのダイヤルアウト**を示します。</span><span class="sxs-lookup"><span data-stu-id="47bbc-136">Skype for Business then shows a **Dialing out to** message until the meeting service dials the user's PBX phone.</span></span> <span data-ttu-id="47bbc-137">職場ユーザーからの通話は、PBX 電話を選び、会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="47bbc-137">The Call Via Work user then picks up the PBX phone and joins the meeting.</span></span>
  
<span data-ttu-id="47bbc-138">職場ユーザーからの通話では、Skype for Business の [**今すぐ会議**] オプションを使用して、[今すぐ会議] 会議を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="47bbc-138">A Call Via Work user can also use the **Meet Now** option in Skype for Business to create Meet Now meetings.</span></span> <span data-ttu-id="47bbc-139">続いてユーザーに「**〜さんにダイヤルしています**」というメッセージが表示され、PBX 電話が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="47bbc-139">The user then sees the **Dialing out to** message, and the PBX phone rings.</span></span>
  
<span data-ttu-id="47bbc-140">職場ユーザーからの通話では、Skype for Business 内から会議ブリッジ番号に電話をかけて会議にダイヤルインすることもできます。</span><span class="sxs-lookup"><span data-stu-id="47bbc-140">A Call Via Work user can also dial in to a meeting by calling the Conference Bridge number from within Skype for Business.</span></span> <span data-ttu-id="47bbc-141">会議 PIN が必要な場合、ユーザーはその PBX 電話を使用して、PIN を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bbc-141">If a conference PIN is required, the user must use their PBX phone to input the PIN.</span></span>
  
### <a name="incoming-calls"></a><span data-ttu-id="47bbc-142">着信通話</span><span class="sxs-lookup"><span data-stu-id="47bbc-142">Incoming Calls</span></span>

<span data-ttu-id="47bbc-143">ユーザーが [勤務先からの通話] を有効にすると、Skype for Business の通話が受信され、PBX 電話とユーザーの Skype for Business クライアントがすべて同時に着信します (ユーザーが同時呼び出しを設定している場合)。</span><span class="sxs-lookup"><span data-stu-id="47bbc-143">When a user enabled for Call Via Work receives a Skype for Business call, the PBX phone and the user's Skype for Business clients all ring simultaneously (if the user has set up simultaneous ring).</span></span> <span data-ttu-id="47bbc-144">ユーザーは、PBX 電話を選ぶか、Skype for Business の通知で [**承諾**] をクリックすることで、通話を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="47bbc-144">The user can accept the call either by picking up the PBX phone or clicking **Accept** on the Skype for Business notification.</span></span> <span data-ttu-id="47bbc-145">ユーザーが Skype for Business を使って通話を受け入れた場合、通話の Skype for business ウィンドウは開いたままになります。</span><span class="sxs-lookup"><span data-stu-id="47bbc-145">If the user accepts the call using Skype for Business, the Skype for Business window for the call stays open.</span></span> <span data-ttu-id="47bbc-146">ただし、ユーザーが PBX 電話を使って通話を受けた場合は、Skype for Business の通知ウィンドウが閉じ、PBX 携帯電話での音声通話のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="47bbc-146">But if the user accepts the call by picking up the PBX phone, then the Skype for Business notification window closes and there is no Skype for Business session, only the voice call over the PBX phone.</span></span>
  
<span data-ttu-id="47bbc-147">勤務先からの通話が有効になっているユーザーが PBX 通話を受信した場合は、PBX 電話のみが着信します。</span><span class="sxs-lookup"><span data-stu-id="47bbc-147">When a user enabled for Call Via Work receives a PBX call, only the PBX phone rings.</span></span>
  
## <a name="limitations-of-call-via-work"></a><span data-ttu-id="47bbc-148">勤務先での通話の制限</span><span class="sxs-lookup"><span data-stu-id="47bbc-148">Limitations of Call Via Work</span></span>

<span data-ttu-id="47bbc-149">[勤務先からの通話] は、わずかなハードウェアのセットアップが必要ですが、完全なエンタープライズ Voip またはリモート通話コントロールで利用できる機能との制限があります。</span><span class="sxs-lookup"><span data-stu-id="47bbc-149">Call Via Work is a voice solution that requires little hardware setup, but has limitations compared to the features available in full Enterprise Voice or remote call control.</span></span> <span data-ttu-id="47bbc-150">勤務先での通話には、次のような制限があります。</span><span class="sxs-lookup"><span data-stu-id="47bbc-150">Call Via Work has the following limitations:</span></span>
  
- <span data-ttu-id="47bbc-151">勤務先からの通話で、勤務先のコールバック番号を使って通話への通話転送を設定した場合、ユーザーの電話番号による会議にこのユーザーを招待しようとしても、招待はユーザーに届かなくなります。</span><span class="sxs-lookup"><span data-stu-id="47bbc-151">If a Call Via Work user has set up call forwarding to the Call Via Work callback number, and someone tries to invite this user to a meeting by the user's phone number, the invitation will not reach the user.</span></span> <span data-ttu-id="47bbc-152">参加者を会議に招待するには、電話番号ではなく名前をクリックするように、ユーザーに伝える必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bbc-152">You should educate your users to invite participants to meetings by clicking the name, not the phone number.</span></span> 
    
- <span data-ttu-id="47bbc-153">拡張された911機能と悪意のある通話の追跡は、勤務先の通話では利用できません。</span><span class="sxs-lookup"><span data-stu-id="47bbc-153">Enhanced 911 capability and malicious call tracing are not available during Call Via Work calls.</span></span>
    
- <span data-ttu-id="47bbc-154">職場での通話が有効になっているユーザーは、委任、チーム呼び出し、または応答グループの機能を使用できません。</span><span class="sxs-lookup"><span data-stu-id="47bbc-154">Users enabled for Call Via Work cannot use the delegation, team call, or response group features.</span></span>
    
- <span data-ttu-id="47bbc-155">勤務先からの通話のユーザーは、Skype for Business を使用して、会議の記録、通話のミュート/ミュート解除、通話の保留または転送、または通話パークの使用を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="47bbc-155">Users of Call Via Work cannot use Skype for Business to record a meeting, mute or unmute the call, hold or transfer the call, or use call park.</span></span>
    
- <span data-ttu-id="47bbc-156">ユーザーは、PBX ボイスメールメッセージにアクセスするために勤務先から通話を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="47bbc-156">Users cannot use Call Via Work to access their PBX voicemail messages.</span></span>
    
- <span data-ttu-id="47bbc-157">勤務先からの通話のユーザーは、音声通話として開始されたセッションを、ビデオ、Powerpoint、ホワイトボード、または1つのノートなどのコミュニケーションを含む共同会議にエスカレートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="47bbc-157">Users of Call Via Work cannot escalate a session that started as a voice call to a collaborative meeting that includes communications such as video, Powerpoint, whiteboard, or One Note.</span></span>
    
- <span data-ttu-id="47bbc-158">勤務先からの通話のユーザーは、2人のユーザーとの通話により多くのユーザーを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="47bbc-158">Users of Call Via Work cannot add more users to a 2-person call.</span></span>
    
- <span data-ttu-id="47bbc-159">卓上電話のペアリングまたは VDI プラグイン ペアリングをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="47bbc-159">No support for deskphone pairing or VDI plugin pairing.</span></span>
    
- <span data-ttu-id="47bbc-160">ユーザーが PBX 電話を使って通話に応答した場合 (Skype for Business ウィンドウを使用していない場合)、通話のログは記録されません。</span><span class="sxs-lookup"><span data-stu-id="47bbc-160">If a user makes or answers a call using the PBX phone (and not using the Skype for Business window), there will be no log of the call.</span></span>
    
- <span data-ttu-id="47bbc-161">PBX システムが **REFER with Replaces** をサポートしていない場合は、次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="47bbc-161">If your PBX system does not support **REFER with Replaces**, the following behavior will happen.</span></span> <span data-ttu-id="47bbc-162">勤務先の通話中に、ユーザーが PBX 携帯電話から進行中の通話を転送した場合、通話ウィンドウは Skype for Business ウィンドウに表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="47bbc-162">While on a Call Via Work call, if the user transfers the ongoing call from the PBX Phone, the call window will not disappear from their Skype for Business window.</span></span> <span data-ttu-id="47bbc-163">ユーザーが通話ウィンドウを閉じると、転送先との間の通話が終了します。</span><span class="sxs-lookup"><span data-stu-id="47bbc-163">If the user then closes the call window, the call between the transfer target and the transferee will end.</span></span> 
    
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="47bbc-164">勤務先での通話の前提条件</span><span class="sxs-lookup"><span data-stu-id="47bbc-164">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="47bbc-165">勤務先から通話を発信できるようにするには、あらかじめいくつかの前提条件を設定しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bbc-165">To enable any users for Call Via Work, you must have some pre-requisites in place.</span></span> <span data-ttu-id="47bbc-166">これらの前提条件について詳しくは、「 [Skype For Business Server 2015 で](../../deploy/deploy-call-via-work.md)の電話での通話の展開」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="47bbc-166">For more information on these prerequisites, and for steps on how to enable users for Call Via Work, see [Deploy Call Via Work in Skype for Business Server 2015](../../deploy/deploy-call-via-work.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="47bbc-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="47bbc-167">See also</span></span>

[<span data-ttu-id="47bbc-168">Skype for Business のリモート通話コントロールを計画する</span><span class="sxs-lookup"><span data-stu-id="47bbc-168">Plan for remote call control in Skype for Business</span></span>](remote-call-control.md)
  
[<span data-ttu-id="47bbc-169">Skype for Business Server 2015 での "勤務先から通話" の展開</span><span class="sxs-lookup"><span data-stu-id="47bbc-169">Deploy Call Via Work in Skype for Business Server 2015</span></span>](../../deploy/deploy-call-via-work.md)

