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
ms.openlocfilehash: ed1dfd2e8879776733e6ca6fbd8d6024533ef622
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a><span data-ttu-id="f5c75-102">Lync Server 2013 でのビデオ帯域幅の構成</span><span class="sxs-lookup"><span data-stu-id="f5c75-102">Configuring video bandwidth in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5c75-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f5c75-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f5c75-104">Lync Server 2013 には、2者間通話とマルチパーティ会議のビデオを管理するための設定がいくつか含まれています。</span><span class="sxs-lookup"><span data-stu-id="f5c75-104">Lync Server 2013 includes several settings for managing video for two-party calls and multiparty conferences.</span></span> <span data-ttu-id="f5c75-105">Lync Server 2013 を展開する場合は、既定の設定が組織に適しているかどうかを評価し、必要に応じて変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c75-105">When you deploy Lync Server 2013, you should evaluate whether the default settings are appropriate for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="f5c75-p102">このセクションで説明するパラメーターは、2 者間通話とマルチパーティ会議の両方に適用されます。これらの設定を表示または変更するときは、次のコマンドレットの 1 つを使用します。</span><span class="sxs-lookup"><span data-stu-id="f5c75-p102">The parameters described in this section apply to both two-party calls and multiparty conferencing. View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="f5c75-108">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="f5c75-108">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="f5c75-109">**Get-csconferencingpolicy**</span><span class="sxs-lookup"><span data-stu-id="f5c75-109">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="f5c75-110">**Get-csconferencingpolicy**</span><span class="sxs-lookup"><span data-stu-id="f5c75-110">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="f5c75-111">会議ポリシーの次の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="f5c75-111">Verify the following settings in your conferencing policy:</span></span>

  - <span data-ttu-id="f5c75-112">**VideoBitRateKb**   この設定は、ユーザーによって送信されるビデオに対して使用されるビデオの最大ビットレート (キロビット/秒 (kbps)) を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5c75-112">**VideoBitRateKb**   This setting specifies the maximum video bit rate in kilobits per second (kbps) used for video sent by a user.</span></span> <span data-ttu-id="f5c75-113">既定値は 50000 kbps です。</span><span class="sxs-lookup"><span data-stu-id="f5c75-113">The default value is 50000 kbps.</span></span> <span data-ttu-id="f5c75-114">有効な値は 0 から 50000 です。</span><span class="sxs-lookup"><span data-stu-id="f5c75-114">Valid values are 0 to 50000.</span></span>
    
    <span data-ttu-id="f5c75-115">この設定は、メイン ビデオと	パノラマ ビデオに別々に適用されます。</span><span class="sxs-lookup"><span data-stu-id="f5c75-115">This setting applies separately to main video and panoramic video.</span></span>
    
    <span data-ttu-id="f5c75-116">例: 2000 kbps を指定すると、Lync Server は、メインビデオストリームに 2000 kbps を送信し、パノラマビデオストリームについては 2000 kbps を送信できます。</span><span class="sxs-lookup"><span data-stu-id="f5c75-116">Example: if you specify 2000 kbps, then Lync Server can send 2000 kbps for the main video stream and 2000 kbps for the panoramic video stream.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f5c75-117">Lync 2013 エンドポイントの最大ビデオネットワーク帯域幅は、メインビデオの場合は 8000 kbps、パノラマビデオの場合は 2500 kbps です。</span><span class="sxs-lookup"><span data-stu-id="f5c75-117">The maximum video network bandwidth for a Lync 2013 endpoint is 8000 kbps for the main video and 2500 kbps for panoramic video.</span></span> <span data-ttu-id="f5c75-118">こらの最大値に達するのは、複数のビデオが送受信される場合に限ります。</span><span class="sxs-lookup"><span data-stu-id="f5c75-118">These maximum values are reached only if multiple videos are received or sent.</span></span> <span data-ttu-id="f5c75-119">詳細については、「 <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Lync Server 2013 のメディアトラフィックのネットワーク帯域幅要件</A>」の「メディアトラフィックネットワークの使用率」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5c75-119">For details, see the "Media Traffic Network Usage" section in <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Network bandwidth requirements for media traffic in Lync Server 2013</A>.</span></span> <span data-ttu-id="f5c75-120">このセクションでは、サポートされているすべての解像度に関して、最大かつ一般的なビデオ ストリーム帯域幅を示します。</span><span class="sxs-lookup"><span data-stu-id="f5c75-120">This section lists the maximum and typical video stream bandwidth for all supported resolutions.</span></span>

    
    </div>

  - <span data-ttu-id="f5c75-121">**TotalReceiveVideoBitRateKb**   この設定は、Lync Server 2013 で新しく追加されたもので、クライアントが受信するすべてのビデオストリームに対して許可される最大のビットレート (1 秒あたりのビット数) を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5c75-121">**TotalReceiveVideoBitRateKb**   This setting, which is new in Lync Server 2013, specifies the maximum allowed bitrate (in kilobits per second) for all the video streams received by a client.</span></span> <span data-ttu-id="f5c75-122">つまり、クライアントが受信できる全ビデオ ストリーム (パノラマ ビデオ ストリームは除く) の合計値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5c75-122">That is, it specifies the combined total for all the video streams, except for panoramic video streams, that a client can receive.</span></span> <span data-ttu-id="f5c75-123">たとえば 1500 kbps を指定すると、クライアントは複数のビデオ ストリームまたは単一のビデオ ストリームから構成される最大 1500 kbps のビデオを受信できます。</span><span class="sxs-lookup"><span data-stu-id="f5c75-123">For example, if you specify 1500 kbps, then a client can receive up to 1500 kbps of video, which may consist of multiple video streams or a single video stream.</span></span> <span data-ttu-id="f5c75-124">この設定は、Lync Server 2013 クライアントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="f5c75-124">This setting applies only to Lync Server 2013 clients.</span></span>
    
    <span data-ttu-id="f5c75-p106">**TotalReceiveVideoBitRateKb** の既定値は 50000 kbps です。ギャラリー ビューの **EnableMultiviewJoin** 設定が True に設定されている場合、**TotalReceiveVideoBitRateKb** を 420 kbps 未満に設定しないようにします。ギャラリー ビューの **EnableMultiviewJoin** 設定が False に設定されている場合、**TotalReceiveVideoBitRateKb** を 100 kbps 未満に設定しないようにします。**EnableMultiviewJoin** が True に設定されており、値を 420 kbps 未満に設定した場合は、既定では、値はしきい値に設定されます。このしきい値によって、ユーザー エクスペリエンスの低下の原因となる予想外の構成ミスを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="f5c75-p106">The default value for **TotalReceiveVideoBitRateKb** is 50000 kbps. If the **EnableMultiviewJoin** setting for Gallery View is set to True, **TotalReceiveVideoBitRateKb** must not be set below 420 kbps. If the **EnableMultiviewJoin** setting for Gallery View is set to False, **TotalReceiveVideoBitRateKb** must not be set below 100 kbps. If **EnableMultiviewJoin** is set to True and you set the value below 420 kbps, the values will default to the threshold value. This threshold helps prevent accidental misconfiguration that might result in poor user experience.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f5c75-130"><STRONG>EnableMultiviewJoin</STRONG>の設定の詳細については、「 <A href="lync-server-2013-configuring-gallery-view.md">Lync Server 2013 でのギャラリービューの構成</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5c75-130">For details about the <STRONG>EnableMultiviewJoin</STRONG> setting, see <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="f5c75-131">**MaxVideoConferencingResolution**   このパラメーターは、lync server 2013 会議の lync server 2013 クライアントでは使用されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f5c75-131">**MaxVideoConferencingResolution**   This parameter is no longer used for Lync Server 2013 clients in Lync Server 2013 conferences.</span></span> <span data-ttu-id="f5c75-132">Lync Server 2013 会議では、このセクションで前述したビットレートコントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="f5c75-132">Lync Server 2013 conferences use the bit rate controls described earlier in this section.</span></span> <span data-ttu-id="f5c75-133">この設定は、Lync Server 2013 会議に参加しているレガシクライアントでも使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5c75-133">This setting is still used for legacy clients joining a Lync Server 2013 conference.</span></span> <span data-ttu-id="f5c75-134">このパラメーターは、Lync Server 2013 に所属するユーザーが開催する、電話会議のレガシクライアントに許可される最大解像度を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5c75-134">This parameter determines the maximum resolution allowed for legacy clients in conferences organized by users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="f5c75-135">つまり、従来のクライアントは、以前のバージョンの Lync Server または Office Communications Server と同じように処理されます。</span><span class="sxs-lookup"><span data-stu-id="f5c75-135">That is, legacy clients are treated the same as they were in previous versions of Lync Server or Office Communications Server.</span></span>

<span data-ttu-id="f5c75-p108">ユーザーに適用される会議ポリシー設定のほかに、メディア構成設定を評価します。これらの設定を表示または変更するときは、次のコマンドレットの 1 つを使用します。</span><span class="sxs-lookup"><span data-stu-id="f5c75-p108">In addition to conferencing policy settings that apply to users, evaluate media configuration settings. View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="f5c75-138">**Get-csmediaconfiguration**</span><span class="sxs-lookup"><span data-stu-id="f5c75-138">**Get-CsMediaConfiguration**</span></span>

  - <span data-ttu-id="f5c75-139">**Get-csmediaconfiguration**</span><span class="sxs-lookup"><span data-stu-id="f5c75-139">**Set- CsMediaConfiguration**</span></span>

  - <span data-ttu-id="f5c75-140">**Get-csmediaconfiguration**</span><span class="sxs-lookup"><span data-stu-id="f5c75-140">**New- CsMediaConfiguration**</span></span>

<span data-ttu-id="f5c75-141">次の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="f5c75-141">Verify the following setting:</span></span>

  - <span data-ttu-id="f5c75-142">**MaxVideoRateAllowed**   このプール設定では、クライアントエンドポイントでビデオ信号を転送する最大速度を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5c75-142">**MaxVideoRateAllowed**   This per-pool setting specifies the maximum rate at which video signals will be transferred at the client endpoints.</span></span> <span data-ttu-id="f5c75-143">これは、以前のバージョンの Lync Server クライアントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="f5c75-143">It applies only to previous versions of Lync Server clients.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f5c75-144">Lync Server 2013 クライアントはこの設定を無視し、代わりに会議ポリシーの TotalReceiveVideoBitRateKb 設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="f5c75-144">Lync Server 2013 clients ignore this setting and use the TotalReceiveVideoBitRateKb setting in conferencing policy instead.</span></span>

    
    </div>
    
    <span data-ttu-id="f5c75-p110">既定値は HD720P です。有効な値は、HD720p15M、VGA600K、および CIF250K です。</span><span class="sxs-lookup"><span data-stu-id="f5c75-p110">The default value is HD720P. Valid values are HD720p15M, VGA600K, and CIF250K.</span></span>
    
    <span data-ttu-id="f5c75-147">例: 1500 kbps を指定すると、プール内の従来のクライアントすべてが、2 者間会議またはマルチパーティ会議で 1500 kbps までのビデオを受信できます。</span><span class="sxs-lookup"><span data-stu-id="f5c75-147">Example: If you specify 1500 kbps, then all the legacy clients in the pool can receive up to 1500 kbps of video in two-party or multiparty conferences.</span></span>

<span data-ttu-id="f5c75-148">次の手順では、このセクションで説明する設定を Lync Server 管理シェルを使用して変更する例を示します。</span><span class="sxs-lookup"><span data-stu-id="f5c75-148">The following procedures are examples of using Lync Server Management Shell to modify the settings described in this section.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a><span data-ttu-id="f5c75-149">ビデオ設定の会議ポリシーを変更するには</span><span class="sxs-lookup"><span data-stu-id="f5c75-149">To modify conferencing policy for video settings</span></span>

1.  <span data-ttu-id="f5c75-150">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5c75-150">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f5c75-151">コマンド ラインで次のコマンドレットを実行して、会議ポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="f5c75-151">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a><span data-ttu-id="f5c75-152">従来のクライアント向けのメディア構成を変更するには</span><span class="sxs-lookup"><span data-stu-id="f5c75-152">To modify media configuration for legacy clients</span></span>

1.  <span data-ttu-id="f5c75-153">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5c75-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f5c75-154">コマンド ラインで次のコマンドレットを実行して、メディア構成を編集します。</span><span class="sxs-lookup"><span data-stu-id="f5c75-154">At the command line, run the following cmdlet to edit the media configuration:</span></span>
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

