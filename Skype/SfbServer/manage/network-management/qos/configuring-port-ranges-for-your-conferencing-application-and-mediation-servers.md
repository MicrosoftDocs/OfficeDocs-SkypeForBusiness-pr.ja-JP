---
title: ポートの範囲と、会議、アプリケーション、および仲介サーバーのサービスの品質ポリシーを構成します。
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: この資料では、ポートの範囲と、会議、アプリケーション、および仲介サーバーのサービスの品質ポリシーを構成する方法について説明します。
ms.openlocfilehash: f1452c9166eb557d186b8569a37d5abb885d4354
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199560"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="35579-103">ポートの範囲と、会議、アプリケーション、および仲介サーバーのサービスの品質ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="35579-103">Configuring port ranges and a Quality of Service policy for your Conferencing, Application, and Mediation servers</span></span>

<span data-ttu-id="35579-104">この資料では、ポートの範囲と、会議、アプリケーション、および仲介サーバーのサービスの品質ポリシーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="35579-104">This article describes how to configure port ranges and a Quality of Service policy for your Conferencing, Application, and Mediation servers.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="35579-105">ポート範囲を構成します。</span><span class="sxs-lookup"><span data-stu-id="35579-105">Configure port ranges</span></span>

<span data-ttu-id="35579-106">品質のサービスを実装するには、オーディオ、ビデオ、およびアプリケーション共有、会議、アプリケーション、および仲介サーバー上の同じポート範囲を構成する必要があります。さらに、これらのポートの範囲は、どのような方法でする必要があります重複しません。</span><span class="sxs-lookup"><span data-stu-id="35579-106">To implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way.</span></span> <span data-ttu-id="35579-107">簡単な例を使用するには、会議サーバー上のビデオの 10999 から 10000 のポートを使用すると仮定します。</span><span class="sxs-lookup"><span data-stu-id="35579-107">To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers.</span></span> <span data-ttu-id="35579-108">つまり、アプリケーションおよび仲介サーバーのビデオのポートを通じて 10999 10000 も予約する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35579-108">That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers.</span></span> <span data-ttu-id="35579-109">有効でない場合、期待どおりに QoS が動作しません。</span><span class="sxs-lookup"><span data-stu-id="35579-109">If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="35579-110">同様に、ポートを介して、ビデオの場合、10999 10000 が、オーディオ用の予約ポート 11999 で 10500 を予約すると仮定します。</span><span class="sxs-lookup"><span data-stu-id="35579-110">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio.</span></span> <span data-ttu-id="35579-111">これにより、ポートの範囲は重複しているために、サービスの品質の問題が生じる。</span><span class="sxs-lookup"><span data-stu-id="35579-111">This can create problems for Quality of Service, because the port ranges overlap.</span></span> <span data-ttu-id="35579-112">各モダリティでは、QoS、ポートの一意のセットをいる必要があります: ビデオの場合、10999 から 10000 のポートを使用するかどうかは、別の範囲 (たとえば、オーディオ用の 11999 を 11000) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35579-112">With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999, for audio).</span></span>

<span data-ttu-id="35579-113">既定では、オーディオとビデオのポート範囲が重複しない Skype のビジネス サーバーです。ただし、ポートの範囲は、オーディオとビデオのポート範囲と重なる部分を共有するアプリケーションに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="35579-113">By default, audio and video port ranges do not overlap in Skype for Business Server; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="35579-114">(、つまり一意であるこれらの範囲のことです。)ビジネス サーバー管理シェルの Skype 内から次のコマンドを実行することによって、会議、アプリケーション、および仲介サーバーの既存のポートの範囲を確認できます。</span><span class="sxs-lookup"><span data-stu-id="35579-114">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Skype for Business Server Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> <span data-ttu-id="35579-115">各ポートの種類: オーディオ、ビデオ、およびアプリケーションの共有 – が 2 つの個別のプロパティ値を割り当てられた、上記のコマンドで示すように、: ポートの開始とポートの数です。</span><span class="sxs-lookup"><span data-stu-id="35579-115">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count.</span></span> <span data-ttu-id="35579-116">ポートの開始に示す最初のポートを使用するモードです。たとえば、オーディオ ポートの開始がいることを意味 50000 と等しい場合オーディオ トラフィック用に使用する最初のポート、ポート 50000 です。</span><span class="sxs-lookup"><span data-stu-id="35579-116">The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000.</span></span> <span data-ttu-id="35579-117">オーディオ ポート数が 2 (これは、有効な値ではありませんが、説明のため、ここで使用)、オーディオの 2 つのポートが割り当てられていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="35579-117">If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes), that means that only two ports are allocated for audio.</span></span> <span data-ttu-id="35579-118">最初のポートは、ポート 50000 とは、2 つのポートの合計、2 番目のポートは、ポート (ポートの範囲は連続している必要がある) を 50, 001 をする必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="35579-118">If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous).</span></span> <span data-ttu-id="35579-119">その結果、オーディオ ポートの範囲は、ポート 50000 から 50, 001、包括的になります。</span><span class="sxs-lookup"><span data-stu-id="35579-119">As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><br><span data-ttu-id="35579-120">またアプリケーション サーバーと仲介サーバーのみサポートしている QoS のオーディオになります。ビデオやアプリケーションの共有、アプリケーション サーバーまたは仲介サーバーのポートを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="35579-120">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>

<span data-ttu-id="35579-121">上記の 3 つのコマンドを実行すると、Business Server の Skype のデフォルトのポートの値が構成されている次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="35579-121">If you run the preceding three commands, you'll see that that the default port values for Skype for Business Server are configured like this:</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35579-122">プロパティ</span><span class="sxs-lookup"><span data-stu-id="35579-122">Property</span></span></th>
<th><span data-ttu-id="35579-123">会議サーバー</span><span class="sxs-lookup"><span data-stu-id="35579-123">Conferencing Server</span></span></th>
<th><span data-ttu-id="35579-124">アプリケーション サーバー</span><span class="sxs-lookup"><span data-stu-id="35579-124">Application Server</span></span></th>
<th><span data-ttu-id="35579-125">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="35579-125">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35579-126">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="35579-126">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="35579-127">49152</span><span class="sxs-lookup"><span data-stu-id="35579-127">49152</span></span></p></td>
<td><p><span data-ttu-id="35579-128">49152</span><span class="sxs-lookup"><span data-stu-id="35579-128">49152</span></span></p></td>
<td><p><span data-ttu-id="35579-129">49152</span><span class="sxs-lookup"><span data-stu-id="35579-129">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35579-130">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="35579-130">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="35579-131">8348</span><span class="sxs-lookup"><span data-stu-id="35579-131">8348</span></span></p></td>
<td><p><span data-ttu-id="35579-132">8348</span><span class="sxs-lookup"><span data-stu-id="35579-132">8348</span></span></p></td>
<td><p><span data-ttu-id="35579-133">8348</span><span class="sxs-lookup"><span data-stu-id="35579-133">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35579-134">VideoPortStart</span><span class="sxs-lookup"><span data-stu-id="35579-134">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="35579-135">57501</span><span class="sxs-lookup"><span data-stu-id="35579-135">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35579-136">VideoPortCount</span><span class="sxs-lookup"><span data-stu-id="35579-136">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="35579-137">8034</span><span class="sxs-lookup"><span data-stu-id="35579-137">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35579-138">ApplicationSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="35579-138">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="35579-139">49152</span><span class="sxs-lookup"><span data-stu-id="35579-139">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35579-140">ApplicationSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="35579-140">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="35579-141">16383</span><span class="sxs-lookup"><span data-stu-id="35579-141">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="35579-142">前述した、ビジネスのサーバー ・ ポートの QoS の Skype を設定するとき、することを確認します: 1) お客様の会議、アプリケーション、および仲介サーバーの間でのオーディオ ポートの設定が同じ2) のポート範囲が重ならないようにします。</span><span class="sxs-lookup"><span data-stu-id="35579-142">As noted previously, when configuring Skype for Business Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="35579-143">場合は上記の表をよく見る、3 つのサーバーの種類の間でポートの範囲が同じであるが表示されます。</span><span class="sxs-lookup"><span data-stu-id="35579-143">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="35579-144">など開始オーディオ ポートがポート 49152 サーバーの種類ごとに設定されて、各サーバーでオーディオ用に予約されたポート数の合計も同じ: 8348。</span><span class="sxs-lookup"><span data-stu-id="35579-144">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="35579-145">ただし、ポートの範囲はオーバー ラップ: 開始ポート 49152、オーディオ ・ ポート、ポート設定も確保アプリケーションを共有するためです。</span><span class="sxs-lookup"><span data-stu-id="35579-145">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="35579-146">サービスの品質の最適な使用をするためにアプリケーションの共有を再構成する一意のポート範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="35579-146">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="35579-147">たとえば、40803 のポートで開始して、8348 ポートを使用するアプリケーションの共有を構成する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="35579-147">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="35579-148">(なぜ 8348 ポートですか。</span><span class="sxs-lookup"><span data-stu-id="35579-148">(Why 8348 ports?</span></span> <span data-ttu-id="35579-149">一緒--これらの値を追加する場合は 40803 + 8348 - つまりアプリケーション共有を使用するポート 40803 49150 のポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="35579-149">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="35579-150">オーディオ ポートは、ポート 49152 までは開始されません、ためするは、ポート範囲を重複します。)</span><span class="sxs-lookup"><span data-stu-id="35579-150">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="35579-151">アプリケーション共有の新しいポートの範囲を選択した後は、セット CsConferencingServer コマンドレットを使用して、変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="35579-151">After you have selected the new port range for application sharing, you can make your change by using the Set-CsConferencingServer cmdlet.</span></span> <span data-ttu-id="35579-152">この変更は、これらのサーバーは、アプリケーションの共有のトラフィックを処理しないため、アプリケーション サーバーまたは仲介サーバーを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="35579-152">This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic.</span></span> <span data-ttu-id="35579-153">オーディオ トラフィックに使用するポートを再割り当てする場合にこれらのサーバー上のポートの値を変更する必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="35579-153">You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="35579-154">単一の会議サーバー上の共有アプリケーションのポートの値を変更するには、ビジネス サーバー管理シェルの Skype 内からこのようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="35579-154">To modify the port values for application sharing on a single Conferencing server, run a command similar to this from within the Skype for Business Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="35579-155">会議のすべてのサーバーに対して変更を行う場合は、代わりにこのコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="35579-155">If you want to make these changes on all your Conferencing servers, you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="35579-156">ポートの設定を変更した後は、停止し、変更の影響を受ける各サービスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35579-156">After changing port settings, you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="35579-157">会議サーバー、アプリケーション サーバー、および仲介サーバーが、正確な同じポートの範囲を共有することが必須ではありません。唯一の真の要件を確保一意のポートの範囲のすべてのサーバーです。</span><span class="sxs-lookup"><span data-stu-id="35579-157">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers.</span></span> <span data-ttu-id="35579-158">ただし、管理通常すべてのサーバー上のポートの同じセットを使用して容易になります。</span><span class="sxs-lookup"><span data-stu-id="35579-158">However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="35579-159">ポリシーを構成するサービスの品質で Skype ビジネス サーバーの会議、アプリケーション、および仲介サーバーの</span><span class="sxs-lookup"><span data-stu-id="35579-159">Configure a Quality of Service policy in Skype for Business Server for your Conferencing, Application, and Mediation servers</span></span>

<span data-ttu-id="35579-160">ポート範囲を構成するには、指定された種類 (たとえば、オーディオ トラフィックをすべて) のすべてのトラフィックが通過ポートの同じセットを確保することにより品質のサービスの使用が容易になります。</span><span class="sxs-lookup"><span data-stu-id="35579-160">Configuring port ranges facilitates the use of Quality of Service by ensuring that all traffic of a specified type (for example, all audio traffic) travels through the same set of ports.</span></span> <span data-ttu-id="35579-161">システムを識別し、与えられたパケットをマークするが容易になります。: ポート 49152 は、オーディオ トラフィック用に予約されて場合は、ポート 49152 経由で転送されるパケットに DSCP コード、オーディオ パケットであることを示しますをマークできます。</span><span class="sxs-lookup"><span data-stu-id="35579-161">This makes it easy for the system to identify and mark a given packet: if port 49152 is reserved for audio traffic, then any packet traveling through port 49152 can be marked with a DSCP code that indicates that this is an audio packet.</span></span> <span data-ttu-id="35579-162">、これにより、ルーターがオーディオ パケットでは、パケットを識別し、パケットが 1 つのサーバーからファイルをコピーするために使用) などのマークが付いていないパケットよりも高い優先順位を付けます。</span><span class="sxs-lookup"><span data-stu-id="35579-162">In turn, this enables routers to identify the packet as an audio packet, and give it higher priority than unmarked packets (such as packets used to copy a file from one server to another).</span></span>

<span data-ttu-id="35579-163">ただし、単に特定の種類のトラフィックをポートのセットを制限することは行われませんでパケットの DSCP に適切なコードでマークされているこれらのポートを通ってします。</span><span class="sxs-lookup"><span data-stu-id="35579-163">However, simply restricting a set of ports to a specific type of traffic does not result in packets traveling through those ports being marked with the appropriate DSCP code.</span></span> <span data-ttu-id="35579-164">ポート範囲を定義するには、各ポートの範囲に関連する DSCP コードを指定するサービスの品質ポリシーを作成することもする必要があります。</span><span class="sxs-lookup"><span data-stu-id="35579-164">In addition to defining port ranges, you must also create Quality of Service policies that specify the DSCP code to be associated with each port range.</span></span> <span data-ttu-id="35579-165">ビジネス サーバーの Skype のことに 2 つのポリシーを作成する: オーディオとビデオのいずれかのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="35579-165">For Skype for Business Server, that typically means creating two policies: one for audio and one for video.</span></span>

<span data-ttu-id="35579-166">サービス ポリシーの品質は、最も簡単に作成、管理、グループ ポリシーを使用してです。</span><span class="sxs-lookup"><span data-stu-id="35579-166">Quality of Service policies are most easily created, and managed, by using Group Policy.</span></span> <span data-ttu-id="35579-167">(これらの同じポリシー作成することもローカル セキュリティ ポリシーを使用しています。</span><span class="sxs-lookup"><span data-stu-id="35579-167">(These same policies can also be created by using local security policies.</span></span> <span data-ttu-id="35579-168">ただし、する必要のある各コンピューターで同じ手順を繰り返すことです。)(オーディオ) とビデオのいずれかに、QoS ポリシーの初期セットは、Skype の会議サーバー、アプリケーション サーバー、仲介サーバー サービスを実行しているビジネスのサーバー コンピューターにのみ適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35579-168">However, that requires you to repeat the same procedure on each and every computer.) Your initial set of QoS policies (one for audio and one for video) should be applied only to Skype for Business Server computers running the Conferencing server, Application server, and/or Mediation server services.</span></span> <span data-ttu-id="35579-169">同じ Active Directory OU には、これらすべてのコンピューターが存在する場合その OU に新しいグループ ポリシー オブジェクト (GPO) を単に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="35579-169">If all of these computers are located in the same Active Directory OU, you can simply assign the new Group Policy object (GPO) to that OU.</span></span> <span data-ttu-id="35579-170">代わりに、新しいポリシーを指定されたコンピューターを対象とするその他の手順を実行できます。たとえば、セキュリティ グループに適切なコンピューターを配置し、そのセキュリティ グループに対してのみ GPO を適用するグループ ポリシーのセキュリティ フィルターを使用します。</span><span class="sxs-lookup"><span data-stu-id="35579-170">Alternatively, you can take other steps to target the new policy to the specified computers; for example, you can place the appropriate computers in a security group, then use Group Policy security filtering to apply the GPO just to that security group.</span></span>

<span data-ttu-id="35579-171">オーディオを管理するためのサービスの品質ポリシーを作成するには、グループ ポリシーの管理がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="35579-171">To create a Quality of Service policy for managing audio, log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="35579-172">グループ ポリシーの管理] を開きます ([**スタート**] ボタン、 **[管理ツール**] をポイントし、[**グループ ポリシーの管理**] をクリック) し、次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="35579-172">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="35579-173">グループ ポリシーの管理では、新しいポリシーを作成するコンテナーを探します。</span><span class="sxs-lookup"><span data-stu-id="35579-173">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="35579-174">などのビジネス サーバー コンピューターに対して、すべての Skype は Skype をという名前のビジネス サーバー OU に存在する場合、新しいポリシーが作成、Skype でビジネス サーバー OU の。</span><span class="sxs-lookup"><span data-stu-id="35579-174">For example, if all your Skype for Business Server computers are located in an OU named Skype for Business Server, then the new policy should be created in the Skype for Business Server OU.</span></span>

2.  <span data-ttu-id="35579-175">適切なコンテナーを右クリックし、**このドメインに GPO を作成しここにリンク**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="35579-175">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="35579-176">**新しい GPO** ] ダイアログ ボックスで (たとえば、**ビジネス サーバーの QoS の Skype**) の [**名前**] ボックスに新しいグループ ポリシー オブジェクトの名前を入力し、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="35579-176">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Skype for Business Server QoS**), and then click **OK**.</span></span>

4.  <span data-ttu-id="35579-177">新しく作成したポリシーを右クリックし、し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="35579-177">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="35579-178">グループ ポリシー管理エディターで、**コンピューター**の構成**ポリシー**] を展開、 **Windows の設定**を展開し、**ポリシー ベースの QoS**では、右、[**新規ポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="35579-178">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="35579-179">**ポリシー ベースの QoS** ] ダイアログ ボックスで [開始] ページで、 **[名前**] ボックスで新しいポリシー (たとえば、**ビジネス サーバーの QoS の Skype**) の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="35579-179">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server QoS**) in the **Name** box.</span></span> <span data-ttu-id="35579-180">**DSCP 値を指定**を選択し、 **46**に値を設定します。</span><span class="sxs-lookup"><span data-stu-id="35579-180">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="35579-181">オフの場合、**アウト バウンドのスロットル率を指定**のままにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="35579-181">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="35579-182">次のページでは、**すべてのアプリケーション**が選択されているかどうかを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="35579-182">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="35579-183">これは、ようにするためだけのすべてのアプリケーションが指定した DSCP コードで指定したポートの範囲からのパケットを一致します。</span><span class="sxs-lookup"><span data-stu-id="35579-183">This simply ensures that all applications will match packets from the specified port range with the specified DSCP code.</span></span>

8.  <span data-ttu-id="35579-184">3 番目のページでは、両方**のソース IP アドレスと宛先の IP アドレス**が選択されているし、[**次へ**] をクリックを確認します。</span><span class="sxs-lookup"><span data-stu-id="35579-184">On the third page, make sure that both **Any source IP address and Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="35579-185">これら 2 つの設定では、パケットが管理されることを確認してどのコンピューター (IP アドレス) は、これらのパケットを送信し、これらのパケットをどのコンピューター (IP アドレス) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="35579-185">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="35579-186">[4] ページでは、**この QoS ポリシーを適用するプロトコルを選択して**ドロップダウン リストから**TCP および UDP**を選択します。</span><span class="sxs-lookup"><span data-stu-id="35579-186">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="35579-187">TCP (伝送制御プロトコル) と UDP (ユーザー データグラム プロトコル) は、最も一般的使用 Skype ビジネス サーバーとそのクライアント アプリケーションの 2 つのネットワーク プロトコルです。</span><span class="sxs-lookup"><span data-stu-id="35579-187">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="35579-188">**発信元ポート番号の指定**の見出しの下には、**この送信元ポートまたは範囲から**選択します。</span><span class="sxs-lookup"><span data-stu-id="35579-188">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="35579-189">付随するテキスト ボックスで、オーディオの転送用に予約されたポートの範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="35579-189">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="35579-190">57500 オーディオ トラフィック用のポートをポート 49152 を予約する場合のこの形式を使用するポートの範囲を入力するたとえば、: **49152:57500**。</span><span class="sxs-lookup"><span data-stu-id="35579-190">For example, if you reserved ports 49152 through ports 57500 for audio traffic, enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="35579-191">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="35579-191">Click **Finish**.</span></span>

> [!NOTE]  
> <span data-ttu-id="35579-192">46 の DSCP 値は多少変動: DSCP 46 がオーディオ パケットのマーキングの使用が多くの場合、必要はありません音声通信の DSCP 46 を使用します。</span><span class="sxs-lookup"><span data-stu-id="35579-192">The DSCP value of 46 is somewhat arbitrary: although DSCP 46 is often used for marking audio packets, you do not have to use DSCP 46 for audio communications.</span></span> <span data-ttu-id="35579-193">QoS を既に実装しているオーディオの場合 (たとえば、DSCP の 40) 異なる DSCP コードを使用している場合は、その同じコード (つまり、オーディオの 40) を使用するようにサービスの品質ポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35579-193">If you have already implemented QoS and you are using a different DSCP code for audio (for example, DSCP 40), you should configure your Quality of Service policy to use that same code (i.e., 40 for audio).</span></span> <span data-ttu-id="35579-194">今、サービスの品質を実装しているかどうかは、単にオーディオの場合、DSCP 46 を使用することをお勧めする値はオーディオ パケットをマークするためです。</span><span class="sxs-lookup"><span data-stu-id="35579-194">If you are just now implementing Quality of Service, then it is recommended that you use DSCP 46 for audio, simply because that value is commonly used to mark audio packets.</span></span>

<span data-ttu-id="35579-195">オーディオ トラフィックの QoS ポリシーを作成した後、ビデオのトラフィック (および、必要に応じて、アプリケーションの共有のトラフィックを管理するための 3 つ目のポリシー) の 2 番目のポリシーを作成してください。</span><span class="sxs-lookup"><span data-stu-id="35579-195">After you have created the QoS policy for audio traffic, you should then create a second policy for video traffic (and, optionally, a third policy for managing application sharing traffic).</span></span> <span data-ttu-id="35579-196">ビデオのポリシーを作成するにした後に、オーディオのポリシーを作成するときにこれらの置換を行うと同じ基本的な手順に従います。</span><span class="sxs-lookup"><span data-stu-id="35579-196">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="35579-197">異なる (そして固有) のポリシーの名前 (たとえば、**ビジネス サーバー ビデオ Skype**) を使用します。</span><span class="sxs-lookup"><span data-stu-id="35579-197">Use a different (and unique) policy name (for example, **Skype for Business Server Video**).</span></span>

  - <span data-ttu-id="35579-198">46 ではなく**34** DSCP 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="35579-198">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="35579-199">(注 34 の DSCP 値を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="35579-199">(Note that you do not have to use a DSCP value of 34.</span></span> <span data-ttu-id="35579-200">唯一の要件はオーディオ用に使用すると、ビデオの別の DSCP 値を使用すること) です。</span><span class="sxs-lookup"><span data-stu-id="35579-200">The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="35579-201">ビデオのトラフィックには、以前に構成されたポートの範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="35579-201">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="35579-202">たとえば、57501 ビデオの 65535 までからのポートを予約する場合、このポート範囲をこれに設定: **57501:65535**。</span><span class="sxs-lookup"><span data-stu-id="35579-202">For example, if you have reserved ports 57501 through 65535 for video, set the port range to this: **57501:65535**.</span></span>

<span data-ttu-id="35579-203">アプリケーション共有トラフィックを管理するポリシーを作成する場合は、作成する必要が 3 つ目のポリシーでは、次の置換を行います。</span><span class="sxs-lookup"><span data-stu-id="35579-203">If you decide to create a policy for managing application sharing traffic, you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="35579-204">異なる (そして固有) のポリシーの名前 (たとえば、**ビジネス サーバー アプリケーションを共有するための Skype**) を使用します。</span><span class="sxs-lookup"><span data-stu-id="35579-204">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="35579-205">46 ではなく**24**に DSCP 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="35579-205">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="35579-206">(繰り返しますが、必要はありません 24 の DSCP 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="35579-206">(Again, you do not have to use a DSCP value of 24.</span></span> <span data-ttu-id="35579-207">唯一の要件は、オーディオやビデオを使用するよりもアプリケーションの共有には、別の DSCP 値を使用すること。)</span><span class="sxs-lookup"><span data-stu-id="35579-207">The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="35579-208">ビデオのトラフィックには、以前に構成されたポートの範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="35579-208">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="35579-209">など 40803 49151 アプリケーションを共有するためのポートを予約する場合、このポートの範囲をこれに設定: **40803:49151**。</span><span class="sxs-lookup"><span data-stu-id="35579-209">For example, if you have reserved ports 40803 through 49151 for application sharing, set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="35579-210">Business Server コンピューターの Skype でグループ ポリシーを更新するまで、作成した新しいポリシーは有効になりません。</span><span class="sxs-lookup"><span data-stu-id="35579-210">The new policies you have created will not take effect until Group Policy has been refreshed on your Skype for Business Server computers.</span></span> <span data-ttu-id="35579-211">グループ ポリシーは定期的に自動更新されますが、グループ ポリシーを更新する必要がある各コンピューター上で次のコマンドを実行すると、即座に強制的に更新することができます。</span><span class="sxs-lookup"><span data-stu-id="35579-211">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="35579-212">ビジネス サーバー管理シェルまたは管理者の資格情報で実行されている任意のコマンド ウィンドウから、Skype 内でこのコマンドから実行することができます。</span><span class="sxs-lookup"><span data-stu-id="35579-212">This command can be run from within the Skype for Business Server Management Shell or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="35579-213">管理者の資格情報のもとでコマンド ウィンドウを開くには、[**スタート**] メニューをクリックし、[**コマンド プロンプト**] を右クリックして、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="35579-213">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="35579-214">新しい QoS ポリシーが適用されていることを確認するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="35579-214">To verify that the new QoS policies have been applied, do the following:</span></span>

1.  <span data-ttu-id="35579-215">ビジネス サーバー コンピューターの Skype では、[**開始**] をクリックし、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="35579-215">On a Skype for Business Server computer, click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="35579-216">**実行**] ダイアログ ボックスで **「regedit」** と入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="35579-216">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="35579-217">レジストリ エディターで、**コンピューター**を展開する**HKEY\_ローカル\_マシン\*\*\*\*ソフトウェア**を展開し、**ポリシー**を展開、**マイクロソフト**の展開、 **Windows**を展開し、[クリックして**QoS**です。</span><span class="sxs-lookup"><span data-stu-id="35579-217">In Registry Editor, expand **Computer**, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Policies**, expand **Microsoft**, expand **Windows**, and then click **QoS**.</span></span> <span data-ttu-id="35579-218">**QoS**で作成した QoS ポリシーのレジストリ キーを参照してください必要があります。</span><span class="sxs-lookup"><span data-stu-id="35579-218">Under **QoS** you should see registry keys for each of the QoS policies you just created.</span></span> <span data-ttu-id="35579-219">など (ビジネス サーバー オーディオの qos の 1 つ名前付きの Skype) とその他の名前付きの Skype ビジネス サーバー ビデオ QoS の 2 つの新しいポリシーを作成した場合は、エントリが表示されますレジストリ Skype のビジネス サーバー オーディオ QoS と Skype のビジネス サーバー ビデオ QoS のです。</span><span class="sxs-lookup"><span data-stu-id="35579-219">For example, if you created two new policies (one named Skype for Business Server Audio QoS and the other named Skype for Business Server Video QoS), you should see registry entries for Skype for Business Server Audio QoS and Skype for Business Server Video QoS.</span></span>

<span data-ttu-id="35579-220">ネットワーク パケットが DSCP 値でマークされていることを確認するには、次の手順を完了して新しいレジストリ エントリの各コンピューターで作成することも必要があります。</span><span class="sxs-lookup"><span data-stu-id="35579-220">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="35579-221">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="35579-221">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="35579-222">**実行**] ダイアログ ボックスで **「regedit」** と入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="35579-222">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="35579-223">レジストリ エディターで、拡張**HKEY\_ローカル\_マシン**、**システム**を展開し、 **CurrentControlSet**を展開し、**サービス**の展開および**Tcpip**を展開し、します。</span><span class="sxs-lookup"><span data-stu-id="35579-223">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="35579-224">**Tcpip**] を右クリックして、**新規**作成] をポイントし、[**キー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="35579-224">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="35579-225">新しいレジストリ キーが作成されるは、 **QoS**を入力し、enter キーを押してキーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="35579-225">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="35579-226">**QoS**を右クリックし、**新規**作成] をポイントし、[**文字列値**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="35579-226">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="35579-227">新しいレジストリ値を作成すると後、は、 **NLA を使用しない**を入力し、値の名前を変更するのには ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="35579-227">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="35579-228">**NLA を使用しない**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="35579-228">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="35579-229">**文字列の編集**] ダイアログ ボックスで、[**値データ**] ボックスに**1**を入力し、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="35579-229">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="35579-230">レジストリ エディターを終了し、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="35579-230">Close the Registry Editor and reboot your computer.</span></span>
