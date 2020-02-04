---
title: 'Lync Server 2013: コール パーク障害復旧の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Call Park disaster recovery
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48185867
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a76052297e527e24fd3daf0c03d02661c7ddc255
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41754457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="6d58b-102">Lync Server 2013 でのコール パーク障害復旧の計画</span><span class="sxs-lookup"><span data-stu-id="6d58b-102">Planning for Call Park disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d58b-103">_**最終更新日:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="6d58b-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="6d58b-104">このセクションでは、障害回復用のコールパークアプリケーションを準備する方法と、障害回復プロセスの考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="6d58b-104">This section describes some ways to prepare the Call Park application for disaster recovery and some considerations for the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a><span data-ttu-id="6d58b-105">コールパークの障害回復の準備</span><span class="sxs-lookup"><span data-stu-id="6d58b-105">Preparing for Call Park Disaster Recovery</span></span>

<span data-ttu-id="6d58b-106">障害回復の手順を準備して実行する場合は、次の点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="6d58b-106">Keep the following in mind when preparing for and carrying out disaster recovery procedures.</span></span>

  - <span data-ttu-id="6d58b-107">キャパシティ計画を行うときの障害回復計画を立てます。</span><span class="sxs-lookup"><span data-stu-id="6d58b-107">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="6d58b-108">障害回復キャパシティの場合、ペア化されたプール内の各プールは、両方のプールのコールパークサービスの作業負荷を処理できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d58b-108">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of the Call Park services in both pools.</span></span> <span data-ttu-id="6d58b-109">通話パークキャパシティ計画の詳細については、「 [Lync Server 2013 でのコールパークのキャパシティ計画](lync-server-2013-capacity-planning-for-call-park.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d58b-109">For details about Call Park capacity planning, see [Capacity planning for Call Park in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).</span></span>

  - <span data-ttu-id="6d58b-110">障害回復中に、フェールオーバープロセスの一環としてバックアッププールにリダイレクトされたユーザーは、バックアッププールで実行されているコールパークサービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="6d58b-110">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park service running in the backup pool.</span></span> <span data-ttu-id="6d58b-111">そのため、障害回復中のコールパークのサポートでは、プライマリプールとバックアッププールの両方でコールパークアプリケーションを展開して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d58b-111">Therefore, support for Call Park during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

  - <span data-ttu-id="6d58b-112">各プールには、そのプールに所属しているユーザーがパーキング通話に使用するために、有効な範囲の軌道番号が必要です。</span><span class="sxs-lookup"><span data-stu-id="6d58b-112">Each pool must have a valid range of orbit numbers for users who are homed in that pool to use for parking calls.</span></span>

  - <span data-ttu-id="6d58b-113">通話パーク用にアップロードされた、カスタマイズした音楽の個別のバックアップコピーを常に保持しておきます。</span><span class="sxs-lookup"><span data-stu-id="6d58b-113">Always keep a separate backup copy of any customized music on hold that has been uploaded for Call Park.</span></span> <span data-ttu-id="6d58b-114">これらのファイルは、Lync Server 2013 の障害回復プロセスの一部としてはバックアップされません。また、プールにアップロードされたファイルが破損、破損、または消去された場合は、失われます。</span><span class="sxs-lookup"><span data-stu-id="6d58b-114">These files are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a><span data-ttu-id="6d58b-115">コールパーク障害回復に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="6d58b-115">Call Park Disaster Recovery Considerations</span></span>

<span data-ttu-id="6d58b-116">1組のコールパークアプリケーションの構成設定と、1つのプールにつき1つのカスタマイズされた音楽オンホールドオーディオファイルを定義できます。</span><span class="sxs-lookup"><span data-stu-id="6d58b-116">You can define only one set of Call Park application configuration settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="6d58b-117">これらの設定には、タイムアウトしきい値、保留中の音楽、最大通話ピックアップ試行回数、タイムアウト URI が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6d58b-117">These settings include the timeout threshold, music on hold, maximum call pickup attempts, and timeout URI.</span></span> <span data-ttu-id="6d58b-118">これらの構成設定を表示するには、 **CsCpsConfiguration**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d58b-118">To view these configuration settings, run the **Get-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="6d58b-119">**CsCpsConfiguration**コマンドレットの詳細については、「 [get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d58b-119">For details about the **Get-CsCpsConfiguration** cmdlet, see [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).</span></span>

<span data-ttu-id="6d58b-120">障害回復中に、コールパークはバックアッププールのコールパークアプリケーションを使用するため、プライマリプールの設定はバックアップされません。</span><span class="sxs-lookup"><span data-stu-id="6d58b-120">During disaster recovery, Call Park uses the Call Park application in the backup pool, so settings in the primary pool are not backed up.</span></span> <span data-ttu-id="6d58b-121">プライマリプールを復元できない場合に、プライマリプールの代わりに新しいプールを展開すると、プライマリプールの設定は失われ、新規プール内のコールパーク設定とカスタマイズされた音楽の保留中のオーディオファイルを再設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d58b-121">If the primary pool can't be recovered and you deploy a new pool to replace the primary pool, the settings from the primary pool are lost, and you need to reconfigure the Call Park settings and any customized music-on-hold audio files in the new pool.</span></span>

<span data-ttu-id="6d58b-122">別の完全修飾ドメイン名 (FQDN) で新しいプールを展開してプライマリプールを置き換える場合は、プライマリプールに関連付けられていたすべてのコールパークの範囲を、新しいプールの FQDN に再割り当てする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d58b-122">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Call Park orbit ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="6d58b-123">新しいプールに軌道範囲を再割り当てするには、Lync Server コントロールパネルまたは**CsCallParkOrbit**コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6d58b-123">To reassign orbit ranges to the new pool, you can use either Lync Server Control Panel or the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="6d58b-124">**CsCallParkOrbit**コマンドレットの詳細については、「 [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d58b-124">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

