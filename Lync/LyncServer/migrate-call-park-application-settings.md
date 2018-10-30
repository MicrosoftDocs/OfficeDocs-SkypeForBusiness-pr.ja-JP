---
title: コール パーク アプリケーション設定の移行
TOCTitle: コール パーク アプリケーション設定の移行
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49886876
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# コール パーク アプリケーション設定の移行

 

_**トピックの最終更新日:** 2012-10-19_

Lync Server 2010 から Lync Server 2013 へのコール パーク アプリケーションの移行では、Lync Server 2010 でアップロードされていた独自の保留音ファイルを Lync Server 2013 プールにプロビジョニングし、サービス レベルの設定を復元し、コール パーク オービットの対象をすべて Lync Server 2013 プールに再設定するなどの作業を行います。カスタマイズされた保留音ファイルが Lync Server 2010 プールで構成されていた場合は、それらのファイルを新しい Lync Server 2013 プールにコピーする必要があります。さらに、コール パークのカスタマイズされた保留音ファイルを Lync Server 2010 から別の保存先にバックアップし、コール パーク用にアップロードされていたカスタマイズされた保留音ファイルのバックアップ コピーを別途保管しておくこともお勧めします。コール パーク アプリケーションのカスタマイズされた保留音ファイルは、プールのファイル ストアに格納されています。Lync Server 2010 プールのファイル ストアから Lync Server 2013 のファイル ストアにオーディオ ファイルをコピーするには、**Xcopy** コマンドを次のパラメーターと共に使用します。

    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>

   &nbsp;

    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 

カスタマイズされたオーディオ ファイルがすべて Lync Server 2013 のファイル ストアにコピーされたら、Lync Server 2013 プールのコール パーク アプリケーションの設定を構成し、Lync Server 2010 プールに関連付けられているコール パーク オービットの範囲を Lync Server 2013 プールに割り当て直す必要があります。

コール パーク アプリケーションの設定には、ピックアップ タイムアウトのしきい値、保留音の有効化と無効化、通話ピックアップの最大回数、タイムアウト要求などがあります。コール パーク アプリケーションの設定を管理するには、Lync Server 管理シェルを使用して **Set-CsCpsConfiguration** コマンドレットを実行する必要があります。Lync Server コントロール パネルを使用してコール パーク アプリケーションの設定を管理することはできません。

**Call Park Service の設定を再構成する**

1.  Lync Server 2013 フロントエンド サーバーから Lync Server 管理シェル を開きます。

2.  コマンドラインで、次のように入力します。
    
    > [!NOTE]
    > Lync Server 2013 コール パーク アプリケーションの設定が既存の Lync Server 2010 の設定と同一である場合は、この手順の実行を省略できます。コール パーク アプリケーションの設定が Lync Server 2013 環境と Lync Server 2010 環境とで異なる場合は、次のコマンドレットをテンプレートとして使用して変更を更新してください。
    
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"

コール パーク オービットの範囲をすべて Lync Server 2010 プールから Lync Server 2013 プールに割り当て直すには、Lync Server コントロール パネルまたは Lync Server 管理シェルを使用します。

**Lync Server コントロール パネルを使用してコール パーク オービットの範囲をすべて割り当て直す**

1.  Lync Server コントロール パネルを開きます。

2.  左側のウィンドウで、\[ **音声機能**\] を選択します。

3.  \[ **コール パーク**\] タブを選択します。

4.  Lync Server 2010 プールに割り当てられているコール パーク オービットの範囲ごとに、\[ **接続先サーバーの FQDN**\] の設定を編集し、コール パーク要求を処理する Lync Server 2013 プールを選択します。

5.  \[ **コミット**\] を選択して変更を保存します。

**Lync Server 管理シェルを使用してコール パーク オービットの範囲をすべて割り当て直す**

1.  Lync Server 管理シェルを開きます。

2.  コマンドラインで、次のように入力します。
    
        Get-CsCallParkOrbit
    
    このコマンドレットを実行すると、展開内のコール パーク オービットの範囲がすべて表示されます。**CallParkServiceId** および **CallParkServerFqdn** パラメーターが Lync Server 2010 プールに設定されているコール パーク オービットをすべて割り当て直す必要があります。
    
    Lync Server 2010 コール パーク オービットの範囲を Lync Server 2013 プールに割り当て直すには、コマンド ラインで次のように入力します。
    
        Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"

コール パーク オービットの範囲をすべて Lync Server 2013 プールに割り当て直すと、コール パーク アプリケーションの移行処理は完了し、それ以降は Lync Server 2013 プールがすべてのコール パーク要求を処理するようになります。

