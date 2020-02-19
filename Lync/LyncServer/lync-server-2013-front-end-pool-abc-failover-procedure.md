---
title: 'Lync Server 2013: フロントエンドプール ABC フェールオーバー手順'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool ABC failover procedure
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945635(v=OCS.15)
ms:contentKeyID: 51541486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38943d8e7d374fdd5b1fe202eaef44101bfeb321
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a><span data-ttu-id="fa7be-102">Lync Server 2013 のフロントエンドプール ABC フェールオーバーの手順</span><span class="sxs-lookup"><span data-stu-id="fa7be-102">Front End pool ABC failover procedure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa7be-103">_**トピックの最終更新日:** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="fa7be-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="fa7be-104">次の手順を使用して、ABC フェールオーバーの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-104">Use the following steps to perform the ABC failover procedure.</span></span> <span data-ttu-id="fa7be-105">この手順には、各手順の概要と、各ステップに対して実行されるコマンドとコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fa7be-105">This procedure contains a high-level description of each step, followed by commands and cmdlets to be run for each step.</span></span>

<span data-ttu-id="fa7be-106">コマンドレットを実行するには、[管理者として実行] を使用して Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="fa7be-106">To run the cmdlets, open a Lync Server Management Shell using Run as Administrator.</span></span>

<div>

## <a name="to-perform-an-abc-failover"></a><span data-ttu-id="fa7be-107">ABC フェールオーバーを実行するには</span><span class="sxs-lookup"><span data-stu-id="fa7be-107">To Perform an ABC Failover</span></span>

1.  <span data-ttu-id="fa7be-108">プール A が中央管理サーバー (CMS) のホストであるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-108">Check whether the pool A is the host for the Central Management Server (CMS).</span></span>
    
      - <span data-ttu-id="fa7be-109">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-109">Run the following cmdlet:</span></span>
        
            Get-CsService -CentralManagement
        
        <span data-ttu-id="fa7be-110">アクティブな CMS の Id フィールドがプール A の完全修飾ドメイン名 (FQDN) を指している場合は、最初に中央管理サーバーをフェールオーバーするには、この手順の手順2および3を使用します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-110">If the Identity field of the active CMS points to the fully qualified domain name (FQDN) of Pool A, then you use steps 2 and 3 of this procedure to fail over the Central Management Server first.</span></span> <span data-ttu-id="fa7be-111">それ以外の場合は、手順4に進みます。</span><span class="sxs-lookup"><span data-stu-id="fa7be-111">Otherwise, skip to step 4.</span></span>

2.  <span data-ttu-id="fa7be-112">次のコマンドレットを実行して、障害復旧モードで CMS をプール B にフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="fa7be-112">Fail over the CMS to Pool B in disaster recovery mode by running the following cmdlet:</span></span>
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    <span data-ttu-id="fa7be-113">この操作を行った後、回復性を高めるために、CMS をプール B から別の既存のプールに移動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fa7be-113">After you do this, we recommend that you move the CMS from pool B to another existing paired pool for extra resiliency.</span></span> <span data-ttu-id="fa7be-114">詳細については、「 [move-csmanagementserver](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa7be-114">For details, see [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..</span></span>

3.  <span data-ttu-id="fa7be-115">プール A に CMS が含まれている場合、LIS 構成をプール A からプール B の LIS データベース (Lis. .mdf) にインポートします。</span><span class="sxs-lookup"><span data-stu-id="fa7be-115">If Pool A contains CMS, import the LIS configuration from pool A into pool B’s LIS database (Lis.mdf).</span></span> <span data-ttu-id="fa7be-116">これは、LIS データを定期的にバックアップしている場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-116">This will work only if you have been backing up LIS data on a regular basis.</span></span> <span data-ttu-id="fa7be-117">LIS 構成をインポートするには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-117">To import the LIS configuration, run the following cmdlets:</span></span>
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  <span data-ttu-id="fa7be-118">バックアップされた Lync Server 応答グループサービスワークフローをプール A からプール B にインポートします。</span><span class="sxs-lookup"><span data-stu-id="fa7be-118">Import backed-up Lync Server Response Group service workflows from pool A into pool B.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fa7be-119">現時点では、 <STRONG>Import-CsRgsConfiguration</STRONG>コマンドレットでは、プール a のキューとワークフロー名が、プール B のキューおよびワークフロー名と異なることが必要です。名前が異なる場合は、 <STRONG>import</STRONG>コマンドレットを実行すると、エラーが発生します。また、キューとワークフローは、pool B で、 <STRONG>Import-csrgsconfiguration</STRONG>コマンドレットを続行する前に名前を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa7be-119">Currently, the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet requires that the queue and workflow names on pool A are distinct from the queue and workflow names on pool B. If the names are not distinct, you will get an error when running the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet, and the queues and workflows will need to be renamed in pool B before proceeding with <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet.</span></span>

    
    </div>
    
    <span data-ttu-id="fa7be-120">プール A からプール B に応答グループの構成をインポートするには、2つのオプションがあります。どちらのオプションを使用するかは、プール A のアプリケーションレベルの設定でプール B のアプリケーションレベルの設定を上書きするかどうかによって決まります。</span><span class="sxs-lookup"><span data-stu-id="fa7be-120">You have two options for importing the Response Group configuration from pool A to pool B. Which option you use depends on whether you want to overwrite the application-level settings of pool B with the application-level settings in pool A.</span></span>
    
      - <span data-ttu-id="fa7be-121">プール B の設定を上書きする場合は、 **Replaceexistingsettings**オプションを指定して**Import-CsRgsConfiguration**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-121">If you want to overwrite the Pool B settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="fa7be-122">プール B の設定を上書きしない場合は、 **Replaceexistingsettings**オプションを指定せずに、 **Import-CsRgsConfiguration**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-122">If you do not want to overwrite the Pool B settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="fa7be-123">バックアッププールのアプリケーションレベルの設定 (プール A) の設定を上書きしない場合、プール a のアプリケーションレベルの設定は、応答グループアプリケーションが失われた場合に失われます。これは、応答グループアプリケーションで、次のようにします。プールごとに1つのアプリケーションレベルの設定のみを格納します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-123">Keep in mind that if you do not want to overwrite the application-level settings of the backup pool (pool B) with the settings of the primary pool (pool A), pool A’s application-level settings will be lost if pool A is lost, because the Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="fa7be-124">プール C を置き換えるためにプール C が展開されている場合は、既定の保留音のオーディオファイルなど、アプリケーションレベルの設定を再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa7be-124">When pool C is deployed to replace pool A, the application-level settings must be reconfigured, including the default music-on-hold audio file.</span></span>

    
    </div>

5.  <span data-ttu-id="fa7be-125">インポートされた応答グループを表示するには、次のコマンドレットを実行して、応答グループ構成のインポートが正常に完了したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-125">Verify that the Response Group configuration import was successful by running the following cmdlets to display the imported response groups.</span></span> <span data-ttu-id="fa7be-126">インポートされた応答グループは、引き続きプール A によって所有されています。</span><span class="sxs-lookup"><span data-stu-id="fa7be-126">Note that the imported response groups are still owned by pool A.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  <span data-ttu-id="fa7be-127">割り当てられていない番号については、[アナウンス] を使用している割り当てられていない番号範囲を、プール A からプール B に選択したアナウンスサービスとして移動します。そのためには次のようにします。</span><span class="sxs-lookup"><span data-stu-id="fa7be-127">For Unassigned Numbers, move the Unassigned Number ranges that are using "Announcement" as the selected announcement service from pool A to pool B. To do so:</span></span>
    
      - <span data-ttu-id="fa7be-128">プール B のプール A に展開されたすべてのアナウンスを再作成します。プール A にアナウンスを展開するときにオーディオファイルが使用された場合、これらのファイルはプール B でアナウンスを再作成するために必要になります。プール B でアナウンスを再作成するには、**新しい-csannouncement**コマンドレットを使用して、pool b を親サービスとして使用します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-128">Re-create all announcements that were deployed in pool A on pool B. If any audio files were used when deploying the announcements in pool A, these files will be needed to re-create the announcements in pool B. To re-create the announcements in pool B, use the **New-CsAnnouncement** cmdlets, with pool B as the Parent service.</span></span>
    
      - <span data-ttu-id="fa7be-129">プール A のアナウンスを対象としているすべての未使用の番号範囲を、プール B に新たに展開されたアナウンスに再ターゲットします。プール A のアナウンスを対象とした割り当てなしの番号範囲ごとに次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-129">Retarget all the Unassigned Number ranges that are targeting an announcement in pool A to the newly deployed announcements in pool B. Run the following cmdlet for every Unassigned Number range targeting an announcement of pool A:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fa7be-130">この手順は、選択したアナウンスサービスとして "Exchange UM" を使用する割り当てられていない番号範囲には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="fa7be-130">This step is not required for unassigned number ranges that use "Exchange UM" as the selected announcement service.</span></span>

    
    </div>

7.  <span data-ttu-id="fa7be-131">次のコマンドレットを実行して、プール A を Disaster Recovery (DR) モードのプール B にフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="fa7be-131">Fail over Pool A to Pool B in Disaster Recovery (DR) mode, by running the following cmdlet:</span></span>
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  <span data-ttu-id="fa7be-132">プール c をビルドします。ただし、プール C ではサービスを開始しないでください。</span><span class="sxs-lookup"><span data-stu-id="fa7be-132">Build pool C, but do not start any services on pool C.</span></span>
    
    <span data-ttu-id="fa7be-133">この手順は、手順5および6と同時に実行できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fa7be-133">Note that this step can be carried out concurrently with steps 5 and 6.</span></span>

9.  <span data-ttu-id="fa7be-134">次のコマンドレットを実行して、プール A に所属するユーザーを強制的にプール C に移動します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-134">Force users homed on pool A to move to pool C by running the following cmdlet:</span></span>
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    <span data-ttu-id="fa7be-135">この時点で、プール A に所属するユーザーは、サービスの停止を開始することになります。</span><span class="sxs-lookup"><span data-stu-id="fa7be-135">At this point, users homed on pool A will begin to experience a service outage.</span></span> <span data-ttu-id="fa7be-136">この停止は、ステップ 16 (プール C でポイントサービスが開始されるまで) まで続きます。</span><span class="sxs-lookup"><span data-stu-id="fa7be-136">This outage will continue until step 16, at which point services are started on pool C.</span></span>

10. <span data-ttu-id="fa7be-137">次のコマンドレットを実行して、プール A の会議ディレクトリを強制的にプール C に移動します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-137">Force the conference directory of pool A to move to pool C by running the following cmdlet:</span></span>
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. <span data-ttu-id="fa7be-138">次のコマンドレットを実行して、会議自動応答 (CAA) 連絡先オブジェクトがプール A からプール C に移動するように強制します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-138">Force the Conference Auto Attendant (CAA) Contact Object to move from pool A to pool C by running the following cmdlet:</span></span>
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. <span data-ttu-id="fa7be-139">会議コンテンツをプール B からプール C にコピーします。</span><span class="sxs-lookup"><span data-stu-id="fa7be-139">Copy conference content from pool B to pool C.</span></span>

13. <span data-ttu-id="fa7be-140">次のコマンドレットを実行して、プール B からユーザーデータをエクスポートし、ユーザーデータをプール C にインポートします。</span><span class="sxs-lookup"><span data-stu-id="fa7be-140">Export user data from pool B and import the user data into pool C by running the following cmdlets:</span></span>
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. <span data-ttu-id="fa7be-141">バックアップされたコールパークアプリケーションデータをプール A からプール C に復元し、プール A からプール C へのコールパークオービットの範囲を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fa7be-141">Restore backed-up Call Park application data from pool A into pool C and assign the Call Park orbit ranges of pool A to pool C.</span></span>
    
      - <span data-ttu-id="fa7be-142">Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、コールパークオービット範囲のプール A からプール C への再割り当てを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fa7be-142">You can reassign a Call Park orbit range of pool A to pool C either through the Lync Server Control Panel or the Lync Server Management Shell.</span></span> <span data-ttu-id="fa7be-143">Lync Server 管理シェルについては、次のコマンドレットを実行して、プール A に割り当てられたすべてのコールパークオービット範囲を指定します (Identity パラメーターは、プール A に属しているコールパークオービット範囲を参照することに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="fa7be-143">For the Lync Server Management Shell, run the following cmdlet for every Call Park orbit range assigned to pool A (note that the Identity parameter refers to the Call Park Orbit Ranges that belong to pool A):</span></span>
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - <span data-ttu-id="fa7be-144">カスタマイズした保留音がプール A のコールパークに対して構成されている場合は、コールパークカスタマイズされた保留中の保留音ファイルをプール C に復元します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-144">If a customized music-on-hold has been configured for Call Park in pool A, restore the Call Park customized music-on-hold file in pool C.</span></span>
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        <span data-ttu-id="fa7be-145">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-145">For example:</span></span>
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - <span data-ttu-id="fa7be-146">最後に、 **new-cscpsconfiguration**コマンドレットを使用して、プール C のコールパーク設定を再構成します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-146">Finally, reconfigure the Call Park settings on pool C by using the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="fa7be-147">コールパークアプリケーションは、1つのプールに対して1セットの設定と1つのカスタマイズされた保留音のオーディオファイルのみを保存できます。また、障害が発生した場合には、これらの設定はバックアップも保持もされません。</span><span class="sxs-lookup"><span data-stu-id="fa7be-147">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool, and these settings are not backed up or preserved in the event of a disaster.</span></span>

15. <span data-ttu-id="fa7be-148">常設チャットの次ホッププールがプール A を指している場合は、次ホップサーバーがプール C をポイントするようにトポロジの変更を行い、公開します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-148">If the next hop pool for Persistent Chat is pointing to pool A, make and publish topology changes so that the next hop server points to pool C.</span></span>
    
      - <span data-ttu-id="fa7be-149">トポロジビルダーで、次ホップとして [プール C] をポイントするように常設チャットプールを変更します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-149">In Topology Builder, change the Persistent Chat pool to point to Pool C as its next hop.</span></span> <span data-ttu-id="fa7be-150">そのためには、常設チャットプールを右クリックし、[**全般**] タブをクリックして、[**次ホッププール**] にプール C の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-150">To do so, right-click on the Persistent Chat pool, then click the **General** tab, and then type the name of Pool C in **Next Hop Pool**.</span></span>
    
      - <span data-ttu-id="fa7be-151">次のコマンドレットを実行して、プール C のサービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-151">Start services on pool C by running the following cmdlet:</span></span>
        
            Start-csWindowsService
    
    <span data-ttu-id="fa7be-152">この時点で、最初にプール A に所属していたユーザーがサービスの停止を終了します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-152">At this point, the service outage ends for users originally homed on pool A.</span></span>

16. <span data-ttu-id="fa7be-153">次のコマンドレットを実行して、プール A からプール C にインポートするために所有されているプール B から Lync Server Response Group service ワークフローをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="fa7be-153">Export Lync Server Response Group service workflows from pool B owned by pool A for import into pool C by running the following cmdlet:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. <span data-ttu-id="fa7be-154">プール B からプール C に Lync Server Response Group service ワークフローをインポートします。</span><span class="sxs-lookup"><span data-stu-id="fa7be-154">Import Lync Server Response Group service workflows into pool C from pool B.</span></span>
    
    <span data-ttu-id="fa7be-155">応答グループの構成をプール B からプール C にインポートするには、2つのオプションがあります。どのオプションを使用するかは、プール C のアプリケーションレベルの設定をプール B のアプリケーションレベルの設定で上書きするかどうかによって決まります。</span><span class="sxs-lookup"><span data-stu-id="fa7be-155">You have two options are for importing the Response Group configuration from pool B to pool C. Which option you use depends on whether you want to overwrite the application-level settings of pool C with the application-level settings in pool B.</span></span>
    
      - <span data-ttu-id="fa7be-156">プール C の設定を上書きする場合は、 **Replaceexistingsettings**オプションを指定して**Import-CsRgsConfiguration**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-156">If you want to overwrite the Pool C settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="fa7be-157">プール C の設定を上書きしない場合は、 **Replaceexistingsettings**オプションを指定せずに、 **Import-CsRgsConfiguration**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-157">If you do not want to overwrite the Pool C settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="fa7be-158">プール C のアプリケーションレベルの設定をバックアッププール (プール B) の設定で上書きしない場合は、応答グループアプリケーションに格納できるアプリケーションレベルのセットが1つのみであるため、プール B のアプリケーションレベルの設定が失われることに注意してください。プールごとの設定。</span><span class="sxs-lookup"><span data-stu-id="fa7be-158">Keep in mind that if you do not want to overwrite the application-level settings of Pool C with the settings of the backup pool (pool B), pool B’s application-level settings will be lost because the Response Group application can store only one set of application-level settings per pool.</span></span>

    
    </div>

18. <span data-ttu-id="fa7be-159">次のコマンドレットを実行して、応答グループ構成のインポートが正常に完了したことを確認して、プール C にインポートされた応答グループを表示します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-159">Verify that the Response Group configuration import was successful by running the following cmdlets to display the response groups that have been imported to Pool C.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. <span data-ttu-id="fa7be-160">インポートした構成がプール C で確認されたら、プライマリプールが所有する応答グループをプール B から削除します。これにより、応答グループのダウンタイムを最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="fa7be-160">When the imported configuration has been verified in pool C, remove the response groups owned by the primary pool from pool B. This will minimize the downtime of the response groups.</span></span>
    
    <span data-ttu-id="fa7be-161">この手順では、エクスポートされた構成で新しいファイルを作成し、プール B からファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-161">This step creates a new file with the exported configuration, and then removes the file from pool B.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. <span data-ttu-id="fa7be-162">プール A からプール B に移動された割り当てられていない番号範囲に、プール C に移動します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-162">Move to pool C the Unassigned Number ranges that were moved from pool A to pool B.</span></span>
    
      - <span data-ttu-id="fa7be-163">プール B のプール A から再作成されたすべてのアナウンスをプール C で再作成します。移動するアナウンスを展開するときにオーディオファイルが使用されていた場合は、これらのファイルを使用して、プール C でアナウンスを再作成する必要があります。プール C でアナウンスを再作成するには、**新しい-csannouncement**コマンドレットを使用し、プール c を親サービスとして使用します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-163">Re-create in pool C all announcements that were re-created from pool A in pool B. If any audio files were used when deploying the announcements to be moved, you will need to use these files to re-create the announcements in pool C. To re-create the announcements in pool C, use the **New-CsAnnouncement** cmdlets, with pool C as the Parent service.</span></span>
    
      - <span data-ttu-id="fa7be-164">プール A からプール B に再ターゲットされたすべての未使用の番号範囲をプール C に再ターゲットします。再ターゲットする必要があるすべての未使用の番号範囲に対して次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-164">Retarget to pool C all the unassigned number ranges that were retargeted from pool A to pool B. Run the following cmdlet for every Unassigned Number range that needs to be retargeted:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - <span data-ttu-id="fa7be-165">オプションプール b で使用されなくなったアナウンスをプール B から削除します。プール B で使用されなくなったアナウンス。アナウンスを削除するには、[**削除]-csannouncement**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-165">(Optional) Remove from pool B the announcements that were re-created in pool C if they are no longer in use in pool B. To remove announcements, use the **Remove-CsAnnouncement** cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="fa7be-166">"Exchange UM" をアナウンスサービスとして使用する割り当てられていない番号範囲では、この手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="fa7be-166">This step is not required for unassigned number ranges that use "Exchange UM" as the announcement service.</span></span>

        
        </div>

21. <span data-ttu-id="fa7be-167">次のコマンドレットを実行して、プール B のプール A のユーザーデータをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="fa7be-167">Clean up user data of pool A in pool B by running the following cmdlet:</span></span>
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. <span data-ttu-id="fa7be-168">トポロジビルダーで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fa7be-168">Do the following in Topology Builder:</span></span>
    
      - <span data-ttu-id="fa7be-169">解除プール A およびプール B。ペアプール B およびプール C。その後、トポロジからプール A を削除して公開します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-169">Unpair pool A and pool B. Pair pool B and pool C. Then remove Pool A from the topology and publish it.</span></span> <span data-ttu-id="fa7be-170">これを行うには、以下のようにします:</span><span class="sxs-lookup"><span data-stu-id="fa7be-170">To do so:</span></span>
        
          - <span data-ttu-id="fa7be-171">トポロジビルダーで、[プール B] を右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa7be-171">In Topology Builder, right-click on Pool B, and then click **Edit Properties**.</span></span>
        
          - <span data-ttu-id="fa7be-172">左側のウィンドウで [**復元**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa7be-172">Click **Resiliency** in the left pane.</span></span>
        
          - <span data-ttu-id="fa7be-173">[**関連付けられたバックアッププール**] の下にある [pool C] を選択します。 [関連付けられているバックアッププール] 選択ボックスには、最初にプール a が表示されます。これは、プール B が以前このプールに関連付けられているためです</span><span class="sxs-lookup"><span data-stu-id="fa7be-173">In the box below **Associated Backup Pool**, select Pool C. Note that the Associated Backup Pool selection box will initially display pool A, because pool B was previously associated with this pool.</span></span>
        
          - <span data-ttu-id="fa7be-174">[**音声の自動フェールオーバーとフェールバック**] を選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa7be-174">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
            
            <span data-ttu-id="fa7be-175">このプールの詳細情報を表示すると、関連付けられているプールが右ウィンドウの [**復元**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="fa7be-175">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span>
        
          - <span data-ttu-id="fa7be-176">コンソールツリーで、[プール A] を右クリックし、[削除] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa7be-176">In the console tree, right-click pool A, and then click Delete.</span></span>
        
          - <span data-ttu-id="fa7be-177">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-177">Publish the topology.</span></span>

23. <span data-ttu-id="fa7be-178">プール c でブートストラップアプリケーションを実行して、backup service アプリケーションをインストールした後、pool C のローカルコンピューターの展開フォルダーから以下を実行して、バックアップサービスアプリケーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-178">Run the bootstrapping application on pool C to install the backup service application, and then start the backup service application by running the following from the deployment folder on a local machine in pool C:</span></span>
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. <span data-ttu-id="fa7be-179">次のコマンドレットを実行して、プール B でバックアップサービスアプリケーションを再起動します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-179">Restart the backup service application on pool B by running the following cmdlets:</span></span>
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. <span data-ttu-id="fa7be-180">プール C が Standard Edition (SE) プールで、プール B に CMS がある場合は、次のコマンドレットを実行して CMS データベースをプール C に手動でインストールします。</span><span class="sxs-lookup"><span data-stu-id="fa7be-180">If pool C is a Standard Edition (SE) Pool and pool B has CMS, install the CMS database manually on pool C by running the following cmdlet:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. <span data-ttu-id="fa7be-181">バックアップサービスを呼び出して、B と C をペアにする前に生成された古い会議コンテンツをプール B からプール C に同期し、プール c からプール c を起動してから、B と C がペアになった後に生成された新しい会議コンテンツをプール c からプール B に同期します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-181">Invoke the backup service to sync old conferencing content from pool B to pool C that was generated before pairing B and C together, and to sync new conferencing content from pool C to pool B that was generated after starting pool C and before B and C were paired together.</span></span> <span data-ttu-id="fa7be-182">これを行うには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-182">To do so, run the following cmdlets:</span></span>
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. <span data-ttu-id="fa7be-183">プール A に関連付けられている各存続可能 Branch アプライアンス X に対して、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="fa7be-183">For each Survivable Branch Appliance X associated with pool A:</span></span>
    
      - <span data-ttu-id="fa7be-184">次のコマンドレットを実行して、SBA X をシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="fa7be-184">Shut down SBA X by running the following cmdlet:</span></span>
        
            Stop-CsWindowsService
    
      - <span data-ttu-id="fa7be-185">SBA X に所属するユーザーの一覧を含むファイルを作成します。このリストは、ユーザーが手順30で SBA X に戻ったときに必要になります。</span><span class="sxs-lookup"><span data-stu-id="fa7be-185">Create a file that contains a list of users homed on SBA X. The list will be needed when the users are moved back to SBA X in step 30.</span></span> <span data-ttu-id="fa7be-186">これを行うには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-186">To do so, run the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - <span data-ttu-id="fa7be-187">次のコマンドレットを実行して、SBA X に所属するユーザーにプール C への移動を強制します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-187">Force users homed on SBA X to move to pool C by running the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - <span data-ttu-id="fa7be-188">最初に次のコマンドレットを実行して、これらのユーザーのデータを更新します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-188">Update the data of these users by first running the following cmdlets:</span></span>
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        <span data-ttu-id="fa7be-189">その後、次のスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-189">And then run this script:</span></span>
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="fa7be-190">プール A に関連付けられている SBAs に所属しているユーザーがプール C に移動するまで、サービスの停止が発生します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-190">A service outage will occur for users who are homed on SBAs that are associated with pool A until these users are moved to pool C.</span></span>

        
        </div>

28. <span data-ttu-id="fa7be-191">トポロジビルダーで、以前はプール A に関連付けられていた各 SBA X に対して、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fa7be-191">In Topology Builder, for each SBA X previously associated with Pool A, do the following:</span></span>
    
      - <span data-ttu-id="fa7be-192">関連付けを [プール C に変更する。これを行うには、ブランチサイトをクリックし、[存続可能ブランチアプライアンスまたはサーバー] ノードを展開して、[**存続可能 Branch Appliance**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa7be-192">Change the association to Pool C. To do so, click the branch site, expand the Survivable Branch Appliances or Servers node, and click **Survivable Branch Appliance**.</span></span> <span data-ttu-id="fa7be-193">次に、この存続可能 Branch アプライアンスがプール C として接続する**フロントエンドプール、ユーザーサービスプール**を選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa7be-193">Then select the **Front End pool, User Services Pool** that this Survivable Branch Appliance will connect to as Pool C, and then click **Next**.</span></span>
    
      - <span data-ttu-id="fa7be-194">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-194">Publish the topology.</span></span> <span data-ttu-id="fa7be-195">そのためには、コンソールツリーで、新しい**存続可能ブランチアプライアンス**を右クリックし、[**トポロジ**] をクリックして、[**公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa7be-195">To do so, in the console tree, right-click the new **Survivable Branch Appliance**, click **Topology**, and then click **Publish**.</span></span>

29. <span data-ttu-id="fa7be-196">プール C に関連付けられた SBA X ごとに、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fa7be-196">For each SBA X now associated with pool C:</span></span>
    
      - <span data-ttu-id="fa7be-197">存続可能ブランチアプライアンスで次のコマンドレットを実行して、SBA X を開始します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-197">Start SBA X by running the following cmdlet on the survivable branch appliance:</span></span>
        
            Start-CsWindowsService
    
      - <span data-ttu-id="fa7be-198">最初に SBA X をホームにしたユーザーを、次のコマンドレットを実行してプール C から SBA X に移動します。</span><span class="sxs-lookup"><span data-stu-id="fa7be-198">Move users who were originally homed on SBA X from pool C to SBA X by running the following cmdlet.</span></span>
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

