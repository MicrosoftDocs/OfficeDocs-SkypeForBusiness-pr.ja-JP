---
title: 'Lync Server 2013: コールパークの障害復旧の計画'
description: 'Lync Server 2013: コールパーク障害復旧の計画。'
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
ms.openlocfilehash: e1d05503f1d8c30f4dd4446a995442d5e2500dbc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554283"
---
# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="35a28-103">Lync Server 2013 でのコールパーク障害復旧の計画</span><span class="sxs-lookup"><span data-stu-id="35a28-103">Planning for Call Park disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35a28-104">_**トピックの最終更新日:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="35a28-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="35a28-105">このセクションでは、障害復旧のためのコールパークアプリケーションの準備方法と、障害復旧プロセスに関するいくつかの考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="35a28-105">This section describes some ways to prepare the Call Park application for disaster recovery and some considerations for the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a><span data-ttu-id="35a28-106">コールパーク障害復旧の準備</span><span class="sxs-lookup"><span data-stu-id="35a28-106">Preparing for Call Park Disaster Recovery</span></span>

<span data-ttu-id="35a28-107">障害復旧手順を作成し、実行する際は、次に留意してください。</span><span class="sxs-lookup"><span data-stu-id="35a28-107">Keep the following in mind when preparing for and carrying out disaster recovery procedures.</span></span>

  - <span data-ttu-id="35a28-108">処理能力計画を行う際に障害復旧を計画します。</span><span class="sxs-lookup"><span data-stu-id="35a28-108">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="35a28-109">障害復旧のためには、ペアになっているプールの各プールで、両方のプールのコールパークサービスのワークロードを処理できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="35a28-109">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of the Call Park services in both pools.</span></span> <span data-ttu-id="35a28-110">コールパーク容量計画の詳細については、「 [Lync Server 2013 のコールパークの容量計画](lync-server-2013-capacity-planning-for-call-park.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35a28-110">For details about Call Park capacity planning, see [Capacity planning for Call Park in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).</span></span>

  - <span data-ttu-id="35a28-111">障害復旧の間、フェールオーバー プロセスの一部としてバックアップ プールにリダイレクトされたユーザーは、バックアップ プールで実行されるたコール パーク サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="35a28-111">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park service running in the backup pool.</span></span> <span data-ttu-id="35a28-112">そのため、障害復旧時のコールパークのサポートでは、プライマリプールとバックアッププールの両方でコールパークアプリケーションを展開して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="35a28-112">Therefore, support for Call Park during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

  - <span data-ttu-id="35a28-113">各プールは、そのプールに所属しているユーザーがパーキング コールに使用するための有効な範囲のオービット数を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="35a28-113">Each pool must have a valid range of orbit numbers for users who are homed in that pool to use for parking calls.</span></span>

  - <span data-ttu-id="35a28-114">コールパーク用にアップロードされたカスタマイズした保留音のバックアップコピーは常に別個に保管してください。</span><span class="sxs-lookup"><span data-stu-id="35a28-114">Always keep a separate backup copy of any customized music on hold that has been uploaded for Call Park.</span></span> <span data-ttu-id="35a28-115">これらのファイルは、Lync Server 2013 の障害復旧プロセスの一部としてはバックアップされず、プールにアップロードされたファイルが破損、破損、または消去されると、失われます。</span><span class="sxs-lookup"><span data-stu-id="35a28-115">These files are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a><span data-ttu-id="35a28-116">コールパーク障害復旧に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="35a28-116">Call Park Disaster Recovery Considerations</span></span>

<span data-ttu-id="35a28-117">1つのプールに対して1セットのコールパークアプリケーション構成設定と1つのカスタマイズされた音楽オンホールドオーディオファイルのみを定義できます。</span><span class="sxs-lookup"><span data-stu-id="35a28-117">You can define only one set of Call Park application configuration settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="35a28-118">これらの設定には、タイムアウトしきい値、保留音、コール ピックアップの最大試行回数、およびタイムアウト URI が含まれます。</span><span class="sxs-lookup"><span data-stu-id="35a28-118">These settings include the timeout threshold, music on hold, maximum call pickup attempts, and timeout URI.</span></span> <span data-ttu-id="35a28-119">構成設定を表示するには、**Get-CsCpsConfiguration** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="35a28-119">To view these configuration settings, run the **Get-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="35a28-120">**New-cscpsconfiguration**コマンドレットの詳細については、「 [new-cscpsconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35a28-120">For details about the **Get-CsCpsConfiguration** cmdlet, see [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).</span></span>

<span data-ttu-id="35a28-121">障害復旧時に、コールパークはバックアッププール内のコールパークアプリケーションを使用するので、プライマリプールの設定はバックアップされません。</span><span class="sxs-lookup"><span data-stu-id="35a28-121">During disaster recovery, Call Park uses the Call Park application in the backup pool, so settings in the primary pool are not backed up.</span></span> <span data-ttu-id="35a28-122">プライマリプールを回復できない場合に、プライマリプールを置き換える新しいプールを展開すると、プライマリプールからの設定は失われ、新しいプールのコールパーク設定とカスタマイズされた音楽オンホールドオーディオファイルを再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35a28-122">If the primary pool can't be recovered and you deploy a new pool to replace the primary pool, the settings from the primary pool are lost, and you need to reconfigure the Call Park settings and any customized music-on-hold audio files in the new pool.</span></span>

<span data-ttu-id="35a28-123">プライマリプールを置き換えるために別の完全修飾ドメイン名 (FQDN) を使用して新しいプールを展開する場合は、プライマリプールに関連付けられたすべてのコールパークオービット範囲を新しいプールの FQDN に再割り当てする必要があります。</span><span class="sxs-lookup"><span data-stu-id="35a28-123">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Call Park orbit ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="35a28-124">オービット範囲を新しいプールに再割り当てするには、Lync Server コントロールパネルまたは **get-cscallparkorbit** コマンドレットのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="35a28-124">To reassign orbit ranges to the new pool, you can use either Lync Server Control Panel or the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="35a28-125">**Get-cscallparkorbit**コマンドレットの詳細については、「 [get-cscallparkorbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35a28-125">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

