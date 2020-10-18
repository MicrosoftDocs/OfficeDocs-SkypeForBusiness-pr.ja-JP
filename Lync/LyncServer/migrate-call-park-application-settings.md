---
title: コール パーク アプリケーション設定の移行
description: コールパークアプリケーションの設定を移行します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da90ca4ee4dd53451c29b8c39861dc76a17ca3c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579413"
---
# <a name="migrate-call-park-application-settings"></a>コール パーク アプリケーション設定の移行

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-19_

Lync server 2010 から Lync Server 2013 へのコールパークアプリケーションの移行には、lync server 2010 にアップロードされたカスタム音楽保留ファイルを含む Lync Server 2013 プールのプロビジョニング、サービスレベル設定の復元、および Lync Server 2013 プールへのコールパークオービットの retargeting が含まれます。 カスタマイズした保留中のファイルが Lync Server 2010 プールに構成されている場合は、これらのファイルを新しい Lync Server 2013 プールにコピーする必要があります。 また、コールパーク用にアップロードされたカスタマイズされた保留音ファイルのバックアップコピーを別に保持するために、コールパークのカスタマイズされた保留音のファイルを Lync Server 2010 から別の送信先にバックアップすることをお勧めします。 コール パーク アプリケーションのカスタマイズされた保留音ファイルは、プールのファイル ストアに格納されています。 Lync Server 2010 プールファイルストアから Lync Server 2013 ファイルストアにオーディオファイルをコピーするには、 **Xcopy** コマンドを次のパラメーターと共に使用します。

   ```console
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```console
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

カスタマイズしたすべてのオーディオファイルが Lync Server 2013 ファイルストアにコピーされたら、lync Server 2013 プールのコールパークアプリケーションの設定を構成し、lync server の2010プールに関連付けられているコールパークオービットの範囲を Lync Server の2013プールに再割り当てする必要があります。

コール パーク アプリケーションの設定には、ピックアップ タイムアウトのしきい値、保留音の有効化と無効化、通話ピックアップの最大回数、タイムアウト要求などがあります。 **New-cscpsconfiguration**コマンドレットを実行するには、Lync Server 管理シェルを使用してコールパークアプリケーションの設定を管理する必要があります。 Lync Server コントロールパネルを使用してコールパークアプリケーションの設定を管理することはできません。

**Call Park Service の設定を再構成する**

1.  Lync Server 2013 フロントエンドサーバーから、Lync Server 管理シェルを開きます。

2.  コマンドラインで、次のように入力します。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 コールパークアプリケーション設定が従来の Lync Server 2010 設定と同一の場合は、この手順の実行をスキップできます。 通話パークアプリケーションの設定が Lync Server 2013 および Lync Server 2010 環境と異なる場合は、次のコマンドレットをテンプレートとして使用して、それらの変更を更新します。

    
    </div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>"-CallPickupTimeoutThreshold" "- <LS2010 CPS TimeSpan> enablemusiconhold" "- <LS2010 CPS value> maxcallpickupattempts" <LS2010 CPS pickup attempts> "-ontimeouturi" <LS2010 CPS timeout URI> " ```

すべてのコールパークオービット範囲を Lync server 2010 プールから Lync Server 2013 プールに再割り当てするには、Lync Server コントロールパネルまたは Lync Server 管理シェルのいずれかを使用できます。

**Lync Server コントロール パネルを使用してコール パーク オービットの範囲をすべて割り当て直す**

1.  [Lync Server コントロール パネル] を開きます。

2.  左側のウィンドウで、[**音声機能**] を選択します。

3.  [**コール パーク**] タブを選択します。

4.  Lync Server 2010 プールに割り当てられている各コールパークオービット範囲に対して、[ **宛先サーバーの FQDN** ] 設定を編集し、コールパーク要求を処理する lync Server 2013 プールを選択します。

5.  [**コミット**] を選択して変更を保存します。

**Lync Server 管理シェルを使用してコール パーク オービットの範囲をすべて割り当て直す**

1.  Lync Server 管理シェルを開きます。

2.  コマンド ラインで、次のように入力します。
    ```powershell
    Get-CsCallParkOrbit
    ```
    
    このコマンドレットを実行すると、展開内のコール パーク オービットの範囲がすべて表示されます。 **CallParkServiceId**および**Callparkserverfqdn**パラメーターが Lync Server 2010 プールとして設定されているすべてのコールパークオービットを再割り当てする必要があります。
    
    Lync Server 2010 のコールパークオービット範囲を Lync Server 2013 プールに再割り当てするには、コマンドラインで、次のように入力します。
    
    ```powershell
    Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"
    ```

すべてのコールパークオービット範囲を Lync Server 2013 プールに再割り当てした後、コールパークアプリケーションの移行プロセスが完了し、Lync Server 2013 プールが、今後のコールパーク要求をすべて処理するようになります。

</div>

<span> </span>

</div>

</div>

</div>

