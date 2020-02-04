---
title: コール パーク アプリケーション設定の移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ba55ec7ff54858d3324df2ab8794176a5dc7a10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="09f04-102">コール パーク アプリケーション設定の移行</span><span class="sxs-lookup"><span data-stu-id="09f04-102">Migrate Call Park application settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09f04-103">_**最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="09f04-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="09f04-104">Lync Server 2010 から Lync Server 2013 へのコールパークアプリケーションの移行には、lync server 2013 プールのプロビジョニングが含まれています。このファイルには、Lync Server 2010 でアップロードされたすべてのカスタム音楽が含まれています。また、サービスレベルの設定と retargeting を復元します。すべてのコールパークが Lync Server 2013 プールに orbits ます。</span><span class="sxs-lookup"><span data-stu-id="09f04-104">The migration of the Call Park application from Lync Server 2010 to Lync Server 2013 includes provisioning the Lync Server 2013 pool with any custom music on hold files that have been uploaded in Lync Server 2010, restoring the service level settings and retargeting all Call Park orbits to the Lync Server 2013 pool.</span></span> <span data-ttu-id="09f04-105">カスタマイズした音楽の保留中のファイルが Lync Server 2010 プールで構成されている場合は、これらのファイルを新しい Lync Server 2013 プールにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="09f04-105">If customized music-on-hold files have been configured in the Lync Server 2010 pool, these files need to be copied to the new Lync Server 2013 pool.</span></span> <span data-ttu-id="09f04-106">さらに、通話パークしたカスタマイズされた音楽の保留中のファイルを Lync Server 2010 から別の場所にバックアップすることをお勧めします。これは、コールパーク用にアップロードされたカスタマイズした音楽の保存ファイルの個別のバックアップコピーを保持するためです。</span><span class="sxs-lookup"><span data-stu-id="09f04-106">Additionally, it is recommended that you back up any Call Park customized music-on-hold files from Lync Server 2010 to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="09f04-107">コールパークアプリケーション用にカスタマイズされた音楽保留のファイルは、プールのファイルストアに保存されます。</span><span class="sxs-lookup"><span data-stu-id="09f04-107">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="09f04-108">Lync Server 2010 プールファイルストアから Lync Server 2013 ファイルストアにオーディオファイルをコピーするには、次のパラメーターを使用して**Xcopy**コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="09f04-108">To copy the audio files from a Lync Server 2010 pool file store to a Lync Server 2013 file store, use the **Xcopy** command with the following parameters:</span></span>

   ```
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

<span data-ttu-id="09f04-109">カスタマイズしたオーディオファイルがすべて Lync Server 2013 ファイルストアにコピーされている場合は、lync Server 2013 プールのコールパークアプリケーション設定を構成する必要があります。また、Lync Server 2010 プールに関連付けられているコールパーク範囲は、再割り当てする必要があります。Lync Server 2013 プール。</span><span class="sxs-lookup"><span data-stu-id="09f04-109">When all customized audio files have been copied to the Lync Server 2013 file store, the Call Park application settings of the Lync Server 2013 pool must be configured, and the Call Park orbit ranges that are associated with the Lync Server 2010 pool must be reassigned to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="09f04-110">コールパークアプリケーションの設定には、ピックアップタイムアウトしきい値、保留中の音楽を有効または無効にする、最大通話ピックアップ試行回数、タイムアウト要求が含まれます。</span><span class="sxs-lookup"><span data-stu-id="09f04-110">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts and the timeout request.</span></span> <span data-ttu-id="09f04-111">**CsCpsConfiguration**コマンドレットを実行するには、Lync Server 管理シェルを使用して、コールパークアプリケーションの設定を管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09f04-111">You must manage Call Park application settings by using the Lync Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="09f04-112">Lync Server コントロールパネルを使用して、[コールパーク] のアプリケーション設定を管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="09f04-112">You cannot manage the Call Park application settings using the Lync Server Control Panel.</span></span>

<span data-ttu-id="09f04-113">**コールパークサービス設定を再構成する**</span><span class="sxs-lookup"><span data-stu-id="09f04-113">**Reconfigure the Call Park Service Settings**</span></span>

1.  <span data-ttu-id="09f04-114">Lync Server 2013 フロントエンドサーバーから、Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="09f04-114">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="09f04-115">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="09f04-115">At the command line, type the following:</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="09f04-116">Lync Server 2013 Call パークのアプリケーション設定が従来の Lync Server の2010設定と同じである場合は、この手順の実行をスキップできます。</span><span class="sxs-lookup"><span data-stu-id="09f04-116">If your Lync Server 2013 Call Park application settings are identical to the legacy Lync Server 2010 settings, you can skip running this step.</span></span> <span data-ttu-id="09f04-117">会議の設定が Lync Server 2013 および Lync Server 2010 環境で異なる場合は、次のコマンドレットをテンプレートとして使用して、それらの変更を更新します。</span><span class="sxs-lookup"><span data-stu-id="09f04-117">If Call Park application settings are different for the Lync Server 2013 and Lync Server 2010 environments, use the cmdlet below as a template to update those changes.</span></span>

    
    </div>
    
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"

<span data-ttu-id="09f04-118">すべてのコールパークの範囲を Lync server 2010 プールから Lync Server 2013 プールに再割り当てするには、Lync Server コントロールパネルまたは Lync server 管理シェルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="09f04-118">To reassign all Call Park orbit ranges from Lync Server 2010 pool to the Lync Server 2013 pool, you can use either the Lync Server Control Panel or the Lync Server Management Shell.</span></span>

<span data-ttu-id="09f04-119">**Lync Server コントロールパネルを使用してすべてのコールパークの範囲を再割り当てする**</span><span class="sxs-lookup"><span data-stu-id="09f04-119">**Reassign all Call Park Orbit Ranges using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="09f04-120">[Lync Server コントロール パネル] を開きます。</span><span class="sxs-lookup"><span data-stu-id="09f04-120">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="09f04-121">左側のウィンドウで、[**音声機能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="09f04-121">In the left pane, select **Voice Features**.</span></span>

3.  <span data-ttu-id="09f04-122">[ **Call パーク**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="09f04-122">Select the **Call Park** tab.</span></span>

4.  <span data-ttu-id="09f04-123">Lync Server 2010 プールに割り当てられている各通話パークの範囲は、[**宛先サーバーの FQDN** ] の設定を編集し、コールパーク要求を処理する lync server 2013 プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="09f04-123">For each Call Park orbit range assigned to a Lync Server 2010 pool, edit the **FQDN of destination server** setting and select the Lync Server 2013 pool that will process the Call Park requests.</span></span>

5.  <span data-ttu-id="09f04-124">[**コミット**] を選んで変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="09f04-124">Select **Commit** to save the changes.</span></span>

<span data-ttu-id="09f04-125">**Lync Server 管理シェルを使用してすべてのコールパーク範囲を再割り当てする**</span><span class="sxs-lookup"><span data-stu-id="09f04-125">**Reassign all Call Park Orbit Ranges using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="09f04-126">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="09f04-126">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="09f04-127">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="09f04-127">At the command line, type the following:</span></span>
    
        Get-CsCallParkOrbit
    
    <span data-ttu-id="09f04-128">このコマンドレットは、展開内のすべてのコールパーク範囲の範囲を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="09f04-128">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="09f04-129">Lync Server 2010 プールとして**CallParkServiceId**と**Callparkserverfqdn**パラメーターが設定されているすべての Call パーク orbits は、再割り当てする必要があります。</span><span class="sxs-lookup"><span data-stu-id="09f04-129">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the Lync Server 2010 pool must be reassigned.</span></span>
    
    <span data-ttu-id="09f04-130">Lync Server 2010 Call パークの範囲を Lync Server 2013 プールに再割り当てするには、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="09f04-130">To reassign the Lync Server 2010 Call Park orbit ranges to the Lync Server 2013 pool, at the command line, type the following:</span></span>
    
        Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"

<span data-ttu-id="09f04-131">すべてのコールパークの範囲を Lync Server 2013 プールに再割り当てすると、コールパークアプリケーションの移行プロセスが完了し、Lync Server 2013 プールは、今後のすべてのコールパーク要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="09f04-131">After reassigning all Call Park orbit ranges to the Lync Server 2013 pool, the migration process for the Call Park application will be completed and the Lync Server 2013 pool will handle all future Call Park requests.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

