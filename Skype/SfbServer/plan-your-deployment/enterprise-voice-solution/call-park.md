---
title: Skype のコール パークのビジネス向けの計画
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: 保留と部門への呼び出しを転送するのに挿入する実際の呼び出しを有効にする Skype のコール パーク ビジネス サーバーのエンタープライズ VoIP の計画。 キャパシティ ・ プランニング、サポートされている呼び出し、およびサポートされているクライアントが含まれています。
ms.openlocfilehash: 92c896bb610827108379af2bca38cd7a89639af2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207028"
---
# <a name="plan-for-call-park-in-skype-for-business"></a><span data-ttu-id="caa05-104">Skype のコール パークのビジネス向けの計画</span><span class="sxs-lookup"><span data-stu-id="caa05-104">Plan for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="caa05-105">保留と部門への呼び出しを転送するのに挿入する実際の呼び出しを有効にする Skype のコール パーク ビジネス サーバーのエンタープライズ VoIP の計画。</span><span class="sxs-lookup"><span data-stu-id="caa05-105">Planning for call park in Skype for Business Server Enterprise Voice, which enables putting calls on hold and transferring calls to departments.</span></span> <span data-ttu-id="caa05-106">キャパシティ ・ プランニング、サポートされている呼び出し、およびサポートされているクライアントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="caa05-106">Includes capacity planning, supported calls, and supported clients.</span></span>
  
<span data-ttu-id="caa05-107">コール パーク アプリケーションは、エンタープライズ VoIP ユーザーは、次の操作を有効にします。</span><span class="sxs-lookup"><span data-stu-id="caa05-107">The Call Park application enables Enterprise Voice users to do the following:</span></span>
  
- <span data-ttu-id="caa05-108">通話を保留にして、同じ電話や別の電話で通話に応答する。</span><span class="sxs-lookup"><span data-stu-id="caa05-108">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>
    
- <span data-ttu-id="caa05-109">通話を保留にして、営業部門や倉庫など、共通領域電話が使用されている部門または一般的な領域に転送する。</span><span class="sxs-lookup"><span data-stu-id="caa05-109">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>
    
- <span data-ttu-id="caa05-110">通話を保留にして、他の通話に元のボイス メールを使用できるようにする。</span><span class="sxs-lookup"><span data-stu-id="caa05-110">Put a call on hold and keep the original answering phone free for other calls.</span></span>
    
<span data-ttu-id="caa05-111">ユーザー公園、Skype のビジネス サーバーの呼び出しは、軌道の呼び出しが取得されるか、タイムアウトになるまでに格納されると呼ばれる一時的な番号に呼び出しを転送します。ビジネス サーバー用の Skype は、呼び出しを保持しているユーザーに回り込みを送信します。</span><span class="sxs-lookup"><span data-stu-id="caa05-111">When a user parks a call, Skype for Business Server transfers the call to a temporary number, called an orbit, where the call is held until it is retrieved or it times out. Skype for Business Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="caa05-112">保留にした通話に応答するには、ユーザーはオービット番号をダイヤルするか、[会話] ウィンドウでオービット リンクまたはボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="caa05-112">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span> 
  
<span data-ttu-id="caa05-p104">通話を保留にしたユーザーは、他のユーザーにオービット番号を連絡するために、インスタント メッセージング (IM) やポケットベルなどの外部の機能を使用して、他のユーザーに通話を知らせて応答させることができます。通話を保留にしたユーザーは、[会話] ウィンドウを開いたままにして、通話が応答されたときに通知を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="caa05-p104">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else. The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>
  
<span data-ttu-id="caa05-115">軌道の範囲はグローバルに一意であるために、ルーティングを適切に構成されている場合は、Business Server サイトまたは PBX 電話、Skype からの呼び出しを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="caa05-115">Because orbit ranges are globally unique, it is possible to retrieve calls from any Skype for Business Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="caa05-116">構成可能な時間内で通話に応答するユーザーがいない場合、通話を保留にしたユーザーが再度呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="caa05-116">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="caa05-117">そのユーザーが再度の呼び出しに応答しない場合、通話はフォールバック先 (構成内容に応じてオペレーターなど) に転送されます。</span><span class="sxs-lookup"><span data-stu-id="caa05-117">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="caa05-118">通話が転送される前に、1 ～ 10 回まで再度呼び出す回数を構成できます。</span><span class="sxs-lookup"><span data-stu-id="caa05-118">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="caa05-119">転送された通話にだれも応答しない場合、その通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="caa05-119">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="caa05-120">通話が応答または切断されると、オービットは解放されます。</span><span class="sxs-lookup"><span data-stu-id="caa05-120">The orbit is freed when the call is retrieved or disconnected.</span></span>
  
<span data-ttu-id="caa05-121">コール パークを展開する場合、通話を保留するために、内線番号の範囲を予約する必要があります。</span><span class="sxs-lookup"><span data-stu-id="caa05-121">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="caa05-122">これらの内線番号は、ユーザーや電話が割り当てられていない、仮想の内線番号にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="caa05-122">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="caa05-123">次に、その内線番号の範囲を使用してコール パーク オービット テーブルを構成し、各範囲を処理するコール パーク アプリケーションをホストするアプリケーション サービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="caa05-123">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="caa05-124">各フロント エンド プールでは、上の対応するバック エンド サーバー プール内に駐機している呼び出しを管理するために使用されるコール パーク テーブルがあります。</span><span class="sxs-lookup"><span data-stu-id="caa05-124">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="caa05-125">サーバーの全体管理での移動範囲の一覧が格納されている保存し、軌道を移動先のプールにルーティングするために使用します。</span><span class="sxs-lookup"><span data-stu-id="caa05-125">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="caa05-126">コール パーク アプリケーションの展開し、構成の場所のビジネス サーバー プールの各 Skype は、1 つまたは複数の軌道の範囲を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="caa05-126">Each Skype for Business Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="caa05-127">軌道の範囲は、ビジネス サーバー配置の Skype 間でグローバルに一意でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="caa05-127">Orbit ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
<span data-ttu-id="caa05-p107">また、通話がタイムアウトになった場合に通話をどこにリダイレクトするのかや、保留になっている発信者に音楽を流すかどうかなど、他のコール パーク設定も構成します。通話が保留になっている間に再生する音楽ファイルも指定できます。</span><span class="sxs-lookup"><span data-stu-id="caa05-p107">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked. You can also specify the music file to play while the call is on hold.</span></span>
  
> [!NOTE]
> <span data-ttu-id="caa05-130">コール パークの音楽-保留中のファイルをカスタマイズしたビジネス サーバーの障害回復プロセスの Skype の一部としてバックアップされませんし、プールにアップロードされたファイルが破損している、壊れているか、または消去すると失われます。</span><span class="sxs-lookup"><span data-stu-id="caa05-130">Customized music-on-hold files for Call Park are not backed up as part of the Skype for Business Server disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="caa05-131">コール パーク用にアップロードされているカスタマイズした保留音ファイルについては、常に個別のバックアップ コピーを保持してください。</span><span class="sxs-lookup"><span data-stu-id="caa05-131">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span> 
  
<span data-ttu-id="caa05-132">コール パーク アプリケーションは、エンタープライズ VoIP のコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="caa05-132">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="caa05-133">エンタープライズ VoIP を展開すると、コール パーク アプリケーションがインストールされ、自動的にアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="caa05-133">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="caa05-134">コール パークを使用することができます、前に、エンタープライズ VoIP 管理者する必要があります構成し、音声ポリシーを使用してユーザーを有効にすることです。</span><span class="sxs-lookup"><span data-stu-id="caa05-134">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="caa05-135">展開と要件</span><span class="sxs-lookup"><span data-stu-id="caa05-135">Deployment and requirements</span></span>

<span data-ttu-id="caa05-136">コール パーク アプリケーションはエンタープライズ VoIP を展開するときに自動的にインストールします。</span><span class="sxs-lookup"><span data-stu-id="caa05-136">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="caa05-137">コール パークを有効にするには、音声ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="caa05-137">You enable Call Park by configuring voice policy.</span></span>
  
### <a name="software-requirements"></a><span data-ttu-id="caa05-138">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="caa05-138">Software requirements</span></span>

<span data-ttu-id="caa05-139">コール パークが展開されているすべてのフロント エンド サーバーと Standard Edition のサーバーに Windows Server 2012 または Windows Server を実行しているサーバーの Windows Server 2008 R2、または Microsoft メディア ファンデーションを実行しているサーバーがインストールされている Windows Media フォーマット ランタイムが必要2012 R2 です。</span><span class="sxs-lookup"><span data-stu-id="caa05-139">All Front End Servers and Standard Edition servers where Call Park is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="caa05-140">Windows Server 2008 R2、Windows デスクトップのエクスペリエンスの一部として Windows Media フォーマット ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="caa05-140">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="caa05-141">Windows Media フォーマット ランタイムや Microsoft メディア ファンデーションは、Windows Media オーディオ (.wma) ファイルのコール パークを再生する音楽を保留にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="caa05-141">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>
  
### <a name="port-requirements"></a><span data-ttu-id="caa05-142">ポートの要件</span><span class="sxs-lookup"><span data-stu-id="caa05-142">Port requirements</span></span>

<span data-ttu-id="caa05-143">コール パーク アプリケーションでは、SIP リッスン要求に**ポート 5075**を使用します。</span><span class="sxs-lookup"><span data-stu-id="caa05-143">The Call Park application uses **Port 5075**  for SIP listening requests.</span></span>
    
> [!NOTE]
> <span data-ttu-id="caa05-144">このポートは既定の設定であり、**Set-CsApplicationServer** コマンドレットを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="caa05-144">This port is a default setting that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="caa05-145">詳細については、このコマンドレットは、Lync Server 管理シェルのマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="caa05-145">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>
  
### <a name="audio-file-requirements"></a><span data-ttu-id="caa05-146">オーディオ ファイルの要件</span><span class="sxs-lookup"><span data-stu-id="caa05-146">Audio File requirements</span></span>

<span data-ttu-id="caa05-147">アプリケーションで音楽用の Windows Media オーディオ (.wma) ファイルのみをサポートするコール パークを保持します。</span><span class="sxs-lookup"><span data-stu-id="caa05-147">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="caa05-148">保留音のファイルをカスタマイズするには、Microsoft Expression Encoder 4 を使用できます。</span><span class="sxs-lookup"><span data-stu-id="caa05-148">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="caa05-149">式エンコーダー 4 をダウンロードするには、 [[Expression Encoder 4」](https://go.microsoft.com/fwlink/p/?linkId=202843)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="caa05-149">To download Expression Encoder 4, see   ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span></span> <span data-ttu-id="caa05-150">このツールを使用すると、ファイルを WMA 形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="caa05-150">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="caa05-151">コール パークの保留中の音楽ファイルの推奨される形式は、Media オーディオ 9、44 kHz、16 ビット、モノラル、CBR、32 kbps です。</span><span class="sxs-lookup"><span data-stu-id="caa05-151">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>
  
> [!NOTE]
> <span data-ttu-id="caa05-152">変換されたファイルは、44 kHz で録音された場合でも、電話では 16 kHz でのみ再生されます。</span><span class="sxs-lookup"><span data-stu-id="caa05-152">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span> 
  
## <a name="supported-clients-and-calls"></a><span data-ttu-id="caa05-153">サポートされるクライアントと通話</span><span class="sxs-lookup"><span data-stu-id="caa05-153">Supported clients and calls</span></span>

<span data-ttu-id="caa05-154">コール パークのサポートは、以下のクライアントの種類の呼び出し</span><span class="sxs-lookup"><span data-stu-id="caa05-154">The following clients and types of calls are supported for Call Park</span></span>
  
### <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="caa05-155">通話の保留をサポートするクライアント</span><span class="sxs-lookup"><span data-stu-id="caa05-155">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="caa05-156">IP、構内交換機 (PBX)、公衆交換電話網 (PSTN)、または携帯電話からの通話を保留できます。</span><span class="sxs-lookup"><span data-stu-id="caa05-156">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>
  
> [!NOTE]
> <span data-ttu-id="caa05-p114">音声通話だけを保留できます。インスタント メッセージと電話会議は保留できません。</span><span class="sxs-lookup"><span data-stu-id="caa05-p114">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span> 
  
<span data-ttu-id="caa05-159">次のクライアントは、コール パークを公園の呼び出しに使用できます。</span><span class="sxs-lookup"><span data-stu-id="caa05-159">The following clients can use Call Park to park calls:</span></span>
  
- <span data-ttu-id="caa05-160">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="caa05-160">Skype for Business</span></span>
    
- <span data-ttu-id="caa05-161">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="caa05-161">Lync 2013</span></span>
    
- <span data-ttu-id="caa05-162">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="caa05-162">Lync 2010</span></span>
    
- <span data-ttu-id="caa05-163">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="caa05-163">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="caa05-164">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="caa05-164">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="caa05-165">携帯電話は、公園の呼び出しに、コール パークを使用できません。</span><span class="sxs-lookup"><span data-stu-id="caa05-165">Mobile phones cannot use Call Park to park calls.</span></span> 
  
### <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="caa05-166">通話の取得をサポートするクライアント</span><span class="sxs-lookup"><span data-stu-id="caa05-166">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="caa05-p115">オービット範囲は仮想の内線番号 (ユーザーまたは電話が割り当てられていない内線番号) のブロックとして構成されます。オービットを仮想の内線番号として構成すると、携帯電話と PSTN 電話は保留された通話を取得できません。</span><span class="sxs-lookup"><span data-stu-id="caa05-p115">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="caa05-169">フェデレーション ユーザーは保留された通話を取得できません。</span><span class="sxs-lookup"><span data-stu-id="caa05-169">Federated users cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="caa05-170">次のクライアントでは、コール パークで駐機している呼び出しを取得できます。</span><span class="sxs-lookup"><span data-stu-id="caa05-170">The following clients can retrieve calls that are parked on Call Park:</span></span>
  
- <span data-ttu-id="caa05-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="caa05-171">Skype for Business</span></span>
    
- <span data-ttu-id="caa05-172">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="caa05-172">Lync 2013</span></span>
    
- <span data-ttu-id="caa05-173">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="caa05-173">Lync 2010</span></span>
    
- <span data-ttu-id="caa05-174">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="caa05-174">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="caa05-175">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="caa05-175">Lync Phone Edition</span></span>
    
- <span data-ttu-id="caa05-176">IP 共通領域電話</span><span class="sxs-lookup"><span data-stu-id="caa05-176">IP common area phones</span></span>
    
- <span data-ttu-id="caa05-177">非 IP 電話の共通領域電話、構内交換 (機 PBX) の電話など、ビジネスのサーバー インフラストラクチャの Skype に接続されています。</span><span class="sxs-lookup"><span data-stu-id="caa05-177">Non-IP phones that are connected to the Skype for Business Server infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>
    
## <a name="call-park-capacity-planning"></a><span data-ttu-id="caa05-178">コール パークの処理能力の計画</span><span class="sxs-lookup"><span data-stu-id="caa05-178">Call Park capacity planning</span></span>

<span data-ttu-id="caa05-179">次の表では、容量計画の基礎として使用できるコール パークのユーザー モデルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="caa05-179">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="caa05-180">災害復旧、容量計画、対になったプールの各プールする必要があることになるコール パーク サービスを両方のプール内のワークロードを処理することに留意してください。</span><span class="sxs-lookup"><span data-stu-id="caa05-180">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span> 
  
<span data-ttu-id="caa05-181">**コール パークのユーザー モデル**</span><span class="sxs-lookup"><span data-stu-id="caa05-181">**Call Park User Model**</span></span>

|<span data-ttu-id="caa05-182">**指標**</span><span class="sxs-lookup"><span data-stu-id="caa05-182">**Metric**</span></span>|<span data-ttu-id="caa05-183">**各フロント エンド プール<br/>で 8 台のフロント エンド サーバー)**</span><span class="sxs-lookup"><span data-stu-id="caa05-183">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="caa05-184">**Standard Edition サーバーごと**</span><span class="sxs-lookup"><span data-stu-id="caa05-184">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="caa05-185">保留率</span><span class="sxs-lookup"><span data-stu-id="caa05-185">Park rate</span></span>  <br/> |<span data-ttu-id="caa05-186">8 分間に 1 回</span><span class="sxs-lookup"><span data-stu-id="caa05-186">8 per minute</span></span>  <br/> |<span data-ttu-id="caa05-187">1 分間に 1 回</span><span class="sxs-lookup"><span data-stu-id="caa05-187">1 per minute</span></span>  <br/> |
|<span data-ttu-id="caa05-188">取得通話保留率</span><span class="sxs-lookup"><span data-stu-id="caa05-188">Retrieve parked call rate</span></span>  <br/> |<span data-ttu-id="caa05-189">8 分間に 1 回</span><span class="sxs-lookup"><span data-stu-id="caa05-189">8 per minute</span></span>  <br/> |<span data-ttu-id="caa05-190">1 分間に 1 回</span><span class="sxs-lookup"><span data-stu-id="caa05-190">1 per minute</span></span>  <br/> |
|<span data-ttu-id="caa05-191">平均保留時間</span><span class="sxs-lookup"><span data-stu-id="caa05-191">Average park duration</span></span>  <br/> |<span data-ttu-id="caa05-192">60 秒</span><span class="sxs-lookup"><span data-stu-id="caa05-192">60 seconds</span></span>  <br/> |<span data-ttu-id="caa05-193">60 秒</span><span class="sxs-lookup"><span data-stu-id="caa05-193">60 seconds</span></span>  <br/> |
   

