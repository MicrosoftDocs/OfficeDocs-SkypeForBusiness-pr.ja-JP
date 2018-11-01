---
title: Enterprise Edition バックエンド サーバーの復元
TOCTitle: Enterprise Edition バックエンド サーバーの復元
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh202163(v=OCS.15)
ms:contentKeyID: 52056538
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enterprise Edition バックエンド サーバーの復元

 

_**トピックの最終更新日:** 2013-02-18_

以下の 2 つのケースで、このトピックの手順を使用します。

  - ミラー化された Enterprise Edition バックエンド サーバーのプライマリ データベースとミラー データベースで障害が発生した。

  - ミラー化されていない Enterprise Edition バックエンド サーバーで障害が発生した。

ミラー化された Enterprise Edition バックエンドがあり、ミラー データベースまたはプライマリ データベースのどちらかのみで障害が発生した場合は、「[ミラー化された Enterprise Edition バックエンド サーバーの復元 - プライマリ](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)」を参照してプライマリ データベースを復元するか、「[ミラー化された Enterprise Edition バック エンド サーバーの復元 - ミラー](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)」を参照してミラーを復元します。

中央管理ストアで障害が発生した場合は、「[中央管理ストアをホストするサーバーの復元](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)」を参照してください。バックエンド サーバー以外の Enterprise Edition メンバー サーバーで障害が発生した場合は、「[Enterprise Edition メンバー サーバーの復元](lync-server-2013-restoring-an-enterprise-edition-member-server.md)」を参照してください。


> [!TIP]
> 復元を開始する前にシステムのイメージ コピーを取得することをお勧めします。復元中に問題が発生した場合に、そのイメージをロールバック ポイントに使用できます。このイメージ コピーをオペレーティング システムと SQL Server のインストール後に作成して、証明書を復元または再登録することもできます。



## Enterprise Edition バックエンド サーバーを復元するには

1.  問題が発生したコンピューターと同じ完全修飾ドメイン名 (FQDN) を持つクリーン サーバーか新規サーバーにオペレーティング システムをインストールし、証明書を復元または再登録します。
    
    > [!NOTE]
    > 組織で定めるサーバーの展開手順に従って、この手順を実行します。


2.  RTCUniversalServerAdmins グループのメンバーであるユーザー アカウントから、復元するサーバーにログオンします。

3.  インスタンス名を障害が発生する前の名前と同じにして、SQL Server 2012 または SQL Server 2008 R2 をインストールします。
    
    > [!NOTE]
    > 展開によっては、バックエンド サーバーに複数の併置されたデータベースまたは別々のデータベースが含まれる場合があります。SQL Server の権限とログインも含めて、最初にサーバーを展開したときと同じ手順で SQL Server をインストールしてください。


4.  SQL Server をインストールした後、次の手順を実行します。
    
    1.  トポロジ ビルダーを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server トポロジ ビルダー**\] の順にクリックします。
    
    2.  \[**既存の展開からトポロジをダウンロードする**\] をクリックし、\[**OK**\] をクリックします。
    
    3.  トポロジを選択し、\[**保存**\] をクリックします。\[**はい**\] をクリックして選択を確定します。
    
    4.  \[**Lync Server 2013**\] ノードを右クリックし、\[**トポロジの公開**\] をクリックします。
    
    5.  **トポロジの公開**ウィザードの指示に従います。\[**データベースの作成**\] ページで、再作成するデータベースを選択します。
        
        > [!NOTE]  
        > [<strong>データベースの作成</strong>] ページには、スタンドアロン データベースだけが表示されます。
    
    6.  ミラー化されていたバックエンドを復元する場合は、\[**ミラー データベースの作成**\] というプロンプトが表示されるまで、引き続きウィザードの残りの指示に従います。インストールするデータベースを選択し、プロセスを完了します。
    
    7.  ウィザードの残りの指示に従います。\[**完了**\] をクリックします。
    

    > [!TIP]
    > トポロジ ビルダーを実行しなくても、<STRONG>Install-CsDatabase</STRONG> コマンドレットを使用して各データベースを作成でき、<STRONG>Install-CsMirrorDatabase</STRONG> コマンドレットを使用してミラー化を構成することができます。詳細については、Lync Server 管理シェルのドキュメントを参照してください。



5.  次の操作を実行してユーザー データを復元します。
    
    1.  ExportedUserData.zip を $Backup\\ からローカル ディレクトリにコピーします。
    
    2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。
    
    3.  ユーザー データを復元する前に Lync サービスを停止する必要があります。これを行うには、以下のように入力します。
        
            Stop-CsWindowsService
    
    4.  ユーザー データを復元するには、コマンド ラインで、次のように入力します。
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        次に例を示します。
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  以下のように入力し、Lync サービスを再起動します。
        
            Start-CsWindowsService

6.  応答グループをこのプールに展開してある場合は、応答グループの構成データを復元します。詳細については、「[応答グループの設定の復元](lync-server-2013-restoring-response-group-settings.md)」を参照してください。

7.  アーカイブ データベースまたは監視データベースを含んでいたバックエンド サーバーを復元する場合は、SQL Server Management Studio などの SQL Server ツールを使用して、アーカイブ データまたは監視データを復元します。詳細については、「[監視データまたはアーカイブ データの復元](lync-server-2013-restoring-monitoring-or-archiving-data.md)」を参照してください。

