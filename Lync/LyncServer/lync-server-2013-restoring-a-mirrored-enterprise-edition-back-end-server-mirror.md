---
title: ミラー化された Enterprise Edition バック エンド サーバーの復元 - ミラー
TOCTitle: ミラー化された Enterprise Edition バック エンド サーバーの復元 - ミラー
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ945626(v=OCS.15)
ms:contentKeyID: 52056588
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ミラー化された Enterprise Edition バック エンド サーバーの復元 - ミラー

 

_**トピックの最終更新日:** 2013-02-19_

ミラー化された構成に Enterprise Edition バックエンド サーバーがあり、ミラーのみで障害が発生した場合は、このセクションで説明する手順に従ってください。プライマリ データベースとミラーの両方で障害が発生した場合は、「[Enterprise Edition バックエンド サーバーの復元](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)」を参照してください。プライマリのみで障害が発生した場合は、「[ミラー化された Enterprise Edition バックエンド サーバーの復元 - プライマリ](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)」を参照してください。中央管理ストアをホストするデータベースで障害が発生した場合は、「[中央管理ストアをホストするサーバーの復元](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)」を参照してください。バックエンド サーバー以外の Enterprise Edition メンバー サーバーで障害が発生した場合は、「[Enterprise Edition メンバー サーバーの復元](lync-server-2013-restoring-an-enterprise-edition-member-server.md)」を参照してください。

復元を開始する前にシステムのイメージ コピーを取得することをお勧めします。復元中に問題が発生した場合に、そのイメージをロールバック ポイントに使用できます。このイメージ コピーをオペレーティング システムと SQL Server のインストール後に作成して、証明書を復元または再登録することもできます。

## Enterprise Edition バックエンド サーバーのミラー データベースを復元するには

1.  RTCUniversalServerAdmins グループのメンバーであるユーザー アカウントから、フロント エンド サーバーにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  ミラーリングをアンインストールします。最初に、次のコマンドレットを入力します。
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    たとえば、次のようになります。
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    このサーバーのすべてのデータベースの種類に対してこの処理を行います。

4.  問題が発生したコンピューターと同じ完全修飾ドメイン名 (FQDN) (DB1.contoso.com) を持つクリーン サーバーまたは新しいサーバーを作成し、オペレーティング システムをインストールして、証明書を復元または再登録します。このサーバーは新しいミラーとして機能します。

5.  RTCUniversalServerAdmins グループのメンバーであるユーザー アカウントから、新しいサーバーにログオンします。

6.  インスタンス名を障害が発生する前の名前と同じにして、SQL Server 2012 または SQL Server 2008 R2 をインストールします。

7.  RTCUniversalServerAdmins グループのメンバーであるユーザー アカウントから、フロント エンド サーバーにログオンします。

8.  トポロジ ビルダーを使用して、ミラー データベースをインストールします。次の操作を実行します。
    
      - トポロジ ビルダーを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server トポロジ ビルダー**\] の順にクリックします。
    
      - \[Lync Server 2013\] ノードを右クリックし、\[**トポロジ**\]、\[**データベースのインストール**\] の順にクリックします。
    
      - **データベースのインストール** ウィザードの指示に従います。\[**データベースの作成**\] ページで、再作成するデータベースを選択します。
    
      - ウィザードの指示に従います。**ミラー データベースの作成**を求めるメッセージが表示されたら、インストールするデータベースを選択し、プロセスを完了します。
        

        > [!TIP]
        > トポロジ ビルダーを実行しなくても、<STRONG>Install-CsMirrorDatabase</STRONG> コマンドレットを使えば、ミラーリングを構成できます。詳細については、Lync Server 管理シェルのドキュメントを参照してください。


