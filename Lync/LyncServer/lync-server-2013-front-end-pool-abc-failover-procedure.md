---
title: 'Lync Server 2013: フロントエンド プール ABC フェールオーバーの手順'
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
ms.openlocfilehash: edf3d12aa519ab7746ccec92998995ed463aa9be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a>Lync Server 2013 フロントエンド プール ABC フェールオーバーの手順

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-05-22_

次の手順を使用して、ABC フェールオーバーの手順を実行します。 この手順では、各手順の概要と、各手順で実行されるコマンドとコマンドレットについて説明します。

コマンドレットを実行するには、[管理者として実行] を使用して、Lync Server 管理シェルを開きます。

<div>

## <a name="to-perform-an-abc-failover"></a>ABC フェールオーバーを実行するには

1.  プール A がセントラル管理サーバー (CMS) のホストであるかどうかを確認します。
    
      - 次のコマンドレットを実行します。
        
            Get-CsService -CentralManagement
        
        Active CMS の Id フィールドが Pool A の完全修飾ドメイン名 (FQDN) をポイントしている場合は、この手順の手順2と3を使用して、最初に中央管理サーバーをフェールオーバーします。 それ以外の場合は、手順4に進みます。

2.  次のコマンドレットを実行して、CMS を障害復旧モードでプール B にフェールオーバーします。
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    この操作を行った後、回復性を強化するために、CMS を pool B から既存のペアリングされた別のプールに移動することをお勧めします。 詳細については、「 [CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)」を参照してください。

3.  Pool A に CMS が含まれている場合、プール A から pool B の LIS データベース (Lis) に LIS 構成をインポートします。 これは、LIS データを定期的にバックアップしている場合にのみ機能します。 LIS 構成をインポートするには、次のコマンドレットを実行します。
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  バックアップされた Lync Server 応答グループサービスワークフローをプール A から pool B にインポートします。
    
    <div>
    

    > [!NOTE]  
    > 現在、 <STRONG>Import-CsRgsConfiguration</STRONG>コマンドレットでは、pool a のキューとワークフロー名が、プール B のキューとワークフロー名と異なる必要があります。名前が異なる場合は、 <STRONG>import-CsRgsConfiguration</STRONG>コマンドレットを実行しているときにエラーが発生します。また、キューとワークフローは、 <STRONG>Import-CsRgsConfiguration</STRONG>コマンドレットを続行する前に、プール B で名前を変更する必要があります。

    
    </div>
    
    [プール A] から [プール B] に応答グループの構成をインポートするには、2つのオプションがあります。どちらのオプションを使うかは、pool B のアプリケーションレベルの設定をプール A のアプリケーションレベルの設定で上書きするかどうかによって異なります。
    
      - プール B の設定を上書きする場合は、 **Replaceexistingsettings**オプションを使用して、 **Import-CsRgsConfiguration**コマンドレットを実行します。
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - プール B の設定を上書きしない場合は、 **Replaceexistingsettings**オプションを指定せずに、 **Import-CsRgsConfiguration**コマンドレットを使います。
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > プライマリプール (プール A) の設定でバックアッププール (プール B) のアプリケーションレベルの設定を上書きしないように注意してください。プール a が失われた場合は、応答グループのアプリケーションレベルの設定が失われることに注意してください。プールごとに1つのアプリケーションレベルの設定のみを保存します。 Pool C を展開してプール A を置き換える場合は、既定の音楽保留オーディオファイルなどのアプリケーションレベルの設定を再構成する必要があります。

    
    </div>

5.  インポートされた応答グループを表示するために、次のコマンドレットを実行して、応答グループの構成インポートが正常に完了したことを確認します。 インポートされた応答グループは、引き続き pool A によって所有されていることに注意してください。
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  未割り当て番号については、選択したアナウンスメントサービスとして "お知らせ" を使用している、割り当てられていない番号範囲をプール A から pool B に移動します。目的:
    
      - プール B のプール A に展開されたすべてのアナウンスを再作成します。プール A でお知らせを展開するときにオーディオファイルが使用されていた場合、これらのファイルはプール B でアナウンスを再作成するために必要です。Pool B でお知らせを再作成するには、**新しい-CsAnnouncement**コマンドレットを使って、プール b を親サービスとして使用します。
    
      - プール A のアナウンスをターゲットとしている未使用のすべての番号範囲を、プール B の新しく展開されたアナウンスに再ターゲットします。プール A のアナウンスのターゲットとして、次のコマンドレットを実行します。
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > この手順は、選択したアナウンスメントサービスとして "Exchange UM" を使用している、割り当てられていない番号範囲には必要ありません。

    
    </div>

7.  次のコマンドレットを実行して、障害回復 (DR) モードでプール A をプール B にフェールオーバーします。
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  プール c をビルドしますが、プール C ではサービスを開始しないでください。
    
    この手順は、手順5と6を同時に実行することができます。

9.  次のコマンドレットを実行して、プール A をホームにしているユーザーをプール C に強制的に移動します。
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    この時点で、プール A をホームにしているユーザーは、サービスの停止を経験し始めます。 この停止は、手順16まで継続され、プール C ではサービスが開始されます。

10. 次のコマンドレットを実行して、pool A の会議ディレクトリをプール C に強制的に移動させます。
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. 次のコマンドレットを実行して、電話会議の自動応答 (CAA を) の連絡先オブジェクトをプール A からプール C に強制的に移動します。
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. 会議コンテンツを pool B から pool C にコピーします。

13. プール B からユーザーデータをエクスポートし、次のコマンドレットを実行してユーザーデータを pool C にインポートします。
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. バックアップされた通話を復元します。プール A からプール C へのアプリケーションデータの割り当てと、プール A のプール C へのコールパーク軌道の範囲の割り当てを行います。
    
      - 通話パークは、Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、プール A の範囲をプール C に再割り当てすることができます。 Lync Server 管理シェルで、pool A に割り当てられているすべての通話パークの範囲に対して、次のコマンドレットを実行します (Id パラメーターは、pool A に属しているコールパークの範囲を参照していることに注意してください)。
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - カスタマイズした音楽の保留がプール A のコールパーク用に構成されている場合は、プール C で、カスタマイズした音楽の保留中のファイルを復元します。
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        次に例を示します。
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - 最後に、 **CsCpsConfiguration**コマンドレットを使用して、プール C のコールパーク設定を再設定します。 コールパークアプリケーションには、1つのプールに1セットの設定と1つのカスタマイズされた音楽オンホールドオーディオファイルのみを保存できます。これらの設定は、障害が発生したときにバックアップまたは保持されません。

15. 常設チャットの next-hop プールがプール A を指している場合は、次ホップサーバーがプール C をポイントするようにトポロジの変更を加えて公開します。
    
      - トポロジービルダーで、次ホップとしてプール C をポイントするように、常設チャットプールを変更します。 そのためには、常設チャットプールを右クリックし、[**全般**] タブをクリックして、[**次ホッププール**] にプール C の名前を入力します。
    
      - 次のコマンドレットを実行して、プール C でサービスを開始します。
        
            Start-csWindowsService
    
    この時点では、サービスの停止が、元々プール A に所属していたユーザーによって終了します。

16. 次のコマンドレットを実行して、プール A によって所有されているプール B から、プール C にインポートして Lync Server 応答グループサービスワークフローをエクスポートします。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. プール B からプール C に Lync Server 応答グループサービスワークフローをインポートします。
    
    [プール B] から [プール C] に応答グループの構成をインポートするには、2つのオプションがあります。どちらのオプションを使用するかは、プール C のアプリケーションレベルの設定をプール B のアプリケーションレベルの設定で上書きするかどうかによって異なります。
    
      - プール C の設定を上書きする場合は、 **Replaceexistingsettings**オプションを指定して、 **Import-CsRgsConfiguration**コマンドレットを実行します。
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - プール C の設定を上書きしない場合は、 **Replaceexistingsettings**オプションを指定せずに、 **Import-CsRgsConfiguration**コマンドレットを使います。
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > プール C のアプリケーションレベルの設定をバックアッププール (プール B) の設定で上書きしないように注意してください。応答グループアプリケーションは1つのアプリケーションレベルのセットしか保存できないため、プール B のアプリケーションレベルの設定は失われます。プールあたりの設定。

    
    </div>

18. プール C にインポートされた応答グループを表示するために、次のコマンドレットを実行して、応答グループの構成インポートが正常に完了したことを確認します。
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. インポートした構成がプール C で確認されたら、プライマリプールによって所有されている応答グループを pool B から削除します。これにより、応答グループのダウンタイムを最小限に抑えることができます。
    
    この手順では、エクスポートされた構成で新しいファイルを作成し、そのファイルを pool B から削除します。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. プール A からプール B に移動された割り当てられていない番号範囲に移動します。
    
      - プール B のプール A から再作成されたすべてのアナウンスをプール C で再作成します。移動するアナウンスの展開時にオーディオファイルが使用されていた場合は、これらのファイルを使用して、プール C でアナウンスを再作成する必要があります。プール C でお知らせを再作成するには、**新しい-CsAnnouncement**コマンドレットを親サービスとしてプール c を使用して使います。
    
      - Pool A から pool B に再ターゲットされたすべての未使用の番号範囲に対して、グループを解除します。再ターゲットとする必要がある、未使用のすべての番号範囲に対して次のコマンドレットを実行します。
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - 省略プール B から削除されたお知らせ (プール B で使用されていない場合は、プール C で再作成したアナウンス)。お知らせを削除するには、" **CsAnnouncement の削除**" コマンドレットを使用します。
        
        <div>
        

        > [!NOTE]  
        > この手順は、"Exchange UM" をアナウンスメントサービスとして使用する、割り当てられていない番号範囲には必要ありません。

        
        </div>

21. 次のコマンドレットを実行して、プール B のプール A のユーザーデータをクリーンアップします。
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. トポロジービルダーで次の操作を行います。
    
      - プール b とプール C をペアリング解除します。次に、トポロジからプール A を削除して公開します。 その手順は、次のとおりです。
        
          - [トポロジビルダー] で、[Pool B] を右クリックし、[**プロパティの編集**] をクリックします。
        
          - 左側のウィンドウで [**復元性**] をクリックします。
        
          - [**関連付けられたバックアッププール**] の下のボックスで、[pool C] を選びます。関連付けられているバックアッププールの選択ボックスには、最初にプール a が表示されます。これは、pool B がこのプールと関連付けられているためです。
        
          - **[音声の自動フェールオーバーとフェールバック]** を選択し、**[OK]** をクリックします。
            
            このプールの詳細情報を表示すると、関連付けられているプールが右ウィンドウの **[復元]** の下に表示されます。
        
          - コンソールツリーで、[pool A] を右クリックし、[削除] をクリックします。
        
          - トポロジを公開します。

23. Pool C でブートストラップアプリケーションを実行して backup service アプリケーションをインストールしてから、pool C のローカルコンピューター上の展開フォルダーから次のように実行して、backup service アプリケーションを起動します。
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. 次のコマンドレットを実行して、プール B の backup service アプリケーションを再起動します。
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. Pool C が標準エディション (SE) プールであり、pool B に CMS がある場合は、次のコマンドレットを実行して、プール C に CMS データベースを手動でインストールします。
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. バックアップサービスを呼び出して、B と C をペアリングする前に生成された新しい会議コンテンツをプール B からプール C に同期し、プール c と B の開始後、B と C の間で作成された新しい会議コンテンツをプール B に同期します。 そのためには、次のコマンドレットを実行します。
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. Pool A に関連付けられている Survivable Branch Appliance X について、次の操作を行います。
    
      - 次のコマンドレットを実行して、SBA X をシャットダウンします。
        
            Stop-CsWindowsService
    
      - SBA X のホームユーザーの一覧を含むファイルを作成します。ユーザーを SBA X に戻す場合は、手順30でリストを表示する必要があります。 そのためには、次のコマンドレットを実行します。
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - 次のコマンドレットを実行して、SBA X をホームにしているユーザーをプール C に移動します。
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - 次のコマンドレットを実行してから、これらのユーザーのデータを更新します。
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        次に、次のスクリプトを実行します。
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > このユーザーがプール C に移動されるまでは、プール A に関連付けられている SBAs に所属しているユーザーに対してサービスの停止が発生します。

        
        </div>

28. Topology Builder で、以前は Pool A に関連付けられていた各 SBA X について、次の操作を行います。
    
      - 関連付けを Pool C に変更します。そのためには、ブランチサイトをクリックし、[Survivable Branch Appliance] または [Servers] ノードを展開して、[ **Survivable Branch Appliance**] をクリックします。 次に、この Survivable Branch アプライアンスがプール C として接続する**フロントエンドプール、ユーザサービスプール**を選択して、「**次へ**」をクリックします。
    
      - トポロジを公開します。 そのためには、コンソールツリーで、新しい**Survivable Branch Appliance**を右クリックし、[ **Topology**] をクリックして、[**発行**] をクリックします。

29. プール C に関連付けられた SBA X ごとに、次の操作を行います。
    
      - SBA X を開始するには、survivable branch appliance で次のコマンドレットを実行します。
        
            Start-CsWindowsService
    
      - 次のコマンドレットを実行して、最初に SBA X に置かれたユーザーのプール C から SBA X に移動します。
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

