---
title: 'Lync Server 2013: ビデオ帯域幅の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cca8df1ea3c4c2458851da24ab8b39dbbab2d3d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734447"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a><span data-ttu-id="04590-102">Lync Server 2013 でのビデオ帯域幅の構成</span><span class="sxs-lookup"><span data-stu-id="04590-102">Configuring video bandwidth in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04590-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="04590-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="04590-104">Lync Server 2013 には、2パーティーの通話とマルチパーティの会議のビデオを管理するためのいくつかの設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="04590-104">Lync Server 2013 includes several settings for managing video for two-party calls and multiparty conferences.</span></span> <span data-ttu-id="04590-105">Lync Server 2013 を展開するときは、既定の設定が組織に適しているかどうかを評価し、必要に応じて変更します。</span><span class="sxs-lookup"><span data-stu-id="04590-105">When you deploy Lync Server 2013, you should evaluate whether the default settings are appropriate for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="04590-106">このセクションで説明するパラメーターは、2人の通話とマルチパーティの会議の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="04590-106">The parameters described in this section apply to both two-party calls and multiparty conferencing.</span></span> <span data-ttu-id="04590-107">これらの設定を表示または変更するには、次のいずれかのコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="04590-107">View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="04590-108">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="04590-108">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="04590-109">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="04590-109">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="04590-110">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="04590-110">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="04590-111">会議ポリシーで、次の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="04590-111">Verify the following settings in your conferencing policy:</span></span>

  - <span data-ttu-id="04590-112">**VideoBitRateKb**   この設定では、ユーザーが送信したビデオに使用されるビデオの最大ビットレート (kbps) を指定します。</span><span class="sxs-lookup"><span data-stu-id="04590-112">**VideoBitRateKb**   This setting specifies the maximum video bit rate in kilobits per second (kbps) used for video sent by a user.</span></span> <span data-ttu-id="04590-113">既定値は 5万 kbps です。</span><span class="sxs-lookup"><span data-stu-id="04590-113">The default value is 50000 kbps.</span></span> <span data-ttu-id="04590-114">有効な値は 0 ~ 5万です。</span><span class="sxs-lookup"><span data-stu-id="04590-114">Valid values are 0 to 50000.</span></span>
    
    <span data-ttu-id="04590-115">この設定は、メインビデオとパノラマビデオに個別に適用されます。</span><span class="sxs-lookup"><span data-stu-id="04590-115">This setting applies separately to main video and panoramic video.</span></span>
    
    <span data-ttu-id="04590-116">例: 2000 kbps を指定した場合、Lync Server は、パノラマビデオストリームについて、メインビデオストリームと 2000 kbps の 2000 kbps を送信できます。</span><span class="sxs-lookup"><span data-stu-id="04590-116">Example: if you specify 2000 kbps, then Lync Server can send 2000 kbps for the main video stream and 2000 kbps for the panoramic video stream.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="04590-117">Lync 2013 エンドポイントの最大ビデオネットワーク帯域幅は、メインビデオでは 8000 kbps、パノラマビデオでは 2500 kbps です。</span><span class="sxs-lookup"><span data-stu-id="04590-117">The maximum video network bandwidth for a Lync 2013 endpoint is 8000 kbps for the main video and 2500 kbps for panoramic video.</span></span> <span data-ttu-id="04590-118">これらの最大値は、複数のビデオを受信または送信した場合にのみ達成されます。</span><span class="sxs-lookup"><span data-stu-id="04590-118">These maximum values are reached only if multiple videos are received or sent.</span></span> <span data-ttu-id="04590-119">詳細については、「 <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Lync Server 2013 のメディアトラフィックのネットワーク帯域幅の要件</A>」の「メディアトラフィックのネットワーク使用量」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="04590-119">For details, see the "Media Traffic Network Usage" section in <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Network bandwidth requirements for media traffic in Lync Server 2013</A>.</span></span> <span data-ttu-id="04590-120">このセクションでは、サポートされているすべての解像度について、最大と標準的なビデオストリームの帯域幅を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="04590-120">This section lists the maximum and typical video stream bandwidth for all supported resolutions.</span></span>

    
    </div>

  - <span data-ttu-id="04590-121">**この設定**は、Lync Server 2013 の新しい設定であり、クライアントが受信するすべてのビデオストリームに対して許可される最大ビットレート (1 秒あたりのビット数) を指定します。   </span><span class="sxs-lookup"><span data-stu-id="04590-121">**TotalReceiveVideoBitRateKb**   This setting, which is new in Lync Server 2013, specifies the maximum allowed bitrate (in kilobits per second) for all the video streams received by a client.</span></span> <span data-ttu-id="04590-122">つまり、クライアントが受け取ることができる、パノラマビデオストリームを除くすべてのビデオストリームの合計が指定されます。</span><span class="sxs-lookup"><span data-stu-id="04590-122">That is, it specifies the combined total for all the video streams, except for panoramic video streams, that a client can receive.</span></span> <span data-ttu-id="04590-123">たとえば、1500 kbps を指定した場合、クライアントは最大 1500 kbps のビデオを受信できます。これは、複数のビデオストリームまたは1つのビデオストリームで構成されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="04590-123">For example, if you specify 1500 kbps, then a client can receive up to 1500 kbps of video, which may consist of multiple video streams or a single video stream.</span></span> <span data-ttu-id="04590-124">この設定は、Lync Server 2013 クライアントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="04590-124">This setting applies only to Lync Server 2013 clients.</span></span>
    
    <span data-ttu-id="04590-125">**TotalReceiveVideoBitRateKb**の既定値は 5万 kbps です。</span><span class="sxs-lookup"><span data-stu-id="04590-125">The default value for **TotalReceiveVideoBitRateKb** is 50000 kbps.</span></span> <span data-ttu-id="04590-126">ギャラリービューの**EnableMultiviewJoin**設定が True に設定されている場合、 **TotalReceiveVideoBitRateKb**は 420 kbps 未満に設定しないでください。</span><span class="sxs-lookup"><span data-stu-id="04590-126">If the **EnableMultiviewJoin** setting for Gallery View is set to True, **TotalReceiveVideoBitRateKb** must not be set below 420 kbps.</span></span> <span data-ttu-id="04590-127">ギャラリービューの**EnableMultiviewJoin**設定が False に設定されている場合、 **TotalReceiveVideoBitRateKb**は 100 kbps 未満に設定しないでください。</span><span class="sxs-lookup"><span data-stu-id="04590-127">If the **EnableMultiviewJoin** setting for Gallery View is set to False, **TotalReceiveVideoBitRateKb** must not be set below 100 kbps.</span></span> <span data-ttu-id="04590-128">**EnableMultiviewJoin**が True に設定されていて、420 kbps 未満の値を設定した場合、値は既定のしきい値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="04590-128">If **EnableMultiviewJoin** is set to True and you set the value below 420 kbps, the values will default to the threshold value.</span></span> <span data-ttu-id="04590-129">このしきい値は、ユーザーエクスペリエンスが低下する可能性がある偶発的な誤りを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="04590-129">This threshold helps prevent accidental misconfiguration that might result in poor user experience.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="04590-130"><STRONG>EnableMultiviewJoin</STRONG>の設定の詳細については、「 <A href="lync-server-2013-configuring-gallery-view.md">Lync Server 2013 でギャラリービューを構成する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04590-130">For details about the <STRONG>EnableMultiviewJoin</STRONG> setting, see <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="04590-131">**MaxVideoConferencingResolution**   このパラメーターは、lync server 2013 会議の lync server 2013 クライアントでは使われなくなりました。</span><span class="sxs-lookup"><span data-stu-id="04590-131">**MaxVideoConferencingResolution**   This parameter is no longer used for Lync Server 2013 clients in Lync Server 2013 conferences.</span></span> <span data-ttu-id="04590-132">Lync Server 2013 会議では、このセクションで既に説明したビットレートコントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="04590-132">Lync Server 2013 conferences use the bit rate controls described earlier in this section.</span></span> <span data-ttu-id="04590-133">この設定は、Lync Server 2013 会議に参加している従来のクライアントでも使用されます。</span><span class="sxs-lookup"><span data-stu-id="04590-133">This setting is still used for legacy clients joining a Lync Server 2013 conference.</span></span> <span data-ttu-id="04590-134">このパラメーターは、Lync Server 2013 を使っているユーザーが開催する、会議内のレガシクライアントで許可される最大解像度を決定します。</span><span class="sxs-lookup"><span data-stu-id="04590-134">This parameter determines the maximum resolution allowed for legacy clients in conferences organized by users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="04590-135">つまり、従来のクライアントは、以前のバージョンの Lync Server または Office Communications Server と同じように扱われます。</span><span class="sxs-lookup"><span data-stu-id="04590-135">That is, legacy clients are treated the same as they were in previous versions of Lync Server or Office Communications Server.</span></span>

<span data-ttu-id="04590-136">ユーザーに適用される会議ポリシーの設定に加えて、メディア構成の設定を評価します。</span><span class="sxs-lookup"><span data-stu-id="04590-136">In addition to conferencing policy settings that apply to users, evaluate media configuration settings.</span></span> <span data-ttu-id="04590-137">これらの設定を表示または変更するには、次のいずれかのコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="04590-137">View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="04590-138">**Get-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="04590-138">**Get-CsMediaConfiguration**</span></span>

  - <span data-ttu-id="04590-139">**Set-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="04590-139">**Set- CsMediaConfiguration**</span></span>

  - <span data-ttu-id="04590-140">**新規-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="04590-140">**New- CsMediaConfiguration**</span></span>

<span data-ttu-id="04590-141">次の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="04590-141">Verify the following setting:</span></span>

  - <span data-ttu-id="04590-142">\*\*\*\*   [プールごとの MaxVideoRateAllowed] 設定では、クライアントエンドポイントでビデオ信号を転送する最大速度を指定します。</span><span class="sxs-lookup"><span data-stu-id="04590-142">**MaxVideoRateAllowed**   This per-pool setting specifies the maximum rate at which video signals will be transferred at the client endpoints.</span></span> <span data-ttu-id="04590-143">これは、以前のバージョンの Lync Server クライアントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="04590-143">It applies only to previous versions of Lync Server clients.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="04590-144">Lync Server 2013 クライアントでは、この設定は無視され、会議ポリシーの TotalReceiveVideoBitRateKb 設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="04590-144">Lync Server 2013 clients ignore this setting and use the TotalReceiveVideoBitRateKb setting in conferencing policy instead.</span></span>

    
    </div>
    
    <span data-ttu-id="04590-145">既定値はあることです。</span><span class="sxs-lookup"><span data-stu-id="04590-145">The default value is HD720P.</span></span> <span data-ttu-id="04590-146">有効な値は、HD720p15M、VGA600K、および CIF250K です。</span><span class="sxs-lookup"><span data-stu-id="04590-146">Valid values are HD720p15M, VGA600K, and CIF250K.</span></span>
    
    <span data-ttu-id="04590-147">例: 1500 kbps を指定した場合、プール内のすべてのレガシークライアントは、2パーティまたはマルチパーティの会議で最大 1500 kbps のビデオを受信できます。</span><span class="sxs-lookup"><span data-stu-id="04590-147">Example: If you specify 1500 kbps, then all the legacy clients in the pool can receive up to 1500 kbps of video in two-party or multiparty conferences.</span></span>

<span data-ttu-id="04590-148">次の手順では、このセクションで説明するように、Lync Server 管理シェルを使用して設定を変更する例を示します。</span><span class="sxs-lookup"><span data-stu-id="04590-148">The following procedures are examples of using Lync Server Management Shell to modify the settings described in this section.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a><span data-ttu-id="04590-149">ビデオ設定の会議ポリシーを変更するには</span><span class="sxs-lookup"><span data-stu-id="04590-149">To modify conferencing policy for video settings</span></span>

1.  <span data-ttu-id="04590-150">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="04590-150">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="04590-151">コマンドラインで、次のコマンドレットを実行して会議ポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="04590-151">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a><span data-ttu-id="04590-152">レガシクライアントのメディア構成を変更するには</span><span class="sxs-lookup"><span data-stu-id="04590-152">To modify media configuration for legacy clients</span></span>

1.  <span data-ttu-id="04590-153">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="04590-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="04590-154">コマンドラインで次のコマンドレットを実行して、メディアの構成を編集します。</span><span class="sxs-lookup"><span data-stu-id="04590-154">At the command line, run the following cmdlet to edit the media configuration:</span></span>
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

