---
title: 'Lync Server 2013: ABC プールフェールオーバーのバックアップ前提条件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9b609a9867b9ca0e6a01f0ced38445ae55c7367
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a><span data-ttu-id="e9ad2-102">Lync Server 2013 での ABC プールフェールオーバーのバックアップ前提条件</span><span class="sxs-lookup"><span data-stu-id="e9ad2-102">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9ad2-103">_**トピックの最終更新日:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="e9ad2-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="e9ad2-104">ABC プールのフェールオーバー手順を使用することで最大のメリットを得るには、障害とフェールオーバーが発生する前に、特定のバックアップを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9ad2-104">To get the maximum benefit from using the ABC pool failover procedure, you must perform certain backups before the disaster and failover happen:</span></span>

  - <span data-ttu-id="e9ad2-105">**Export-cslisconfiguration**コマンドレットを使用して、プール A から場所情報サービス (LIS) 構成データを定期的にバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9ad2-105">You must regularly back up the Location Information Service (LIS) configuration data from pool A by using the **Export-CsLISConfiguration** cmdlet.</span></span>
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - <span data-ttu-id="e9ad2-106">**Export-CsRgsConfiguration**コマンドレットを使用して、プール A の応答グループ構成データを定期的にバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9ad2-106">You must regularly back up the Response Group configuration data in pool A by using the **Export-CsRgsConfiguration** cmdlet.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <span data-ttu-id="e9ad2-107">一般に、毎日バックアップを行うことをお勧めしますが、変更が多い場合は、より頻度の高いバックアップのスケジュールが必要になることもあります。</span><span class="sxs-lookup"><span data-stu-id="e9ad2-107">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="e9ad2-108">障害が発生した場合に失われる可能性のある情報は、バックアップの頻度、および変更の頻度と量によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e9ad2-108">The amount of information that you can lose in the event of a disaster depends on the frequency of your backups, as well as on the frequency and volume of changes.</span></span>
    
    <span data-ttu-id="e9ad2-109">応答グループアプリケーションに保存できるアプリケーションレベルの設定は、プールごとに1つだけです。</span><span class="sxs-lookup"><span data-stu-id="e9ad2-109">The Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="e9ad2-110">これらの設定には、 **Get-CsRgsConfiguration**コマンドレットを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e9ad2-110">These settings can be accessed through the **Get-CsRgsConfiguration** cmdlets.</span></span> <span data-ttu-id="e9ad2-111">設定には、既定の保留音の設定、既定の保留音のオーディオファイル、エージェントの呼び出し元の猶予期間、呼び出しコンテキストの構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e9ad2-111">The settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ring-back grace period, and the call context configuration.</span></span> <span data-ttu-id="e9ad2-112">これらの設定**は、** **replaceexistingsettings**パラメーターを使用して、別のプールから別のプールに移動できます。ただし、この操作は、移動先のプール内のアプリケーションレベルの設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="e9ad2-112">These settings can be transferred from one pool to another through the **Import-CsRgsConfiguration** cmdlet by using the **ReplaceExistingSettings** parameter, but this operation will override any application-level settings in the destination pool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e9ad2-113">別の場所に、応答グループアプリケーションの構成に使用したすべての元のオーディオファイル (つまり、レコーディングまたは音楽の保留中のファイル) のバックアップコピーを保存します。</span><span class="sxs-lookup"><span data-stu-id="e9ad2-113">In a separate location, keep a backup copy of all the original audio files that have been used to configure the Response Group application (that is, any recordings or music-on-hold files).</span></span>

    
    </div>
    
    <span data-ttu-id="e9ad2-114">コールパーク用にアップロードされた保留中のカスタマイズされた保留中のファイルがプールにある場合は、それらのコピーを別の場所に保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9ad2-114">If you have any customized music-on-hold files that have been uploaded for Call Park in a pool, you should keep a copy of these in another location.</span></span> <span data-ttu-id="e9ad2-115">これらのファイルは、Lync Server 2013 の障害復旧プロセスの一環としてバックアップされません。プールにアップロードされたファイルが破損、破損、または消去されると、それらのファイルは失われます。</span><span class="sxs-lookup"><span data-stu-id="e9ad2-115">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9ad2-116">コールパークアプリケーションは、1つのプールに対して1セットの設定と1つのカスタマイズされた音楽保留オーディオファイルのみを保存できます。</span><span class="sxs-lookup"><span data-stu-id="e9ad2-116">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="e9ad2-117">これらの設定には、 <STRONG>new-cscpsconfiguration</STRONG>コマンドレットを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e9ad2-117">These settings can be accessed through the <STRONG>Get-CsCpsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="e9ad2-118">コールパークの障害復旧メカニズムは、バックアッププールのコールパークアプリケーションに依存しているため、障害が発生した場合、プライマリプールの設定はバックアップまたは保持されません。</span><span class="sxs-lookup"><span data-stu-id="e9ad2-118">Because the disaster recovery mechanism for Call Park relies on the Call Park application of the backup pool, the settings of the primary pool are not backed up or preserved if a disaster occurs.</span></span> <span data-ttu-id="e9ad2-119">プライマリプールが失われた場合、これらの設定を回復することはできません。また、プライマリプールを置き換えるために新しいプールを展開する場合は、コールパーク設定とカスタマイズされた音楽オンホールドオーディオファイルを再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9ad2-119">If the primary pool is lost, these settings cannot be recovered, and when a new pool is deployed to replace the primary pool, the Call Park settings and any customized music-on-hold audio file would need to be reconfigured.</span></span>

    
    </div>

  - <span data-ttu-id="e9ad2-120">割り当てられていない電話機能の一部としてアナウンスを構成する場合は、最初の構成時に使用した元のオーディオファイルのコピーを別の場所に保存することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e9ad2-120">If you configure any announcements as part of the Unassigned Number Voice Feature, we recommend that you keep in another location a copy of any original audio file used during the initial configuration.</span></span> <span data-ttu-id="e9ad2-121">この操作を行わなかった場合は、オーディオファイルのインポート先のサーバーまたはプールのファイルストアに構成されたオーディオファイルのコピーを取得できます。</span><span class="sxs-lookup"><span data-stu-id="e9ad2-121">If you did not do that, you can get a copy of the configured audio files in the file store of the server or pool to which the audio files were imported.</span></span> <span data-ttu-id="e9ad2-122">これらのファイルは、Lync Server 2013 の障害復旧プロセスの一環としてバックアップされません。プールにアップロードされたファイルが破損、破損、または消去されると、それらのファイルは失われます。</span><span class="sxs-lookup"><span data-stu-id="e9ad2-122">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="e9ad2-123">未使用の番号の音声機能を構成するために使用されているすべてのオーディオファイルを、サーバーまたはプールのファイルストアからコピーするには、次の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="e9ad2-123">To copy all the audio files used to configure the Unassigned Number Voice Feature from the file store of a server or a pool, use:</span></span>
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - <span data-ttu-id="e9ad2-124">プール内にデータベースの監視とアーカイブを行っている場合は、SQL Server 管理ツールを使用してバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9ad2-124">If you have Monitoring and Archiving databases in a pool, you should use SQL Server management tools to back them up.</span></span> <span data-ttu-id="e9ad2-125">このようなデータベースは Lync Server バックアップサービスを使用してバックアップされないため、ABC フェールオーバーの手順では、データベースがプール A に併置されている場合、監視およびアーカイブデータベースは保持されません。</span><span class="sxs-lookup"><span data-stu-id="e9ad2-125">In the ABC failover procedure, Monitoring and Archiving databases are not preserved if they are collocated in pool A, because these databases are not backed up through Lync Server Backup Service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

