---
title: 'Lync Server 2013: フロントエンド プール ABC フェールオーバーの手順'
TOCTitle: フロントエンド プール ABC フェールオーバーの手順
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ945635(v=OCS.15)
ms:contentKeyID: 52056611
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 フロントエンド プール ABC フェールオーバーの手順

 

_**トピックの最終更新日:** 2014-05-22_

ABC フェールオーバーを実行するには、以下の手順を使用します。この手順では、各手順の概要を解説した後、各手順で実行するコマンドとコマンドレットを説明します。

コマンドレットを実行するには、\[管理者として実行\] を使用して Lync Server 管理シェルを開きます。

## ABC フェールオーバーを実行するには

1.  プール A が中央管理サーバー (CMS) のホストであるかどうか確認してください。
    
      - 次のコマンドレットを実行します。
        
            Get-CsService -CentralManagement
        
        アクティブな CMS の ID フィールドが、プール A の完全修飾ドメイン名前 (FQDN) を示す場合、手順 2. および 3. を使用して、最初に中央管理サーバーをフェールオーバーします。その他の場合には、手順 4. に進みます。

2.  以下のコマンドレットを実行して、障害復旧モードで CMS をプール B にフェールオーバーします。
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    これを行った後で、復元力を強化する目的で、CMS をプール B から、別の、既存の、ペアにされたプールに移動することをお勧めします。詳細については、「[Move-CsManagementServer](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsManagementServer)」を参照してください。

3.  プール A が CMS を含む場合は、プール A からプール B の LIS データベース (Lis.mdf) に LIS 構成をインポートします。これは、これまで定期的に LIS データをバックアップしていた場合に限り、機能します。LIS 構成をインポートするには、以下のコマンドレットを実行します。
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  プール A からプール B に、バックアップされた Lync Server 応答グループ サービス ワークフローをインポートします。
    
    > [!NOTE]
    > 現在、<strong>Import-CsRgsConfiguration</strong> コマンドレットでは、プール A のキューおよびワークフロー名が、プール B のキューおよびワークフロー名とは別である必要があります。名前が区別されていない場合、<strong>Import-CsRgsConfiguration</strong> コマンドレットを実行するとき、エラーが発生します。そして、<strong>Import-CsRgsConfiguration</strong> コマンドレットを実行する前に、プール B のキューとワークフローの名前を変更する必要があります。
    
    プール A からプール B に応答グループ構成をインポートする場合、2 つの方法があります。どちらの方法を使用するかは、プール A のアプリケーションレベル設定で、プール B のアプリケーション レベル設定を上書きするかによります。
    
      - プール B 設定を上書きする場合は、以下のように、**ReplaceExistingSettings** オプションを指定して **Import-CsRgsConfiguration** コマンドレットを実行します。
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - プール B 設定を上書きしない場合は、以下のように、**ReplaceExistingSettings** オプションを指定せずに **Import-CsRgsConfiguration** コマンドレットを使用します。
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    

    > [!WARNING]
    > バックアップ プール (プール B) のアプリケーションレベル設定をプライマリ プール (プール A) の設定で上書きしない場合は、プール A が失われたときにプール A のアプリケーションレベル設定も失われることに注意してください。これは、応答グループ アプリケーションは、プールごとに 1 つのセットのアプリケーションレベル設定しか格納できないことによります。プール A を置き換える目的でプール C を展開するとき、アプリケーションレベル設定は、既定の保留音オーディオ ファイルを含めて、再構成する必要があります。



5.  応答グループ構成インポートが正常に完了したかを、以下のコマンドレットを実行し、インポートした応答グループを表示して確認してください。インポートされた応答グループはプール A に所有されたままとなることに注意してください。
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  未使用の番号については、選択したアナウンス サービスとして "アナウンス" を使用している未使用の番号範囲を、プール A からプール B に移動します。これを行うには、以下のようにします。
    
      - プール A に展開されたすべてのアナウンスを、プール B に、再度、作成します。プール A でのアナウンスの展開にオーディオ ファイルが使用された場合、これらのファイルは、プール B でアナウンスを、再度、作成する目的で必要となります。プール B でアナウンスを、再度、作成するには、親サービスとしてプール B を指定して、**New-CsAnnouncement** コマンドレットを使用します。
    
      - プール A でアナウンスを対象としているすべての未使用の番号範囲を、プール B で新しく展開されたアナウンスに、再度、対象設定します。プール A のアナウンスを対象としているすべての未使用の番号範囲について、以下のコマンドレットを実行します。
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    > [!NOTE]
    > この手順は、選択したアナウンス サービスとして &quot;Exchange UM&quot; を使用する未使用の番号範囲では不要です。


7.  以下のコマンドレットを実行して、障害復旧 (DR) モードでプール A をプール B にフェールオーバーします。
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  プール C を作成します。しかし、プール C ではサービスを開始しないでください。
    
    この手順は、手順 5. および 6. と同時に実行できることに注意してください。

9.  以下のコマンドレットを実行して、プール A に所属するユーザーを、プール C に強制的に移動します。
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    この時点で、プール A に所属するユーザーに対してサービス停止が発生しはじめます。この機能停止は、プール C でサービスが開始される手順 16. まで続きます。

10. 以下のコマンドレットを実行して、プール A の電話会議ディレクトリを、プール C に強制的に移動します。
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. 以下のコマンドレットを実行して、会議自動アテンダント (CAA) 連絡先オブジェクトを、プール A からプール C に強制的に移動します。
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. プール B からプール C に電話会議コンテンツをコピーします。

13. 以下のコマンドレットを実行して、プール B からユーザー データをエクスポートし、プール C にユーザー データをインポートします。
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. バックアップされたコール パーク アプリケーション データをプール A からプール C に復元し、プール A のコール パーク オービット範囲をプール C に割り当てます。
    
      - Lync Server コントロール パネルまたは Lync Server 管理シェルにより、プール A のコール パーク オービット範囲をプール C に、再度、割り当てることができます。Lync Server 管理シェルで、プール A に割り当てられたすべてのコール パーク オービット範囲について、以下のコマンドレットを実行します (ID パラメーターとは、プール A に属するコール パーク オービット範囲を示すことに注意してください)。
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - プール A 内のコール パークにカスタマイズされた保留音が構成されている場合、コール パークのカスタマイズされた保留音ファイルをプール C に復元します。
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        次に例を示します。
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - 最後に、**Set-CsCpsConfiguration** コマンドレットを使用して、プール C でコール パーク設定を、再度、構成します。コール パーク アプリケーションは、プールごとに、1 セットの構成設定、および 1 つのカスタマイズされた保留音オーディオ ファイルしか保管できません。障害が発生したとき、これらの設定は、バックアップまた保持されません。

15. 常設チャットの次のホップ プールがプール A を示している場合は、次のホップ サーバーがプール C を示すようにトポロジ変更を行って発行します。
    
      - トポロジ ビルダーで、常設チャット プールを、次のホップとしてプール C を示すように変更します。この作業をするには、常設チャット プールを右クリックし、次に \[**全般**\] タブをクリックして、\[**次ホップ プール**\] で、プール C の名前を入力します。
    
      - 以下のコマンドレットを実行することにより、プール C でサービスを開始します。
        
            Start-csWindowsService
    
    この時点で、当初プール A に所属していたユーザーに対するサービス停止は終了します。

16. 以下のコマンドレットを実行することにより、プール C にインポートする目的で、プール A によって所有されるプール B から、Lync Server 応答グループ サービス ワークフローをエクスポートします。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. プール B からプール C に、Lync Server 応答グループ サービス ワークフローをインポートします。
    
    プール B からプール C に応答グループ構成をインポートする場合、2 つの方法があります。どちらの方法を使用するかは、プール B のアプリケーションレベル設定で、プール C のアプリケーション レベル設定を上書きするかによります。
    
      - プール C 設定を上書きする場合は、以下のように、**ReplaceExistingSettings** オプションを指定して **Import-CsRgsConfiguration** コマンドレットを実行します。
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - プール C 設定を上書きしない場合は、以下のように、**ReplaceExistingSettings** オプションを指定せずに **Import-CsRgsConfiguration** コマンドレットを使用します。
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    

    > [!WARNING]
    > プール C のアプリケーションレベル設定をバックアップ プール (プール B) の設定で上書きしない場合は、プール B のアプリケーションレベル設定も失われることに注意してください。これは、応答グループ アプリケーションは、プールごとに 1 つのセットのアプリケーションレベル設定しか格納できないことによります。



18. 応答グループ構成インポートが正常に完了したかを、以下のコマンドレットを実行し、プール C にインポートされた応答グループを表示して確認してください。
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. インポートした構成をプール C で確認した後で、プライマリ プールによって所有されている応答グループをプール B から削除します。これにより、応答グループのダウンタイムを最小限にできます。
    
    このステップでは、エクスポートされた構成で新しいファイルを作成し、そのファイルをプール B から削除します。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. プール A からプール B に移動された未使用の番号範囲をプール C に移動します。
    
      - プール A からプール B に、再度、作成されたすべてのアナウンスを、プール C に、再度、作成します。移動されるアナウンスを展開するときにオーディオ ファイルが使用された場合、これらのファイルは、プール C でアナウンスを、再度、作成する目的で必要となります。プール C でアナウンスを、再度、作成するには、親サービスとしてプール C を指定して、**New-CsAnnouncement** コマンドレットを使用します。
    
      - プール A からプール B に、再度、対象設定されたすべての未使用の番号範囲を、プール C に、再度、対象設定します。再度、対象設定する必要があるすべての未使用の番号範囲について、以下のコマンドレットを実行します。
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - (省略可) プール C で、再度、作成されたアナウンスがプール B で使用されていない場合は、それらをプール B から削除します。アナウンスを削除するには、**Remove-CsAnnouncement** コマンドレットを使用します。
        
        > [!NOTE]  
        > この手順は、アナウンス サービスとして &quot;Exchange UM&quot; を使用する未使用の番号範囲では不要です。

21. 以下のコマンドレットを実行することにより、プール B 内のプール A のユーザー データをクリーンアップします。
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. トポロジ ビルダーで次の操作を行います。
    
      - プール A とプール B をペア解除します。プール B とプール C をペアにします。次にトポロジからプール A を削除して、それを発行します。これを行うには、以下のようにします。
        
          - トポロジ ビルダーで、プール B を右クリックし、\[**プロパティの編集**\] をクリックします。
        
          - 左ウィンドウの \[**復元**\] をクリックします。
        
          - \[**関連付けられているバックアップ プール**\] ボックスの下で、プール C を選択します。プール A とプール B が以前に関連付けられていたことにより、\[関連付けられているバックアップ プール\] 選択ボックスには、当初は、プール A が表示されていることに注意してください。
        
          - \[**音声の自動フェールオーバーとフェールバック**\] を選択し、\[**OK**\] をクリックします。
            
            このプールの詳細情報を表示すると、関連付けられているプールが右ウィンドウの \[**復元**\] の下に表示されます。
        
          - コンソール ツリーで、プール A を右クリックし、\[削除\] をクリックします。
        
          - トポロジを公開します。

23. プール C でブートストラップ アプリケーションを実行して、バックアップ サービス アプリケーションをインストールします。次に、プール C のローカル マシンの展開フォルダーから以下を実行して、バックアップ サービス アプリケーションを開始します。
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. 以下のコマンドレットを実行して、プール B でバックアップ サービス アプリケーションを再起動します。
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. プール C が Standard Edition (SE) プールであり、プール B が CMS を持っている場合は、以下のコマンドレットを実行して、プール C で CMS データベースを手動でインストールします。
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. 2 つの目的で、バックアップ サービスを呼び出します。B と C をペアリングする前に生成された古い会議コンテンツをプール B からプール C に同期します。また、プール C が開始された後、B と C がペアにされる前に生成された新しい会議コンテンツをプール C からプール B に同期します。これを行うには、次のコマンドレットを実行します。
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. プール A に関連付けられた各存続可能ブランチ アプライアンス X について以下を行います。
    
      - 以下のコマンドレットを実行して SBA X を終了します。
        
            Stop-CsWindowsService
    
      - SBA X に所属するユーザーのリストを含むファイルを作成します。手順 30. でユーザーを SBA X に戻すときに、このリストが必要になります。これを行うには、次のコマンドレットを実行します。
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - 以下のコマンドレットを実行して、SBA X に所属するユーザーを、プール C に強制的に移動します。
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - まず、以下のコマンドレットを実行して、これらのユーザーのデータを更新します。
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        次に、このスクリプトを実行します。
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - }
        
        > [!NOTE]  
        > プール A に関連付けられた SBA に所属するユーザーには、サービス停止が発生します。これは、これらのユーザーがプール C に移動されるまで続きます。


28. トポロジ ビルダーで、以前にプール A に関連付けられた各 SBA X について、以下の操作を実行します。
    
      - プール C に関連付けを変更します。これを行うには、ブランチ サイトをクリックし、存続可能ブランチ アプライアンスまたはサーバーノードを展開して、\[**存続可能ブランチ アプライアンス**\] をクリックします。次に、この存続可能ブランチ アプライアンスがプール C として接続する **フロントエンド プール、ユーザー サービス プール**を選択して、\[**次に**\] をクリックします。
    
      - トポロジを公開します。これを行うには、コンソールツリーで、新しい \[**存続可能ブランチ アプライアンス**\] を右クリックして、\[**トポロジ**\]、\[**発行**\] の順にクリックします。

29. プール C に関連付けられた各 SBA X について以下を行います。
    
      - 存続可能ブランチ アプライアンスで以下のコマンドレットを実行することにより、SBA X を開始します。
        
            Start-CsWindowsService
    
      - 以下のコマンドレットを実行することにより、当初 SBA X に所属したユーザーを、プール C から SBA X に移動します。
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

