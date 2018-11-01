---
title: ミラー化された Enterprise Edition バックエンド サーバーの復元 - プライマリ
TOCTitle: ミラー化された Enterprise Edition バックエンド サーバーの復元 - プライマリ
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ945648(v=OCS.15)
ms:contentKeyID: 52056692
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ミラー化された Enterprise Edition バックエンド サーバーの復元 - プライマリ

 

_**トピックの最終更新日:** 2013-02-17_

ミラー化された構成に Enterprise Edition バックエンド サーバーがあり、プライマリ データベースのみで障害が発生した場合は、このセクションで説明する手順に従ってください。プライマリ データベースとミラーの両方で障害が発生した場合は、「[Enterprise Edition バックエンド サーバーの復元](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)」を参照してください。ミラーのみで障害が発生した場合は、「[ミラー化された Enterprise Edition バック エンド サーバーの復元 - ミラー](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)」を参照してください。中央管理ストアをホストするデータベースで障害が発生した場合は、「[中央管理ストアをホストするサーバーの復元](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)」を参照してください。バックエンド サーバー以外の Enterprise Edition メンバー サーバーで障害が発生した場合は、「[Enterprise Edition メンバー サーバーの復元](lync-server-2013-restoring-an-enterprise-edition-member-server.md)」を参照してください。

復元を開始する前にシステムのイメージ コピーを取得することをお勧めします。復元中に問題が発生した場合に、そのイメージをロールバック ポイントに使用できます。このイメージ コピーをオペレーティング システムと SQL Server のインストール後に作成して、証明書を復元または再登録することもできます。

このトピックの例では、プライマリ データベースに BE1.contoso.com という完全修飾ドメイン名 (FQDN) があり、ミラー データベースに BE2.contoso.com という FQDN があります。

## Enterprise Edition バックエンド サーバーのプライマリ データベースを復元するには

1.  RTCUniversalServerAdmins グループのメンバーであるユーザー アカウントから、フロント エンド サーバーにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  構成済みのすべてのデータベースを強制的にミラーにフェールオーバーします。このサーバーで構成したデータベースの種類ごとに、次のコマンドレットを入力します。
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    たとえば、次のようになります。
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    

    > [!WARNING]
    > ミラーリング監視を伴う同期されたミラーリングを使用するようにバックエンド データベースを構成している場合、フェールオーバーは自動で行われます。



4.  フェールオーバーの完了後に、以下を実行します。
    
      - トポロジ ビルダーを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server トポロジ ビルダー**\] の順にクリックします。
    
      - バックエンド サーバーでミラーリングを無効にします。これを行うには、\[**Enterprise Edition フロントエンド プール**\] でプールを右クリックし、\[**プロパティの編集**\] を選択します。\[**全般**\] タブの \[**関連付け**\] で、\[**SQL Server ストア ミラーリングの有効化**\] チェック ボックスをオフにします。必要に応じて、アーカイブおよび監視にも同様のことを行います。\[**OK**\] をクリックします。
    
      - \[Lync Server 2013\] ノードを右クリックし、\[**トポロジ**\]、\[**公開**\] の順にクリックします。
    
      - 機能しているバックエンド (BE2.contoso.com) を選択して新しい SQL ストアにします。これには、\[**Enterprise Edition フロントエンド プール**\] でプールを右クリックし、\[**プロパティの編集**\] を選択します。\[**全般**\] タブの \[**関連付け**］で、\[**SQL Server ストア**\] フィールドに、機能しているバックエンドの FQDN (この例では、BE2.contoso.com) を入力します。
    
      - \[Lync Server 2013\] ノードを右クリックし、\[**トポロジ**\]、\[**公開**\] の順にクリックします。
    
      - サービスを再起動して、各サーバーが新しいトポロジを読み込めるようにします。Lync Server 管理シェルから、このプールに所属するフロントエンド サーバーごとに次のコマンドレットを実行します。
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  ミラーリングをアンインストールします。Lync Server 管理シェルから次のコマンドレットを実行します。
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    たとえば、次のようになります。
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    このサーバーのすべてのデータベースの種類に対してこの処理を行います。

6.  障害が発生したコンピューターと同じ FQDN (この例では DB1.contoso.com) を持つクリーン サーバーか新しいサーバーを作成し、オペレーティング システムをインストールして、証明書を復元または再登録します。このサーバーは新しいミラーとして機能します。

7.  RTCUniversalServerAdmins グループのメンバーであるユーザー アカウントから、新しいサーバーにログオンします。

8.  インスタンス名を障害が発生する前の名前と同じにして、SQL Server 2012 または SQL Server 2008 R2 をインストールします。

9.  RTCUniversalServerAdmins グループのメンバーであるユーザー アカウントから、フロント エンド サーバーにログオンします。

10. トポロジ ビルダーを使用して、ミラー DB をインストールします。次の手順を実行します。
    
      - トポロジ ビルダーを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server トポロジ ビルダー**\] の順にクリックします。
    
      - バックエンド サーバーでミラーリングを有効にします。これを行うには、\[**Enterprise Edition フロントエンド プール**\] でプールを右クリックし、\[**プロパティの編集**\] を選択します。\[**全般**\] タブの \[**関連付け**\] で、\[**SQL Server ストア ミラーリングの有効化**\] チェック ボックスをオンにします。必要に応じて、アーカイブおよび監視にも同様のことを行います。
        
        次に \[**ミラー SQL Server ストア**\] フィールドに、新しいサーバーの FQDN (この例では BE1.contoso.com) を入力します。次に \[**OK**\] をクリックします。
    
      - \[Lync Server 2013\] ノードを右クリックし、\[**トポロジ**\]、\[**データベースのインストール**\] の順にクリックします。
    
      - **データベースのインストール** ウィザードの指示に従います。\[**データベースの作成**\] ページで、再作成するデータベースを選択します。
    
      - \[**ミラー データベースの作成**\] プロンプトが表示されるまで、ウィザードの指示に従います。インストールするデータベースを選択し、プロセスを完了します。

