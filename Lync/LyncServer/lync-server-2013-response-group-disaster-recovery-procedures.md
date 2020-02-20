---
title: Lync Server 2013 応答グループの障害復旧手順
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group disaster recovery procedures
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48185171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ecd074254243629bbb3a6dc732b11a93cfebbe7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a><span data-ttu-id="37fd2-102">Lync Server 2013 の応答グループの障害復旧手順</span><span class="sxs-lookup"><span data-stu-id="37fd2-102">Response group disaster recovery procedures in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37fd2-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="37fd2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="37fd2-104">障害復旧のフェールオーバー フェーズ中、応答グループは (使用できない) プライマリ プールとバックアップ プールという複数のプールに存在します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-104">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="37fd2-105">どちらのプールでも応答グループの名前と所有者 (プライマリ プール) は同じですが、その親は異なります。</span><span class="sxs-lookup"><span data-stu-id="37fd2-105">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span> <span data-ttu-id="37fd2-106">この間、応答グループコマンドレットの動作は少し異なります。</span><span class="sxs-lookup"><span data-stu-id="37fd2-106">During this time, Response Group cmdlets work a little differently.</span></span> <span data-ttu-id="37fd2-107">次の手順で指定されているように、必ずパラメーターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="37fd2-107">Be sure to use parameters as specified in the following procedure.</span></span> <span data-ttu-id="37fd2-108">フェールオーバーフェーズ中のコマンドレットの動作の詳細については、「NextHop blog 記事 "Lync Server 2013: Disaster Recovery の[https://go.microsoft.com/fwlink/p/?LinkId=263957](https://go.microsoft.com/fwlink/p/?linkid=263957)間の応答グループの回復」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37fd2-108">For details about how cmdlets work during the failover phase, see NextHop blog article "Lync Server 2013: Recovering Response Groups During Disaster Recovery" at [https://go.microsoft.com/fwlink/p/?LinkId=263957](https://go.microsoft.com/fwlink/p/?linkid=263957).</span></span> <span data-ttu-id="37fd2-109">このブログ記事は、リリース版の Lync Server 2013 にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="37fd2-109">This blog article also applies to the released version of Lync Server 2013.</span></span>

<span data-ttu-id="37fd2-110">Lync Server Response Group service の障害復旧を準備および実行するには、以下の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-110">Use the steps in the following procedure to prepare for and perform disaster recovery for Lync Server Response Group service.</span></span>

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a><span data-ttu-id="37fd2-111">応答グループをフェールオーバーおよびフェールバックするには</span><span class="sxs-lookup"><span data-stu-id="37fd2-111">To fail over and fail back Response Group</span></span>

1.  <span data-ttu-id="37fd2-112">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="37fd2-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="37fd2-p102">定期的にバックアップを実行します。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-p102">Routinely perform backups. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="37fd2-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-115">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  <span data-ttu-id="37fd2-p103">停止中、バックアップ プールにフェールオーバーした後で、応答グループをバックアップ プールにインポートします。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-p103">During an outage, after failover to the backup pool, import the response groups to the backup pool. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="37fd2-p104">バックアップ プールのアプリケーションレベルの設定をプライマリ プールの設定に置き換える場合は、–ReplaceExistingSettings パラメーターを含めます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-p104">If you want to replace the application-level settings in the backup pool with the settings from the primary pool, include the –ReplaceExistingSettings parameter. For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="37fd2-120">バックアップ プールの設定を置き換えず、プライマリ プールを復元できない場合、プライマリ プールの設定は失われます。</span><span class="sxs-lookup"><span data-stu-id="37fd2-120">If you do not replace the settings in the backup pool and the primary pool can't be recovered, the primary pool settings will be lost.</span></span> <span data-ttu-id="37fd2-121">詳細については、「 <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Lync Server 2013 で応答グループの障害復旧を計画する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37fd2-121">For details, see <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for response group disaster recovery in Lync Server 2013</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="37fd2-p106">インポートされた応答グループを表示して、インポートが成功したことを確認します。インポートされた応答グループはプライマリ プールに所有されたままです。次の手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="37fd2-p106">Verify that the import was successful by displaying the imported response groups. The imported response groups are still owned by the primary pool. Do the following:</span></span>
    
      - <span data-ttu-id="37fd2-p107">プライマリ プールに所有されているバックアップ プールのすべてのワークフローを表示し、プライマリ プールのワークフローがすべて含まれていることを確認します。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-p107">Display all the workflows in the backup pool that are owned by the primary pool, and verify that all the primary pool workflows are included. At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="37fd2-127">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-127">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - <span data-ttu-id="37fd2-p108">プライマリ プールに所有されているバックアップ プールのすべてのキューを表示し、プライマリ プールのキューがすべて含まれていることを確認します。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-p108">Display all the queues in the backup pool that are owned by the primary pool, and verify that all the primary pool queues are included. At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="37fd2-130">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-130">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="37fd2-p109">プライマリ プールに所有されているバックアップ プールのすべてのエージェント グループを表示し、プライマリ プールのエージェント グループがすべて含まれていることを確認します。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-p109">Display all the agent groups in the backup pool that are owned by the primary pool, and verify that all the primary pool agent groups are included. At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="37fd2-133">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-133">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="37fd2-p110">プライマリ プールに所有されているバックアップ プールのすべての営業時間を表示し、プライマリ プールの営業時間がすべて含まれていることを確認します。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-p110">Display all the hours of business in the backup pool that are owned by the primary pool, and verify that all the primary pool hours of business are included. At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="37fd2-136">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-136">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="37fd2-p111">プライマリ プールに所有されているバックアップ プールのすべての休日セットを表示し、プライマリ プールの休日セットがすべて含まれていることを確認します。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-p111">Display all the holiday sets in the backup pool that are owned by the primary pool, and verify that all the primary pool holiday sets are included. At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="37fd2-139">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-139">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    <span data-ttu-id="37fd2-p112">また、–Owner パラメーターの代わりに –ShowAll パラメーターを使用して、バックアップ プールのすべての応答グループを表示することもできます。これには、プライマリ プールに所有されているものと、バックアップ プールに所有されているものが含まれます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-p112">Alternatively, you can display all the response groups in the backup pool, including the ones owned by the primary pool and the ones owned by the backup pool by using the –ShowAll parameter instead of the –Owner parameter. For example:</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="37fd2-p113">–ShowAll パラメーターと –Owner パラメーターはどちらかを使用する必要があります。これらのパラメーターのいずれも使用しない場合、バックアップ プールにインポートした応答グループはコマンドレットによって返される結果に表示されません。</span><span class="sxs-lookup"><span data-stu-id="37fd2-p113">You must use either the –ShowAll parameter or the –Owner parameter. If you do not use either of these parameters, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>

    
    </div>

5.  <span data-ttu-id="37fd2-144">インポートが正常に完了したことを確認します。そのためには、インポートされた応答グループに電話をかけて通話が正常に処理されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-144">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="37fd2-145">公式エージェント グループのメンバーであるエージェントに、バックアップ プールのエージェント グループにサインインするよう要求します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-145">Request agents who are members of formal agent groups to sign in to their agent groups in the backup pool.</span></span>

7.  <span data-ttu-id="37fd2-146">インポートした応答グループを通常どおりに管理および変更します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-146">Manage and modify the imported response groups as usual.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="37fd2-147">応答グループがバックアッププールにある間は、Lync Server 管理シェルを使用してそれらを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37fd2-147">While the response groups are in the backup pool, you need to use Lync Server Management Shell to manage them.</span></span> <span data-ttu-id="37fd2-148">Lync Server コントロールパネルを使用して、バックアッププールにインポートした応答グループを管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="37fd2-148">You cannot use Lync Server Control Panel to manage the response groups that you imported to the backup pool.</span></span>

    
    </div>

8.  <span data-ttu-id="37fd2-p115">プライマリ プールが復元されてフェールバックが完了したら、バックアップ プールにインポートされたプライマリ プールの応答グループをエクスポートします。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-p115">After the primary pool is restored and failback is complete, export the primary pool response groups that were imported to the backup pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  <span data-ttu-id="37fd2-p116">応答グループをプライマリ プールに再びインポートします。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-p116">Import the response groups back to the primary pool. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    <span data-ttu-id="37fd2-153">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-153">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="37fd2-p117">復旧中にプールを構築し直す場合は、完全修飾ドメイン名 (FQDN) を同じにするか別にするかにかかわらず、–OverwriteOwner パラメーターを使用する必要があります。大まかには、プライマリ プールに応答グループを再びインポートするときは常に –OverwriteOwner パラメーターを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="37fd2-p117">If you rebuild a pool during recovery, whether with the same or a different fully qualified domain name (FQDN), you need to use the –OverwriteOwner parameter. As a rule of thumb, you can always use the –OverwriteOwner parameter when you import response groups back to the primary pool.</span></span>

    
    </div>
    
    <span data-ttu-id="37fd2-p118">(同じまたは異なる完全修飾ドメイン名 (FQDN) の) 新しいプールを展開してプライマリ プールを置き換え、新しいプールにバックアップ プールからのアプリケーションレベルの設定を使用する場合は、–ReplaceExistingSettings パラメータを含めます。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-p118">If you deployed a new pool (with the same or a different FQDN) to replace the primary pool, and you want to use the application-level settings from the backup pool for the new pool, include the –ReplaceExistingSettings parameter. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    <span data-ttu-id="37fd2-158">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-158">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="37fd2-159">新しいプールのアプリケーションレベルの設定と既定の保留音のオーディオ ファイルをバックアップ プールからの設定に置き換えない場合、新しいプールは既定のアプリケーションレベルの設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-159">If you don't want to replace the application-level settings and default music-on-hold audio file for the new pool with the settings from the backup pool, the new pool will use the default application-level settings.</span></span>

    
    </div>

10. <span data-ttu-id="37fd2-p119">再びインポートされた応答グループ構成を表示して、プライマリ プールへのインポートが成功したことを確認します。次の手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="37fd2-p119">Verify that the import back to the primary pool was successful by displaying the imported response group configuration. Do the following:</span></span>
    
      - <span data-ttu-id="37fd2-p120">プライマリ プールのすべてのワークフローを表示して、インポートされたワークフローがすべて含まれていることを確認します。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-p120">Display all the workflows in the primary pool, and verify that all the imported workflows are included. At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="37fd2-164">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-164">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="37fd2-p121">プライマリ プールのすべてのキューを表示して、インポートされたキューがすべて含まれていることを確認します。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-p121">Display all the queues in the primary pool, and verify that all the imported queues are included. At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="37fd2-167">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-167">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="37fd2-p122">プライマリ プールのすべてのエージェント グループを表示して、インポートされたエージェント グループがすべて含まれていることを確認します。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-p122">Display all the agent groups in the primary pool, and verify that all the imported agent groups are included. At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="37fd2-170">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-170">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="37fd2-p123">プライマリ プールのすべての営業時間を表示して、インポートされた営業時間がすべて含まれていることを確認します。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-p123">Display all the hours of business in the primary pool, and verify that all the imported hours of business are included. At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="37fd2-173">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-173">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="37fd2-p124">プライマリ プールのすべての休日セットを表示して、インポートされた休日セットがすべて含まれていることを確認します。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-p124">Display all the holiday sets in the primary pool, and verify that all the imported holiday sets are included. At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="37fd2-176">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-176">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. <span data-ttu-id="37fd2-177">インポートが正常に完了したことを確認します。そのためには、インポートされた応答グループに電話をかけて通話が正常に処理されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-177">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

12. <span data-ttu-id="37fd2-p125">オプションで、プライマリ プールが所有する応答グループをバックアップ プールから削除します。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-p125">Optionally, remove the response groups owned by the primary pool from the backup pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    <span data-ttu-id="37fd2-180">例:</span><span class="sxs-lookup"><span data-stu-id="37fd2-180">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="37fd2-181">このステップでは、エクスポートされた構成で新しいファイルを作成し、そのファイルをバックアップ プールから削除します。</span><span class="sxs-lookup"><span data-stu-id="37fd2-181">This step creates a new file with the exported configuration, and then removes it from the backup pool.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

