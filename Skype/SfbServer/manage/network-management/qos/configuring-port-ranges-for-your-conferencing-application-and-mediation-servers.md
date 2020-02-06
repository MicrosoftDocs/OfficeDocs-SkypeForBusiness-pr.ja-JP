---
title: 電話会議、アプリケーション、および仲介サーバーのポート範囲とサービス品質ポリシーを構成する
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: この記事では、会議、アプリケーション、および仲介サーバーのポート範囲とサービス品質ポリシーを構成する方法について説明します。
ms.openlocfilehash: 76373407a8087e3646668d7ce9952c83c500af97
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817446"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="de9f8-103">電話会議、アプリケーション、および仲介サーバーのポート範囲とサービス品質ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="de9f8-103">Configuring port ranges and a Quality of Service policy for your Conferencing, Application, and Mediation servers</span></span>

<span data-ttu-id="de9f8-104">この記事では、会議、アプリケーション、および仲介サーバーのポート範囲とサービス品質ポリシーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-104">This article describes how to configure port ranges and a Quality of Service policy for your Conferencing, Application, and Mediation servers.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="de9f8-105">ポート範囲を構成する</span><span class="sxs-lookup"><span data-stu-id="de9f8-105">Configure port ranges</span></span>

<span data-ttu-id="de9f8-106">サービスの品質を実装するには、会議、アプリケーション、および仲介サーバー上で音声、ビデオ、およびアプリケーション共有用に同一のポート範囲を構成する必要があります。さらに、これらのポート範囲は、何らかの方法でオーバーラップすることはできません。</span><span class="sxs-lookup"><span data-stu-id="de9f8-106">To implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way.</span></span> <span data-ttu-id="de9f8-107">簡単な例を使用するには、電話会議サーバー上のビデオに 1万 ~ 10999 のポートを使用しているとします。</span><span class="sxs-lookup"><span data-stu-id="de9f8-107">To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers.</span></span> <span data-ttu-id="de9f8-108">つまり、アプリケーションや仲介サーバー上のビデオ用に、1万 ~ 10999 のポートを予約する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de9f8-108">That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers.</span></span> <span data-ttu-id="de9f8-109">そうしないと、QoS は期待どおりに動作しません。</span><span class="sxs-lookup"><span data-stu-id="de9f8-109">If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="de9f8-110">同様に、1万 ~ 10999 のビデオ用にポートを予約していて、オーディオ用にポート10500から11999を予約したとします。</span><span class="sxs-lookup"><span data-stu-id="de9f8-110">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio.</span></span> <span data-ttu-id="de9f8-111">これにより、ポートの範囲が重複するため、サービスの品質に関する問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="de9f8-111">This can create problems for Quality of Service, because the port ranges overlap.</span></span> <span data-ttu-id="de9f8-112">QoS では、各モダリティには固有のポートのセットが必要です。ビデオ用に 1万 ~ 10999 のポートを使用している場合は、別の範囲を使用する必要があります (たとえば、11000 ~ 11999、オーディオ用)。</span><span class="sxs-lookup"><span data-stu-id="de9f8-112">With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999, for audio).</span></span>

<span data-ttu-id="de9f8-113">既定では、Skype for Business Server では、オーディオポートとビデオポートの範囲は重複していません。ただし、アプリケーション共有に割り当てられているポート範囲は、オーディオポート範囲とビデオポート範囲の両方と重複しています。</span><span class="sxs-lookup"><span data-stu-id="de9f8-113">By default, audio and video port ranges do not overlap in Skype for Business Server; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="de9f8-114">(これにより、これらの範囲のいずれも一意ではないことを意味します)。Skype for Business Server 管理シェルで次の3つのコマンドを実行して、会議、アプリケーション、および仲介サーバーの既存のポート範囲を確認できます。</span><span class="sxs-lookup"><span data-stu-id="de9f8-114">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Skype for Business Server Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> <span data-ttu-id="de9f8-115">上に示したように、各ポートの種類 (オーディオ、ビデオ、およびアプリケーションの共有) には、ポートの開始とポート数という2つの個別のプロパティ値が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="de9f8-115">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count.</span></span> <span data-ttu-id="de9f8-116">ポート start は、そのモダリティで使用される最初のポートを示します。たとえば、オーディオポートの start が5万に等しい場合、オーディオトラフィックに使われる最初のポートがポート5万であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-116">The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000.</span></span> <span data-ttu-id="de9f8-117">オーディオポート数が 2 (有効な値ではありませんが、ここでは説明のために使用されています) の場合、オーディオには2つのポートのみが割り当てられていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-117">If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes), that means that only two ports are allocated for audio.</span></span> <span data-ttu-id="de9f8-118">第1のポートがポート5万であり、合計2つのポートがある場合は、2番目のポートがポート 50001 (ポート範囲は連続している必要があります) であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-118">If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous).</span></span> <span data-ttu-id="de9f8-119">その結果、オーディオのポート範囲は、5万 ~ 50001 のポートになります。</span><span class="sxs-lookup"><span data-stu-id="de9f8-119">As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><br><span data-ttu-id="de9f8-120">また、アプリケーションサーバーと仲介サーバーは、オーディオの場合にのみ QoS をサポートしていることに注意してください。アプリケーションサーバーまたは仲介サーバーで、ビデオまたはアプリケーションの共有ポートを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="de9f8-120">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>

<span data-ttu-id="de9f8-121">上記の3つのコマンドを実行すると、Skype for Business Server の既定のポートの値が次のように構成されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="de9f8-121">If you run the preceding three commands, you'll see that that the default port values for Skype for Business Server are configured like this:</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="de9f8-122">プロパティ</span><span class="sxs-lookup"><span data-stu-id="de9f8-122">Property</span></span></th>
<th><span data-ttu-id="de9f8-123">会議サーバー</span><span class="sxs-lookup"><span data-stu-id="de9f8-123">Conferencing Server</span></span></th>
<th><span data-ttu-id="de9f8-124">アプリケーションサーバー</span><span class="sxs-lookup"><span data-stu-id="de9f8-124">Application Server</span></span></th>
<th><span data-ttu-id="de9f8-125">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="de9f8-125">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="de9f8-126">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="de9f8-126">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="de9f8-127">49152</span><span class="sxs-lookup"><span data-stu-id="de9f8-127">49152</span></span></p></td>
<td><p><span data-ttu-id="de9f8-128">49152</span><span class="sxs-lookup"><span data-stu-id="de9f8-128">49152</span></span></p></td>
<td><p><span data-ttu-id="de9f8-129">49152</span><span class="sxs-lookup"><span data-stu-id="de9f8-129">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de9f8-130">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="de9f8-130">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="de9f8-131">8348</span><span class="sxs-lookup"><span data-stu-id="de9f8-131">8348</span></span></p></td>
<td><p><span data-ttu-id="de9f8-132">8348</span><span class="sxs-lookup"><span data-stu-id="de9f8-132">8348</span></span></p></td>
<td><p><span data-ttu-id="de9f8-133">8348</span><span class="sxs-lookup"><span data-stu-id="de9f8-133">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de9f8-134">VideoPortStart</span><span class="sxs-lookup"><span data-stu-id="de9f8-134">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="de9f8-135">57501</span><span class="sxs-lookup"><span data-stu-id="de9f8-135">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de9f8-136">VideoPortCount</span><span class="sxs-lookup"><span data-stu-id="de9f8-136">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="de9f8-137">8034</span><span class="sxs-lookup"><span data-stu-id="de9f8-137">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de9f8-138">ApplicationSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="de9f8-138">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="de9f8-139">49152</span><span class="sxs-lookup"><span data-stu-id="de9f8-139">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de9f8-140">ApplicationSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="de9f8-140">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="de9f8-141">16383</span><span class="sxs-lookup"><span data-stu-id="de9f8-141">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="de9f8-142">前に説明したように、QoS のために Skype for Business Server ポートを構成する場合は、お客様の会議、アプリケーション、および仲介サーバーで、オーディオポートの設定が同じであることを確認する必要があります。and、2) ポート範囲は重なりません。</span><span class="sxs-lookup"><span data-stu-id="de9f8-142">As noted previously, when configuring Skype for Business Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="de9f8-143">上記の表をよく見ると、3種類のサーバー間でポート範囲が同じであることがわかります。</span><span class="sxs-lookup"><span data-stu-id="de9f8-143">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="de9f8-144">たとえば、[開始オーディオ] ポートは各サーバーの種類で [port 49152] に設定されています。また、各サーバーのオーディオ用に予約されているポートの合計数も8348と同じです。</span><span class="sxs-lookup"><span data-stu-id="de9f8-144">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="de9f8-145">ただし、ポートの範囲が重複しています。オーディオポートはポート49152から始まりますが、アプリケーション共有用にポートが設定されています。</span><span class="sxs-lookup"><span data-stu-id="de9f8-145">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="de9f8-146">サービスの品質を最大限に活用するために、固有のポート範囲を使用するようにアプリケーション共有を再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de9f8-146">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="de9f8-147">たとえば、ポート40803で開始するようにアプリケーション共有を構成し、8348ポートを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="de9f8-147">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="de9f8-148">(8348 ポートの理由</span><span class="sxs-lookup"><span data-stu-id="de9f8-148">(Why 8348 ports?</span></span> <span data-ttu-id="de9f8-149">これらの値を一緒に追加した場合は 8348 40803、アプリケーションの共有でポート40803からポート49150が使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-149">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="de9f8-150">オーディオポートはポート49152まで開始されないため、重複するポート範囲はなくなります。)</span><span class="sxs-lookup"><span data-stu-id="de9f8-150">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="de9f8-151">アプリケーション共有用の新しいポート範囲を選んだら、CsConferencingServer コマンドレットを使用して変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="de9f8-151">After you have selected the new port range for application sharing, you can make your change by using the Set-CsConferencingServer cmdlet.</span></span> <span data-ttu-id="de9f8-152">この変更は、アプリケーションサーバーまたは仲介サーバーで行う必要はありません。これらのサーバーは、アプリケーション共有トラフィックを処理しないためです。</span><span class="sxs-lookup"><span data-stu-id="de9f8-152">This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic.</span></span> <span data-ttu-id="de9f8-153">オーディオトラフィック用に使用されているポートを再割り当てする場合は、これらのサーバーでポートの値を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de9f8-153">You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="de9f8-154">単一の会議サーバーでのアプリケーション共有のポート値を変更するには、Skype for Business Server 管理シェルで次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-154">To modify the port values for application sharing on a single Conferencing server, run a command similar to this from within the Skype for Business Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="de9f8-155">このような変更をすべての会議サーバーで行う場合は、代わりに次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-155">If you want to make these changes on all your Conferencing servers, you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="de9f8-156">ポート設定を変更した後で、変更の影響を受ける各サービスを停止してから再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de9f8-156">After changing port settings, you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="de9f8-157">会議サーバー、アプリケーションサーバー、および仲介サーバーがまったく同じポート範囲を共有していることは必須ではありません。唯一の条件として、すべてのサーバーで固有のポート範囲を確保する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de9f8-157">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers.</span></span> <span data-ttu-id="de9f8-158">ただし、すべてのサーバーで同じポートセットを使用すると、通常、管理が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="de9f8-158">However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="de9f8-159">会議、アプリケーション、および仲介サーバー用の Skype for Business Server のサービス品質ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="de9f8-159">Configure a Quality of Service policy in Skype for Business Server for your Conferencing, Application, and Mediation servers</span></span>

<span data-ttu-id="de9f8-160">ポート範囲を構成すると、指定した種類のすべてのトラフィック (たとえば、すべての音声トラフィック) が同じポートセットを通過するようにすることで、サービスの品質を活用できます。</span><span class="sxs-lookup"><span data-stu-id="de9f8-160">Configuring port ranges facilitates the use of Quality of Service by ensuring that all traffic of a specified type (for example, all audio traffic) travels through the same set of ports.</span></span> <span data-ttu-id="de9f8-161">これにより、特定のパケットをシステムで識別してマークすることが簡単になります。ポート49152が音声トラフィック用に予約されている場合は、ポート49152経由で移動したパケットは、オーディオパケットであることを示す DSCP コードでマークできます。</span><span class="sxs-lookup"><span data-stu-id="de9f8-161">This makes it easy for the system to identify and mark a given packet: if port 49152 is reserved for audio traffic, then any packet traveling through port 49152 can be marked with a DSCP code that indicates that this is an audio packet.</span></span> <span data-ttu-id="de9f8-162">これにより、ルーターは、パケットをオーディオパケットとして識別し、マークされていないパケット (あるサーバーから別のサーバーにファイルをコピーするために使用されるパケットなど) よりも高い優先順位を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="de9f8-162">In turn, this enables routers to identify the packet as an audio packet, and give it higher priority than unmarked packets (such as packets used to copy a file from one server to another).</span></span>

<span data-ttu-id="de9f8-163">ただし、ポートのセットを特定の種類のトラフィックに制限するだけでは、適切な DSCP コードでマークされているポートを経由してパケットが移動されることはありません。</span><span class="sxs-lookup"><span data-stu-id="de9f8-163">However, simply restricting a set of ports to a specific type of traffic does not result in packets traveling through those ports being marked with the appropriate DSCP code.</span></span> <span data-ttu-id="de9f8-164">ポート範囲の定義に加えて、各ポート範囲に関連付ける DSCP コードを指定するサービス品質ポリシーも作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de9f8-164">In addition to defining port ranges, you must also create Quality of Service policies that specify the DSCP code to be associated with each port range.</span></span> <span data-ttu-id="de9f8-165">Skype for Business Server の場合、通常は、オーディオ用とビデオ用の2つのポリシーを作成することになります。</span><span class="sxs-lookup"><span data-stu-id="de9f8-165">For Skype for Business Server, that typically means creating two policies: one for audio and one for video.</span></span>

<span data-ttu-id="de9f8-166">サービス品質ポリシーは、グループポリシーを使って、最も簡単に作成、管理できます。</span><span class="sxs-lookup"><span data-stu-id="de9f8-166">Quality of Service policies are most easily created, and managed, by using Group Policy.</span></span> <span data-ttu-id="de9f8-167">(これらのポリシーは、ローカルセキュリティポリシーを使用して作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="de9f8-167">(These same policies can also be created by using local security policies.</span></span> <span data-ttu-id="de9f8-168">ただし、そのためには、すべてのコンピューターで同じ手順を繰り返す必要があります。)最初の QoS ポリシーのセット (1 つはオーディオ用と1つ) を、会議サーバー、アプリケーションサーバー、または仲介サーバーサービスを実行している Skype for Business Server コンピューターにのみ適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de9f8-168">However, that requires you to repeat the same procedure on each and every computer.) Your initial set of QoS policies (one for audio and one for video) should be applied only to Skype for Business Server computers running the Conferencing server, Application server, and/or Mediation server services.</span></span> <span data-ttu-id="de9f8-169">これらのすべてのコンピューターが同じ Active Directory OU に配置されている場合は、その OU に新しいグループポリシーオブジェクト (GPO) を割り当てるだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="de9f8-169">If all of these computers are located in the same Active Directory OU, you can simply assign the new Group Policy object (GPO) to that OU.</span></span> <span data-ttu-id="de9f8-170">または、別の手順を実行して、指定したコンピューターに新しいポリシーを作成することもできます。たとえば、セキュリティグループに適切なコンピューターを配置し、グループポリシーセキュリティフィルターを使用して、そのセキュリティグループだけに GPO を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="de9f8-170">Alternatively, you can take other steps to target the new policy to the specified computers; for example, you can place the appropriate computers in a security group, then use Group Policy security filtering to apply the GPO just to that security group.</span></span>

<span data-ttu-id="de9f8-171">音声を管理するためのサービス品質ポリシーを作成するには、グループポリシー管理がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="de9f8-171">To create a Quality of Service policy for managing audio, log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="de9f8-172">[グループポリシーの管理] を開き ([**スタート**] をクリックし、[**管理ツール**] をポイントして、[**グループポリシーの管理**] をクリックし)、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-172">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="de9f8-173">[グループポリシーの管理] で、新しいポリシーを作成するコンテナーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="de9f8-173">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="de9f8-174">たとえば、すべての Skype for Business Server コンピューターが Skype for Business Server という名前の OU にある場合、新しいポリシーは Skype for Business Server OU で作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de9f8-174">For example, if all your Skype for Business Server computers are located in an OU named Skype for Business Server, then the new policy should be created in the Skype for Business Server OU.</span></span>

2.  <span data-ttu-id="de9f8-175">適切なコンテナーを右クリックし、[**このドメインに GPO を作成**] をクリックして、ここにリンクを設定します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-175">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="de9f8-176">[**新しい GPO** ] ダイアログボックスで、[**名前**] ボックスに新しいグループポリシーオブジェクトの名前を入力し (たとえば、 **Skype for business Server QoS**)、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de9f8-176">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Skype for Business Server QoS**), and then click **OK**.</span></span>

4.  <span data-ttu-id="de9f8-177">新しく作成したポリシーを右クリックし、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de9f8-177">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="de9f8-178">グループポリシー管理エディターで、[**コンピューターの構成**]、[**ポリシー**]、[ **Windows 設定**] の順に展開し、[**ポリシーベースの QoS**] を右クリックして、[**新しいポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de9f8-178">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="de9f8-179">[**ポリシーベースの QoS** ] ダイアログボックスの [開く] ページで、[**名前**] ボックスに新しいポリシーの名前 (例: **Skype for business Server QoS**) を入力します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-179">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server QoS**) in the **Name** box.</span></span> <span data-ttu-id="de9f8-180">[ **DSCP 値の指定**] を選択し、値を**46**に設定します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-180">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="de9f8-181">[**送信スロットルの比率を指定する**] をオフにして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de9f8-181">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="de9f8-182">次のページで、[すべての**アプリケーション**] が選択されていることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de9f8-182">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="de9f8-183">これにより、すべてのアプリケーションが指定のポート範囲のパケットを指定した DSCP コードに一致させるだけです。</span><span class="sxs-lookup"><span data-stu-id="de9f8-183">This simply ensures that all applications will match packets from the specified port range with the specified DSCP code.</span></span>

8.  <span data-ttu-id="de9f8-184">3番目のページで、[**ソース ip アドレス] と [宛先 ip アドレス**] の両方が選択されていることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de9f8-184">On the third page, make sure that both **Any source IP address and Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="de9f8-185">この2つの設定では、どのコンピューター (IP アドレス) がそれらのパケットを送信したか、どのコンピューター (IP アドレス) がそれらのパケットを受信するかに関係なく、パケットが管理されるようにします。</span><span class="sxs-lookup"><span data-stu-id="de9f8-185">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="de9f8-186">4ページ目で、[**この QoS ポリシーが適用されるプロトコルを選択**してください] ドロップダウンリストから [ **TCP および UDP** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="de9f8-186">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="de9f8-187">TCP (伝送制御プロトコル) と UDP (ユーザーデータグラムプロトコル) は、Skype for Business Server およびそのクライアントアプリケーションで最も一般的に使用される2つのネットワークプロトコルです。</span><span class="sxs-lookup"><span data-stu-id="de9f8-187">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="de9f8-188">見出しの下で、**ソースポート番号を指定**して、[**このソースポートまたは範囲から**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-188">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="de9f8-189">[付随するテキスト] ボックスに、オーディオ送信用に予約されているポート範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-189">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="de9f8-190">たとえば、ポート49152からオーディオトラフィック用にポート57500を予約した場合は、「 **49152:57500**」の形式でポート範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-190">For example, if you reserved ports 49152 through ports 57500 for audio traffic, enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="de9f8-191">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de9f8-191">Click **Finish**.</span></span>

> [!NOTE]  
> <span data-ttu-id="de9f8-192">46の DSCP 値は、何らかの方法で行うことができます。 DSCP 46 はオーディオパケットをマークするために使われることが多いのですが、オーディオ通信には DSCP 46 を使う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="de9f8-192">The DSCP value of 46 is somewhat arbitrary: although DSCP 46 is often used for marking audio packets, you do not have to use DSCP 46 for audio communications.</span></span> <span data-ttu-id="de9f8-193">既に QoS を実装していて、オーディオ用に別の DSCP コード (たとえば、DSCP 40) を使用している場合は、その同じコードを使用するようにサービスの品質ポリシーを構成する必要があります (例:40 for audio)。</span><span class="sxs-lookup"><span data-stu-id="de9f8-193">If you have already implemented QoS and you are using a different DSCP code for audio (for example, DSCP 40), you should configure your Quality of Service policy to use that same code (i.e., 40 for audio).</span></span> <span data-ttu-id="de9f8-194">現在、サービスの品質を実装している場合は、その値が一般的にオーディオパケットをマークするために使用されるため、オーディオには DSCP 46 を使うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="de9f8-194">If you are just now implementing Quality of Service, then it is recommended that you use DSCP 46 for audio, simply because that value is commonly used to mark audio packets.</span></span>

<span data-ttu-id="de9f8-195">オーディオトラフィックの QoS ポリシーを作成した後、ビデオトラフィック用の第2のポリシーを作成します (必要に応じて、アプリケーション共有トラフィックを管理するための第3のポリシーを作成する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="de9f8-195">After you have created the QoS policy for audio traffic, you should then create a second policy for video traffic (and, optionally, a third policy for managing application sharing traffic).</span></span> <span data-ttu-id="de9f8-196">ビデオのポリシーを作成するには、オーディオポリシーを作成する場合と同じ基本的な手順に従い、次のように置き換えます。</span><span class="sxs-lookup"><span data-stu-id="de9f8-196">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="de9f8-197">別の (一意の) ポリシー名 (「 **Skype For Business Server のビデオ**」など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-197">Use a different (and unique) policy name (for example, **Skype for Business Server Video**).</span></span>

  - <span data-ttu-id="de9f8-198">DSCP 値を46ではなく、 **34**に設定します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-198">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="de9f8-199">(DSCP 値34は使う必要がないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="de9f8-199">(Note that you do not have to use a DSCP value of 34.</span></span> <span data-ttu-id="de9f8-200">唯一の要件は、オーディオに使用したものとは異なる DSCP 値をビデオに使用することです。</span><span class="sxs-lookup"><span data-stu-id="de9f8-200">The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="de9f8-201">以前に構成されたポート範囲をビデオトラフィックに使用します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-201">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="de9f8-202">たとえば、ビデオ用にポート 57501 ~ 65535 を予約している場合は、ポート範囲を次のよう**57501:65535**に設定します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-202">For example, if you have reserved ports 57501 through 65535 for video, set the port range to this: **57501:65535**.</span></span>

<span data-ttu-id="de9f8-203">アプリケーション共有トラフィックを管理するためのポリシーを作成する場合は、3番目のポリシーを作成し、次のように置き換えます。</span><span class="sxs-lookup"><span data-stu-id="de9f8-203">If you decide to create a policy for managing application sharing traffic, you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="de9f8-204">別の (一意の) ポリシー名 (「 **Skype For Business Server アプリケーション共有**」など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-204">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="de9f8-205">DSCP 値を46の代わりに**24**に設定します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-205">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="de9f8-206">(この場合も、DSCP 値24を使用する必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="de9f8-206">(Again, you do not have to use a DSCP value of 24.</span></span> <span data-ttu-id="de9f8-207">唯一の要件として、アプリケーション共有には、オーディオまたはビデオに使用したのとは異なる DSCP 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-207">The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="de9f8-208">以前に構成されたポート範囲をビデオトラフィックに使用します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-208">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="de9f8-209">たとえば、アプリケーション共有用にポート 40803 ~ 49151 を予約している場合は、ポート範囲を " **40803:49151**" に設定します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-209">For example, if you have reserved ports 40803 through 49151 for application sharing, set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="de9f8-210">作成した新しいポリシーは、Skype for Business Server コンピューターのグループポリシーが更新されるまで有効になりません。</span><span class="sxs-lookup"><span data-stu-id="de9f8-210">The new policies you have created will not take effect until Group Policy has been refreshed on your Skype for Business Server computers.</span></span> <span data-ttu-id="de9f8-211">グループ ポリシーは定期的に自動更新されますが、グループ ポリシーを更新する必要がある各コンピューター上で次のコマンドを実行すると、即座に強制的に更新することができます。</span><span class="sxs-lookup"><span data-stu-id="de9f8-211">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="de9f8-212">このコマンドは、Skype for Business Server 管理シェルから、または管理者の資格情報で実行されているコマンドウィンドウから実行できます。</span><span class="sxs-lookup"><span data-stu-id="de9f8-212">This command can be run from within the Skype for Business Server Management Shell or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="de9f8-213">管理者の資格情報のもとでコマンド ウィンドウを開くには、[**スタート**] メニューをクリックし、[**コマンド プロンプト**] を右クリックして、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de9f8-213">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="de9f8-214">新しい QoS ポリシーが適用されていることを確認するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="de9f8-214">To verify that the new QoS policies have been applied, do the following:</span></span>

1.  <span data-ttu-id="de9f8-215">Skype for Business Server コンピューターで、[**スタート**] をクリックし、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de9f8-215">On a Skype for Business Server computer, click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="de9f8-216">[**実行**] ダイアログボックスで、「 **regedit**」と入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-216">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="de9f8-217">レジストリエディターで、[**コンピューター**] を展開し、[ **\_HKEY ローカル\_コンピューター**]、[**ソフトウェア**]、[**ポリシー**]、[ **Microsoft**]、[ **Windows**]、[ **QoS**] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-217">In Registry Editor, expand **Computer**, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Policies**, expand **Microsoft**, expand **Windows**, and then click **QoS**.</span></span> <span data-ttu-id="de9f8-218">[ **Qos** ] の下に、作成した各 qos ポリシーのレジストリキーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="de9f8-218">Under **QoS** you should see registry keys for each of the QoS policies you just created.</span></span> <span data-ttu-id="de9f8-219">たとえば、2つの新しいポリシー (Skype for Business Server Audio QoS およびその他の Skype for business Server ビデオ QoS という名前) を作成した場合は、Skype for Business Server Audio QoS および Skype for Business server Video qos のレジストリエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="de9f8-219">For example, if you created two new policies (one named Skype for Business Server Audio QoS and the other named Skype for Business Server Video QoS), you should see registry entries for Skype for Business Server Audio QoS and Skype for Business Server Video QoS.</span></span>

<span data-ttu-id="de9f8-220">ネットワークパケットが適切な DSCP 値でマークされていることを確認するには、次の手順に従って、各コンピューターに新しいレジストリエントリを作成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="de9f8-220">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="de9f8-221">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de9f8-221">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="de9f8-222">[**実行**] ダイアログボックスで、「 **regedit**」と入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-222">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="de9f8-223">レジストリエディターで、[ **\_HKEY ローカル\_コンピューター**]、[**システム**]、[ **CurrentControlSet**] の順に展開し、[**サービス**] を展開して、[ **Tcpip**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-223">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="de9f8-224">[ **Tcpip**] を右クリックし、[**新規作成**] をポイントして、[**キー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de9f8-224">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="de9f8-225">新しいレジストリキーが作成されたら、「 **QoS**」と入力し、enter キーを押してキーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-225">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="de9f8-226">[ **QoS**] を右クリックし、[**新規作成**] をポイントして、[**文字列値**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de9f8-226">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="de9f8-227">新しいレジストリ値が作成されたら、[ **NLA を使用しない**] と入力し、enter キーを押して値の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-227">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="de9f8-228">[ **NLA を使わない**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="de9f8-228">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="de9f8-229">[**文字列の編集**] ダイアログボックスで、[**値のデータ**] ボックスに「 **1** 」と入力して、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de9f8-229">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="de9f8-230">レジストリエディターを終了し、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-230">Close the Registry Editor and reboot your computer.</span></span>
