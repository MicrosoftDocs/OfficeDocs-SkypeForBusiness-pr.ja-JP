---
title: 'Lync Server 2013: コールパークの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Call Park
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48184939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22811a0c55f0e0c7a7bfb7f3aeeb3ab5fcbc2653
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530674"
---
# <a name="overview-of-call-park-in-lync-server-2013"></a><span data-ttu-id="ce61d-102">Lync Server 2013 のコールパークの概要</span><span class="sxs-lookup"><span data-stu-id="ce61d-102">Overview of Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce61d-103">_**トピックの最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="ce61d-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="ce61d-104">Lync Server 2013 コールパークアプリケーションを使用すると、エンタープライズ Voip ユーザーは次のいずれかの操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="ce61d-104">The Lync Server 2013 Call Park application lets Enterprise Voice users do any of the following:</span></span>

  - <span data-ttu-id="ce61d-105">通話を保留にしてから、同じ電話または別の電話から通話を取得します。</span><span class="sxs-lookup"><span data-stu-id="ce61d-105">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>

  - <span data-ttu-id="ce61d-106">通話を保留にして、部署または一般エリアに転送します (たとえば、営業部門や、共通領域電話がある倉庫に転送します)。</span><span class="sxs-lookup"><span data-stu-id="ce61d-106">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>

  - <span data-ttu-id="ce61d-107">通話を保留にして、元の応答電話を他の通話に対して無料にします。</span><span class="sxs-lookup"><span data-stu-id="ce61d-107">Put a call on hold and keep the original answering phone free for other calls.</span></span>

<span data-ttu-id="ce61d-108">ユーザーが電話をパークすると、Lync Server は、通話を *オービット*と呼ばれる一時的な番号に転送します。この番号は、通話が取得されるかタイムアウトになるまで保持されます。Lync Server は、呼び出しを保留したユーザーにオービットを送信します。</span><span class="sxs-lookup"><span data-stu-id="ce61d-108">When a user parks a call, Lync Server transfers the call to a temporary number, called an *orbit*, where the call is held until it is retrieved or it times out. Lync Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="ce61d-109">保留された通話を取得するには、ユーザーはオービット番号をダイヤルするか、[会話] ウィンドウで [オービット] リンクまたはボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce61d-109">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span>

<span data-ttu-id="ce61d-110">通話を保留にしたユーザーは、インスタントメッセージング (IM) やページングシステムなどの外部メカニズムを使用して通話を取得することにより、他のユーザーにオービット番号を通知できます。</span><span class="sxs-lookup"><span data-stu-id="ce61d-110">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else.</span></span> <span data-ttu-id="ce61d-111">呼び出しを保留したユーザーは、通話が取得されたときに通知を受け取るための会話ウィンドウを開いたままにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ce61d-111">The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>

<span data-ttu-id="ce61d-112">オービット範囲はグローバルに一意であるため、ルーティングが適切に構成されている場合は、任意の Lync Server サイトまたは PBX 電話からの呼び出しを取得できます。</span><span class="sxs-lookup"><span data-stu-id="ce61d-112">Because orbit ranges are globally unique, it is possible to retrieve calls from any Lync Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="ce61d-113">構成可能な時間内に呼び出しを取得していない場合は、通話が保留されたユーザーに着信が戻されます。</span><span class="sxs-lookup"><span data-stu-id="ce61d-113">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="ce61d-114">その人物がリングバックに応答しない場合、通話は、オペレーターなどのフォールバック先 (構成されている場合) に転送されます。</span><span class="sxs-lookup"><span data-stu-id="ce61d-114">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="ce61d-115">呼び出しが転送される回数を構成できます。この回数を 1 ~ 10 回に設定できます。</span><span class="sxs-lookup"><span data-stu-id="ce61d-115">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="ce61d-116">転送された通話に応答しない場合、通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="ce61d-116">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="ce61d-117">呼び出しが取得または切断されると、オービットは解放されます。</span><span class="sxs-lookup"><span data-stu-id="ce61d-117">The orbit is freed when the call is retrieved or disconnected.</span></span>

<span data-ttu-id="ce61d-118">コールパークを展開する場合は、保留電話の内線番号の範囲を予約する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce61d-118">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="ce61d-119">これらの拡張機能は仮想拡張機能である必要があります。ユーザーまたは電話が割り当てられていない拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="ce61d-119">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="ce61d-120">次に、内線番号の範囲を使用してコールパークオービットテーブルを構成し、各範囲を処理するコールパークアプリケーションをホストするアプリケーションサービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ce61d-120">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="ce61d-121">各フロントエンドプールには、対応するバックエンドサーバー上のコールパークテーブルがあり、これを使用して、プールに保留されている通話を管理します。</span><span class="sxs-lookup"><span data-stu-id="ce61d-121">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="ce61d-122">オービット範囲の一覧は、中央管理ストアに格納され、オービットを宛先プールにルーティングするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ce61d-122">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="ce61d-123">コールパークアプリケーションが展開および構成されている各 Lync Server プールは、1つ以上のオービット範囲を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="ce61d-123">Each Lync Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="ce61d-124">オービット範囲は、Lync Server の展開間でグローバルに一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce61d-124">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<span data-ttu-id="ce61d-125">また、通話がタイムアウトした場合の通話のリダイレクトや、電話のユーザーが保留中に音楽を聞くかどうかなど、他のコールパーク設定も構成します。</span><span class="sxs-lookup"><span data-stu-id="ce61d-125">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked.</span></span> <span data-ttu-id="ce61d-126">通話の保留中に再生する音楽ファイルを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="ce61d-126">You can also specify the music file to play while the call is on hold.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ce61d-127">コールパークのカスタマイズされた保留中のファイルは、Lync Server 2013 の障害復旧プロセスの一部としてはバックアップされず、プールにアップロードされたファイルが破損、破損、または消去されると失われます。</span><span class="sxs-lookup"><span data-stu-id="ce61d-127">Customized music-on-hold files for Call Park are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="ce61d-128">コールパーク用にアップロードしたカスタマイズされた保留音ファイルのバックアップコピーを常に別個に保持します。</span><span class="sxs-lookup"><span data-stu-id="ce61d-128">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="ce61d-129">コールパークアプリケーションは、エンタープライズ Voip のコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="ce61d-129">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="ce61d-130">エンタープライズ Voip を展開すると、コールパークアプリケーションが自動的にインストールされ、アクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="ce61d-130">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="ce61d-131">ただし、コールパークを使用する前に、エンタープライズ Voip 管理者はそれを構成して、音声ポリシーを通じてユーザーに対して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce61d-131">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

