---
title: Plan for Call Via Work in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: Skype for Business と PBX 電話システムの統合が可能で、ユーザーが Skype for Business を使用して PBX 電話を制御できるような、Skype for Business Server での[通話から作業] の計画。
ms.openlocfilehash: e443a5d2709f1aca69ef200e72de43251cd16047
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825877"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="116d9-103">Plan for Call Via Work in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="116d9-103">Plan for Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="116d9-104">Skype for Business と PBX 電話システムの統合が可能で、ユーザーが Skype for Business を使用して PBX 電話を制御できるような、Skype for Business Server での[作業から通話] の計画。</span><span class="sxs-lookup"><span data-stu-id="116d9-104">Planning for Call Via Work in Skype for Business Server, which enables integration between Skype for Business and your PBX phone system, so that users can use Skype for Business to control their PBX phones.</span></span>
  
 <span data-ttu-id="116d9-105">**Call Via Work** は、Skype for Business Server の新機能で、Skype for Business ソリューションを既存の PBX 電話システムと統合できます。</span><span class="sxs-lookup"><span data-stu-id="116d9-105">**Call Via Work** is a new feature in Skype for Business Server which enables you to integrate your Skype for Business solution with your existing PBX phone systems.</span></span> <span data-ttu-id="116d9-106">[仕事から通話] が有効なユーザーは、Skype for Business でクリックして、展開内または外部ユーザーのどちらかに別のユーザーに電話をかけできます。</span><span class="sxs-lookup"><span data-stu-id="116d9-106">A user enabled for Call Via Work can click in Skype for Business to call another user, either within your deployment or an external user.</span></span> <span data-ttu-id="116d9-107">通話は、ユーザーの PBX 電話を使用して完了します。</span><span class="sxs-lookup"><span data-stu-id="116d9-107">The call is completed using the user's PBX phone.</span></span> <span data-ttu-id="116d9-108">これにより、PBX 電話を使用するユーザーは、豊富な Skype for Business 会話にオーディオを含めできます。</span><span class="sxs-lookup"><span data-stu-id="116d9-108">This enables a user with a PBX phone to include audio in their rich Skype for Business conversations.</span></span> <span data-ttu-id="116d9-109">以前のバージョンの Lync Server のリモート通話コントロールは、ユーザーが Lync Server を使用して PBX 電話を制御できる機能でした。</span><span class="sxs-lookup"><span data-stu-id="116d9-109">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="116d9-110">Skype for Business Server では、この機能は [Call Via Work] に置き換えられた機能です。</span><span class="sxs-lookup"><span data-stu-id="116d9-110">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>
  
<span data-ttu-id="116d9-111">[Call Via Work] を使用すると、PBX 電話ユーザーに対して次の機能が有効にされます。</span><span class="sxs-lookup"><span data-stu-id="116d9-111">Call Via Work enables the following for PBX phone users</span></span>
  
- <span data-ttu-id="116d9-112">PBX 電話を介して提供される音声による、クリックして呼び出しのエクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="116d9-112">Click-to-call experience, with the audio provided through the PBX phone.</span></span>
    
- <span data-ttu-id="116d9-113">プレゼンス、ユーザー検索、および IM 統合 。たとえば、IM セッションで 2 人の "仕事から通話" ユーザーが、PBX 電話経由で提供される音声を使用して、セッションにオーディオを追加できます。</span><span class="sxs-lookup"><span data-stu-id="116d9-113">Presence, user search, and IM integration-- for example, two Call Via Work users in an IM session can add audio to their session, with the audio provided through the PBX phones.</span></span>
    
- <span data-ttu-id="116d9-114">IM、アプリケーション共有、およびファイル転送を [Call Via Work] 通話に追加する機能。</span><span class="sxs-lookup"><span data-stu-id="116d9-114">The ability to add IM, application sharing, and file transfer to a Call Via Work call.</span></span>
    
- <span data-ttu-id="116d9-115">1 回クリックで会議参加機能</span><span class="sxs-lookup"><span data-stu-id="116d9-115">One-click meeting join capability</span></span>
    
## <a name="how-it-works"></a><span data-ttu-id="116d9-116">メカニズム</span><span class="sxs-lookup"><span data-stu-id="116d9-116">How it works</span></span>

<span data-ttu-id="116d9-117">Call Via Work は、PBX システムと Skype for Business Server 展開との間のバック to バック ユーザー エージェント (B2BUA) として Unified Communications Web API (UCWA) を使用します。そのため、Skype for Business Server を PBX システムに接続するためにコンピューターサポートの通信アプリケーション (CSTA) ゲートウェイは必要とされません。</span><span class="sxs-lookup"><span data-stu-id="116d9-117">Call Via Work uses Unified Communications Web API (UCWA) as the back-to-back user agent (B2BUA) between the PBX system and your Skype for Business Server deployment, so that no computer-supported telecommunications application (CSTA) gateway is needed to connect Skype for Business Server with your PBX system.</span></span> <span data-ttu-id="116d9-118">UCWA は、モバイルおよび Web クライアントとの接続を可能にする以前のバージョンの Lync Server で導入されたサービスであり、すべてのフロントエンド サーバーに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="116d9-118">UCWA is a service introduced in previous versions of Lync Server to enable connectivity with mobile and web clients, and is automatically installed on every Front End Server.</span></span>
  
### <a name="call-workflow-for-a-call-via-work-call"></a><span data-ttu-id="116d9-119">[Call Via Work] 通話の通話ワークフロー</span><span class="sxs-lookup"><span data-stu-id="116d9-119">Call workflow for a Call Via Work call</span></span>

<span data-ttu-id="116d9-120">次の図は、ユーザーが [仕事から通話] を有効にした場合に、Skype for Business Server を使用して通話を行う方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="116d9-120">The following illustrates how a user enabled for Call Via Work can use the Skype for Business Server to make a call:</span></span>
  
![[Call Via Work] 通話中の手順を示します。最初に、発信者がクリックして Skype for Business クライアントで他のユーザーに電話します。UCWA が発信者の電話に着信します。](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. <span data-ttu-id="116d9-123">ユーザーは Skype for Business クライアントでユーザーを選択し、電話アイコンをクリックしてユーザーに電話します。</span><span class="sxs-lookup"><span data-stu-id="116d9-123">The user selects a user in their Skype for Business client, and clicks the phone icon to call them.</span></span> <span data-ttu-id="116d9-124">または、IM 会話中に、ユーザーがクリックして、セッションを受け取っているユーザーに電話します。</span><span class="sxs-lookup"><span data-stu-id="116d9-124">Or, during an IM conversation, the user clicks to call the user they are having the session with.</span></span>
    
2. <span data-ttu-id="116d9-125">呼び出しを行ったユーザーの PBX 電話が呼び出しを開始します。</span><span class="sxs-lookup"><span data-stu-id="116d9-125">The PBX phone of the user who placed the call starts to ring.</span></span> <span data-ttu-id="116d9-126">この電話の発信者番号には、通話を行うすべてのユーザーの発信者番号に表示するために設定したグローバル電話番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="116d9-126">The caller ID for this phone shows a global phone number which you have set up to show in the caller ID of all users placing Call Via Work calls.</span></span> <span data-ttu-id="116d9-127">このグローバル電話番号は、1 人のユーザーの電話に対応する実際の電話番号ではありません。</span><span class="sxs-lookup"><span data-stu-id="116d9-127">This global phone number is not an actual phone number that corresponds to any one person's phone.</span></span> <span data-ttu-id="116d9-128">代わりに、これが自分の発信通話であり、同時に発生する着信呼び出しではないことをユーザーに知らせる視覚的な信号です。</span><span class="sxs-lookup"><span data-stu-id="116d9-128">Instead, it is a visual signal to let a user know that this is their own outgoing call, and not an incoming call happening at the same time.</span></span> <span data-ttu-id="116d9-129">[Call Via Work] を展開する場合は、これらのユーザーにこのグローバル電話番号とそれが何を意味するのかを教育する必要があります。</span><span class="sxs-lookup"><span data-stu-id="116d9-129">When you deploy Call Via Work, you should educate those users about this global phone number and what it means.</span></span>
    
3. <span data-ttu-id="116d9-130">通話を行ったユーザーは、PBX 電話を使用します。</span><span class="sxs-lookup"><span data-stu-id="116d9-130">The user who placed the call picks up their PBX phone.</span></span> <span data-ttu-id="116d9-131">次に、Skype for Business は呼び出し先への音声呼び出しを開始します。</span><span class="sxs-lookup"><span data-stu-id="116d9-131">Skype for Business then initiates the voice call to the callee.</span></span> 
    
4. <span data-ttu-id="116d9-132">呼び出し先が応答すると、音声呼び出しが開始されます。</span><span class="sxs-lookup"><span data-stu-id="116d9-132">When the callee answers, the voice call begins.</span></span> <span data-ttu-id="116d9-133">2 人のユーザーが既に IM セッションを継続している場合は、続行できます。</span><span class="sxs-lookup"><span data-stu-id="116d9-133">If the two users already had an IM session going, it can continue.</span></span>
    
### <a name="joining-a-conference-with-call-via-work"></a><span data-ttu-id="116d9-134">[仕事から通話] で電話会議に参加する</span><span class="sxs-lookup"><span data-stu-id="116d9-134">Joining a Conference With Call Via Work</span></span>

<span data-ttu-id="116d9-135">[Call Via Work] (仕事から通話) ユーザーは、会議 URL をクリックして、スケジュールされた会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="116d9-135">A Call Via Work user can join a scheduled meeting by clicking the meeting URL.</span></span> <span data-ttu-id="116d9-136">次に、Skype for  Business は、会議サービスがユーザーの PBX 電話にダイヤルするまで、メッセージへのダイヤルアウトを表示します。</span><span class="sxs-lookup"><span data-stu-id="116d9-136">Skype for Business then shows a **Dialing out to** message until the meeting service dials the user's PBX phone.</span></span> <span data-ttu-id="116d9-137">次に、Call Via Work ユーザーが PBX 電話を選択し、会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="116d9-137">The Call Via Work user then picks up the PBX phone and joins the meeting.</span></span>
  
<span data-ttu-id="116d9-138">[仕事から通話] ユーザーは、Skype for Business の [今すぐミーティング] オプションを使用して今すぐ会議を作成することもできます。 </span><span class="sxs-lookup"><span data-stu-id="116d9-138">A Call Via Work user can also use the **Meet Now** option in Skype for Business to create Meet Now meetings.</span></span> <span data-ttu-id="116d9-139">次に、ユーザーに [ **ダイヤルアウト** ] メッセージが表示され、PBX 電話が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="116d9-139">The user then sees the **Dialing out to** message, and the PBX phone rings.</span></span>
  
<span data-ttu-id="116d9-140">Call Via Work ユーザーは、Skype for Business 内から会議ブリッジ番号に電話をかけ、会議にダイヤルインできます。</span><span class="sxs-lookup"><span data-stu-id="116d9-140">A Call Via Work user can also dial in to a meeting by calling the Conference Bridge number from within Skype for Business.</span></span> <span data-ttu-id="116d9-141">会議 PIN が必要な場合、ユーザーは PBX 電話を使用して PIN を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="116d9-141">If a conference PIN is required, the user must use their PBX phone to input the PIN.</span></span>
  
### <a name="incoming-calls"></a><span data-ttu-id="116d9-142">着信呼び出し</span><span class="sxs-lookup"><span data-stu-id="116d9-142">Incoming Calls</span></span>

<span data-ttu-id="116d9-143">[仕事から通話] が有効になっているユーザーが Skype for Business 通話を受信すると、PBX 電話とユーザーの Skype for Business クライアントはすべて同時に呼び出されます (ユーザーが同時呼び出しを設定している場合)。</span><span class="sxs-lookup"><span data-stu-id="116d9-143">When a user enabled for Call Via Work receives a Skype for Business call, the PBX phone and the user's Skype for Business clients all ring simultaneously (if the user has set up simultaneous ring).</span></span> <span data-ttu-id="116d9-144">ユーザーは、PBX 電話を受け取る、または Skype for Business 通知の **[** 承諾] をクリックして、通話を承諾できます。</span><span class="sxs-lookup"><span data-stu-id="116d9-144">The user can accept the call either by picking up the PBX phone or clicking **Accept** on the Skype for Business notification.</span></span> <span data-ttu-id="116d9-145">ユーザーが Skype for Business を使用して通話を承諾した場合、通話の Skype for Business ウィンドウは開いたままです。</span><span class="sxs-lookup"><span data-stu-id="116d9-145">If the user accepts the call using Skype for Business, the Skype for Business window for the call stays open.</span></span> <span data-ttu-id="116d9-146">ただし、ユーザーが PBX 電話を受け取って通話を受け入れる場合は、Skype for Business 通知ウィンドウが閉じ、Skype for Business セッションは表示されません。PBX 電話を経由する音声通話のみです。</span><span class="sxs-lookup"><span data-stu-id="116d9-146">But if the user accepts the call by picking up the PBX phone, then the Skype for Business notification window closes and there is no Skype for Business session, only the voice call over the PBX phone.</span></span>
  
<span data-ttu-id="116d9-147">[Call Via Work] が有効なユーザーが PBX 呼び出しを受信すると、PBX 電話だけが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="116d9-147">When a user enabled for Call Via Work receives a PBX call, only the PBX phone rings.</span></span>
  
## <a name="limitations-of-call-via-work"></a><span data-ttu-id="116d9-148">[仕事から通話] の制限事項</span><span class="sxs-lookup"><span data-stu-id="116d9-148">Limitations of Call Via Work</span></span>

<span data-ttu-id="116d9-149">Call Via Work は、ハードウェアのセットアップをほとんど必要としませんが、フル エンタープライズ VoIP またはリモート通話コントロールで使用できる機能に比べて制限がある音声ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="116d9-149">Call Via Work is a voice solution that requires little hardware setup, but has limitations compared to the features available in full Enterprise Voice or remote call control.</span></span> <span data-ttu-id="116d9-150">[Call Via Work] (仕事から通話) には、次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="116d9-150">Call Via Work has the following limitations:</span></span>
  
- <span data-ttu-id="116d9-151">[Call Via Work] ユーザーが [Call Via Work] コールバック番号への呼び出し転送を設定し、ユーザーがユーザーの電話番号でこのユーザーを会議に招待しようとすると、招待はそのユーザーに届かない。</span><span class="sxs-lookup"><span data-stu-id="116d9-151">If a Call Via Work user has set up call forwarding to the Call Via Work callback number, and someone tries to invite this user to a meeting by the user's phone number, the invitation will not reach the user.</span></span> <span data-ttu-id="116d9-152">電話番号ではなく名前をクリックして会議に参加者を招待するユーザーを教育する必要があります。</span><span class="sxs-lookup"><span data-stu-id="116d9-152">You should educate your users to invite participants to meetings by clicking the name, not the phone number.</span></span> 
    
- <span data-ttu-id="116d9-153">拡張 911 機能と悪意のある呼び出しのトレースは、"仕事から通話" の呼び出し時には使用できません。</span><span class="sxs-lookup"><span data-stu-id="116d9-153">Enhanced 911 capability and malicious call tracing are not available during Call Via Work calls.</span></span>
    
- <span data-ttu-id="116d9-154">[会社から通話] が有効なユーザーは、委任、チーム通話、または応答グループの機能を使用できません。</span><span class="sxs-lookup"><span data-stu-id="116d9-154">Users enabled for Call Via Work cannot use the delegation, team call, or response group features.</span></span>
    
- <span data-ttu-id="116d9-155">ユーザーが Skype for Business を使用して会議を録音したり、通話をミュートまたはミュート解除したり、通話を保留または転送したり、コール パークを使用したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="116d9-155">Users of Call Via Work cannot use Skype for Business to record a meeting, mute or unmute the call, hold or transfer the call, or use call park.</span></span>
    
- <span data-ttu-id="116d9-156">ユーザーは[Call Via Work]を使用して PBX ボイスメール メッセージにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="116d9-156">Users cannot use Call Via Work to access their PBX voicemail messages.</span></span>
    
- <span data-ttu-id="116d9-157">[仕事から通話] のユーザーは、音声通話として開始されたセッションを、ビデオ、Powerpoint、ホワイトボード、One Note などの通信を含む共同作業会議にエスカレートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="116d9-157">Users of Call Via Work cannot escalate a session that started as a voice call to a collaborative meeting that includes communications such as video, Powerpoint, whiteboard, or One Note.</span></span>
    
- <span data-ttu-id="116d9-158">[仕事から通話] のユーザーは、2 人通話にユーザーを追加できません。</span><span class="sxs-lookup"><span data-stu-id="116d9-158">Users of Call Via Work cannot add more users to a 2-person call.</span></span>
    
- <span data-ttu-id="116d9-159">電話のペアリングや VDI プラグインのペアリングはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="116d9-159">No support for deskphone pairing or VDI plugin pairing.</span></span>
    
- <span data-ttu-id="116d9-160">ユーザーが PBX 電話を使用して (Skype for Business ウィンドウを使用しない) 通話に応答した場合、通話のログは表示されません。</span><span class="sxs-lookup"><span data-stu-id="116d9-160">If a user makes or answers a call using the PBX phone (and not using the Skype for Business window), there will be no log of the call.</span></span>
    
- <span data-ttu-id="116d9-161">PBX システムが置換で **REFER をサポートしていない** 場合は、次の動作が発生します。</span><span class="sxs-lookup"><span data-stu-id="116d9-161">If your PBX system does not support **REFER with Replaces**, the following behavior will happen.</span></span> <span data-ttu-id="116d9-162">[Call Via Work] 通話中に、ユーザーが PBX 電話から進行中の通話を転送した場合、通話ウィンドウは Skype for Business ウィンドウから消えません。</span><span class="sxs-lookup"><span data-stu-id="116d9-162">While on a Call Via Work call, if the user transfers the ongoing call from the PBX Phone, the call window will not disappear from their Skype for Business window.</span></span> <span data-ttu-id="116d9-163">ユーザーが通話ウィンドウを閉じると、転送先と転送先の間の通話が終了します。</span><span class="sxs-lookup"><span data-stu-id="116d9-163">If the user then closes the call window, the call between the transfer target and the transferee will end.</span></span> 
    
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="116d9-164">[仕事から通話] の前提条件</span><span class="sxs-lookup"><span data-stu-id="116d9-164">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="116d9-165">[仕事から通話] に対してすべてのユーザーを有効にするには、いくつかの前提条件が必要です。</span><span class="sxs-lookup"><span data-stu-id="116d9-165">To enable any users for Call Via Work, you must have some pre-requisites in place.</span></span> <span data-ttu-id="116d9-166">これらの前提条件の詳細、およびユーザーの [通話の実行] を [作業から] に対して有効にする手順については [、「Deploy Call Via Work in Skype for Business Server 2015」](../../deploy/deploy-call-via-work.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="116d9-166">For more information on these prerequisites, and for steps on how to enable users for Call Via Work, see [Deploy Call Via Work in Skype for Business Server 2015](../../deploy/deploy-call-via-work.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="116d9-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="116d9-167">See also</span></span>

[<span data-ttu-id="116d9-168">Skype for Business でのリモート通話コントロールの計画</span><span class="sxs-lookup"><span data-stu-id="116d9-168">Plan for remote call control in Skype for Business</span></span>](remote-call-control.md)
  
[<span data-ttu-id="116d9-169">Deploy Call Via Work in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="116d9-169">Deploy Call Via Work in Skype for Business Server 2015</span></span>](../../deploy/deploy-call-via-work.md)

