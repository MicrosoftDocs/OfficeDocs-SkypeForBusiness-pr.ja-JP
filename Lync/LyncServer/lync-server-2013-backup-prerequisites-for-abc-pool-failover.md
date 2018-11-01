---
title: ABC プール フェールオーバーのバックアップの前提条件
TOCTitle: ABC プール フェールオーバーのバックアップの前提条件
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ945634(v=OCS.15)
ms:contentKeyID: 52056622
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ABC プール フェールオーバーのバックアップの前提条件

 

_**トピックの最終更新日:** 2013-03-26_

ABC プール フェールオーバー手順の利点を最大に活かすには、障害が発生してフェールオーバーが行われる前に、特定のバックアップを実行する必要があります。

  - **Export-CsLISConfiguration** コマンドレットを使用して、プール A から場所情報サービス (LIS) 構成データを定期的にバックアップする必要があります。
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - **Export-CsRgsConfiguration** コマンドレットを使用して、プール A の応答グループ構成データを定期的にバックアップする必要があります。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    一般に、毎日バックアップを行うことをお勧めしますが、変更が多い場合は、より頻度の高いバックアップのスケジュールが必要になることもあります。障害発生時に失われる情報の量は、バックアップの頻度および変更の頻度と量に左右されます。
    
    応答グループ アプリケーションは、プールごとにアプリケーションレベルの設定のセットを 1 つだけ保管できます。これらの設定は **Get-CsRgsConfiguration** コマンドレットによりアクセスできます。このような設定として、既定の保留音の構成、既定の保留音オーディオ ファイル、エージェントかけ直し猶予期間、呼び出しコンテキストの構成があります。これらの設定は、**Import-CsRgsConfiguration** コマンドレットで **ReplaceExistingSettings** パラメーターを使用して、1 つのプールから別のプールに転送できます。しかし、この処理は、移動先プールですべてのアプリケーションレベル設定をオーバーライドします。
    

    > [!TIP]
    > 物理的に別の場所で、応答グループ アプリケーションを構成する目的で使用したすべてのオリジナルの音声ファイル (つまり、録音ファイルまたは保留音ファイル) のバックアップ コピーを保管してください。

    
    プール内のコール パークにアップロードしたカスタマイズ済み保留音ファイルがあれば、それらのコピーを別の場所に保管してください。これらのファイルは Lync Server 2013 の障害復旧プロセスではバックアップされないことから、プールにアップロードされたファイルが破損したり、消去されたりした場合はファイルが失われます。
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    > [!NOTE]
    > コール パーク アプリケーションは、プールごとに、1 セットの構成設定、および 1 つのカスタマイズされた保留音オーディオ ファイルしか保管できません。これらの設定は <strong>Get-CsCpsConfiguration</strong> コマンドレットからアクセスできます。コール パークの障害復旧メカニズムは、バックアップ プールのコール パーク アプリケーションに依存します。このことから、障害が発生したとき、プライマリ プールの設定は、バックアップまた保持されません。プライマリプールが失われた場合、これらの設定は復旧されません。プライマリ プールを置き換える目的で新しいプールを展開したとき、コール パーク設定とすべてのカスタマイズされた保留音オーディオ ファイルは、構成する必要があります。


  - 未使用の番号ボイス機能の一部としてアナウンスを構成する場合、初期設定中に使用されたオリジナルのオーディオ ファイルのコピーを他の場所に保管することをお勧めします。これをしなかった場合、オーディオ ファイルがインポートされたサーバーまたはプールのファイル ストアで、構成されたオーディオ ファイルのコピーを入手できます。これらのファイルは Lync Server 2013 の障害復旧プロセスではバックアップされないことから、プールにアップロードされたファイルが破損したり、消去されたりした場合はファイルが失われます。未使用の番号ボイス機能を構成する目的で使用した、すべてのオーディオ ファイルをサーバーまたはプールのファイル ストアからコピーするには、以下を使用します。
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - プールに監視データベースとアーカイブ データベースがある場合、それらをバックアップするには、SQL Server 管理ツールを使用する必要があります。ABC フェールオーバー手順で、プール A に監視データベースとアーカイブ データベースが併置されている場合は、これらは保持されません。これは、これらのデータベースが Lync Server Backup Service によりバックアップされないことによります。

