---
title: 'Lync Server 2013: 共有線の外観を計画する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Shared Line Appearance
ms:assetid: a35c83d8-f531-445b-a8d2-d5d8cec77c6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712151(v=OCS.15)
ms:contentKeyID: 72522136
ms.date: 03/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef6bb768ca892aa684613d1261d88266237ab111
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="c61c2-102">Lync Server 2013 での共有線の外観を計画する</span><span class="sxs-lookup"><span data-stu-id="c61c2-102">Plan for Shared Line Appearance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c61c2-103">_**トピックの最終更新日:** 2016-03-21_</span><span class="sxs-lookup"><span data-stu-id="c61c2-103">_**Topic Last Modified:** 2016-03-21_</span></span>

<span data-ttu-id="c61c2-104">このトピックでは、Lync Server 2013 (累積更新プログラム4月 2016) での共有回線の外観 (SLA) の計画方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c61c2-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="c61c2-105">共有線の外観は、Lync Server 2013 の機能で、累積的な更新プログラム4月2016は、共有番号と呼ばれる特定の番号で複数の通話を処理します。</span><span class="sxs-lookup"><span data-stu-id="c61c2-105">Shared Line Appearance is a feature in Lync Server 2013, Cumulative Update April 2016 for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="c61c2-106">SLA では、エンタープライズ voip が有効な Lync ユーザーが複数の通話に応答するために複数の回線を使用して共有番号として構成することができます。</span><span class="sxs-lookup"><span data-stu-id="c61c2-106">SLA can configure any enterprise voice enabled Lync user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="c61c2-107">呼び出しは、実際には共有番号で受信されません。代わりに、共有番号の代理人として機能するユーザーに転送されます。</span><span class="sxs-lookup"><span data-stu-id="c61c2-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="c61c2-108">いずれかの代理人が通話を取得できますが、残りの代理人は通話をピックアップしたユーザーと、その結果としてどの回線がビジー状態になったかについての通知を電話で受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c61c2-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="c61c2-109">行数と代理人の両方が、SLA の共有番号に対して構成できます。</span><span class="sxs-lookup"><span data-stu-id="c61c2-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="c61c2-110">さらに、BusyOption などの高度なオプション (すべての回線がビジー状態で行われる状況) および MissedCallOption (代理人が通話を選択しない場合) は、共有番号に対しても構成できます。</span><span class="sxs-lookup"><span data-stu-id="c61c2-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>

<span data-ttu-id="c61c2-111">SLA は、次の電話デバイスでのみサポートされます (コンピューター、携帯電話、その他のデバイス上の Lync クライアントではサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="c61c2-111">SLA is supported only on the following phone devices (it is not supported for Lync clients on computers, mobile phones, or other devices):</span></span>

  - <span data-ttu-id="c61c2-112">Polycom VVX300 with ファームウェア更新5.4.1</span><span class="sxs-lookup"><span data-stu-id="c61c2-112">Polycom VVX300 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="c61c2-113">Polycom VVX400 with ファームウェア更新5.4.1</span><span class="sxs-lookup"><span data-stu-id="c61c2-113">Polycom VVX400 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="c61c2-114">Polycom VVX500 with ファームウェア更新5.4.1</span><span class="sxs-lookup"><span data-stu-id="c61c2-114">Polycom VVX500 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="c61c2-115">Polycom VVX600 with ファームウェア更新5.4.1</span><span class="sxs-lookup"><span data-stu-id="c61c2-115">Polycom VVX600 with firmware update 5.4.1</span></span>

<span data-ttu-id="c61c2-116">SLA は、Lync Server 2013 の新しい機能で、累積更新プログラムは4月2016です。</span><span class="sxs-lookup"><span data-stu-id="c61c2-116">SLA is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="c61c2-117">SLA の展開については、「 [Lync Server 2013 での共有線の外観の展開](lync-server-2013-deploy-shared-line-appearance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c61c2-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span></span>

<div>

## <a name="feature-list"></a><span data-ttu-id="c61c2-118">機能リスト</span><span class="sxs-lookup"><span data-stu-id="c61c2-118">Feature List</span></span>

<span data-ttu-id="c61c2-119">SLA グループを設定すると、次のことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="c61c2-119">Setting up an SLA group enables the following:</span></span>

  - <span data-ttu-id="c61c2-120">グループ内のすべての委任は、同じ共有番号への着信呼び出しに応答できます。</span><span class="sxs-lookup"><span data-stu-id="c61c2-120">All delegates in the group can answer inbound calls to the same shared number.</span></span> <span data-ttu-id="c61c2-121">通話は、PSTN ベースまたは SIP ベースの場合があります。</span><span class="sxs-lookup"><span data-stu-id="c61c2-121">The calls can be PSTN-based or SIP-based.</span></span>

  - <span data-ttu-id="c61c2-122">代理人は、通話を保留および取得できます。</span><span class="sxs-lookup"><span data-stu-id="c61c2-122">Delegates can hold and pick up calls.</span></span>

  - <span data-ttu-id="c61c2-123">代理人は、SLA グループの外部の番号に通話を転送できます。</span><span class="sxs-lookup"><span data-stu-id="c61c2-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>

  - <span data-ttu-id="c61c2-124">代理人は、現在共有番号にある通話数を確認したり、それぞれの通話の状態を表示したりできます。</span><span class="sxs-lookup"><span data-stu-id="c61c2-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>

  - <span data-ttu-id="c61c2-125">共有番号に対して同時呼び出しの最大数を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c61c2-125">You can configure a maximum number of concurrent calls for the shared number.</span></span> <span data-ttu-id="c61c2-126">また、この最大数に達した後に、追加の呼び出しを処理する方法を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c61c2-126">You can also set how you want additional calls to be handled after this maximum is reached.</span></span> <span data-ttu-id="c61c2-127">余分な通話は、通話中の信号を使用して拒否したり、代替番号に転送したり、ボイスメールに転送したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="c61c2-127">Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>

  - <span data-ttu-id="c61c2-128">不在着信 (一定の時間が経過した後に呼び出されなかった通話) を処理する方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c61c2-128">You can configure how you want missed calls (calls not picked up after a certain time) to be handled.</span></span> <span data-ttu-id="c61c2-129">グループ id に対してボイスメールを有効にした場合、不在着信は自動的にボイスメールに移動します。</span><span class="sxs-lookup"><span data-stu-id="c61c2-129">If you enable voice mail for the group identity, missed calls automatically go to voice mail.</span></span> <span data-ttu-id="c61c2-130">グループ id (共有番号) に対してボイスメールが有効になっていない場合、不在着信を拒否する場合は、通話中の信号を使用して拒否するか、代替番号に転送するか、または切断するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c61c2-130">If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

