---
title: 'Lync Server 2013: コールパークの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Call Park
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48184939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2d6f6b8f0f6a91e75071c7d103cf4bff3b4be1f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-park-in-lync-server-2013"></a><span data-ttu-id="1496c-102">Lync Server 2013 のコールパークの概要</span><span class="sxs-lookup"><span data-stu-id="1496c-102">Overview of Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1496c-103">_**最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="1496c-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="1496c-104">Lync Server 2013 Call パークアプリケーションを使うと、エンタープライズ Voip ユーザーは次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1496c-104">The Lync Server 2013 Call Park application lets Enterprise Voice users do any of the following:</span></span>

  - <span data-ttu-id="1496c-105">通話を保留にして、同じ電話や別の電話で通話に応答する。</span><span class="sxs-lookup"><span data-stu-id="1496c-105">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>

  - <span data-ttu-id="1496c-106">通話を保留にして、営業部門や倉庫など、共通領域電話が使用されている部門または一般的な領域に転送する。</span><span class="sxs-lookup"><span data-stu-id="1496c-106">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>

  - <span data-ttu-id="1496c-107">通話を保留にして、他の通話に元のボイス メールを使用できるようにする。</span><span class="sxs-lookup"><span data-stu-id="1496c-107">Put a call on hold and keep the original answering phone free for other calls.</span></span>

<span data-ttu-id="1496c-108">ユーザーが電話にパークすると、Lync Server は、着信が転送されるまで、またはタイムアウトするまで、通話を保持している一時的な番号 (*オービット*) に転送します。通話を保留したユーザーに、軌道が送信されます。</span><span class="sxs-lookup"><span data-stu-id="1496c-108">When a user parks a call, Lync Server transfers the call to a temporary number, called an *orbit*, where the call is held until it is retrieved or it times out. Lync Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="1496c-109">保留にした通話に応答するには、ユーザーはオービット番号をダイヤルするか、[会話] ウィンドウでオービット リンクまたはボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1496c-109">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span>

<span data-ttu-id="1496c-p102">通話を保留にしたユーザーは、他のユーザーにオービット番号を連絡するために、インスタント メッセージング (IM) やポケットベルなどの外部の機能を使用して、他のユーザーに通話を知らせて応答させることができます。通話を保留にしたユーザーは、[会話] ウィンドウを開いたままにして、通話が応答されたときに通知を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="1496c-p102">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else. The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>

<span data-ttu-id="1496c-112">オービット範囲はグローバルに一意であるため、ルーティングが適切に構成されている場合は、任意の Lync Server サイトまたは PBX 携帯電話からの通話を取得できます。</span><span class="sxs-lookup"><span data-stu-id="1496c-112">Because orbit ranges are globally unique, it is possible to retrieve calls from any Lync Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="1496c-113">構成可能な時間内で通話に応答するユーザーがいない場合、通話を保留にしたユーザーが再度呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1496c-113">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="1496c-114">そのユーザーが再度の呼び出しに応答しない場合、通話はフォールバック先 (構成内容に応じてオペレーターなど) に転送されます。</span><span class="sxs-lookup"><span data-stu-id="1496c-114">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="1496c-115">通話が転送される前に、1 ～ 10 回まで再度呼び出す回数を構成できます。</span><span class="sxs-lookup"><span data-stu-id="1496c-115">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="1496c-116">転送された通話にだれも応答しない場合、その通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="1496c-116">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="1496c-117">通話が応答または切断されると、オービットは解放されます。</span><span class="sxs-lookup"><span data-stu-id="1496c-117">The orbit is freed when the call is retrieved or disconnected.</span></span>

<span data-ttu-id="1496c-118">コール パークを展開する場合、通話を保留するために、内線番号の範囲を予約する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1496c-118">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="1496c-119">これらの内線番号は、ユーザーや電話が割り当てられていない、仮想の内線番号にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1496c-119">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="1496c-120">次に、その内線番号の範囲を使用してコール パーク オービット テーブルを構成し、各範囲を処理するコール パーク アプリケーションをホストするアプリケーション サービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="1496c-120">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="1496c-121">各フロントエンドプールには、プールで保留されている通話を管理するために使用される、対応するバックエンドサーバー上の "コールパーク" テーブルがあります。</span><span class="sxs-lookup"><span data-stu-id="1496c-121">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="1496c-122">オービット範囲のリストは、一元管理ストアに保存され、orbits を宛先プールにルーティングするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1496c-122">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="1496c-123">コールパークアプリケーションが展開され構成されている各 Lync サーバープールは、1つ以上の軌道範囲を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="1496c-123">Each Lync Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="1496c-124">オービット範囲は、Lync Server 展開でグローバルに一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1496c-124">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<span data-ttu-id="1496c-p105">また、通話がタイムアウトになった場合に通話をどこにリダイレクトするのかや、保留になっている発信者に音楽を流すかどうかなど、他のコール パーク設定も構成します。通話が保留になっている間に再生する音楽ファイルも指定できます。</span><span class="sxs-lookup"><span data-stu-id="1496c-p105">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked. You can also specify the music file to play while the call is on hold.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1496c-127">コールパークのカスタマイズされた音楽保留ファイルは、Lync Server 2013 の障害回復プロセスの一環としてはバックアップされず、プールにアップロードされたファイルが破損、破損、または消去された場合は、失われます。</span><span class="sxs-lookup"><span data-stu-id="1496c-127">Customized music-on-hold files for Call Park are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="1496c-128">コール パーク用にアップロードされているカスタマイズした保留音ファイルについては、常に個別のバックアップ コピーを保持してください。</span><span class="sxs-lookup"><span data-stu-id="1496c-128">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="1496c-129">コール パーク アプリケーションは、エンタープライズ VoIP のコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="1496c-129">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="1496c-130">エンタープライズ Voip を展開すると、コールパークアプリケーションがインストールされて自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="1496c-130">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="1496c-131">ただし、[コールパーク] を使用する前に、エンタープライズボイス管理者が音声ポリシーを使ってそれを構成して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1496c-131">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

