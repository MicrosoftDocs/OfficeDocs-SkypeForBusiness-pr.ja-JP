---
title: 'Lync Server 2013: Enterprise Edition バックエンドサーバーの復元'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e0121ee654846bcb60acc6da6847995b967a880
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a>Lync Server 2013 で Enterprise Edition バックエンドサーバーを復元する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-18_

このトピックで説明する手順は、次の2つの場合に使用します。

  - ミラー化された Enterprise Edition バックエンドサーバーのプライマリデータベースとミラーデータベースの両方が失敗します。

  - ミラーリングされていない Enterprise Edition バックエンドサーバーで障害が発生します。

ミラー化された Enterprise Edition バックエンドがあり、ミラーまたはプライマリデータベースのみが失敗する場合は、「 [Lync Server 2013 でのミラーリングされた Enterprise Edition バックエンドサーバーの復元](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)」を参照してください。プライマリデータベースの復元とミラー化された[ミラーの復元Lync Server 2013 の Enterprise Edition バックエンドサーバー-](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)ミラーを復元するためのミラー。

サーバーの全体管理ストアでエラーが発生した場合は、「 [Lync server 2013 で中央管理ストアをホストしているサーバーの復元](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)」を参照してください。 バックエンドサーバーではない Enterprise Edition のメンバーサーバーに障害が発生した場合は、「 [Lync server 2013 で Enterprise edition のメンバーサーバーを復元](lync-server-2013-restoring-an-enterprise-edition-member-server.md)する」を参照してください。

<div>


> [!TIP]  
> 復元を開始する前に、システムのイメージコピーを取得することをお勧めします。 復元中に問題が発生した場合に備えて、この画像をロールバックポイントとして使うことができます。 オペレーティングシステムと SQL Server をインストールした後に画像のコピーを取得し、証明書を復元または reenroll することができます。



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a>Enterprise Edition バックエンドサーバーを復元するには

1.  障害のあるコンピューターと同じ完全修飾ドメイン名 (FQDN) を持つクリーンで、または新しいサーバーから始め、オペレーティングシステムをインストールして、証明書を復元または reenroll します。
    
    <div>
    

    > [!NOTE]  
    > 組織のサーバー展開手順に従って、この手順を実行します。

    
    </div>

2.  RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、復元しているサーバーにログオンします。

3.  SQL Server 2012 または SQL Server 2008 R2 をインストールして、インスタンス名がエラーの前と同じになるようにします。
    
    <div>
    

    > [!NOTE]  
    > 展開によっては、バックエンドサーバーに複数の併置されたデータベースまたは個別のデータベースが含まれている場合があります。 SQL Server の権限とログインなど、サーバーの展開に最初に使用した SQL Server をインストールするには、同じ手順に従います。

    
    </div>

4.  SQL Server をインストールしたら、次の手順を実行します。
    
    1.  トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。
    
    2.  [**既存の展開からトポロジをダウンロード**] をクリックし、[ **OK**] をクリックします。
    
    3.  トポロジを選択し、[**保存**] をクリックします。 選択内容を確認するには、[**はい]** をクリックします。
    
    4.  [ **Lync Server 2013** ] ノードを右クリックし、[**トポロジの公開**] をクリックします。
    
    5.  [**トポロジの発行**] ウィザードを実行します。 [**データベースの作成**] ページで、再作成するデータベースを選択します。
        
        <div>
        

        > [!NOTE]  
        > <STRONG>データベースの作成</STRONG>ページには、スタンドアロンデータベースのみが表示されます。

        
        </div>
    
    6.  ミラー化されたバックエンドを復元する場合は、「**ミラーデータベースの作成**」というプロンプトが表示されるまで、ウィザードの残りの指示に従って操作を続けます。 インストールするデータベースを選択し、プロセスを完了します。
    
    7.  ウィザードの残りの手順に従って、[**完了**] をクリックします。
    
    <div>
    

    > [!TIP]  
    > トポロジビルダーを実行する代わりに、 <STRONG>CsMirrorDatabase</STRONG>コマンド<STRONG></STRONG>レットを使用して各データベースを作成し、このコマンドレットを使ってミラーリングを構成することができます。 詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。

    
    </div>

5.  ユーザーデータを復元するには、次の操作を行います。
    
    1.  $Backup\\からローカルディレクトリに ExportedUserData をコピーします。
    
    2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。
    
    3.  ユーザーデータを復元する前に、Lync サービスを停止する必要があります。 そのためには、次のように入力します。
        
            Stop-CsWindowsService
    
    4.  ユーザーデータを復元するには、コマンドラインで次のように入力します。
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        次に例を示します。
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  次のように入力して Lync サービスを再起動します。
        
            Start-CsWindowsService

6.  このプールで応答グループを展開した場合は、応答グループの構成データを復元します。 詳細については、「 [Lync Server 2013 での応答グループの設定の復元](lync-server-2013-restoring-response-group-settings.md)」を参照してください。

7.  アーカイブまたは監視データベースが含まれているバックエンドサーバーを復元する場合は、SQL Server Management Studio などの SQL Server ツールを使用して、アーカイブまたは監視データを復元します。 詳細について[は、「Lync Server 2013 で監視またはアーカイブデータを復元](lync-server-2013-restoring-monitoring-or-archiving-data.md)する」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

