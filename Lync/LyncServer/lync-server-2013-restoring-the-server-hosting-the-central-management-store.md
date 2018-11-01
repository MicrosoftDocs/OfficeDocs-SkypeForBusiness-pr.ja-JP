---
title: 中央管理ストアをホストするサーバーの復元
TOCTitle: 中央管理ストアをホストするサーバーの復元
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh202172(v=OCS.15)
ms:contentKeyID: 52056579
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 中央管理ストアをホストするサーバーの復元

 

_**トピックの最終更新日:** 2013-02-21_

Lync Server の展開には、単一の中央管理ストアが含まれます。これは、Lync Server サーバーの役割を実行する各サーバーに複製されるコピーです。このトピックでは、中央管理ストアをホストするバック エンド サーバーまたは Standard Edition サーバーの復元方法について説明します。

中央管理サーバーが配置されているプールを見つけるには、トポロジ ビルダーを開き、\[**Lync Server**\] をクリックして、**中央管理サーバー**の右側のウィンドウを調べます。

中央管理ストアをホストするバック エンド サーバーがミラー化された設定で、ミラー データベースがまだ機能している場合は、この機能しているミラーのバックアップを作成し、そのバックアップを使用して、プライマリ データベースとミラー データベースの両方で完全復元を実行することをお勧めします。ここでは、その復元手順について説明します。この手順が必要なのは、バック エンドの復元には、トポロジの変更と発行が必要だからです。この手順は、CMS をホストするプライマリ データベースが稼働している場合にのみ実行できます。また、トポロジを発行できない場合は、プライマリ データベース ロールとミラー データベース ロールを交換できないことにも注意してください。

> [!NOTE]
> 中央管理ストアをホストしないバック エンド サーバーまたは Standard Edition サーバーでエラーが発生した場合は、「<a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Enterprise Edition バックエンド サーバーの復元</a>」または「<a href="lync-server-2013-restoring-a-standard-edition-server.md">Standard Edition サーバーの復元</a>」を参照してください。中央管理ストアをホストするバック エンド サーバーがミラー化された構成で、ミラーのみでエラーが発生した場合は、「<a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">ミラー化された Enterprise Edition バック エンド サーバーの復元 - ミラー</a>」を参照してください。それ以外のサーバーでエラーが発生した場合は、「<a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Enterprise Edition メンバー サーバーの復元</a>」を参照してください。



> [!TIP]
> 復元を開始する前にシステムのイメージ コピーを取得することをお勧めします。復元中に問題が発生した場合に、そのイメージをロールバック ポイントに使用できます。このイメージ コピーをオペレーティング システムと SQL Server のインストール後に作成して、証明書を復元または再登録することもできます。



## 中央管理ストアを復元するには

1.  問題が発生したコンピューターと同じ完全修飾ドメイン名 (FQDN) を持つクリーン サーバーか新規サーバーにオペレーティング システムをインストールし、証明書を復元または再登録します。
    
    > [!NOTE]
    > 組織で定めるサーバーの展開手順に従って、この手順を実行します。


2.  RTCUniversalServerAdmins グループおよび Local Administrators グループのメンバーであるユーザー アカウントから、復元するサーバーにログオンします。

3.  Standard Edition サーバーを復元する場合は、$Backup から適切なファイル ストアをサーバー上のファイル ストアの場所にコピーすることで、ファイル ストアを復元し、フォルダーを共有します。
    

    > [!IMPORTANT]
    > 復元されたファイル ストアのパスとファイル名は、ファイルを使用するコンポーネントがそのファイルにアクセスできるように、バックアップされたファイル ストアと正確に一致する必要があります。



4.  次のどちらかの操作を行います。
    
      - Standard Edition サーバーをインストールする場合は、Lync Server インストール フォルダーまたはメディアを参照し、\\setup\\amd64\\Setup.exe にある Lync Server 展開ウィザードを起動します。展開ウィザードで、\[**最初の Standard Edition サーバーの準備**\] をクリックし、ウィザードの指示に従って中央管理ストアをインストールします。
    
      - エンタープライズ バック エンド サーバーをインストールする場合は、SQL Server 2012 または SQL Server 2008 R2 をインストールします。インスタンス名にはエラーが発生する前と同じ名前を使用します。
        
        
        > [!NOTE]  
        > 復元するサーバーと展開によっては、サーバーに複数の併置されたデータベースまたは個別のデータベースが含まれる場合があります。SQL Server の権限とログインも含めて、最初にサーバーを展開したときと同じ手順で SQL Server をインストールしてください。


5.  フロント エンド サーバーから、Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

6.  中央管理ストアを再作成します。コマンドラインで、次のように入力します。
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    例:
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  中央管理ストアに Active Directory ドメイン サービス コントロール ポイントを設定します。コマンドラインで、次のように入力します。
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    例:
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    > [!NOTE]
    > 接続ポイントを失った場合は、このコマンドレットを再実行できます。


8.  中央管理ストアのデータを $Backup からインポートします。コマンドラインで、次のように入力します。
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    例:
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  上記の手順で行った変更を有効にします。コマンドラインで、次のように入力します。
    
        Enable-CsTopology
    
    > [!NOTE]
    > トポロジを有効にすると、データベースにトポロジ ドキュメントができます。


10. CMS もホストされた Enterprise Editionバック エンド サーバーを復元する場合、または CMS のミラーを再作成する必要がある場合は、次の手順に従います。それ以外の場合は、手順 11. に進みます。
    
    次の操作を行って、スタンドアロン データベースをインストールします。
    
    1.  トポロジ ビルダーを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server トポロジ ビルダー**\] の順にクリックします。
    
    2.  \[**既存の展開からトポロジをダウンロードする**\] をクリックし、\[**OK**\] をクリックします。
    
    3.  トポロジを選択し、\[**保存**\] をクリックします。\[**はい**\] をクリックして選択を確定します。
    
    4.  \[**Lync Server 2013**\] ノードを右クリックし、\[**データベースのインストール**\] をクリックします。
    
    5.  **データベースのインストール** ウィザードの指示に従います。中央管理ストア以外のデータベースをこのサーバーに復元する場合は、\[**データベースの作成**\] ページで、再作成するデータベースを選択します。
        
        > [!NOTE]  
        > [<strong>データベースの作成</strong>] ページには、スタンドアロン データベースだけが表示されます。併置されるデータベースは、Lync Server 展開ウィザードを実行すると作成されます。
    
    6.  ミラー化されたバック エンド サーバーを復元する場合は、引き続きウィザードの残りの指示に従います。ミラー データベースの作成を求めるメッセージが表示されたら、インストールするデータベースを選択し、プロセスを完了します。
    
    7.  ウィザードの残りの指示に従います。\[**完了**\] をクリックします。
    

    > [!TIP]
    > トポロジ ビルダーを実行するのではなく、<STRONG>Install-CsDatabase</STRONG> コマンドレットを使用して、各データベースを作成できます。また、<STRONG>Install-CsMirrorDatabase</STRONG> コマンドを使用して、ミラーリングを構成できます。詳細については、「<A href="https://docs.microsoft.com/en-us/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</A>」および「<A href="https://docs.microsoft.com/en-us/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</A>」を参照してください。



11. Standard Edition サーバーを復元する場合は、Lync Server インストール フォルダーまたはメディアを参照し、\\setup\\amd64\\Setup.exe にある Lync Server 展開ウィザードを起動します。Lync Server 展開ウィザードで、次の操作を行います。
    
    1.  \[**手順 1: ローカル構成ストアのインストール**\] を実行して、ローカル構成ファイルをインストールします。
    
    2.  \[**手順 2: Lync Server コンポーネントのセットアップまたは削除**\] を実行して、Lync Server のサーバーの役割をインストールします。
    
    3.  \[**手順 3: 証明書の要求、インストール、または割り当て**\] を実行して、証明書を割り当てます。
    
    4.  \[**手順 4: サービスの開始**\] を実行して、サーバー上でサービスを開始します。
    
    展開ウィザードの実行の詳細については、展開に関するドキュメントで、復元しているサーバーの役割を参照してください。

12. 次の操作を実行してユーザー データを復元します。
    
    1.  ExportedUserData.zip を $Backup\\ からローカル ディレクトリにコピーします。
    
    2.  ユーザー データを復元する前に Lync サービスを停止する必要があります。これを行うには、以下のように入力します。
        
            Stop-CsWindowsService
    
    3.  ユーザー データを復元するには、コマンド ラインで、次のように入力します。
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        例:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  以下のように入力し、Lync サービスを再起動します。
        
            Start-CsWindowsService

13. 位置情報データを中央管理ストアに復元します。コマンドラインで、次のように入力します。
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    例:
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. このプールまたは Standard Edition サーバーに応答グループを展開していた場合は、応答グループの構成データを復元します。詳細については、「[応答グループの設定の復元](lync-server-2013-restoring-response-group-settings.md)」を参照してください。

15. アーカイブまたは監視データベースを含むバック エンド サーバーを復元する場合は、SQL Server Management Studio などの SQL Server 管理ツールを使用して、アーカイブまたは監視データを復元します。詳細については、「[監視データまたはアーカイブ データの復元](lync-server-2013-restoring-monitoring-or-archiving-data.md)」を参照してください。

