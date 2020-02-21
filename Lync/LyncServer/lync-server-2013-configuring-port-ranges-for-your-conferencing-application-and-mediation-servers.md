---
title: 'Lync Server 2013: 会議、アプリケーション、および仲介サーバーのポート範囲の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Conferencing, Application, and Mediation servers
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
ms.date: 05/01/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3c1666e0f1c6f4c208cf5664741ca7cedbe6a1f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="95f51-102">Lync Server 2013 での会議、アプリケーション、および仲介サーバー用のポート範囲の構成</span><span class="sxs-lookup"><span data-stu-id="95f51-102">Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95f51-103">_**トピックの最終更新日:** 2015-04-30_</span><span class="sxs-lookup"><span data-stu-id="95f51-103">_**Topic Last Modified:** 2015-04-30_</span></span>

<span data-ttu-id="95f51-104">サービスの品質を実装するには、電話会議、アプリケーション、および仲介サーバー上で音声、ビデオ、アプリケーション共有に対して同一のポート範囲を構成する必要があります。さらに、これらのポート範囲は、どのような方法でも重複してはなりません。</span><span class="sxs-lookup"><span data-stu-id="95f51-104">In order to implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way.</span></span> <span data-ttu-id="95f51-105">簡単な例を使用するために、電話会議サーバー上のビデオに 1万 ~ 10999 のポートを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="95f51-105">To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers.</span></span> <span data-ttu-id="95f51-106">そのため、アプリケーションおよび仲介サーバーでは、ビデオ用にポート 1万 ~ 10999 も予約する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95f51-106">That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers.</span></span> <span data-ttu-id="95f51-107">指定しない場合、QoS は予想どおりに機能しません。</span><span class="sxs-lookup"><span data-stu-id="95f51-107">If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="95f51-108">同様に、ビデオ用にポート 1万 ~ 10999 を予約していて、オーディオ用にポート 10500 ~ 11999 を予約しているとします。</span><span class="sxs-lookup"><span data-stu-id="95f51-108">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio.</span></span> <span data-ttu-id="95f51-109">これにより、ポート範囲が重複するため、サービスの品質の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="95f51-109">This can create problems for Quality of Service, because the port ranges overlap.</span></span> <span data-ttu-id="95f51-110">QoS では、各モダリティに固有のポートセットが必要です。ポート 1万 ~ 10999 をビデオに使用する場合は、別の範囲 (たとえば、11000 ~ 11999 for audio) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95f51-110">With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999 for audio).</span></span>

<span data-ttu-id="95f51-111">既定では、オーディオおよびビデオのポート範囲は Microsoft Lync Server 2013 では重複していません。ただし、アプリケーション共有に割り当てられているポート範囲は、オーディオポートとビデオポート範囲の両方と重なっています。</span><span class="sxs-lookup"><span data-stu-id="95f51-111">By default, audio and video port ranges do not overlap in Microsoft Lync Server 2013; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="95f51-112">(つまり、これらの範囲が一意ではないことを意味します)。Lync Server 2013 管理シェルから次の3つのコマンドを実行することによって、会議、アプリケーション、および仲介サーバーの既存のポート範囲を確認できます。</span><span class="sxs-lookup"><span data-stu-id="95f51-112">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> <span data-ttu-id="95f51-113">上記のコマンドでわかるように、各ポートの種類–オーディオ、ビデオ、およびアプリケーション共有–には、ポートの開始とポート数という2つの個別のプロパティ値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="95f51-113">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count.</span></span> <span data-ttu-id="95f51-114">ポートの開始は、そのモダリティで使用される最初のポートを示します。たとえば、オーディオポートの start が5万の場合は、オーディオトラフィックに使用される最初のポートはポート5万であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="95f51-114">The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000.</span></span> <span data-ttu-id="95f51-115">オーディオポート数が 2 (有効な値ではありませんが、ここでは説明のために使用されています) の場合は、2つのポートのみがオーディオに割り当てられることを意味します。</span><span class="sxs-lookup"><span data-stu-id="95f51-115">If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes) that means that only 2 ports are allocated for audio.</span></span> <span data-ttu-id="95f51-116">最初のポートがポート5万で、合計2つのポートがある場合、2番目のポートはポート50001でなければなりません (ポート範囲は連続している必要があります)。</span><span class="sxs-lookup"><span data-stu-id="95f51-116">If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous).</span></span> <span data-ttu-id="95f51-117">その結果、音声のポート範囲は 5万 ~ 50001 のポートになります。</span><span class="sxs-lookup"><span data-stu-id="95f51-117">As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><span data-ttu-id="95f51-118">また、アプリケーションサーバーと仲介サーバーがオーディオ用に QoS をサポートしていることにも注意してください。アプリケーションサーバーまたは仲介サーバーでは、ビデオまたはアプリケーション共有のポートを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="95f51-118">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>



</div>

<span data-ttu-id="95f51-119">上記の3つのコマンドを実行すると、Lync Server 2013 の既定のポート値は次のように構成されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="95f51-119">If you run the preceding three commands you'll see that the default port values for Lync Server 2013 are configured like this:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95f51-120">プロパティ</span><span class="sxs-lookup"><span data-stu-id="95f51-120">Property</span></span></th>
<th><span data-ttu-id="95f51-121">Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="95f51-121">Conferencing Server</span></span></th>
<th><span data-ttu-id="95f51-122">アプリケーション サーバー</span><span class="sxs-lookup"><span data-stu-id="95f51-122">Application Server</span></span></th>
<th><span data-ttu-id="95f51-123">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="95f51-123">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95f51-124">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="95f51-124">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="95f51-125">49152</span><span class="sxs-lookup"><span data-stu-id="95f51-125">49152</span></span></p></td>
<td><p><span data-ttu-id="95f51-126">49152</span><span class="sxs-lookup"><span data-stu-id="95f51-126">49152</span></span></p></td>
<td><p><span data-ttu-id="95f51-127">49152</span><span class="sxs-lookup"><span data-stu-id="95f51-127">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f51-128">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="95f51-128">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="95f51-129">8348</span><span class="sxs-lookup"><span data-stu-id="95f51-129">8348</span></span></p></td>
<td><p><span data-ttu-id="95f51-130">8348</span><span class="sxs-lookup"><span data-stu-id="95f51-130">8348</span></span></p></td>
<td><p><span data-ttu-id="95f51-131">8348</span><span class="sxs-lookup"><span data-stu-id="95f51-131">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f51-132">VideoPortStart</span><span class="sxs-lookup"><span data-stu-id="95f51-132">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="95f51-133">57501</span><span class="sxs-lookup"><span data-stu-id="95f51-133">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f51-134">VideoPortCount</span><span class="sxs-lookup"><span data-stu-id="95f51-134">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="95f51-135">8034</span><span class="sxs-lookup"><span data-stu-id="95f51-135">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f51-136">ApplicationSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="95f51-136">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="95f51-137">49152</span><span class="sxs-lookup"><span data-stu-id="95f51-137">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f51-138">ApplicationSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="95f51-138">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="95f51-139">16383</span><span class="sxs-lookup"><span data-stu-id="95f51-139">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="95f51-140">前述したように、QoS 用に Lync Server ポートを構成する場合は、会議、アプリケーション、および仲介サーバー間でのオーディオポート設定が同一であることを確認する必要があります。and, 2) のポート範囲が重なっていません。</span><span class="sxs-lookup"><span data-stu-id="95f51-140">As noted previously, when configuring Lync Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="95f51-141">上記の表をよく見ると、3つのサーバーの種類でポート範囲が同一であることがわかります。</span><span class="sxs-lookup"><span data-stu-id="95f51-141">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="95f51-142">たとえば、開始オーディオポートは、各サーバーの種類のポート49152に設定され、各サーバーのオーディオ用に予約されているポートの合計数も8348になります。</span><span class="sxs-lookup"><span data-stu-id="95f51-142">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="95f51-143">ただし、ポートの範囲が重複しています。オーディオポートはポート49152で開始されますが、アプリケーション共有のためにポートが設定されています。</span><span class="sxs-lookup"><span data-stu-id="95f51-143">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="95f51-144">サービスの品質を最大限に利用するためには、一意のポート範囲を使用するようにアプリケーション共有を再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95f51-144">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="95f51-145">たとえば、ポート40803で開始し、8348ポートを使用するようにアプリケーション共有を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="95f51-145">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="95f51-146">(8348 ポートがあるのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="95f51-146">(Why 8348 ports?</span></span> <span data-ttu-id="95f51-147">これら 8348 40803 の値を一緒に追加すると、アプリケーション共有でポート40803をポート49150が使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="95f51-147">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="95f51-148">オーディオポートはポート49152まで開始されないため、重複するポート範囲がなくなります。</span><span class="sxs-lookup"><span data-stu-id="95f51-148">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="95f51-149">アプリケーション共有の新しいポート範囲を選択したら、CsConferencingServer コマンドレットを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="95f51-149">After you have selected the new port range for application sharing you can make your change by using the Set-CsConferencingServer cmdlet.</span></span> <span data-ttu-id="95f51-150">このようなサーバーはアプリケーション共有トラフィックを処理しないので、アプリケーションサーバーまたは仲介サーバーでこの変更を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="95f51-150">This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic.</span></span> <span data-ttu-id="95f51-151">オーディオトラフィックに使用するポートを再割り当てする場合にのみ、これらのサーバーのポート値を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95f51-151">You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="95f51-152">単一の会議サーバーでアプリケーション共有のポート値を変更するには、Lync Server 管理シェルで次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="95f51-152">To modify the port values for application sharing on a single Conferencing server run a command similar to this from within the Lync Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="95f51-153">すべての会議サーバーでこれらの変更を行う場合は、代わりに次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="95f51-153">If you want to make these changes on all your Conferencing servers you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="95f51-154">ポート設定を変更した後は、変更によって影響を受ける各サービスを停止してから再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95f51-154">After changing port settings you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="95f51-155">会議サーバー、アプリケーションサーバー、および仲介サーバーが同一のポート範囲を共有していることは必須ではありません。実際に必要なのは、すべてのサーバーに固有のポート範囲を設定することだけです。</span><span class="sxs-lookup"><span data-stu-id="95f51-155">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers.</span></span> <span data-ttu-id="95f51-156">ただし、すべてのサーバーで同じポートセットを使用すると、通常、管理が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="95f51-156">However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

