---
title: 'Lync Server 2013: Enterprise Edition バックエンドサーバーの復元'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9aee487bb9e1a42c7a02e384101b81625482116
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a>Lync Server 2013 で Enterprise Edition バックエンドサーバーを復元する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-18_

このトピックで説明する手順は、次の2つの場合に使用します。

  - ミラー化された Enterprise Edition バックエンドサーバーのプライマリデータベースとミラーデータベースの両方が失敗します。

  - ミラーリングされていない Enterprise Edition バックエンドサーバーで障害が発生します。

ミラー化された Enterprise Edition バックエンドがあり、ミラーまたはプライマリデータベースのみに障害が発生した場合は、「ミラーリングされた[Enterprise Edition バックエンドサーバーを Lync server 2013 で](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)復元する」と「プライマリデータベースを復元する」、および「 [lync server 2013 でミラー化された Enterprise Edition バックエンドサーバーを](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)復元する」をご覧ください。

中央管理ストアに障害が発生した場合は、「 [Lync server 2013 の中央管理ストアをホスト](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)しているサーバーを復元する」を参照してください。 バックエンドサーバーに含まれていない Enterprise Edition メンバーサーバーの障害が発生した場合は、「 [Lync server 2013 で Enterprise edition のメンバーサーバーを復元](lync-server-2013-restoring-an-enterprise-edition-member-server.md)する」を参照してください。

<div>


> [!TIP]  
> 復元を開始する前に、システムのイメージコピーを取得することをお勧めします。 復元中に問題が発生した場合に備えて、このイメージをロールバックポイントとして使用できます。 オペレーティングシステムと SQL Server をインストールした後、画像コピーを取得し、証明書を復元または reenroll することができます。



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a>Enterprise Edition バックエンド サーバーを復元するには

1.  障害が発生したコンピューターと同じ完全修飾ドメイン名 (FQDN) を持つクリーンサーバーまたは新しいサーバーを起動し、オペレーティングシステムをインストールしてから、証明書を復元または reenroll します。
    
    <div>
    

    > [!NOTE]  
    > 組織で定めるサーバーの展開手順に従って、この手順を実行します。

    
    </div>

2.  RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、復元するサーバーにログオンします。

3.  SQL Server 2012 または SQL Server 2008 R2 をインストールして、インスタンス名を失敗前と同じ状態に保ちます。
    
    <div>
    

    > [!NOTE]  
    > 展開によっては、バックエンド サーバーに複数の併置されたデータベースまたは別々のデータベースが含まれる場合があります。SQL Server の権限とログインも含めて、最初にサーバーを展開したときと同じ手順で SQL Server をインストールしてください。

    
    </div>

4.  SQL Server をインストールした後、次の手順を実行します。
    
    1.  トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。
    
    2.  [**既存の展開からトポロジをダウンロードする**] をクリックし、[**OK**] をクリックします。
    
    3.  トポロジを選択し、[**保存**] をクリックします。[**はい**] をクリックして選択を確定します。
    
    4.  [ **Lync Server 2013** ] ノードを右クリックし、[**トポロジの公開**] をクリックします。
    
    5.  **トポロジの公開**ウィザードの指示に従います。 [**データベースの作成**] ページで、再作成するデータベースを選択します。
        
        <div>
        

        > [!NOTE]  
        > [<STRONG>データベースの作成</STRONG>] ページにはスタンドアロン データベースのみ表示されます。

        
        </div>
    
    6.  ミラー化されたバックエンドを復元する場合は、[**ミラーデータベースの作成**] というプロンプトが表示されるまで、ウィザードの残りの手順を続行します。 インストールするデータベースを選択し、処理を完了します。
    
    7.  ウィザードの残りの指示に従います。[**完了**] をクリックします。
    
    <div>
    

    > [!TIP]  
    > トポロジビルダーを実行する代わりに、 <STRONG>install-csmirrordatabase</STRONG>コマンド<STRONG>レットを</STRONG>使用して各データベースを作成し、コマンドレットを使用してミラーリングを構成できます。 詳細については、Lync Server 管理シェルのドキュメントを参照してください。

    
    </div>

5.  次の操作を実行してユーザー データを復元します。
    
    1.  ExportedUserData を $Backup\\からローカルディレクトリにコピーします。
    
    2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。
    
    3.  ユーザーデータを復元する前に、Lync services を停止する必要があります。 これを行うには、次のように入力します。
        
            Stop-CsWindowsService
    
    4.  ユーザー データを復元するには、コマンド ラインで、次のように入力します。
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        次に例を示します。
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  次のように入力して Lync Services を再起動します。
        
            Start-CsWindowsService

6.  このプールに応答グループを展開した場合は、応答グループ構成データを復元します。 詳細については、「 [Lync Server 2013 での応答グループの設定の復元](lync-server-2013-restoring-response-group-settings.md)」を参照してください。

7.  アーカイブ データベースまたは監視データベースを含んでいたバックエンド サーバーを復元する場合は、SQL Server Management Studio などの SQL Server ツールを使用して、アーカイブ データまたは監視データを復元します。 詳細については、「 [Lync Server 2013 での監視またはアーカイブデータの復元](lync-server-2013-restoring-monitoring-or-archiving-data.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

