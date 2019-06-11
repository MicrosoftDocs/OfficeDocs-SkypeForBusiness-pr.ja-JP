---
title: 'Lync Server 2013: 中央管理ストアをホストしているサーバーの復元'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95696c682e7acfba32e4f9a2bfd71ba988f22243
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a>Lync Server 2013 での中央管理ストアをホストしているサーバーの復元

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

Lync Server の展開には、1つの一元管理ストアがあります。これらのコピーは、Lync Server server の役割を実行している各サーバーにレプリケートされます。 このトピックでは、中央管理ストアをホストするバックエンドサーバーまたは Standard Edition サーバーを復元する方法について説明します。

中央管理サーバーが配置されているプールを見つけるには、トポロジビルダーを開き、[ **Lync Server**] をクリックして、右側のウィンドウの [サーバーの**全体管理**] を確認します。

中央管理ストアをホストしているバックエンドサーバーがミラーリングされたセットアップであり、ミラーデータベースがまだ機能している場合は、このまま機能しているミラーのバックアップを作成して、プライマリデータベースと、以下の復元手順に従って、このバックアップを使用してデータベースをミラー化します。 バックエンドの復元ではトポロジを変更して発行する必要があります。これは、CMS をホストしているプライマリデータベースが動作している場合にのみ実行できます。 また、トポロジを公開できない場合は、プライマリデータベースロールとミラーデータベースロールを交換できないことに注意してください。

<div>


> [!NOTE]  
> 中央管理ストアをホストしていないバックエンドサーバーまたは Standard Edition サーバーで障害が発生した場合は、「 <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Lync server 2013 で Enterprise Edition バックエンドサーバーを復元する</A>」または「 <A href="lync-server-2013-restoring-a-standard-edition-server.md">lync Server 2013 で standard Edition サーバーを復元</A>する」を参照してください。 中央管理ストアをホストするバックエンドサーバーがミラーリングされた構成であり、ミラーに失敗した場合にのみ、「 <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Lync Server 2013-mirror でのミラーリングされた Enterprise Edition バックエンドサーバーの復元</A>」を参照してください。 他のサーバーにエラーが発生した場合は、「 <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Lync server 2013 で Enterprise Edition のメンバーサーバーを復元する</A>」を参照してください。



</div>

<div>


> [!TIP]  
> 復元を開始する前に、システムのイメージコピーを取得することをお勧めします。 復元中に問題が発生した場合に備えて、この画像をロールバックポイントとして使うことができます。 オペレーティングシステムと SQL Server をインストールした後に画像のコピーを取得し、証明書を復元または reenroll することができます。



</div>

<div>

## <a name="to-restore-the-central-management-store"></a>中央管理ストアを復元するには

1.  障害のあるコンピューターと同じ完全修飾ドメイン名 (FQDN) を持つクリーンで、または新しいサーバーから始め、オペレーティングシステムをインストールして、証明書を復元または reenroll します。
    
    <div>
    

    > [!NOTE]  
    > 組織のサーバー展開手順に従って、この手順を実行します。

    
    </div>

2.  RTCUniversalServerAdmins グループとローカルの管理者グループのメンバーであるユーザーアカウントから、復元しているサーバーにログオンします。

3.  Standard Edition サーバーを復元する場合は、適切なファイルストアを $Backup からサーバー上のファイルストアの場所にコピーして、ファイルストアを復元し、そのフォルダーを共有します。
    
    <div>
    

    > [!IMPORTANT]  
    > 復元されたファイルストアのパスとファイル名は、ファイルを使用するコンポーネントがアクセスできるように、バックアップされたファイルストアとまったく同じである必要があります。

    
    </div>

4.  次のいずれかの操作を行います。
    
      - Standard Edition サーバーをインストールする場合は、Lync Server のインストールフォルダーまたはメディアを参照し、セットアップ\\\\Amd64\\Setup.exe で [lync server 展開ウィザード] を起動します。 展開ウィザードで、[**最初の Standard Edition サーバーの準備**] をクリックし、ウィザードに従って中央管理ストアをインストールします。
    
      - エンタープライズバックエンドサーバーをインストールする場合は、SQL Server 2012 または SQL Server 2008 R2 をインストールして、インスタンス名がエラーの前と同じになるようにします。
        
        <div>
        

        > [!NOTE]  
        > 復元しているサーバーによって、展開時にサーバーに複数の併置されたデータベースや個別のデータベースが含まれている場合があります。 SQL Server の権限とログインなど、サーバーの展開に最初に使用した SQL Server をインストールするには、同じ手順に従います。

        
        </div>

5.  フロントエンドサーバーから、Lync Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

6.  中央管理ストアを再作成します。 コマンドラインで、次のように入力します。
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    例:
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  中央管理ストアの Active Directory ドメインサービスの制御点を設定します。 コマンドラインで、次のように入力します。
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    例:
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > 接続ポイントを失った場合は、このコマンドレットを再実行できます。

    
    </div>

8.  $Backup から中央管理ストアのデータをインポートします。 コマンドラインで、次のように入力します。
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    例:
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  直前に行った変更を有効にします。 コマンド ラインで次を入力します。
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > トポロジを有効にすると、データベース内でトポロジドキュメントを見つけることができます。

    
    </div>

10. CMS をホストしている Enterprise Edition バックエンドサーバーを復元している場合、または CMS のミラーを再作成する必要がある場合は、この手順を実行します。 それ以外の場合は、手順11に進んでください。
    
    次の手順に従って、スタンドアロンデータベースをインストールします。
    
    1.  トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。
    
    2.  [**既存の展開からトポロジをダウンロード**] をクリックし、[ **OK**] をクリックします。
    
    3.  トポロジを選択し、[**保存**] をクリックします。 選択内容を確認するには、[**はい]** をクリックします。
    
    4.  [ **Lync Server 2013** ] ノードを右クリックし、[**データベースのインストール**] をクリックします。
    
    5.  データベースの**インストール**ウィザードを実行します。 このサーバーの中央管理ストア以外のデータベースを復元する場合は、[データベースの**作成**] ページで、再作成するデータベースを選びます。
        
        <div>
        

        > [!NOTE]  
        > <STRONG>データベースの作成</STRONG>ページには、スタンドアロンデータベースのみが表示されます。 併置されたデータベースは、Lync Server 展開ウィザードを実行したときに作成されます。

        
        </div>
    
    6.  ミラーバックエンドサーバーを復元する場合は、「ミラーデータベースの作成」のプロンプトが表示されるまで、ウィザードの残りの指示に従って操作を続けます。 インストールするデータベースを選択し、プロセスを完了します。
    
    7.  ウィザードの残りの手順に従って、[**完了**] をクリックします。
    
    <div>
    

    > [!TIP]  
    > トポロジビルダーを実行する代わりに、 <STRONG>CsMirrorDatabase</STRONG>コマンド<STRONG></STRONG>レットを使用して各データベースを作成し、このコマンドレットを使ってミラーリングを構成することができます。 詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">CsDatabase</A>と<A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">CsMirrorDatabase</A>をインストールする」を参照してください。

    
    </div>

11. Standard Edition サーバーを復元する場合は、Lync Server のインストールフォルダーまたはメディアを参照し、セットアップ\\\\Amd64\\Setup.exe で [lync server 展開ウィザード] を起動します。 Lync Server 展開ウィザードを使用して、次の操作を行います。
    
    1.  **手順 1: ローカル構成ストアをインストール**して、ローカル構成ファイルをインストールします。
    
    2.  **手順 2: lync server のコンポーネントをセットアップまたは削除**して lync server サーバーの役割をインストールする
    
    3.  手順 3: 証明書を割り当てるために**証明書を要求、インストール、または割り当て**ます。
    
    4.  **手順 4: サービスを開始**して、サーバー上のサービスを開始します。
    
    展開ウィザードの実行の詳細については、復元するサーバーの役割の展開ドキュメントを参照してください。

12. ユーザーデータを復元するには、次の操作を行います。
    
    1.  $Backup\\からローカルディレクトリに ExportedUserData をコピーします。
    
    2.  ユーザーデータを復元する前に、Lync サービスを停止する必要があります。 そのためには、次のように入力します。
        
            Stop-CsWindowsService
    
    3.  ユーザーデータを復元するには、コマンドラインで次のように入力します。
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        次に例を示します。
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  次のように入力して Lync サービスを再起動します。
        
            Start-CsWindowsService

13. 位置情報データを中央管理ストアに復元します。 コマンドラインで、次のように入力します。
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    例:
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. このプールまたは Standard Edition サーバーに応答グループを展開した場合は、応答グループの構成データを復元します。 詳細については、「 [Lync Server 2013 での応答グループの設定の復元](lync-server-2013-restoring-response-group-settings.md)」を参照してください。

15. アーカイブデータベースや監視データベースを含むバックエンドサーバーを復元する場合は、sql Server Management Studio などの SQL Server 管理ツールを使用して、アーカイブまたは監視データを復元します。 詳細について[は、「Lync Server 2013 で監視またはアーカイブデータを復元](lync-server-2013-restoring-monitoring-or-archiving-data.md)する」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

