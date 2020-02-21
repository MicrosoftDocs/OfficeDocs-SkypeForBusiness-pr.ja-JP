---
title: 'Lync Server 2013: 中央管理ストアをホストしているサーバーを復元する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 772646b8122e228aa43818aa5fe7fe2fb6689366
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201363"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a>Lync Server 2013 で中央管理ストアをホストしているサーバーを復元する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

Lync Server の展開には、中央管理ストアが1つあり、そのコピーが、Lync Server サーバーの役割を実行する各サーバーにレプリケートされます。 このトピックでは、中央管理ストアをホストするバックエンドサーバーまたは Standard Edition サーバーを復元する方法について説明します。

中央管理サーバーが配置されているプールを検索するには、トポロジビルダーを開き、[ **Lync Server**] をクリックして、右側のウィンドウで [**中央管理サーバー**] を探します。

中央管理ストアをホストするバックエンドサーバーがミラー化された設定で、ミラーデータベースがまだ機能している場合は、このまま動作しているミラーのバックアップを作成し、プライマリデータベースとに対して完全な復元を実行することをお勧めします。次の復元手順に従って、このバックアップを使用してデータベースをミラー化します。 これは、バックエンドの復元でトポロジを変更および発行する必要があるためです。これは、CMS をホストしているプライマリデータベースが稼働している場合にのみ行うことができます。 また、トポロジを公開できない場合は、プライマリデータベースとミラーデータベースの役割を交換できないことにも注意してください。

<div>


> [!NOTE]  
> 中央管理ストアをホストしていないバックエンドサーバーまたは Standard Edition サーバーが失敗した場合は、「 <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Lync server 2013 で Enterprise Edition バックエンドサーバーを復元</A>する」または「 <A href="lync-server-2013-restoring-a-standard-edition-server.md">lync Server 2013 で standard Edition サーバーを復元</A>する」を参照してください。 中央管理ストアをホストするバックエンドサーバーがミラーリングされた構成であり、ミラーのみが失敗した場合は、「 <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Lync Server 2013-mirror でのミラーリングされた Enterprise Edition バックエンドサーバーの復元</A>」を参照してください。 他のサーバーで障害が発生した場合は、「 <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Lync server 2013 で Enterprise Edition のメンバーサーバーを復元する</A>」を参照してください。



</div>

<div>


> [!TIP]  
> 復元を開始する前に、システムのイメージコピーを取得することをお勧めします。 復元中に問題が発生した場合に備えて、このイメージをロールバックポイントとして使用できます。 オペレーティングシステムと SQL Server をインストールした後、画像コピーを取得し、証明書を復元または reenroll することができます。



</div>

<div>

## <a name="to-restore-the-central-management-store"></a>中央管理ストアを復元するには

1.  障害が発生したコンピューターと同じ完全修飾ドメイン名 (FQDN) を持つクリーンサーバーまたは新しいサーバーを起動し、オペレーティングシステムをインストールしてから、証明書を復元または reenroll します。
    
    <div>
    

    > [!NOTE]  
    > 組織で定めるサーバーの展開手順に従って、この手順を実行します。

    
    </div>

2.  RTCUniversalServerAdmins グループとローカルの Administrators グループのメンバーであるユーザーアカウントから、復元するサーバーにログオンします。

3.  Standard Edition サーバーを復元する場合は、適切なファイルストアを $Backup からサーバー上のファイルストアの場所にコピーしてファイルストアを復元し、フォルダーを共有します。
    
    <div>
    

    > [!IMPORTANT]  
    > 復元されたファイルストアのパスおよびファイル名は、ファイルを使用するコンポーネントがアクセスできるように、バックアップされたファイルストアと正確に一致する必要があります。

    
    </div>

4.  次のいずれかの操作を行います。
    
      - Standard Edition サーバーをインストールする場合は、Lync Server のインストールフォルダーまたはメディアを参照してから、setup \\\\Amd64\\setup.exe で lync server 展開ウィザードを起動します。 展開ウィザードで、[**最初の Standard Edition サーバーの準備**] をクリックし、ウィザードの指示に従って中央管理ストアをインストールします。
    
      - エンタープライズバックエンドサーバーをインストールする場合は、SQL Server 2012 または SQL Server 2008 R2 をインストールして、インスタンス名を失敗前と同じ状態に保ちます。
        
        <div>
        

        > [!NOTE]  
        > 復元するサーバーと展開によっては、サーバーに複数の併置されたデータベースまたは別のデータベースが含まれる場合があります。 サーバーの展開で最初に使用した SQL Server (SQL Server のアクセス許可とログインを含む) をインストールしたときと同じ手順に従います。

        
        </div>

5.  フロントエンドサーバーから、Lync Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

6.  中央管理ストアを再作成します。 コマンドラインで、次のように入力します。
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    次に例を示します。
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  中央管理ストアの Active Directory ドメインサービスコントロールポイントを設定します。 コマンドラインで、次のように入力します。
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    次に例を示します。
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > 接続ポイントを失った場合は、このコマンドレットを再実行できます。

    
    </div>

8.  中央管理ストアのデータを $Backup からインポートします。 コマンドラインで、次のように入力します。
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    次に例を示します。
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  上記の手順で行った変更を有効にします。コマンドラインで、次のように入力します。
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > トポロジを有効にすると、データベースにトポロジ ドキュメントができます。

    
    </div>

10. CMS もホストしている Enterprise Edition バックエンドサーバーを復元する場合、または CMS のミラーを再作成する必要がある場合は、この手順を実行します。 それ以外の場合は、手順11に進みます。
    
    次の手順を実行して、スタンドアロンデータベースをインストールします。
    
    1.  トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。
    
    2.  [**既存の展開からトポロジをダウンロードする**] をクリックし、[**OK**] をクリックします。
    
    3.  トポロジを選択し、[**保存**] をクリックします。[**はい**] をクリックして選択を確定します。
    
    4.  [ **Lync Server 2013** ] ノードを右クリックし、[**データベースのインストール**] をクリックします。
    
    5.  [**データベースのインストール**] ウィザードに従います。 このサーバー上の中央管理ストア以外のデータベースを復元する場合は、[**データベースの作成**] ページで、再作成するデータベースを選択します。
        
        <div>
        

        > [!NOTE]  
        > [<STRONG>データベースの作成</STRONG>] ページにはスタンドアロン データベースのみ表示されます。 Lync Server 展開ウィザードを実行すると、併置されたデータベースが作成されます。

        
        </div>
    
    6.  ミラー化されたバックエンドサーバーを復元する場合は、ミラーデータベースの作成を求めるメッセージが表示されるまで、ウィザードの残りの手順を続行します。 インストールするデータベースを選択し、処理を完了します。
    
    7.  ウィザードの残りの指示に従います。[**完了**] をクリックします。
    
    <div>
    

    > [!TIP]  
    > トポロジビルダーを実行する代わりに、 <STRONG>install-csmirrordatabase</STRONG>コマンド<STRONG>レットを</STRONG>使用して各データベースを作成し、コマンドレットを使用してミラーリングを構成できます。 詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">install-CsDatabase</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">install-install-csmirrordatabase</A>」を参照してください。

    
    </div>

11. Standard Edition サーバーを復元する場合は、Lync Server のインストールフォルダーまたはメディアを参照して、setup \\\\Amd64\\setup.exe で lync server 展開ウィザードを起動します。 Lync Server 展開ウィザードを使用して、次の操作を行います。
    
    1.  [**ステップ 1: ローカル構成ストアのインストール**] を実行して、ローカル構成ファイルをインストールします。
    
    2.  [**ステップ 2: lync Server コンポーネントのセットアップまたは削除**を実行して、lync server のサーバーの役割をインストールする」を実行します。
    
    3.  [**ステップ 3: 証明書の要求、インストール、または割り当て**] を実行して、証明書を割り当てます。
    
    4.  [**ステップ 4: サービスの開始**] を実行して、サーバー上でサービスを開始します。
    
    展開ウィザードの実行の詳細については、「展開」のドキュメントの「復元」を参照してください。

12. 次の操作を実行してユーザー データを復元します。
    
    1.  ExportedUserData を $Backup\\からローカルディレクトリにコピーします。
    
    2.  ユーザーデータを復元する前に、Lync services を停止する必要があります。 これを行うには、次のように入力します。
        
            Stop-CsWindowsService
    
    3.  ユーザー データを復元するには、コマンド ラインで、次のように入力します。
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        例:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  次のように入力して Lync services を再起動します。
        
            Start-CsWindowsService

13. 場所情報データを中央管理ストアに復元します。 コマンドラインで、次のように入力します。
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    次に例を示します。
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. このプールまたは Standard Edition サーバーに応答グループを展開した場合は、応答グループ構成データを復元します。 詳細については、「 [Lync Server 2013 での応答グループの設定の復元](lync-server-2013-restoring-response-group-settings.md)」を参照してください。

15. アーカイブデータベースまたは監視データベースを含むバックエンドサーバーを復元する場合は、sql server management Studio などの SQL Server 管理ツールを使用して、アーカイブデータまたは監視データを復元します。 詳細については、「 [Lync Server 2013 での監視またはアーカイブデータの復元](lync-server-2013-restoring-monitoring-or-archiving-data.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

