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
ms.openlocfilehash: 755bff84b8902e346135139d1c8c5b26c55605c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="39f71-102">Lync Server 2013 での共有線の外観を計画する</span><span class="sxs-lookup"><span data-stu-id="39f71-102">Plan for Shared Line Appearance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39f71-103">_**最終更新日:** 2016-03-21_</span><span class="sxs-lookup"><span data-stu-id="39f71-103">_**Topic Last Modified:** 2016-03-21_</span></span>

<span data-ttu-id="39f71-104">このトピックでは、Lync Server 2013 での共有線の外観 (SLA) を計画する方法について説明します。累積更新プログラム (2016 年4月)</span><span class="sxs-lookup"><span data-stu-id="39f71-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="39f71-105">共有された線の外観は、Lync Server 2013 の累積更新プログラムである、共有番号という特定の番号での複数の通話を処理するための、2016年4月の機能です。</span><span class="sxs-lookup"><span data-stu-id="39f71-105">Shared Line Appearance is a feature in Lync Server 2013, Cumulative Update April 2016 for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="39f71-106">SLA では、エンタープライズボイス対応の Lync ユーザーを、複数の回線と複数の通話に応答する共有番号として構成できます。</span><span class="sxs-lookup"><span data-stu-id="39f71-106">SLA can configure any enterprise voice enabled Lync user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="39f71-107">実際には共有番号で通話を受信するのではなく、共有番号の代理人として機能するユーザーに通話が転送されます。</span><span class="sxs-lookup"><span data-stu-id="39f71-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="39f71-108">いずれかの代理人が通話に応答すると、残りの代理人は誰が通話に応答したか、またその結果としてどの回線が通話中になったかを示す通知を自分の電話で受け取ります。</span><span class="sxs-lookup"><span data-stu-id="39f71-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="39f71-109">SLA では、回線の番号と代理人の両方を共有番号に対して構成できます。</span><span class="sxs-lookup"><span data-stu-id="39f71-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="39f71-110">さらに、BusyOption (すべての回線が通話中のときに実行する処理) と MissedCallOption (通話に応答できる代理人がいない場合の処理) などの高度なオプションも共有番号に対して構成できます。</span><span class="sxs-lookup"><span data-stu-id="39f71-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>

<span data-ttu-id="39f71-111">SLA は、次の電話デバイスでのみサポートされます (コンピューター、携帯電話、その他のデバイス上の Lync クライアントではサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="39f71-111">SLA is supported only on the following phone devices (it is not supported for Lync clients on computers, mobile phones, or other devices):</span></span>

  - <span data-ttu-id="39f71-112">Polycom VVX300 (ファームウェア更新プログラム 5.4.1 インストール済み)</span><span class="sxs-lookup"><span data-stu-id="39f71-112">Polycom VVX300 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="39f71-113">Polycom VVX400 (ファームウェア更新プログラム 5.4.1 インストール済み)</span><span class="sxs-lookup"><span data-stu-id="39f71-113">Polycom VVX400 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="39f71-114">Polycom VVX500 (ファームウェア更新プログラム 5.4.1 インストール済み)</span><span class="sxs-lookup"><span data-stu-id="39f71-114">Polycom VVX500 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="39f71-115">Polycom VVX600 (ファームウェア更新プログラム 5.4.1 インストール済み)</span><span class="sxs-lookup"><span data-stu-id="39f71-115">Polycom VVX600 with firmware update 5.4.1</span></span>

<span data-ttu-id="39f71-116">SLA は、Lync Server 2013 の累積更新プログラム、2016年4月の新機能です。</span><span class="sxs-lookup"><span data-stu-id="39f71-116">SLA is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="39f71-117">SLA の展開については、「 [Lync Server 2013 で共有線の外観を展開](lync-server-2013-deploy-shared-line-appearance.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39f71-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span></span>

<div>

## <a name="feature-list"></a><span data-ttu-id="39f71-118">機能リスト</span><span class="sxs-lookup"><span data-stu-id="39f71-118">Feature List</span></span>

<span data-ttu-id="39f71-119">SLA グループをセットアップすると次のことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="39f71-119">Setting up an SLA group enables the following:</span></span>

  - <span data-ttu-id="39f71-p102">グループ内のすべての代理人が同じ共有番号への着信通話に応答できます。PSTN ベースまたは SIP ベースの通話を利用できます。</span><span class="sxs-lookup"><span data-stu-id="39f71-p102">All delegates in the group can answer inbound calls to the same shared number. The calls can be PSTN-based or SIP-based.</span></span>

  - <span data-ttu-id="39f71-122">代理人は、通話に応答することも保留にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="39f71-122">Delegates can hold and pick up calls.</span></span>

  - <span data-ttu-id="39f71-123">代理人は、SLA グループの外部の番号に通話を転送できます。</span><span class="sxs-lookup"><span data-stu-id="39f71-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>

  - <span data-ttu-id="39f71-124">代理人は、現在の共有番号上の通話数と、それらの各通話のステータスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="39f71-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>

  - <span data-ttu-id="39f71-p103">共有番号で受信する通話の最大数を構成できます。この最大数に達した後にかかってきた通話の処理方法も設定できます。その後の通話に対しては、話中音を流すか、代替番号に転送するか、ボイス メールに転送できます。</span><span class="sxs-lookup"><span data-stu-id="39f71-p103">You can configure a maximum number of concurrent calls for the shared number. You can also set how you want additional calls to be handled after this maximum is reached. Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>

  - <span data-ttu-id="39f71-p104">不在着信 (一定の時間が経過しても応答されなかった通話) の処理方法を構成できます。グループ ID のボイス メールを有効にした場合、不在着信は自動的にボイス メールに転送されます。グループ ID (共有番号) のボイス メールを有効にしない場合、不在着信に対して話中音を流すか、代替番号に転送するか、切断するかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="39f71-p104">You can configure how you want missed calls (calls not picked up after a certain time) to be handled. If you enable voice mail for the group identity, missed calls automatically go to voice mail. If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

