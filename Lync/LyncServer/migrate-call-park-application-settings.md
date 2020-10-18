---
title: コール パーク アプリケーション設定の移行
description: コールパークアプリケーションの設定を移行します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da90ca4ee4dd53451c29b8c39861dc76a17ca3c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579413"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="2669a-103">コール パーク アプリケーション設定の移行</span><span class="sxs-lookup"><span data-stu-id="2669a-103">Migrate Call Park application settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2669a-104">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="2669a-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="2669a-105">Lync server 2010 から Lync Server 2013 へのコールパークアプリケーションの移行には、lync server 2010 にアップロードされたカスタム音楽保留ファイルを含む Lync Server 2013 プールのプロビジョニング、サービスレベル設定の復元、および Lync Server 2013 プールへのコールパークオービットの retargeting が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2669a-105">The migration of the Call Park application from Lync Server 2010 to Lync Server 2013 includes provisioning the Lync Server 2013 pool with any custom music on hold files that have been uploaded in Lync Server 2010, restoring the service level settings and retargeting all Call Park orbits to the Lync Server 2013 pool.</span></span> <span data-ttu-id="2669a-106">カスタマイズした保留中のファイルが Lync Server 2010 プールに構成されている場合は、これらのファイルを新しい Lync Server 2013 プールにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2669a-106">If customized music-on-hold files have been configured in the Lync Server 2010 pool, these files need to be copied to the new Lync Server 2013 pool.</span></span> <span data-ttu-id="2669a-107">また、コールパーク用にアップロードされたカスタマイズされた保留音ファイルのバックアップコピーを別に保持するために、コールパークのカスタマイズされた保留音のファイルを Lync Server 2010 から別の送信先にバックアップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2669a-107">Additionally, it is recommended that you back up any Call Park customized music-on-hold files from Lync Server 2010 to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="2669a-108">コール パーク アプリケーションのカスタマイズされた保留音ファイルは、プールのファイル ストアに格納されています。</span><span class="sxs-lookup"><span data-stu-id="2669a-108">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="2669a-109">Lync Server 2010 プールファイルストアから Lync Server 2013 ファイルストアにオーディオファイルをコピーするには、 **Xcopy** コマンドを次のパラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="2669a-109">To copy the audio files from a Lync Server 2010 pool file store to a Lync Server 2013 file store, use the **Xcopy** command with the following parameters:</span></span>

   ```console
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```console
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

<span data-ttu-id="2669a-110">カスタマイズしたすべてのオーディオファイルが Lync Server 2013 ファイルストアにコピーされたら、lync Server 2013 プールのコールパークアプリケーションの設定を構成し、lync server の2010プールに関連付けられているコールパークオービットの範囲を Lync Server の2013プールに再割り当てする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2669a-110">When all customized audio files have been copied to the Lync Server 2013 file store, the Call Park application settings of the Lync Server 2013 pool must be configured, and the Call Park orbit ranges that are associated with the Lync Server 2010 pool must be reassigned to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="2669a-111">コール パーク アプリケーションの設定には、ピックアップ タイムアウトのしきい値、保留音の有効化と無効化、通話ピックアップの最大回数、タイムアウト要求などがあります。</span><span class="sxs-lookup"><span data-stu-id="2669a-111">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts and the timeout request.</span></span> <span data-ttu-id="2669a-112">**New-cscpsconfiguration**コマンドレットを実行するには、Lync Server 管理シェルを使用してコールパークアプリケーションの設定を管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2669a-112">You must manage Call Park application settings by using the Lync Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="2669a-113">Lync Server コントロールパネルを使用してコールパークアプリケーションの設定を管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="2669a-113">You cannot manage the Call Park application settings using the Lync Server Control Panel.</span></span>

<span data-ttu-id="2669a-114">**Call Park Service の設定を再構成する**</span><span class="sxs-lookup"><span data-stu-id="2669a-114">**Reconfigure the Call Park Service Settings**</span></span>

1.  <span data-ttu-id="2669a-115">Lync Server 2013 フロントエンドサーバーから、Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2669a-115">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="2669a-116">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2669a-116">At the command line, type the following:</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2669a-117">Lync Server 2013 コールパークアプリケーション設定が従来の Lync Server 2010 設定と同一の場合は、この手順の実行をスキップできます。</span><span class="sxs-lookup"><span data-stu-id="2669a-117">If your Lync Server 2013 Call Park application settings are identical to the legacy Lync Server 2010 settings, you can skip running this step.</span></span> <span data-ttu-id="2669a-118">通話パークアプリケーションの設定が Lync Server 2013 および Lync Server 2010 環境と異なる場合は、次のコマンドレットをテンプレートとして使用して、それらの変更を更新します。</span><span class="sxs-lookup"><span data-stu-id="2669a-118">If Call Park application settings are different for the Lync Server 2013 and Lync Server 2010 environments, use the cmdlet below as a template to update those changes.</span></span>

    
    <span data-ttu-id="2669a-119"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>"-CallPickupTimeoutThreshold" "- <LS2010 CPS TimeSpan> enablemusiconhold" "- <LS2010 CPS value> maxcallpickupattempts" <LS2010 CPS pickup attempts> "-ontimeouturi" <LS2010 CPS timeout URI> " ```</span><span class="sxs-lookup"><span data-stu-id="2669a-119"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>" ```</span></span>

<span data-ttu-id="2669a-120">すべてのコールパークオービット範囲を Lync server 2010 プールから Lync Server 2013 プールに再割り当てするには、Lync Server コントロールパネルまたは Lync Server 管理シェルのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2669a-120">To reassign all Call Park orbit ranges from Lync Server 2010 pool to the Lync Server 2013 pool, you can use either the Lync Server Control Panel or the Lync Server Management Shell.</span></span>

<span data-ttu-id="2669a-121">**Lync Server コントロール パネルを使用してコール パーク オービットの範囲をすべて割り当て直す**</span><span class="sxs-lookup"><span data-stu-id="2669a-121">**Reassign all Call Park Orbit Ranges using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="2669a-122">[Lync Server コントロール パネル] を開きます。</span><span class="sxs-lookup"><span data-stu-id="2669a-122">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="2669a-123">左側のウィンドウで、[**音声機能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2669a-123">In the left pane, select **Voice Features**.</span></span>

3.  <span data-ttu-id="2669a-124">[**コール パーク**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="2669a-124">Select the **Call Park** tab.</span></span>

4.  <span data-ttu-id="2669a-125">Lync Server 2010 プールに割り当てられている各コールパークオービット範囲に対して、[ **宛先サーバーの FQDN** ] 設定を編集し、コールパーク要求を処理する lync Server 2013 プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="2669a-125">For each Call Park orbit range assigned to a Lync Server 2010 pool, edit the **FQDN of destination server** setting and select the Lync Server 2013 pool that will process the Call Park requests.</span></span>

5.  <span data-ttu-id="2669a-126">[**コミット**] を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="2669a-126">Select **Commit** to save the changes.</span></span>

<span data-ttu-id="2669a-127">**Lync Server 管理シェルを使用してコール パーク オービットの範囲をすべて割り当て直す**</span><span class="sxs-lookup"><span data-stu-id="2669a-127">**Reassign all Call Park Orbit Ranges using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="2669a-128">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2669a-128">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="2669a-129">コマンド ラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2669a-129">At the command line, type the following:</span></span>
    ```powershell
    Get-CsCallParkOrbit
    ```
    
    <span data-ttu-id="2669a-130">このコマンドレットを実行すると、展開内のコール パーク オービットの範囲がすべて表示されます。</span><span class="sxs-lookup"><span data-stu-id="2669a-130">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="2669a-131">**CallParkServiceId**および**Callparkserverfqdn**パラメーターが Lync Server 2010 プールとして設定されているすべてのコールパークオービットを再割り当てする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2669a-131">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the Lync Server 2010 pool must be reassigned.</span></span>
    
    <span data-ttu-id="2669a-132">Lync Server 2010 のコールパークオービット範囲を Lync Server 2013 プールに再割り当てするには、コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2669a-132">To reassign the Lync Server 2010 Call Park orbit ranges to the Lync Server 2013 pool, at the command line, type the following:</span></span>
    
    ```powershell
    Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"
    ```

<span data-ttu-id="2669a-133">すべてのコールパークオービット範囲を Lync Server 2013 プールに再割り当てした後、コールパークアプリケーションの移行プロセスが完了し、Lync Server 2013 プールが、今後のコールパーク要求をすべて処理するようになります。</span><span class="sxs-lookup"><span data-stu-id="2669a-133">After reassigning all Call Park orbit ranges to the Lync Server 2013 pool, the migration process for the Call Park application will be completed and the Lync Server 2013 pool will handle all future Call Park requests.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

