---
title: 'Lync Server 2013: Standard Edition サーバーの復元'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Standard Edition server
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202190(v=OCS.15)
ms:contentKeyID: 51541519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bff6ad3eec632aaf6f076e0df92d7b8df3ac67e0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a>Lync Server 2013 での Standard Edition サーバーの復元

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

中央管理ストアをホストしていない Standard Edition サーバーで障害が発生した場合は、このセクションの手順を実行します。 中央管理ストアに障害が発生した場合は、「 [Lync server 2013 の中央管理ストアをホスト](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)しているサーバーを復元する」を参照してください。

<div>


> [!TIP]  
> 復元を開始する前に、システムのイメージコピーを取得することをお勧めします。 復元中に問題が発生した場合に備えて、このイメージをロールバックポイントとして使用できます。 オペレーティングシステムと SQL Server をインストールしてから、証明書を復元または再登録した後で、イメージコピーを取得することもできます。



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a>Standard Edition サーバーを復元するには

1.  障害が発生したコンピューターと同じ完全修飾ドメイン名 (FQDN) を持つクリーンサーバーまたは新しいサーバーを起動し、オペレーティングシステムをインストールしてから、証明書を復元または reenroll します。
    
    <div>
    

    > [!NOTE]  
    > 組織で定めるサーバーの展開手順に従って、この手順を実行します。

    
    </div>

2.  RTCUniversalServerAdmins グループとローカルの Administrators グループのメンバーであるユーザーアカウントから、復元するサーバーにログオンします。

3.  適切なファイルストアを $Backup からサーバー上のファイルストアの場所にコピーし、フォルダーを共有することによって、ファイルストアを復元します。
    
    <div>
    

    > [!IMPORTANT]  
    > 復元されたファイルストアのパスおよびファイル名は、ファイルを使用するコンポーネントがアクセスできるように、バックアップされたファイルストアと正確に一致する必要があります。

    
    </div>

4.  トポロジビルダーを実行します。
    
    1.  トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。
    
    2.  [**既存の展開からトポロジをダウンロードする**] をクリックし、[**OK**] をクリックします。
    
    3.  トポロジを選択し、[**保存**] をクリックします。[**はい**] をクリックして選択を確定します。

5.  Lync Server インストールフォルダーまたはメディアを参照して、セットアップ\\\\Amd64\\setup.exe で lync server 展開ウィザードを起動します。 Lync Server 展開ウィザードを使用して、次の操作を行います。
    
    1.  [**ステップ 1: ローカル構成ストアのインストール**] を実行して、ローカル構成ファイルをインストールします。
    
    2.  [**ステップ 2: lync Server コンポーネントのセットアップまたは削除**を実行して、lync server のサーバーの役割をインストールする」を実行します。
    
    3.  [**ステップ 3: 証明書の要求、インストール、または割り当て**] を実行して、証明書を割り当てます。
    
    4.  [**ステップ 4: サービスの開始**] を実行して、サーバー上でサービスを開始します。
    
    展開ウィザードの実行の詳細については、展開に関するドキュメントで復元しているサーバーの役割を参照してください。

6.  次の操作を実行してユーザー データを復元します。
    
    1.  ExportedUserData を $Backup\\からローカルディレクトリにコピーします。
    
    2.  ユーザーデータを復元する前に、Lync services を停止する必要があります。 これを行うには、次のように入力します。
        
            Stop-CsWindowsService
    
    3.  ユーザー データを復元するには、コマンド ラインで、次のように入力します。
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        次に例を示します。
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  次のように入力して Lync services を再起動します。
        
            Start-CsWindowsService

7.  この Standard Edition サーバーで応答グループを展開した場合は、応答グループ構成データを復元します。 詳細については、「 [Lync Server 2013 での応答グループの設定の復元](lync-server-2013-restoring-response-group-settings.md)」を参照してください。

8.  この Standard Edition サーバーで常設チャットを展開した場合は、常設チャットデータベース (mgc) を復元します。
    
    SQL Server バックアップを使用して常設チャットデータベースをバックアップした場合は、SQL Server の復元手順を使用して復元します。
    
    Export-cspersistentchatdata コマンドレットを使用してバックアップを作成した場合は、Export-cspersistentchatdata を使用してそれを復元します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

