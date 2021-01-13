---
title: 電話会議、アプリケーション、および仲介サーバーのポート範囲とサービス品質ポリシーの構成
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: この記事では、電話会議、アプリケーション、および仲介サーバーのポート範囲とサービスの品質ポリシーを構成する方法について説明します。
ms.openlocfilehash: 8c65e36528615aca181b6aac17aab844c1a4d206
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800127"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="6db9c-103">電話会議、アプリケーション、および仲介サーバーのポート範囲とサービス品質ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="6db9c-103">Configuring port ranges and a Quality of Service policy for your Conferencing, Application, and Mediation servers</span></span>

<span data-ttu-id="6db9c-104">この記事では、会議サーバー、アプリケーション サーバー、および仲介サーバーのポート範囲とサービス品質ポリシーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6db9c-104">This article describes how to configure port ranges and a Quality of Service policy for your Conferencing, Application, and Mediation servers.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="6db9c-105">ポート範囲を構成する</span><span class="sxs-lookup"><span data-stu-id="6db9c-105">Configure port ranges</span></span>

<span data-ttu-id="6db9c-106">サービスの品質を実装するには、電話会議、アプリケーション、および仲介サーバーで音声、ビデオ、およびアプリケーション共有に対して同じポート範囲を構成する必要があります。さらに、これらのポート範囲は何も重ならないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6db9c-106">To implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way.</span></span> <span data-ttu-id="6db9c-107">簡単な例を使用するには、会議サーバーのビデオにポート 10000 ~ 10999 を使用するとします。</span><span class="sxs-lookup"><span data-stu-id="6db9c-107">To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers.</span></span> <span data-ttu-id="6db9c-108">つまり、アプリケーション サーバーと仲介サーバーのビデオ用にポート 10000 ~ 10999 も予約する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6db9c-108">That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers.</span></span> <span data-ttu-id="6db9c-109">そうしない場合、QoS は期待通り動作しません。</span><span class="sxs-lookup"><span data-stu-id="6db9c-109">If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="6db9c-110">同様に、ポート 10000 ~ 10999 をビデオ用に予約し、ポート 10500 ~ 11999 をオーディオ用に予約するとします。</span><span class="sxs-lookup"><span data-stu-id="6db9c-110">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio.</span></span> <span data-ttu-id="6db9c-111">これにより、ポート範囲が重複するため、サービスの品質に問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6db9c-111">This can create problems for Quality of Service, because the port ranges overlap.</span></span> <span data-ttu-id="6db9c-112">QoS では、各モダリティに固有のポート セットが必要です。ポート 10000 ~ 10999 をビデオに使用する場合は、異なる範囲 (たとえば、11000 ~ 11999、音声) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6db9c-112">With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999, for audio).</span></span>

<span data-ttu-id="6db9c-113">既定では、音声とビデオのポート範囲は Skype for Business Server で重複しません。ただし、アプリケーション共有に割り当てられたポート範囲は、音声とビデオの両方のポート範囲と重複しています。</span><span class="sxs-lookup"><span data-stu-id="6db9c-113">By default, audio and video port ranges do not overlap in Skype for Business Server; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="6db9c-114">(つまり、これらの範囲はいずれも一意でもありません。Skype for Business Server 管理シェル内から次の 3 つのコマンドを実行して、会議、アプリケーション、および仲介サーバーの既存のポート範囲を確認できます。</span><span class="sxs-lookup"><span data-stu-id="6db9c-114">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Skype for Business Server Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> <span data-ttu-id="6db9c-115">前のコマンドで確認した通り、各ポートの種類 (オーディオ、ビデオ、アプリケーション共有) には、ポートの開始とポート数という 2 つの個別のプロパティ値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="6db9c-115">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count.</span></span> <span data-ttu-id="6db9c-116">ポートの開始は、そのモダリティに使用される最初のポートを示します。たとえば、オーディオ ポートの開始が 50000 に等しい場合、オーディオ トラフィックに使用される最初のポートはポート 50000 です。</span><span class="sxs-lookup"><span data-stu-id="6db9c-116">The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000.</span></span> <span data-ttu-id="6db9c-117">オーディオ ポート数が 2 (有効な値ではないが、ここで説明のために使用されている) の場合、オーディオには 2 つのポートだけが割り当てられるという意味です。</span><span class="sxs-lookup"><span data-stu-id="6db9c-117">If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes), that means that only two ports are allocated for audio.</span></span> <span data-ttu-id="6db9c-118">最初のポートがポート 50000 で、合計 2 つのポートがある場合、つまり 2 番目のポートはポート 50001 である必要があります (ポート範囲は連続している必要があります)。</span><span class="sxs-lookup"><span data-stu-id="6db9c-118">If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous).</span></span> <span data-ttu-id="6db9c-119">その結果、オーディオのポート範囲はポート 50000 ~ 50001 になります。</span><span class="sxs-lookup"><span data-stu-id="6db9c-119">As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><br><span data-ttu-id="6db9c-120">また、アプリケーション サーバーと仲介サーバーは音声の QoS のみをサポートします。アプリケーション サーバーまたは仲介サーバーのビデオポートやアプリケーション共有ポートを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6db9c-120">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>

<span data-ttu-id="6db9c-121">上記の 3 つのコマンドを実行すると、Skype for Business Server の既定のポート値は次のように構成されています。</span><span class="sxs-lookup"><span data-stu-id="6db9c-121">If you run the preceding three commands, you'll see that that the default port values for Skype for Business Server are configured like this:</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6db9c-122">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6db9c-122">Property</span></span></th>
<th><span data-ttu-id="6db9c-123">Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="6db9c-123">Conferencing Server</span></span></th>
<th><span data-ttu-id="6db9c-124">アプリケーション サーバー</span><span class="sxs-lookup"><span data-stu-id="6db9c-124">Application Server</span></span></th>
<th><span data-ttu-id="6db9c-125">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="6db9c-125">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6db9c-126">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="6db9c-126">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="6db9c-127">49152</span><span class="sxs-lookup"><span data-stu-id="6db9c-127">49152</span></span></p></td>
<td><p><span data-ttu-id="6db9c-128">49152</span><span class="sxs-lookup"><span data-stu-id="6db9c-128">49152</span></span></p></td>
<td><p><span data-ttu-id="6db9c-129">49152</span><span class="sxs-lookup"><span data-stu-id="6db9c-129">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6db9c-130">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="6db9c-130">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="6db9c-131">8348</span><span class="sxs-lookup"><span data-stu-id="6db9c-131">8348</span></span></p></td>
<td><p><span data-ttu-id="6db9c-132">8348</span><span class="sxs-lookup"><span data-stu-id="6db9c-132">8348</span></span></p></td>
<td><p><span data-ttu-id="6db9c-133">8348</span><span class="sxs-lookup"><span data-stu-id="6db9c-133">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6db9c-134">VideoPortStart</span><span class="sxs-lookup"><span data-stu-id="6db9c-134">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="6db9c-135">57501</span><span class="sxs-lookup"><span data-stu-id="6db9c-135">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6db9c-136">VideoPortCount</span><span class="sxs-lookup"><span data-stu-id="6db9c-136">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="6db9c-137">8034</span><span class="sxs-lookup"><span data-stu-id="6db9c-137">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6db9c-138">ApplicationSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="6db9c-138">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="6db9c-139">49152</span><span class="sxs-lookup"><span data-stu-id="6db9c-139">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6db9c-140">ApplicationSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="6db9c-140">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="6db9c-141">16383</span><span class="sxs-lookup"><span data-stu-id="6db9c-141">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6db9c-142">前に説明した QoS 用の Skype for Business Server ポートを構成する場合は、次の点を確認する必要があります。2) ポート範囲が重ならないようにします。</span><span class="sxs-lookup"><span data-stu-id="6db9c-142">As noted previously, when configuring Skype for Business Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="6db9c-143">上の表を詳しく見てみた場合、ポート範囲は 3 種類のサーバー間で同一であるのが分かっています。</span><span class="sxs-lookup"><span data-stu-id="6db9c-143">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="6db9c-144">たとえば、開始オーディオ ポートは各サーバーの種類でポート 49152 に設定され、各サーバーのオーディオ用に予約されているポートの総数も 8348 です。</span><span class="sxs-lookup"><span data-stu-id="6db9c-144">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="6db9c-145">ただし、ポート範囲は重複します。オーディオ ポートはポート 49152 から開始しますが、アプリケーション共有のためにポートを確保します。</span><span class="sxs-lookup"><span data-stu-id="6db9c-145">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="6db9c-146">サービスの品質を最適に利用するには、一意のポート範囲を使用するアプリケーション共有を再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6db9c-146">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="6db9c-147">たとえば、ポート 40803 から開始し、8348 ポートを使用するアプリケーション共有を構成できます。</span><span class="sxs-lookup"><span data-stu-id="6db9c-147">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="6db9c-148">(なぜ 8348 ポートですか?</span><span class="sxs-lookup"><span data-stu-id="6db9c-148">(Why 8348 ports?</span></span> <span data-ttu-id="6db9c-149">これらの値を 40803 + 8348 と共に追加すると、アプリケーション共有ではポート 40803 ~ ポート 49150 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="6db9c-149">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="6db9c-150">オーディオ ポートはポート 49152 まで開始されないので、ポート範囲が重複しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="6db9c-150">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="6db9c-151">アプリケーション共有の新しいポート範囲を選択した後、次のコマンドレットを使用してSet-CsConferencingServerできます。</span><span class="sxs-lookup"><span data-stu-id="6db9c-151">After you have selected the new port range for application sharing, you can make your change by using the Set-CsConferencingServer cmdlet.</span></span> <span data-ttu-id="6db9c-152">これらのサーバーはアプリケーション共有トラフィックを処理しないので、アプリケーション サーバーまたは仲介サーバーでこの変更を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6db9c-152">This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic.</span></span> <span data-ttu-id="6db9c-153">オーディオ トラフィックに使用するポートを再割り当てする場合にのみ、これらのサーバーのポート値を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6db9c-153">You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="6db9c-154">単一の会議サーバーでアプリケーション共有のポート値を変更するには、Skype for Business Server 管理シェルから次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6db9c-154">To modify the port values for application sharing on a single Conferencing server, run a command similar to this from within the Skype for Business Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="6db9c-155">すべての会議サーバーでこれらの変更を行う場合は、代わりに次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6db9c-155">If you want to make these changes on all your Conferencing servers, you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="6db9c-156">ポート設定を変更した後、変更の影響を受ける各サービスを停止してから再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6db9c-156">After changing port settings, you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="6db9c-157">会議サーバー、アプリケーション サーバー、および仲介サーバーがまったく同じポート範囲を共有する必要はありません。唯一の真の要件は、すべてのサーバーで一意のポート範囲を確保する必要があるという条件です。</span><span class="sxs-lookup"><span data-stu-id="6db9c-157">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers.</span></span> <span data-ttu-id="6db9c-158">ただし、すべてのサーバーで同じポート セットを使用すると、通常は管理が容易になります。</span><span class="sxs-lookup"><span data-stu-id="6db9c-158">However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="6db9c-159">会議サーバー、アプリケーション サーバー、および仲介サーバー用に Skype for Business Server のサービス品質ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="6db9c-159">Configure a Quality of Service policy in Skype for Business Server for your Conferencing, Application, and Mediation servers</span></span>

<span data-ttu-id="6db9c-p108">ポート範囲を構成すると、指定した種類のすべてのトラフィック (すべての音声トラフィックなど) が同じポート セットを通過するようになるため、サービス品質の使用が促進されます。これにより、システムは特定のパケットを簡単に識別およびマークできるようになります。ポート 49152 が音声トラフィック用に予約されている場合、ポート 49152 を通過するパケットは、これが音声パケットであることを示す DSCP コードでマークできます。さらに、これによりルーターはパケットを音声パケットとして識別し、マークされていないパケット (サーバーからサーバーへのファイルのコピーに使用されるパケットなど) よりも高い優先順位を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6db9c-p108">Configuring port ranges facilitates the use of Quality of Service by ensuring that all traffic of a specified type (for example, all audio traffic) travels through the same set of ports. This makes it easy for the system to identify and mark a given packet: if port 49152 is reserved for audio traffic, then any packet traveling through port 49152 can be marked with a DSCP code that indicates that this is an audio packet. In turn, this enables routers to identify the packet as an audio packet, and give it higher priority than unmarked packets (such as packets used to copy a file from one server to another).</span></span>

<span data-ttu-id="6db9c-163">ただし、ポートのセットを特定の種類のトラフィックに限定するだけでは、これらのポートを通過するパケットは適切な DSCP コードでマークされません。</span><span class="sxs-lookup"><span data-stu-id="6db9c-163">However, simply restricting a set of ports to a specific type of traffic does not result in packets traveling through those ports being marked with the appropriate DSCP code.</span></span> <span data-ttu-id="6db9c-164">ポート範囲の定義に加えて、各ポート範囲に関連付けられる DSCP コードを指定するサービス品質ポリシーも作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6db9c-164">In addition to defining port ranges, you must also create Quality of Service policies that specify the DSCP code to be associated with each port range.</span></span> <span data-ttu-id="6db9c-165">Skype for Business Server の場合、通常は、オーディオ用とビデオ用の 2 つのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6db9c-165">For Skype for Business Server, that typically means creating two policies: one for audio and one for video.</span></span>

<span data-ttu-id="6db9c-166">サービス品質ポリシーは、グループ ポリシーを使用して最も簡単に作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="6db9c-166">Quality of Service policies are most easily created, and managed, by using Group Policy.</span></span> <span data-ttu-id="6db9c-167">(これらの同じポリシーは、ローカル セキュリティ ポリシーを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="6db9c-167">(These same policies can also be created by using local security policies.</span></span> <span data-ttu-id="6db9c-168">ただし、各コンピューターで同じ手順を繰り返す必要があります)。QoS ポリシーの初期セット (1 つは音声用、もう 1 つはビデオ用) は、会議サーバー、アプリケーション サーバー、仲介サーバー サービスを実行している Skype for Business Server コンピューターにのみ適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6db9c-168">However, that requires you to repeat the same procedure on each and every computer.) Your initial set of QoS policies (one for audio and one for video) should be applied only to Skype for Business Server computers running the Conferencing server, Application server, and/or Mediation server services.</span></span> <span data-ttu-id="6db9c-169">これらのコンピューターすべてが同じ Active Directory OU に存在する場合は、新しいグループ ポリシー オブジェクト (GPO) をその OU に割り当てるだけでできます。</span><span class="sxs-lookup"><span data-stu-id="6db9c-169">If all of these computers are located in the same Active Directory OU, you can simply assign the new Group Policy object (GPO) to that OU.</span></span> <span data-ttu-id="6db9c-170">または、新しいポリシーの対象を指定したコンピューターに設定する他の手順を実行することもできます。たとえば、適切なコンピューターをセキュリティ グループに配置し、グループ ポリシーのセキュリティ フィルターを使用して、そのセキュリティ グループに GPO を適用できます。</span><span class="sxs-lookup"><span data-stu-id="6db9c-170">Alternatively, you can take other steps to target the new policy to the specified computers; for example, you can place the appropriate computers in a security group, then use Group Policy security filtering to apply the GPO just to that security group.</span></span>

<span data-ttu-id="6db9c-171">音声を管理するためのサービス品質ポリシーを作成するには、グループ ポリシー管理がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6db9c-171">To create a Quality of Service policy for managing audio, log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="6db9c-172">グループ ポリシー管理を開き ([**スタート**] をクリックし、[**管理ツール**] をポイントし、[**グループ ポリシーの管理**] をクリックして、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6db9c-172">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="6db9c-173">グループ ポリシーの管理で、新しいポリシーのを作成するコンテナーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="6db9c-173">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="6db9c-174">たとえば、すべての Skype for Business Server コンピューターが Skype for Business Server という名前の OU にある場合は、Skype for Business Server OU に新しいポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6db9c-174">For example, if all your Skype for Business Server computers are located in an OU named Skype for Business Server, then the new policy should be created in the Skype for Business Server OU.</span></span>

2.  <span data-ttu-id="6db9c-175">適切なコンテナーを右クリックし、[このドメインに GPO を作成する] をクリックし、 **ここにリンクします**。</span><span class="sxs-lookup"><span data-stu-id="6db9c-175">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="6db9c-176">[新 **しい GPO]** ダイアログ ボックスで、[名前] ボックスに新しいグループ ポリシー オブジェクトの名前 **(Skype for Business Server QoS** など) を入力し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db9c-176">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Skype for Business Server QoS**), and then click **OK**.</span></span>

4.  <span data-ttu-id="6db9c-177">新しく作成したポリシーを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="6db9c-177">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="6db9c-178">グループ ポリシー管理エディターで、[**コンピューターの構成**]、[**ポリシー**]、[**Windows の設定**] の順に展開し、[**ポリシー ベースの QoS**] を右クリックして [**新規ポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db9c-178">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="6db9c-179">[**ポリシーベースの QoS]** ダイアログ ボックスの開始ページで、新しいポリシーの名前 **(Skype for Business Server QoS** など)を [名前] ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="6db9c-179">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server QoS**) in the **Name** box.</span></span> <span data-ttu-id="6db9c-180">[**DSCP 値を指定する**] を選択し、値を **46** に設定します。</span><span class="sxs-lookup"><span data-stu-id="6db9c-180">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="6db9c-181">[**出力方向のスロットル率を指定する**] をオフのままにして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db9c-181">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="6db9c-182">次のページで、[すべてのアプリケーション]が選択されているのを確認し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="6db9c-182">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="6db9c-183">これにより、すべてのアプリケーションが、指定した DSCP コードを持つ指定したポート範囲からのパケットに一致するようになります。</span><span class="sxs-lookup"><span data-stu-id="6db9c-183">This simply ensures that all applications will match packets from the specified port range with the specified DSCP code.</span></span>

8.  <span data-ttu-id="6db9c-184">3 番目のページで、[ **すべての** 送信元 IP アドレス] と [すべての宛先 IP アドレス] の両方が選択され、[次へ] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6db9c-184">On the third page, make sure that both **Any source IP address and Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="6db9c-185">この 2 つの設定により、これらのパケットを送信したコンピューター (IP アドレス) やこれらのパケットを受信するコンピューター (IP アドレス) にかかわらず、パケットが管理されます。</span><span class="sxs-lookup"><span data-stu-id="6db9c-185">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="6db9c-186">4 番目のページで、[**この QoS ポリシーを適用するプロトコルを選択してください**] ドロップダウン リストから [**TCP と UDP**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6db9c-186">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="6db9c-187">TCP (伝送制御プロトコル) と UDP (ユーザー データグラム プロトコル) は、Skype for Business Server とそのクライアント アプリケーションで最も一般的に使用される 2 つのネットワーク プロトコルです。</span><span class="sxs-lookup"><span data-stu-id="6db9c-187">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="6db9c-188">[**発信元ポート番号を指定してください**] 見出しの下で、[**次の発信元ポート番号か範囲**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db9c-188">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="6db9c-189">付随するテキスト ボックスに、オーディオ送信用に予約されたポート範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="6db9c-189">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="6db9c-190">たとえば、ポート 49152 からポート 57500 までをオーディオ トラフィック用に予約した場合は、次の形式でポート範囲を入力します **。49152:57500**。</span><span class="sxs-lookup"><span data-stu-id="6db9c-190">For example, if you reserved ports 49152 through ports 57500 for audio traffic, enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="6db9c-191">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db9c-191">Click **Finish**.</span></span>

> [!NOTE]  
> <span data-ttu-id="6db9c-192">DSCP 値 46 は任意です。DSCP 46 はオーディオ パケットのマーキングによく使用されますが、音声通信に DSCP 46 を使用する必要はない。</span><span class="sxs-lookup"><span data-stu-id="6db9c-192">The DSCP value of 46 is somewhat arbitrary: although DSCP 46 is often used for marking audio packets, you do not have to use DSCP 46 for audio communications.</span></span> <span data-ttu-id="6db9c-193">QoS を既に実装済みで、音声に別の DSCP コード (DSCP 40 など) を使用している場合は、サービス品質ポリシーを構成して、同じコード (つまり、音声に 40) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6db9c-193">If you have already implemented QoS and you are using a different DSCP code for audio (for example, DSCP 40), you should configure your Quality of Service policy to use that same code (i.e., 40 for audio).</span></span> <span data-ttu-id="6db9c-194">サービスの品質を実装しそうな場合は、音声に DSCP 46 を使用するようにお勧めします。これは、その値が一般的にオーディオ パケットのマークに使用されるからです。</span><span class="sxs-lookup"><span data-stu-id="6db9c-194">If you are just now implementing Quality of Service, then it is recommended that you use DSCP 46 for audio, simply because that value is commonly used to mark audio packets.</span></span>

<span data-ttu-id="6db9c-195">音声トラフィックの QoS ポリシーを作成した後、ビデオ トラフィック用の 2 つ目のポリシー (およびオプションで、アプリケーション共有トラフィックを管理するための 3 つ目のポリシー) を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6db9c-195">After you have created the QoS policy for audio traffic, you should then create a second policy for video traffic (and, optionally, a third policy for managing application sharing traffic).</span></span> <span data-ttu-id="6db9c-196">ビデオのポリシーを作成するには、次の点を置き換えて、音声ポリシーの作成時に従ったのと同じ基本手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6db9c-196">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="6db9c-197">別の (および一意の) ポリシー名 **(Skype for Business Server ビデオなど) を使用します**。</span><span class="sxs-lookup"><span data-stu-id="6db9c-197">Use a different (and unique) policy name (for example, **Skype for Business Server Video**).</span></span>

  - <span data-ttu-id="6db9c-p120">DSCP 値を 46 ではなく **34** に設定します (34 の DSCP 値の使用は必須ではありません。要件は、音声に使用したのとは異なる DSCP 値をビデオに使用することだけです)。</span><span class="sxs-lookup"><span data-stu-id="6db9c-p120">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="6db9c-201">ビデオ トラフィックには、以前に構成したポート範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="6db9c-201">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="6db9c-202">たとえば、ポート 57501 ~ 65535 をビデオ用に予約している場合、ポート範囲を次に設定します **。57501:65535**。</span><span class="sxs-lookup"><span data-stu-id="6db9c-202">For example, if you have reserved ports 57501 through 65535 for video, set the port range to this: **57501:65535**.</span></span>

<span data-ttu-id="6db9c-203">アプリケーション共有トラフィックを管理するポリシーを作成する場合は、3 つ目のポリシーを作成して、次の代替を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6db9c-203">If you decide to create a policy for managing application sharing traffic, you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="6db9c-204">別の (および一意の) ポリシー名 **(Skype for Business Server アプリケーション** 共有など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="6db9c-204">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="6db9c-p122">DSCP 値を 46 ではなく **24** に設定します (この場合も、24 の DSCP 値の使用は必須ではありません。要件は、音声またはビデオに使用したのとは異なる DSCP 値をアプリケーション共有に使用することだけです)。</span><span class="sxs-lookup"><span data-stu-id="6db9c-p122">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="6db9c-208">ビデオ トラフィックには、以前に構成したポート範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="6db9c-208">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="6db9c-209">たとえば、アプリケーション共有用にポート 40803 ~ 49151 を予約している場合、ポート範囲を **40803:49151** に設定します。</span><span class="sxs-lookup"><span data-stu-id="6db9c-209">For example, if you have reserved ports 40803 through 49151 for application sharing, set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="6db9c-210">作成した新しいポリシーは、Skype for Business Server コンピューターでグループ ポリシーが更新されるまで有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="6db9c-210">The new policies you have created will not take effect until Group Policy has been refreshed on your Skype for Business Server computers.</span></span> <span data-ttu-id="6db9c-211">グループ ポリシーは自身を定期的に更新しますが、グループ ポリシーを更新する必要のある各コンピューターで次のコマンドを実行することにより、強制的に即時に更新できます。</span><span class="sxs-lookup"><span data-stu-id="6db9c-211">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="6db9c-212">このコマンドは、Skype for Business Server 管理シェル内から、または管理者の資格情報で実行されている任意のコマンド ウィンドウから実行できます。</span><span class="sxs-lookup"><span data-stu-id="6db9c-212">This command can be run from within the Skype for Business Server Management Shell or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="6db9c-213">管理者の資格情報でコマンド ウィンドウを実行するには、[**スタート**] ボタンをクリックして、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db9c-213">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="6db9c-214">新しい QoS ポリシーが適用されたことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6db9c-214">To verify that the new QoS policies have been applied, do the following:</span></span>

1.  <span data-ttu-id="6db9c-215">Skype for Business Server コンピューターで、[スタート] ボタン **をクリックし**、[ファイル名を指定して実行] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6db9c-215">On a Skype for Business Server computer, click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="6db9c-216">[ファイル名 **を指定** して実行] ダイアログ ボックスに **「regedit」と** 入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6db9c-216">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="6db9c-217">レジストリ エディターで、[コンピューター ] を展開し **、[HKEY \_ LOCAL \_ MACHINE]** を展開し、[**ソフトウェア**]、[ポリシー]、Microsoft、[Windows] の順に展開し **、[QoS] をクリックします**。   </span><span class="sxs-lookup"><span data-stu-id="6db9c-217">In Registry Editor, expand **Computer**, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Policies**, expand **Microsoft**, expand **Windows**, and then click **QoS**.</span></span> <span data-ttu-id="6db9c-218">[**QoS**] に、作成した各 QoS ポリシーのレジストリ キーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6db9c-218">Under **QoS** you should see registry keys for each of the QoS policies you just created.</span></span> <span data-ttu-id="6db9c-219">たとえば、2 つの新しいポリシー (1 つは Skype for Business Server Audio QoS、もう 1 つは Skype for Business Server Video QoS という名前) を作成した場合は、Skype for Business Server Audio QoS と Skype for Business Server ビデオ QoS のレジストリ エントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6db9c-219">For example, if you created two new policies (one named Skype for Business Server Audio QoS and the other named Skype for Business Server Video QoS), you should see registry entries for Skype for Business Server Audio QoS and Skype for Business Server Video QoS.</span></span>

<span data-ttu-id="6db9c-220">ネットワーク パケットが適切な DSCP 値でマークされるようにするには、次の手順を実行して、各コンピューターに新しいレジストリ エントリを作成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="6db9c-220">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="6db9c-221">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db9c-221">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="6db9c-222">[ファイル名 **を指定** して実行] ダイアログ ボックスに **「regedit」と** 入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6db9c-222">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="6db9c-223">レジストリ エディターで **、HKEY \_ LOCAL \_ MACHINE、\*\*\*\*システム\*\*\*\*、CurrentControlSet、** サービス、Tcpip の順に **展開します**。 </span><span class="sxs-lookup"><span data-stu-id="6db9c-223">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="6db9c-224">[**Tcpip**] を右クリックし、[**新規**] をポイントして [**キー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db9c-224">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="6db9c-225">新しいレジストリ キーを作成したら **、「QoS」** と入力し、Enter キーを押してキーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="6db9c-225">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="6db9c-226">[**QoS**] を右クリックし、[**新規**] をポイントして [**文字列値**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db9c-226">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="6db9c-227">新しいレジストリ値を作成したら **、「NLA** を使用しない」と入力し、Enter キーを押して値の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="6db9c-227">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="6db9c-228">[**Do no use NLA**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db9c-228">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="6db9c-229">[文字列の **編集]** ダイアログ ボックスで、[値のデータ] ボックスに **「1」** と **入力し\*\*\*\*、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db9c-229">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="6db9c-230">レジストリ エディターを閉じて、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="6db9c-230">Close the Registry Editor and reboot your computer.</span></span>
