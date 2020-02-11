---
title: コール パーク アプリケーション設定の移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee1afd2e53bd29571818b9194fe77d3d350386f1
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-call-park-application-settings"></a>コール パーク アプリケーション設定の移行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-19_

Lync Server 2010 から Lync Server 2013 へのコールパークアプリケーションの移行には、lync server 2013 プールのプロビジョニングが含まれています。このファイルには、Lync Server 2010 でアップロードされたすべてのカスタム音楽が含まれています。また、サービスレベルの設定と retargeting を復元します。すべてのコールパークが Lync Server 2013 プールに orbits ます。 カスタマイズした音楽の保留中のファイルが Lync Server 2010 プールで構成されている場合は、これらのファイルを新しい Lync Server 2013 プールにコピーする必要があります。 さらに、通話パークしたカスタマイズされた音楽の保留中のファイルを Lync Server 2010 から別の場所にバックアップすることをお勧めします。これは、コールパーク用にアップロードされたカスタマイズした音楽の保存ファイルの個別のバックアップコピーを保持するためです。 コールパークアプリケーション用にカスタマイズされた音楽保留のファイルは、プールのファイルストアに保存されます。 Lync Server 2010 プールファイルストアから Lync Server 2013 ファイルストアにオーディオファイルをコピーするには、次のパラメーターを使用して**Xcopy**コマンドを使用します。

   ```console
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```console
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

カスタマイズしたオーディオファイルがすべて Lync Server 2013 ファイルストアにコピーされている場合は、lync Server 2013 プールのコールパークアプリケーション設定を構成する必要があります。また、Lync Server 2010 プールに関連付けられているコールパーク範囲は、再割り当てする必要があります。Lync Server 2013 プール。

コールパークアプリケーションの設定には、ピックアップタイムアウトしきい値、保留中の音楽を有効または無効にする、最大通話ピックアップ試行回数、タイムアウト要求が含まれます。 **CsCpsConfiguration**コマンドレットを実行するには、Lync Server 管理シェルを使用して、コールパークアプリケーションの設定を管理する必要があります。 Lync Server コントロールパネルを使用して、[コールパーク] のアプリケーション設定を管理することはできません。

**コールパークサービス設定を再構成する**

1.  Lync Server 2013 フロントエンドサーバーから、Lync Server 管理シェルを開きます。

2.  コマンドラインで、次のように入力します。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 Call パークのアプリケーション設定が従来の Lync Server の2010設定と同じである場合は、この手順の実行をスキップできます。 会議の設定が Lync Server 2013 および Lync Server 2010 環境で異なる場合は、次のコマンドレットをテンプレートとして使用して、それらの変更を更新します。

    
    </div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>"-Callpup<LS2010 CPS TimeSpan>Uptimeoutthreshold" "-enablemusiconhold<LS2010 CPS value>" "-maxcallピック upattempts"<LS2010 CPS pickup attempts>"-ontimeouturi"<LS2010 CPS timeout URI>"```

すべてのコールパークの範囲を Lync server 2010 プールから Lync Server 2013 プールに再割り当てするには、Lync Server コントロールパネルまたは Lync server 管理シェルを使用できます。

**Lync Server コントロールパネルを使用してすべてのコールパークの範囲を再割り当てする**

1.  [Lync Server コントロール パネル] を開きます。

2.  左側のウィンドウで、[**音声機能**] を選択します。

3.  [ **Call パーク**] タブを選択します。

4.  Lync Server 2010 プールに割り当てられている各通話パークの範囲は、[**宛先サーバーの FQDN** ] の設定を編集し、コールパーク要求を処理する lync server 2013 プールを選択します。

5.  [**コミット**] を選んで変更を保存します。

**Lync Server 管理シェルを使用してすべてのコールパーク範囲を再割り当てする**

1.  Lync Server 管理シェルを開きます。

2.  コマンドラインで、次のように入力します。
    ```powershell
    Get-CsCallParkOrbit
    ```
    
    このコマンドレットは、展開内のすべてのコールパーク範囲の範囲を一覧表示します。 Lync Server 2010 プールとして**CallParkServiceId**と**Callparkserverfqdn**パラメーターが設定されているすべての Call パーク orbits は、再割り当てする必要があります。
    
    Lync Server 2010 Call パークの範囲を Lync Server 2013 プールに再割り当てするには、コマンドラインで次のように入力します。
    
    ```powershell
    Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"
    ```

すべてのコールパークの範囲を Lync Server 2013 プールに再割り当てすると、コールパークアプリケーションの移行プロセスが完了し、Lync Server 2013 プールは、今後のすべてのコールパーク要求を処理します。

</div>

<span> </span>

</div>

</div>

</div>

