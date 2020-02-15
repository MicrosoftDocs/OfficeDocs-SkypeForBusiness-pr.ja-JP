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
ms.openlocfilehash: e2f3798dbe49b9da0e76810d1ea8e6619a4e9b6e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038099"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a>Lync Server 2013 のフロントエンドプール ABC フェールオーバーの手順

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-05-22_

次の手順を使用して、ABC フェールオーバーの手順を実行します。 この手順には、各手順の概要と、各ステップに対して実行されるコマンドとコマンドレットが含まれています。

コマンドレットを実行するには、[管理者として実行] を使用して Lync Server 管理シェルを開きます。

<div>

## <a name="to-perform-an-abc-failover"></a>ABC フェールオーバーを実行するには

1.  プール A が中央管理サーバー (CMS) のホストであるかどうかを確認します。
    
      - 次のコマンドレットを実行します。
        
            Get-CsService -CentralManagement
        
        アクティブな CMS の Id フィールドがプール A の完全修飾ドメイン名 (FQDN) を指している場合は、最初に中央管理サーバーをフェールオーバーするには、この手順の手順2および3を使用します。 それ以外の場合は、手順4に進みます。

2.  次のコマンドレットを実行して、障害復旧モードで CMS をプール B にフェールオーバーします。
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    この操作を行った後、回復性を高めるために、CMS をプール B から別の既存のプールに移動することをお勧めします。 詳細については、「 [move-csmanagementserver](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)」を参照してください。

3.  プール A に CMS が含まれている場合、LIS 構成をプール A からプール B の LIS データベース (Lis. .mdf) にインポートします。 これは、LIS データを定期的にバックアップしている場合にのみ機能します。 LIS 構成をインポートするには、次のコマンドレットを実行します。
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  バックアップされた Lync Server 応答グループサービスワークフローをプール A からプール B にインポートします。
    
    <div>
    

    > [!NOTE]  
    > 現時点では、 <STRONG>Import-CsRgsConfiguration</STRONG>コマンドレットでは、プール a のキューとワークフロー名が、プール B のキューおよびワークフロー名と異なることが必要です。名前が異なる場合は、 <STRONG>import</STRONG>コマンドレットを実行すると、エラーが発生します。また、キューとワークフローは、pool B で、 <STRONG>Import-csrgsconfiguration</STRONG>コマンドレットを続行する前に名前を変更する必要があります。

    
    </div>
    
    プール A からプール B に応答グループの構成をインポートするには、2つのオプションがあります。どちらのオプションを使用するかは、プール A のアプリケーションレベルの設定でプール B のアプリケーションレベルの設定を上書きするかどうかによって決まります。
    
      - プール B の設定を上書きする場合は、 **Replaceexistingsettings**オプションを指定して**Import-CsRgsConfiguration**コマンドレットを実行します。
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - プール B の設定を上書きしない場合は、 **Replaceexistingsettings**オプションを指定せずに、 **Import-CsRgsConfiguration**コマンドレットを使用します。
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > バックアッププールのアプリケーションレベルの設定 (プール A) の設定を上書きしない場合、プール a のアプリケーションレベルの設定は、応答グループアプリケーションが失われた場合に失われます。これは、応答グループアプリケーションで、次のようにします。プールごとに1つのアプリケーションレベルの設定のみを格納します。 プール C を置き換えるためにプール C が展開されている場合は、既定の保留音のオーディオファイルなど、アプリケーションレベルの設定を再構成する必要があります。

    
    </div>

5.  インポートされた応答グループを表示するには、次のコマンドレットを実行して、応答グループ構成のインポートが正常に完了したことを確認します。 インポートされた応答グループは、引き続きプール A によって所有されています。
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  割り当てられていない番号については、[アナウンス] を使用している割り当てられていない番号範囲を、プール A からプール B に選択したアナウンスサービスとして移動します。そのためには次のようにします。
    
      - プール B のプール A に展開されたすべてのアナウンスを再作成します。プール A にアナウンスを展開するときにオーディオファイルが使用された場合、これらのファイルはプール B でアナウンスを再作成するために必要になります。プール B でアナウンスを再作成するには、**新しい-csannouncement**コマンドレットを使用して、pool b を親サービスとして使用します。
    
      - プール A のアナウンスを対象としているすべての未使用の番号範囲を、プール B に新たに展開されたアナウンスに再ターゲットします。プール A のアナウンスを対象とした割り当てなしの番号範囲ごとに次のコマンドレットを実行します。
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > この手順は、選択したアナウンスサービスとして "Exchange UM" を使用する割り当てられていない番号範囲には必要ありません。

    
    </div>

7.  次のコマンドレットを実行して、プール A を Disaster Recovery (DR) モードのプール B にフェールオーバーします。
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  プール c をビルドします。ただし、プール C ではサービスを開始しないでください。
    
    この手順は、手順5および6と同時に実行できることに注意してください。

9.  次のコマンドレットを実行して、プール A に所属するユーザーを強制的にプール C に移動します。
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    この時点で、プール A に所属するユーザーは、サービスの停止を開始することになります。 この停止は、ステップ 16 (プール C でポイントサービスが開始されるまで) まで続きます。

10. 次のコマンドレットを実行して、プール A の会議ディレクトリを強制的にプール C に移動します。
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. 次のコマンドレットを実行して、会議自動応答 (CAA) 連絡先オブジェクトがプール A からプール C に移動するように強制します。
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. 会議コンテンツをプール B からプール C にコピーします。

13. 次のコマンドレットを実行して、プール B からユーザーデータをエクスポートし、ユーザーデータをプール C にインポートします。
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. バックアップされたコールパークアプリケーションデータをプール A からプール C に復元し、プール A からプール C へのコールパークオービットの範囲を割り当てます。
    
      - Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、コールパークオービット範囲のプール A からプール C への再割り当てを行うことができます。 Lync Server 管理シェルについては、次のコマンドレットを実行して、プール A に割り当てられたすべてのコールパークオービット範囲を指定します (Identity パラメーターは、プール A に属しているコールパークオービット範囲を参照することに注意してください)。
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - カスタマイズした保留音がプール A のコールパークに対して構成されている場合は、コールパークカスタマイズされた保留中の保留音ファイルをプール C に復元します。
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        例:
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - 最後に、 **new-cscpsconfiguration**コマンドレットを使用して、プール C のコールパーク設定を再構成します。 コールパークアプリケーションは、1つのプールに対して1セットの設定と1つのカスタマイズされた保留音のオーディオファイルのみを保存できます。また、障害が発生した場合には、これらの設定はバックアップも保持もされません。

15. 常設チャットの次ホッププールがプール A を指している場合は、次ホップサーバーがプール C をポイントするようにトポロジの変更を行い、公開します。
    
      - トポロジビルダーで、次ホップとして [プール C] をポイントするように常設チャットプールを変更します。 そのためには、常設チャットプールを右クリックし、[**全般**] タブをクリックして、[**次ホッププール**] にプール C の名前を入力します。
    
      - 次のコマンドレットを実行して、プール C のサービスを開始します。
        
            Start-csWindowsService
    
    この時点で、最初にプール A に所属していたユーザーがサービスの停止を終了します。

16. 次のコマンドレットを実行して、プール A からプール C にインポートするために所有されているプール B から Lync Server Response Group service ワークフローをエクスポートします。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. プール B からプール C に Lync Server Response Group service ワークフローをインポートします。
    
    応答グループの構成をプール B からプール C にインポートするには、2つのオプションがあります。どのオプションを使用するかは、プール C のアプリケーションレベルの設定をプール B のアプリケーションレベルの設定で上書きするかどうかによって決まります。
    
      - プール C の設定を上書きする場合は、 **Replaceexistingsettings**オプションを指定して**Import-CsRgsConfiguration**コマンドレットを実行します。
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - プール C の設定を上書きしない場合は、 **Replaceexistingsettings**オプションを指定せずに、 **Import-CsRgsConfiguration**コマンドレットを使用します。
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > プール C のアプリケーションレベルの設定をバックアッププール (プール B) の設定で上書きしない場合は、応答グループアプリケーションに格納できるアプリケーションレベルのセットが1つのみであるため、プール B のアプリケーションレベルの設定が失われることに注意してください。プールごとの設定。

    
    </div>

18. 次のコマンドレットを実行して、応答グループ構成のインポートが正常に完了したことを確認して、プール C にインポートされた応答グループを表示します。
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. インポートした構成がプール C で確認されたら、プライマリプールが所有する応答グループをプール B から削除します。これにより、応答グループのダウンタイムを最小限に抑えることができます。
    
    この手順では、エクスポートされた構成で新しいファイルを作成し、プール B からファイルを削除します。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. プール A からプール B に移動された割り当てられていない番号範囲に、プール C に移動します。
    
      - プール B のプール A から再作成されたすべてのアナウンスをプール C で再作成します。移動するアナウンスを展開するときにオーディオファイルが使用されていた場合は、これらのファイルを使用して、プール C でアナウンスを再作成する必要があります。プール C でアナウンスを再作成するには、**新しい-csannouncement**コマンドレットを使用し、プール c を親サービスとして使用します。
    
      - プール A からプール B に再ターゲットされたすべての未使用の番号範囲をプール C に再ターゲットします。再ターゲットする必要があるすべての未使用の番号範囲に対して次のコマンドレットを実行します。
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - オプションプール b で使用されなくなったアナウンスをプール B から削除します。プール B で使用されなくなったアナウンス。アナウンスを削除するには、[**削除]-csannouncement**コマンドレットを使用します。
        
        <div>
        

        > [!NOTE]  
        > "Exchange UM" をアナウンスサービスとして使用する割り当てられていない番号範囲では、この手順は必要ありません。

        
        </div>

21. 次のコマンドレットを実行して、プール B のプール A のユーザーデータをクリーンアップします。
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. トポロジビルダーで、次の操作を行います。
    
      - 解除プール A およびプール B。ペアプール B およびプール C。その後、トポロジからプール A を削除して公開します。 これを行うには、以下のようにします:
        
          - トポロジビルダーで、[プール B] を右クリックし、[**プロパティの編集**] をクリックします。
        
          - 左側のウィンドウで [**復元**] をクリックします。
        
          - [**関連付けられたバックアッププール**] の下にある [pool C] を選択します。 [関連付けられているバックアッププール] 選択ボックスには、最初にプール a が表示されます。これは、プール B が以前このプールに関連付けられているためです
        
          - [**音声の自動フェールオーバーとフェールバック**] を選択し、[**OK**] をクリックします。
            
            このプールの詳細情報を表示すると、関連付けられているプールが右ウィンドウの [**復元**] の下に表示されます。
        
          - コンソールツリーで、[プール A] を右クリックし、[削除] をクリックします。
        
          - トポロジを公開します。

23. プール c でブートストラップアプリケーションを実行して、backup service アプリケーションをインストールした後、pool C のローカルコンピューターの展開フォルダーから以下を実行して、バックアップサービスアプリケーションを開始します。
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. 次のコマンドレットを実行して、プール B でバックアップサービスアプリケーションを再起動します。
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. プール C が Standard Edition (SE) プールで、プール B に CMS がある場合は、次のコマンドレットを実行して CMS データベースをプール C に手動でインストールします。
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. バックアップサービスを呼び出して、B と C をペアにする前に生成された古い会議コンテンツをプール B からプール C に同期し、プール c からプール c を起動してから、B と C がペアになった後に生成された新しい会議コンテンツをプール c からプール B に同期します。 これを行うには、次のコマンドレットを実行します。
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. プール A に関連付けられている各存続可能 Branch アプライアンス X に対して、次のようにします。
    
      - 次のコマンドレットを実行して、SBA X をシャットダウンします。
        
            Stop-CsWindowsService
    
      - SBA X に所属するユーザーの一覧を含むファイルを作成します。このリストは、ユーザーが手順30で SBA X に戻ったときに必要になります。 これを行うには、次のコマンドレットを実行します。
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - 次のコマンドレットを実行して、SBA X に所属するユーザーにプール C への移動を強制します。
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - 最初に次のコマンドレットを実行して、これらのユーザーのデータを更新します。
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        その後、次のスクリプトを実行します。
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > プール A に関連付けられている SBAs に所属しているユーザーがプール C に移動するまで、サービスの停止が発生します。

        
        </div>

28. トポロジビルダーで、以前はプール A に関連付けられていた各 SBA X に対して、次の操作を行います。
    
      - 関連付けを [プール C に変更する。これを行うには、ブランチサイトをクリックし、[存続可能ブランチアプライアンスまたはサーバー] ノードを展開して、[**存続可能 Branch Appliance**] をクリックします。 次に、この存続可能 Branch アプライアンスがプール C として接続する**フロントエンドプール、ユーザーサービスプール**を選択して、[**次へ**] をクリックします。
    
      - トポロジを公開します。 そのためには、コンソールツリーで、新しい**存続可能ブランチアプライアンス**を右クリックし、[**トポロジ**] をクリックして、[**公開**] をクリックします。

29. プール C に関連付けられた SBA X ごとに、次のようになります。
    
      - 存続可能ブランチアプライアンスで次のコマンドレットを実行して、SBA X を開始します。
        
            Start-CsWindowsService
    
      - 最初に SBA X をホームにしたユーザーを、次のコマンドレットを実行してプール C から SBA X に移動します。
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

