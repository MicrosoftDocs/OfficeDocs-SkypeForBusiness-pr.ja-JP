---
title: Skype for Business のコール パークを計画する
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
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Skype for Business Server エンタープライズ VoIP のコール パークの計画。これにより、通話を保留にし、通話を部門に転送できます。 容量計画、サポートされる通話、およびサポートされるクライアントが含まれます。
ms.openlocfilehash: c324e8d61f6d0e9e67870f05597a9157965a3eb3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825927"
---
# <a name="plan-for-call-park-in-skype-for-business"></a><span data-ttu-id="ae53b-104">Skype for Business のコール パークを計画する</span><span class="sxs-lookup"><span data-stu-id="ae53b-104">Plan for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="ae53b-105">Skype for Business Server エンタープライズ VoIP のコール パークの計画。これにより、通話を保留にし、通話を部門に転送できます。</span><span class="sxs-lookup"><span data-stu-id="ae53b-105">Planning for call park in Skype for Business Server Enterprise Voice, which enables putting calls on hold and transferring calls to departments.</span></span> <span data-ttu-id="ae53b-106">容量計画、サポートされる通話、およびサポートされるクライアントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ae53b-106">Includes capacity planning, supported calls, and supported clients.</span></span>
  
<span data-ttu-id="ae53b-107">コール パーク アプリケーションを使用するとエンタープライズ VoIPユーザーは次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="ae53b-107">The Call Park application enables Enterprise Voice users to do the following:</span></span>
  
- <span data-ttu-id="ae53b-108">通話を保留にしてから、同じ電話または別の電話から通話を取得します。</span><span class="sxs-lookup"><span data-stu-id="ae53b-108">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>
    
- <span data-ttu-id="ae53b-109">通話を保留にし、部門または全般領域 (たとえば、共通領域電話がある営業部門やウェアハウス) に転送します。</span><span class="sxs-lookup"><span data-stu-id="ae53b-109">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>
    
- <span data-ttu-id="ae53b-110">通話を保留にし、元の応答電話を他の通話に対して無料で保持します。</span><span class="sxs-lookup"><span data-stu-id="ae53b-110">Put a call on hold and keep the original answering phone free for other calls.</span></span>
    
<span data-ttu-id="ae53b-111">ユーザーが通話をパークすると、Skype for Business Server は、呼び出しをオービットと呼ばれる一時的な番号に転送します。オービットは、通話が取得されるか、またはタイム アウトするまで保持されます。Skype for Business Server は、通話をパークしたユーザーにオービットを送信します。</span><span class="sxs-lookup"><span data-stu-id="ae53b-111">When a user parks a call, Skype for Business Server transfers the call to a temporary number, called an orbit, where the call is held until it is retrieved or it times out. Skype for Business Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="ae53b-112">パークされた通話を取得するには、ユーザーはオービット番号にダイヤルするか、[会話] ウィンドウのオービット リンクまたはボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae53b-112">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span> 
  
<span data-ttu-id="ae53b-113">通話をパークしたユーザーは、インスタント メッセージング (IM) やページング システムなどの外部メカニズムを使用して、オービット番号を他のユーザーに通知することで、通話を受け取るユーザーに通知できます。</span><span class="sxs-lookup"><span data-stu-id="ae53b-113">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else.</span></span> <span data-ttu-id="ae53b-114">通話をパークしたユーザーは、[会話] ウィンドウを開いたままにしておき、通話の受信時に通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ae53b-114">The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>
  
<span data-ttu-id="ae53b-115">オービット範囲はグローバルに一意なので、ルーティングが適切に構成されている場合は、任意の Skype for Business Server サイトまたは PBX 電話から通話を取得できます。</span><span class="sxs-lookup"><span data-stu-id="ae53b-115">Because orbit ranges are globally unique, it is possible to retrieve calls from any Skype for Business Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="ae53b-116">構成可能な時間内に誰も通話を受け取らない場合、通話は通話をパークした人に呼び戻されます。</span><span class="sxs-lookup"><span data-stu-id="ae53b-116">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="ae53b-117">そのユーザーがリングバックに応答しない場合、呼び出しは、構成されている場合は、オペレーターなどのフォールバック先に転送されます。</span><span class="sxs-lookup"><span data-stu-id="ae53b-117">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="ae53b-118">1 回から 10 回転送される前に、通話が戻る回数を構成できます。</span><span class="sxs-lookup"><span data-stu-id="ae53b-118">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="ae53b-119">転送された通話に誰も応答がない場合、通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="ae53b-119">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="ae53b-120">オービットは、通話が取得または切断されると解放されます。</span><span class="sxs-lookup"><span data-stu-id="ae53b-120">The orbit is freed when the call is retrieved or disconnected.</span></span>
  
<span data-ttu-id="ae53b-121">コール パークを展開する場合は、通話をパークするために内線番号の範囲を予約する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae53b-121">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="ae53b-122">これらの内線番号は、仮想の内線番号である必要があります。ユーザーまたは電話が割り当てられていない内線番号です。</span><span class="sxs-lookup"><span data-stu-id="ae53b-122">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="ae53b-123">次に、内線番号の範囲を使用してコール パーク オービット テーブルを構成し、各範囲を処理するコール パーク アプリケーションをホストするアプリケーション サービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae53b-123">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="ae53b-124">各フロントエンド プールには、対応するバック エンド サーバー上にコール パーク テーブルがあります。このテーブルは、プールでパークされる通話を管理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae53b-124">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="ae53b-125">オービット範囲のリストは中央管理ストアに格納され、オービットを送信先プールにルーティングするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae53b-125">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="ae53b-126">コール パーク アプリケーションが展開および構成されている各 Skype for Business Server プールには、1 つ以上のオービット範囲を設定できます。</span><span class="sxs-lookup"><span data-stu-id="ae53b-126">Each Skype for Business Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="ae53b-127">オービット範囲は、Skype for Business Server 展開全体でグローバルに一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae53b-127">Orbit ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
<span data-ttu-id="ae53b-128">また、通話がタイム アウトした場合に通話がリダイレクトされる場所や、通話のパーク中に電話のユーザーが音楽を聞くかどうかなど、他のコール パーク設定も構成します。</span><span class="sxs-lookup"><span data-stu-id="ae53b-128">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked.</span></span> <span data-ttu-id="ae53b-129">通話が保留されている間に再生する音楽ファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ae53b-129">You can also specify the music file to play while the call is on hold.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ae53b-130">コール パーク用のカスタマイズされた保留音ファイルは、Skype for Business Server の障害復旧プロセスの一部としてバックアップされません。プールにアップロードされたファイルが破損したり、消去された場合は失われます。</span><span class="sxs-lookup"><span data-stu-id="ae53b-130">Customized music-on-hold files for Call Park are not backed up as part of the Skype for Business Server disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="ae53b-131">コール パーク用にアップロードしたカスタマイズされた保留音ファイルのバックアップ コピーは、常に個別に保持します。</span><span class="sxs-lookup"><span data-stu-id="ae53b-131">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span> 
  
<span data-ttu-id="ae53b-132">コール パーク アプリケーションは、次のコンポーネントエンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="ae53b-132">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="ae53b-133">この機能を展開エンタープライズ VoIP、コール パーク アプリケーションが自動的にインストールされ、アクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="ae53b-133">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="ae53b-134">ただし、コール パークを使用するには、エンタープライズ VoIP管理者がコール パークを構成し、音声ポリシーを使用してユーザーに対して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae53b-134">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="ae53b-135">展開と要件</span><span class="sxs-lookup"><span data-stu-id="ae53b-135">Deployment and requirements</span></span>

<span data-ttu-id="ae53b-136">コール パーク アプリケーションは、展開時に自動的にインストールエンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="ae53b-136">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="ae53b-137">コール パークを有効にするには、音声ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="ae53b-137">You enable Call Park by configuring voice policy.</span></span>
  
### <a name="software-requirements"></a><span data-ttu-id="ae53b-138">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="ae53b-138">Software requirements</span></span>

<span data-ttu-id="ae53b-139">コール パークが展開されているすべてのフロントエンド サーバーと Standard Edition サーバーには、Windows Server 2008 R2 を実行しているサーバー用の Windows Media フォーマット ランタイムがインストールされている必要があります。または、Windows Server 2012 または Windows Server 2012 R2 を実行しているサーバー用の Microsoft Media Foundation がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae53b-139">All Front End Servers and Standard Edition servers where Call Park is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="ae53b-140">たとえばWindows Server 2008 R2、Windows Media フォーマット ランタイムは Windows デスクトップ エクスペリエンスの一部としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="ae53b-140">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="ae53b-141">コール パークが保留音として再生する Windows Media オーディオ (.wma) ファイルには、Windows Media フォーマット ランタイムまたは Microsoft Media Foundation が必要です。</span><span class="sxs-lookup"><span data-stu-id="ae53b-141">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>
  
### <a name="port-requirements"></a><span data-ttu-id="ae53b-142">ポートの要件</span><span class="sxs-lookup"><span data-stu-id="ae53b-142">Port requirements</span></span>

<span data-ttu-id="ae53b-143">コール パーク アプリケーションは、SIP リッスン **要求にポート 5075**  を使用します。</span><span class="sxs-lookup"><span data-stu-id="ae53b-143">The Call Park application uses **Port 5075**  for SIP listening requests.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ae53b-144">このポートは既定の設定であり、**Set-CsApplicationServer** コマンドレットを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="ae53b-144">This port is a default setting that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="ae53b-145">このコマンドレットの詳細については、Lync Server 管理シェルのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae53b-145">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>
  
### <a name="audio-file-requirements"></a><span data-ttu-id="ae53b-146">オーディオ ファイルの要件</span><span class="sxs-lookup"><span data-stu-id="ae53b-146">Audio File requirements</span></span>

<span data-ttu-id="ae53b-147">コール パーク アプリケーションは、保留音用の Windows Media オーディオ (.wma) ファイルのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="ae53b-147">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="ae53b-148">保留音のファイルをカスタマイズするには、Microsoft Expression Encoder 4 を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae53b-148">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="ae53b-149">Expression Encoder 4 をダウンロードするには   [、「Expression Encoder 4」を参照してください](https://go.microsoft.com/fwlink/p/?linkId=202843)。</span><span class="sxs-lookup"><span data-stu-id="ae53b-149">To download Expression Encoder 4, see   ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span></span> <span data-ttu-id="ae53b-150">このツールを使用すると、ファイルを WMA 形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="ae53b-150">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="ae53b-151">コール パークの保留音ファイルとしての推奨形式は Media Audio 9、44 kHz、16 ビット、モノラル、CBR、32 kbps です。</span><span class="sxs-lookup"><span data-stu-id="ae53b-151">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ae53b-152">変換されたファイルは、44 kHz で録音された場合でも、電話では 16 kHz でのみ再生されます。</span><span class="sxs-lookup"><span data-stu-id="ae53b-152">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span> 
  
## <a name="supported-clients-and-calls"></a><span data-ttu-id="ae53b-153">サポートされるクライアントと通話</span><span class="sxs-lookup"><span data-stu-id="ae53b-153">Supported clients and calls</span></span>

<span data-ttu-id="ae53b-154">コール パークでは、次のクライアントと通話の種類がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ae53b-154">The following clients and types of calls are supported for Call Park</span></span>
  
### <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="ae53b-155">通話の保留をサポートするクライアント</span><span class="sxs-lookup"><span data-stu-id="ae53b-155">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="ae53b-156">IP、構内交換機 (PBX)、公衆交換電話網 (PSTN)、または携帯電話からの通話を保留できます。</span><span class="sxs-lookup"><span data-stu-id="ae53b-156">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ae53b-p114">音声通話だけを保留できます。 インスタント メッセージと電話会議は保留できません。</span><span class="sxs-lookup"><span data-stu-id="ae53b-p114">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span> 
  
<span data-ttu-id="ae53b-159">次のクライアントはコール パークを使用して通話をパークできます。</span><span class="sxs-lookup"><span data-stu-id="ae53b-159">The following clients can use Call Park to park calls:</span></span>
  
- <span data-ttu-id="ae53b-160">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ae53b-160">Skype for Business</span></span>
    
- <span data-ttu-id="ae53b-161">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="ae53b-161">Lync 2013</span></span>
    
- <span data-ttu-id="ae53b-162">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="ae53b-162">Lync 2010</span></span>
    
- <span data-ttu-id="ae53b-163">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="ae53b-163">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="ae53b-164">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="ae53b-164">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="ae53b-165">携帯電話はコール パークを使用して通話をパークできません。</span><span class="sxs-lookup"><span data-stu-id="ae53b-165">Mobile phones cannot use Call Park to park calls.</span></span> 
  
### <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="ae53b-166">通話の取得をサポートするクライアント</span><span class="sxs-lookup"><span data-stu-id="ae53b-166">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="ae53b-p115">オービット範囲は仮想の内線番号 (ユーザーまたは電話が割り当てられていない内線番号) のブロックとして構成されます。 オービットを仮想の内線番号として構成すると、携帯電話と PSTN 電話は保留された通話を取得できません。</span><span class="sxs-lookup"><span data-stu-id="ae53b-p115">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="ae53b-169">フェデレーション ユーザーは保留された通話を取得できません。</span><span class="sxs-lookup"><span data-stu-id="ae53b-169">Federated users cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="ae53b-170">次のクライアントは、コール パークでパークされている通話を取得できます。</span><span class="sxs-lookup"><span data-stu-id="ae53b-170">The following clients can retrieve calls that are parked on Call Park:</span></span>
  
- <span data-ttu-id="ae53b-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ae53b-171">Skype for Business</span></span>
    
- <span data-ttu-id="ae53b-172">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="ae53b-172">Lync 2013</span></span>
    
- <span data-ttu-id="ae53b-173">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="ae53b-173">Lync 2010</span></span>
    
- <span data-ttu-id="ae53b-174">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="ae53b-174">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="ae53b-175">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="ae53b-175">Lync Phone Edition</span></span>
    
- <span data-ttu-id="ae53b-176">IP 共通領域電話</span><span class="sxs-lookup"><span data-stu-id="ae53b-176">IP common area phones</span></span>
    
- <span data-ttu-id="ae53b-177">共通領域電話、PBX (Private Branch Exchange) 電話など、Skype for Business Server インフラストラクチャに接続されている非 IP 電話</span><span class="sxs-lookup"><span data-stu-id="ae53b-177">Non-IP phones that are connected to the Skype for Business Server infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>
    
## <a name="call-park-capacity-planning"></a><span data-ttu-id="ae53b-178">コール パークの処理能力の計画</span><span class="sxs-lookup"><span data-stu-id="ae53b-178">Call Park capacity planning</span></span>

<span data-ttu-id="ae53b-179">次の表に、容量計画の要件の基礎として使用できるコール パーク ユーザー モデルを示します。</span><span class="sxs-lookup"><span data-stu-id="ae53b-179">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ae53b-180">障害復旧の処理能力の計画では、ペアのプールの各プールが両方のプールのコール パーク サービスのワークロードを処理できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae53b-180">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span> 
  
<span data-ttu-id="ae53b-181">**コール パークのユーザー モデル**</span><span class="sxs-lookup"><span data-stu-id="ae53b-181">**Call Park User Model**</span></span>

|<span data-ttu-id="ae53b-182">**測定基準**</span><span class="sxs-lookup"><span data-stu-id="ae53b-182">**Metric**</span></span>|<span data-ttu-id="ae53b-183">**フロント エンド プールごとに  <br/>  (8 つのフロントエンド サーバーを使用)**</span><span class="sxs-lookup"><span data-stu-id="ae53b-183">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="ae53b-184">**Standard Edition サーバーごとに**</span><span class="sxs-lookup"><span data-stu-id="ae53b-184">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ae53b-185">保留率</span><span class="sxs-lookup"><span data-stu-id="ae53b-185">Park rate</span></span>  <br/> |<span data-ttu-id="ae53b-186">8 分間に 1 回</span><span class="sxs-lookup"><span data-stu-id="ae53b-186">8 per minute</span></span>  <br/> |<span data-ttu-id="ae53b-187">1 分間に 1 回</span><span class="sxs-lookup"><span data-stu-id="ae53b-187">1 per minute</span></span>  <br/> |
|<span data-ttu-id="ae53b-188">取得通話保留率</span><span class="sxs-lookup"><span data-stu-id="ae53b-188">Retrieve parked call rate</span></span>  <br/> |<span data-ttu-id="ae53b-189">8 分間に 1 回</span><span class="sxs-lookup"><span data-stu-id="ae53b-189">8 per minute</span></span>  <br/> |<span data-ttu-id="ae53b-190">1 分間に 1 回</span><span class="sxs-lookup"><span data-stu-id="ae53b-190">1 per minute</span></span>  <br/> |
|<span data-ttu-id="ae53b-191">平均保留時間</span><span class="sxs-lookup"><span data-stu-id="ae53b-191">Average park duration</span></span>  <br/> |<span data-ttu-id="ae53b-192">60 秒</span><span class="sxs-lookup"><span data-stu-id="ae53b-192">60 seconds</span></span>  <br/> |<span data-ttu-id="ae53b-193">60 秒</span><span class="sxs-lookup"><span data-stu-id="ae53b-193">60 seconds</span></span>  <br/> |
   

