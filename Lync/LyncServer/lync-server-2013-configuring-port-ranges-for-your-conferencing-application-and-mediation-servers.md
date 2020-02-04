---
title: 'Lync Server 2013: 会議、アプリケーション、および仲介サーバーのポート範囲を構成する'
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
ms.openlocfilehash: 54aab5efbca06d918cc2dbeccc0e36aee9d4abf8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="9a21b-102">Lync Server 2013 での、会議、アプリケーション、および仲介サーバー向けのポート範囲の構成</span><span class="sxs-lookup"><span data-stu-id="9a21b-102">Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a21b-103">_**最終更新日:** 2015-04-30_</span><span class="sxs-lookup"><span data-stu-id="9a21b-103">_**Topic Last Modified:** 2015-04-30_</span></span>

<span data-ttu-id="9a21b-104">サービスの品質を実現するには、会議、アプリケーション、および仲介サーバー上で音声、ビデオ、およびアプリケーション共有用に同一のポート範囲を構成する必要があります。さらに、これらのポート範囲は、何らかの方法でオーバーラップすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9a21b-104">In order to implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way.</span></span> <span data-ttu-id="9a21b-105">簡単な例を使用するには、電話会議サーバー上のビデオに 1万 ~ 10999 のポートを使用しているとします。</span><span class="sxs-lookup"><span data-stu-id="9a21b-105">To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers.</span></span> <span data-ttu-id="9a21b-106">つまり、アプリケーションや仲介サーバー上のビデオ用に、1万 ~ 10999 のポートを予約する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a21b-106">That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers.</span></span> <span data-ttu-id="9a21b-107">そうしないと、QoS は期待どおりに動作しません。</span><span class="sxs-lookup"><span data-stu-id="9a21b-107">If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="9a21b-108">同様に、1万 ~ 10999 のビデオ用にポートを予約していて、オーディオ用にポート10500から11999を予約したとします。</span><span class="sxs-lookup"><span data-stu-id="9a21b-108">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio.</span></span> <span data-ttu-id="9a21b-109">これにより、ポートの範囲が重複するため、サービスの品質に関する問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9a21b-109">This can create problems for Quality of Service, because the port ranges overlap.</span></span> <span data-ttu-id="9a21b-110">QoS では、各モダリティに固有のポートセットが必要です。ビデオ用に 1万 ~ 10999 のポートを使用している場合は、別の範囲を使用する必要があります (たとえば、11000から11999を使用してください)。</span><span class="sxs-lookup"><span data-stu-id="9a21b-110">With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999 for audio).</span></span>

<span data-ttu-id="9a21b-111">既定では、オーディオとビデオのポート範囲は Microsoft Lync Server 2013 では重複しません。ただし、アプリケーション共有に割り当てられているポート範囲は、オーディオポート範囲とビデオポート範囲の両方と重複しています。</span><span class="sxs-lookup"><span data-stu-id="9a21b-111">By default, audio and video port ranges do not overlap in Microsoft Lync Server 2013; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="9a21b-112">(これにより、これらの範囲のいずれも一意ではないことを意味します)。Lync Server 2013 管理シェル内から次の3つのコマンドを実行して、会議、アプリケーション、および仲介サーバーの既存のポート範囲を確認できます。</span><span class="sxs-lookup"><span data-stu-id="9a21b-112">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> <span data-ttu-id="9a21b-113">上に示したように、各ポートの種類 (オーディオ、ビデオ、およびアプリケーションの共有) には、ポートの開始とポート数という2つの個別のプロパティ値が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="9a21b-113">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count.</span></span> <span data-ttu-id="9a21b-114">ポート start は、そのモダリティで使用される最初のポートを示します。たとえば、オーディオポートの start が5万に等しい場合、オーディオトラフィックに使われる最初のポートがポート5万であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="9a21b-114">The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000.</span></span> <span data-ttu-id="9a21b-115">オーディオポート数が 2 (有効な値ではありませんが、ここでは説明のために使用されます) である場合、オーディオには2つのポートしか割り当てられないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="9a21b-115">If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes) that means that only 2 ports are allocated for audio.</span></span> <span data-ttu-id="9a21b-116">第1のポートがポート5万であり、合計2つのポートがある場合は、2番目のポートがポート 50001 (ポート範囲は連続している必要があります) であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="9a21b-116">If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous).</span></span> <span data-ttu-id="9a21b-117">その結果、オーディオのポート範囲は、5万 ~ 50001 のポートになります。</span><span class="sxs-lookup"><span data-stu-id="9a21b-117">As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><span data-ttu-id="9a21b-118">また、アプリケーションサーバーと仲介サーバーは、オーディオの場合にのみ QoS をサポートしていることに注意してください。アプリケーションサーバーまたは仲介サーバーで、ビデオまたはアプリケーションの共有ポートを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9a21b-118">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>



</div>

<span data-ttu-id="9a21b-119">上記の3つのコマンドを実行すると、Lync Server 2013 の既定のポート値が次のように構成されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="9a21b-119">If you run the preceding three commands you'll see that the default port values for Lync Server 2013 are configured like this:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9a21b-120">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9a21b-120">Property</span></span></th>
<th><span data-ttu-id="9a21b-121">会議サーバー</span><span class="sxs-lookup"><span data-stu-id="9a21b-121">Conferencing Server</span></span></th>
<th><span data-ttu-id="9a21b-122">アプリケーションサーバー</span><span class="sxs-lookup"><span data-stu-id="9a21b-122">Application Server</span></span></th>
<th><span data-ttu-id="9a21b-123">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="9a21b-123">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a21b-124">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="9a21b-124">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="9a21b-125">49152</span><span class="sxs-lookup"><span data-stu-id="9a21b-125">49152</span></span></p></td>
<td><p><span data-ttu-id="9a21b-126">49152</span><span class="sxs-lookup"><span data-stu-id="9a21b-126">49152</span></span></p></td>
<td><p><span data-ttu-id="9a21b-127">49152</span><span class="sxs-lookup"><span data-stu-id="9a21b-127">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a21b-128">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="9a21b-128">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="9a21b-129">8348</span><span class="sxs-lookup"><span data-stu-id="9a21b-129">8348</span></span></p></td>
<td><p><span data-ttu-id="9a21b-130">8348</span><span class="sxs-lookup"><span data-stu-id="9a21b-130">8348</span></span></p></td>
<td><p><span data-ttu-id="9a21b-131">8348</span><span class="sxs-lookup"><span data-stu-id="9a21b-131">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a21b-132">VideoPortStart</span><span class="sxs-lookup"><span data-stu-id="9a21b-132">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="9a21b-133">57501</span><span class="sxs-lookup"><span data-stu-id="9a21b-133">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a21b-134">VideoPortCount</span><span class="sxs-lookup"><span data-stu-id="9a21b-134">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="9a21b-135">8034</span><span class="sxs-lookup"><span data-stu-id="9a21b-135">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a21b-136">ApplicationSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="9a21b-136">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="9a21b-137">49152</span><span class="sxs-lookup"><span data-stu-id="9a21b-137">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a21b-138">ApplicationSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="9a21b-138">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="9a21b-139">16383</span><span class="sxs-lookup"><span data-stu-id="9a21b-139">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9a21b-140">前に説明したように、QoS のために Lync Server のポートを構成する場合は、お客様の会議、アプリケーション、および仲介サーバーで、オーディオポートの設定が同じであることを確認する必要があります。and、2) ポート範囲は重なりません。</span><span class="sxs-lookup"><span data-stu-id="9a21b-140">As noted previously, when configuring Lync Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="9a21b-141">上記の表をよく見ると、3種類のサーバー間でポート範囲が同じであることがわかります。</span><span class="sxs-lookup"><span data-stu-id="9a21b-141">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="9a21b-142">たとえば、[開始オーディオ] ポートは各サーバーの種類で [port 49152] に設定されています。また、各サーバーのオーディオ用に予約されているポートの合計数も8348と同じです。</span><span class="sxs-lookup"><span data-stu-id="9a21b-142">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="9a21b-143">ただし、ポートの範囲が重複しています。オーディオポートはポート49152から始まりますが、アプリケーション共有用にポートが設定されています。</span><span class="sxs-lookup"><span data-stu-id="9a21b-143">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="9a21b-144">サービスの品質を最大限に活用するために、固有のポート範囲を使用するようにアプリケーション共有を再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a21b-144">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="9a21b-145">たとえば、ポート40803で開始するようにアプリケーション共有を構成し、8348ポートを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="9a21b-145">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="9a21b-146">(8348 ポートの理由</span><span class="sxs-lookup"><span data-stu-id="9a21b-146">(Why 8348 ports?</span></span> <span data-ttu-id="9a21b-147">これらの値を一緒に追加した場合は 8348 40803、アプリケーションの共有でポート40803からポート49150が使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="9a21b-147">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="9a21b-148">オーディオポートはポート49152まで開始されないため、重複するポート範囲はなくなります。)</span><span class="sxs-lookup"><span data-stu-id="9a21b-148">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="9a21b-149">アプリケーション共有用の新しいポート範囲を選んだら、CsConferencingServer コマンドレットを使用して変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9a21b-149">After you have selected the new port range for application sharing you can make your change by using the Set-CsConferencingServer cmdlet.</span></span> <span data-ttu-id="9a21b-150">この変更は、アプリケーションサーバーまたは仲介サーバーで行う必要はありません。これらのサーバーは、アプリケーション共有トラフィックを処理しないためです。</span><span class="sxs-lookup"><span data-stu-id="9a21b-150">This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic.</span></span> <span data-ttu-id="9a21b-151">オーディオトラフィック用に使用されているポートを再割り当てする場合は、これらのサーバーでポートの値を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a21b-151">You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="9a21b-152">単一の会議サーバーでアプリケーション共有のポート値を変更するには、Lync Server 管理シェルで次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9a21b-152">To modify the port values for application sharing on a single Conferencing server run a command similar to this from within the Lync Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="9a21b-153">すべての会議サーバーでこれらの変更を行う場合は、代わりに次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9a21b-153">If you want to make these changes on all your Conferencing servers you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="9a21b-154">ポート設定を変更した後で、変更の影響を受ける各サービスを停止してから再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a21b-154">After changing port settings you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="9a21b-155">会議サーバー、アプリケーションサーバー、および仲介サーバーがまったく同じポート範囲を共有していることは必須ではありません。唯一の条件として、すべてのサーバーで固有のポート範囲を確保する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a21b-155">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers.</span></span> <span data-ttu-id="9a21b-156">ただし、すべてのサーバーで同じポートセットを使用すると、通常、管理が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="9a21b-156">However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

