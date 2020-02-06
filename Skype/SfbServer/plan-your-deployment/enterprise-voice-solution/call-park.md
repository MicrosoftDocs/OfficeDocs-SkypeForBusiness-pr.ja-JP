---
title: Skype for Business のコールパークの計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Skype for Business Server エンタープライズボイスのコールパークの計画。通話を保留にしたり、部署に通話を転送したりできます。 容量の計画、サポートされている通話、サポートされているクライアントが含まれます。
ms.openlocfilehash: 3effeab4afef60fb7a5021206d9fc3cd0227ceb1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803197"
---
# <a name="plan-for-call-park-in-skype-for-business"></a><span data-ttu-id="0685e-104">Skype for Business のコールパークの計画</span><span class="sxs-lookup"><span data-stu-id="0685e-104">Plan for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="0685e-105">Skype for Business Server エンタープライズボイスのコールパークの計画。通話を保留にしたり、部署に通話を転送したりできます。</span><span class="sxs-lookup"><span data-stu-id="0685e-105">Planning for call park in Skype for Business Server Enterprise Voice, which enables putting calls on hold and transferring calls to departments.</span></span> <span data-ttu-id="0685e-106">容量の計画、サポートされている通話、サポートされているクライアントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0685e-106">Includes capacity planning, supported calls, and supported clients.</span></span>
  
<span data-ttu-id="0685e-107">コールパークアプリケーションを使用すると、エンタープライズボイスユーザーは次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="0685e-107">The Call Park application enables Enterprise Voice users to do the following:</span></span>
  
- <span data-ttu-id="0685e-108">通話を保留にして、同じ電話や別の電話で通話に応答する。</span><span class="sxs-lookup"><span data-stu-id="0685e-108">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>
    
- <span data-ttu-id="0685e-109">通話を保留にして、営業部門や倉庫など、共通領域電話が使用されている部門または一般的な領域に転送する。</span><span class="sxs-lookup"><span data-stu-id="0685e-109">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>
    
- <span data-ttu-id="0685e-110">通話を保留にして、他の通話に元のボイス メールを使用できるようにする。</span><span class="sxs-lookup"><span data-stu-id="0685e-110">Put a call on hold and keep the original answering phone free for other calls.</span></span>
    
<span data-ttu-id="0685e-111">ユーザーが電話にパークすると、Skype for Business Server は、着信が転送されるまで、またはタイムアウトするまで、通話を保持している一時的な番号に転送します。Skype for Business Server では、通話を保留したユーザーに軌道が送信されます。</span><span class="sxs-lookup"><span data-stu-id="0685e-111">When a user parks a call, Skype for Business Server transfers the call to a temporary number, called an orbit, where the call is held until it is retrieved or it times out. Skype for Business Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="0685e-112">保留にした通話に応答するには、ユーザーはオービット番号をダイヤルするか、[会話] ウィンドウでオービット リンクまたはボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0685e-112">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span> 
  
<span data-ttu-id="0685e-p104">通話を保留にしたユーザーは、他のユーザーにオービット番号を連絡するために、インスタント メッセージング (IM) やポケットベルなどの外部の機能を使用して、他のユーザーに通話を知らせて応答させることができます。通話を保留にしたユーザーは、[会話] ウィンドウを開いたままにして、通話が応答されたときに通知を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="0685e-p104">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else. The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>
  
<span data-ttu-id="0685e-115">オービット範囲はグローバルに一意であるため、ルーティングが適切に構成されている場合は、どの Skype for Business Server サイトまたは PBX 電話からでも通話を取得できます。</span><span class="sxs-lookup"><span data-stu-id="0685e-115">Because orbit ranges are globally unique, it is possible to retrieve calls from any Skype for Business Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="0685e-116">構成可能な時間内で通話に応答するユーザーがいない場合、通話を保留にしたユーザーが再度呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="0685e-116">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="0685e-117">そのユーザーが再度の呼び出しに応答しない場合、通話はフォールバック先 (構成内容に応じてオペレーターなど) に転送されます。</span><span class="sxs-lookup"><span data-stu-id="0685e-117">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="0685e-118">通話が転送される前に、1 ～ 10 回まで再度呼び出す回数を構成できます。</span><span class="sxs-lookup"><span data-stu-id="0685e-118">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="0685e-119">転送された通話にだれも応答しない場合、その通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="0685e-119">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="0685e-120">通話が応答または切断されると、オービットは解放されます。</span><span class="sxs-lookup"><span data-stu-id="0685e-120">The orbit is freed when the call is retrieved or disconnected.</span></span>
  
<span data-ttu-id="0685e-121">コール パークを展開する場合、通話を保留するために、内線番号の範囲を予約する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0685e-121">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="0685e-122">これらの内線番号は、ユーザーや電話が割り当てられていない、仮想の内線番号にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0685e-122">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="0685e-123">次に、その内線番号の範囲を使用してコール パーク オービット テーブルを構成し、各範囲を処理するコール パーク アプリケーションをホストするアプリケーション サービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="0685e-123">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="0685e-124">各フロントエンドプールには、プールで保留されている通話を管理するために使用される、対応するバックエンドサーバー上の "コールパーク" テーブルがあります。</span><span class="sxs-lookup"><span data-stu-id="0685e-124">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="0685e-125">オービット範囲のリストは、一元管理ストアに保存され、orbits を宛先プールにルーティングするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0685e-125">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="0685e-126">コールパークアプリケーションが展開され構成されている各 Skype for Business Server プールは、1つ以上の軌道範囲を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="0685e-126">Each Skype for Business Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="0685e-127">オービット範囲は、Skype for Business Server の展開でグローバルに一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0685e-127">Orbit ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
<span data-ttu-id="0685e-p107">また、通話がタイムアウトになった場合に通話をどこにリダイレクトするのかや、保留になっている発信者に音楽を流すかどうかなど、他のコール パーク設定も構成します。通話が保留になっている間に再生する音楽ファイルも指定できます。</span><span class="sxs-lookup"><span data-stu-id="0685e-p107">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked. You can also specify the music file to play while the call is on hold.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0685e-130">コールパークのカスタマイズされた音楽の保留ファイルは、Skype for Business Server の障害回復プロセスの一部としてはバックアップされません。また、プールにアップロードされたファイルが破損、破損、または消去されると失われます。</span><span class="sxs-lookup"><span data-stu-id="0685e-130">Customized music-on-hold files for Call Park are not backed up as part of the Skype for Business Server disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="0685e-131">コール パーク用にアップロードされているカスタマイズした保留音ファイルについては、常に個別のバックアップ コピーを保持してください。</span><span class="sxs-lookup"><span data-stu-id="0685e-131">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span> 
  
<span data-ttu-id="0685e-132">コール パーク アプリケーションは、エンタープライズ VoIP のコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="0685e-132">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="0685e-133">エンタープライズ Voip を展開すると、コールパークアプリケーションがインストールされて自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="0685e-133">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="0685e-134">ただし、[コールパーク] を使用する前に、エンタープライズボイス管理者が音声ポリシーを使ってそれを構成して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0685e-134">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="0685e-135">展開と要件</span><span class="sxs-lookup"><span data-stu-id="0685e-135">Deployment and requirements</span></span>

<span data-ttu-id="0685e-136">エンタープライズ Voip を展開すると、コールパークアプリケーションが自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="0685e-136">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="0685e-137">音声ポリシーを構成して、コールパークを有効にします。</span><span class="sxs-lookup"><span data-stu-id="0685e-137">You enable Call Park by configuring voice policy.</span></span>
  
### <a name="software-requirements"></a><span data-ttu-id="0685e-138">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="0685e-138">Software requirements</span></span>

<span data-ttu-id="0685e-139">コールパークが展開されているすべてのフロントエンドサーバーおよび標準エディションサーバーには、windows server 2008 R2 を実行しているサーバー、または windows server 2012 または Windows Server を実行しているサーバーの Microsoft メディアファンデーションがインストールされている必要があります。2012 R2。</span><span class="sxs-lookup"><span data-stu-id="0685e-139">All Front End Servers and Standard Edition servers where Call Park is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="0685e-140">Windows Server 2008 R2 の場合、windows Media Format Runtime は Windows デスクトップエクスペリエンスの一部としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="0685e-140">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="0685e-141">Windows media 形式のランタイムまたは Microsoft メディアファンデーションが必要なのは、Windows Media オーディオ (.wma) ファイルで、保留中の音楽の再生が再生されます。</span><span class="sxs-lookup"><span data-stu-id="0685e-141">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>
  
### <a name="port-requirements"></a><span data-ttu-id="0685e-142">ポートの要件</span><span class="sxs-lookup"><span data-stu-id="0685e-142">Port requirements</span></span>

<span data-ttu-id="0685e-143">コールパークアプリケーションは、SIP リスニング要求に**ポート 5075**を使用します。</span><span class="sxs-lookup"><span data-stu-id="0685e-143">The Call Park application uses **Port 5075**  for SIP listening requests.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0685e-144">このポートは既定の設定であり、**Set-CsApplicationServer** コマンドレットを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="0685e-144">This port is a default setting that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="0685e-145">このコマンドレットの詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0685e-145">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>
  
### <a name="audio-file-requirements"></a><span data-ttu-id="0685e-146">オーディオ ファイルの要件</span><span class="sxs-lookup"><span data-stu-id="0685e-146">Audio File requirements</span></span>

<span data-ttu-id="0685e-147">コールパークアプリケーションは、保留中の音楽に対して Windows Media オーディオ (.wma) ファイルのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="0685e-147">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="0685e-148">保留音のファイルをカスタマイズするには、Microsoft Expression Encoder 4 を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0685e-148">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="0685e-149">式エンコーダー4をダウンロードするには、「 [Expression encoder 4」](https://go.microsoft.com/fwlink/p/?linkId=202843)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0685e-149">To download Expression Encoder 4, see   ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span></span> <span data-ttu-id="0685e-150">このツールを使用すると、ファイルを WMA 形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="0685e-150">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="0685e-151">通話パーク音楽の保存に推奨される形式は、メディアオーディオ9、44 kHz、16ビット、モノラル、CBR、32 kbps です。</span><span class="sxs-lookup"><span data-stu-id="0685e-151">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0685e-152">変換されたファイルは、44 kHz で録音された場合でも、電話では 16 kHz でのみ再生されます。</span><span class="sxs-lookup"><span data-stu-id="0685e-152">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span> 
  
## <a name="supported-clients-and-calls"></a><span data-ttu-id="0685e-153">サポートされるクライアントと通話</span><span class="sxs-lookup"><span data-stu-id="0685e-153">Supported clients and calls</span></span>

<span data-ttu-id="0685e-154">次のクライアントと通話の種類は、コールパークでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0685e-154">The following clients and types of calls are supported for Call Park</span></span>
  
### <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="0685e-155">通話の保留をサポートするクライアント</span><span class="sxs-lookup"><span data-stu-id="0685e-155">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="0685e-156">IP、構内交換機 (PBX)、公衆交換電話網 (PSTN)、または携帯電話からの通話を保留できます。</span><span class="sxs-lookup"><span data-stu-id="0685e-156">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0685e-p114">音声通話だけを保留できます。インスタント メッセージと電話会議は保留できません。</span><span class="sxs-lookup"><span data-stu-id="0685e-p114">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span> 
  
<span data-ttu-id="0685e-159">次のクライアントでは、通話パークを使って通話をパークできます。</span><span class="sxs-lookup"><span data-stu-id="0685e-159">The following clients can use Call Park to park calls:</span></span>
  
- <span data-ttu-id="0685e-160">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0685e-160">Skype for Business</span></span>
    
- <span data-ttu-id="0685e-161">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="0685e-161">Lync 2013</span></span>
    
- <span data-ttu-id="0685e-162">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="0685e-162">Lync 2010</span></span>
    
- <span data-ttu-id="0685e-163">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="0685e-163">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="0685e-164">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="0685e-164">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="0685e-165">携帯電話では、通話パークを使って通話をパークすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0685e-165">Mobile phones cannot use Call Park to park calls.</span></span> 
  
### <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="0685e-166">通話の取得をサポートするクライアント</span><span class="sxs-lookup"><span data-stu-id="0685e-166">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="0685e-p115">オービット範囲は仮想の内線番号 (ユーザーまたは電話が割り当てられていない内線番号) のブロックとして構成されます。オービットを仮想の内線番号として構成すると、携帯電話と PSTN 電話は保留された通話を取得できません。</span><span class="sxs-lookup"><span data-stu-id="0685e-p115">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="0685e-169">フェデレーション ユーザーは保留された通話を取得できません。</span><span class="sxs-lookup"><span data-stu-id="0685e-169">Federated users cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="0685e-170">次のクライアントは、コールパークで保留中の通話を取得できます。</span><span class="sxs-lookup"><span data-stu-id="0685e-170">The following clients can retrieve calls that are parked on Call Park:</span></span>
  
- <span data-ttu-id="0685e-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0685e-171">Skype for Business</span></span>
    
- <span data-ttu-id="0685e-172">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="0685e-172">Lync 2013</span></span>
    
- <span data-ttu-id="0685e-173">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="0685e-173">Lync 2010</span></span>
    
- <span data-ttu-id="0685e-174">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="0685e-174">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="0685e-175">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="0685e-175">Lync Phone Edition</span></span>
    
- <span data-ttu-id="0685e-176">IP 共通領域電話</span><span class="sxs-lookup"><span data-stu-id="0685e-176">IP common area phones</span></span>
    
- <span data-ttu-id="0685e-177">Skype for Business Server インフラストラクチャに接続されている IP 以外の電話 (一般的な市外局番と構内交換機 (PBX) 電話など)</span><span class="sxs-lookup"><span data-stu-id="0685e-177">Non-IP phones that are connected to the Skype for Business Server infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>
    
## <a name="call-park-capacity-planning"></a><span data-ttu-id="0685e-178">コール パークの処理能力の計画</span><span class="sxs-lookup"><span data-stu-id="0685e-178">Call Park capacity planning</span></span>

<span data-ttu-id="0685e-179">次の表では、キャパシティ計画の要件の基礎として使用できるコールパークユーザーモデルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0685e-179">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0685e-180">障害復旧のキャパシティ計画として、ペアリングされたプールの各プールは、両方のプールのコールパークサービスのワークロードを処理できる必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0685e-180">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span> 
  
<span data-ttu-id="0685e-181">**コール パークのユーザー モデル**</span><span class="sxs-lookup"><span data-stu-id="0685e-181">**Call Park User Model**</span></span>

|<span data-ttu-id="0685e-182">**指標**</span><span class="sxs-lookup"><span data-stu-id="0685e-182">**Metric**</span></span>|<span data-ttu-id="0685e-183">**フロントエンドプール<br/>あたり (8 個のフロントエンドサーバーを含む)**</span><span class="sxs-lookup"><span data-stu-id="0685e-183">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="0685e-184">**Standard Edition サーバーごと**</span><span class="sxs-lookup"><span data-stu-id="0685e-184">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0685e-185">保留率</span><span class="sxs-lookup"><span data-stu-id="0685e-185">Park rate</span></span>  <br/> |<span data-ttu-id="0685e-186">8 分間に 1 回</span><span class="sxs-lookup"><span data-stu-id="0685e-186">8 per minute</span></span>  <br/> |<span data-ttu-id="0685e-187">1 分間に 1 回</span><span class="sxs-lookup"><span data-stu-id="0685e-187">1 per minute</span></span>  <br/> |
|<span data-ttu-id="0685e-188">取得通話保留率</span><span class="sxs-lookup"><span data-stu-id="0685e-188">Retrieve parked call rate</span></span>  <br/> |<span data-ttu-id="0685e-189">8 分間に 1 回</span><span class="sxs-lookup"><span data-stu-id="0685e-189">8 per minute</span></span>  <br/> |<span data-ttu-id="0685e-190">1 分間に 1 回</span><span class="sxs-lookup"><span data-stu-id="0685e-190">1 per minute</span></span>  <br/> |
|<span data-ttu-id="0685e-191">平均保留時間</span><span class="sxs-lookup"><span data-stu-id="0685e-191">Average park duration</span></span>  <br/> |<span data-ttu-id="0685e-192">60 秒</span><span class="sxs-lookup"><span data-stu-id="0685e-192">60 seconds</span></span>  <br/> |<span data-ttu-id="0685e-193">60 秒</span><span class="sxs-lookup"><span data-stu-id="0685e-193">60 seconds</span></span>  <br/> |
   

