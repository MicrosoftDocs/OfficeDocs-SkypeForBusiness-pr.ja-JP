---
title: Lync Server 2013 のビデオ帯域幅の構成
TOCTitle: Lync Server 2013 のビデオ帯域幅の構成
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48271929
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のビデオ帯域幅の構成

 

_**トピックの最終更新日:** 2012-10-02_

Lync Server 2013 には、2 者間通話とマルチパーティ会議用のビデオを管理するための複数の設定があります。Lync Server 2013 を展開するとき、既定の設定が組織にとって適切なものかどうかを検証し、必要に応じて変更する必要があります。

このセクションで説明するパラメーターは、2 者間通話とマルチパーティ会議の両方に適用されます。これらの設定を表示または変更するときは、次のコマンドレットの 1 つを使用します。

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

会議ポリシーの次の設定を確認します。

  - **VideoBitRateKb**   この設定では、ユーザーによって送信されるビデオに使用する最大ビデオ ビット レートをキロビット/秒 (kbps) で指定します。既定値は 50000 kbps です。有効な値は 0 から 50000 です。
    
    この設定は、メイン ビデオと パノラマ ビデオに別々に適用されます。
    
    たとえば 2000 kbps を指定すると、Lync Server はメイン ビデオ ストリームに関して 2000 kbps、パノラマ ビデオ ストリームに関して 2000 kbps を送信できます。
    
    > [!NOTE]
    > Lync 2013 エンドポイントの最大ビデオ ネットワーク帯域幅は、メイン ビデオでは 8000 kbps、パノラマ ビデオでは 2500 kbps です。こらの最大値に達するのは、複数のビデオが送受信される場合に限ります。詳細については、「<a href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Lync Server 2013 でのメディア トラフィックのネットワーク帯域幅の要件</a>」の「メディア トラフィック ネットワークの使用」を参照してください。このセクションでは、サポートされているすべての解像度に関して、最大かつ一般的なビデオ ストリーム帯域幅を示します。


  - **TotalReceiveVideoBitRateKb**   これは Lync Server 2013 の新しい設定で、クライアントが受信するすべてのビデオ ストリームに対して許容される最大ビットレート (キロビット/秒) を指定します。つまり、クライアントが受信できる全ビデオ ストリーム (パノラマ ビデオ ストリームは除く) の合計値を指定します。たとえば 1500 kbps を指定すると、クライアントは複数のビデオ ストリームまたは単一のビデオ ストリームから構成される最大 1500 kbps のビデオを受信できます。この設定は、Lync Server 2013 クライアントにのみ適用されます。
    
    **TotalReceiveVideoBitRateKb** の既定値は 50000 kbps です。ギャラリー ビューの **EnableMultiviewJoin** 設定が True に設定されている場合、**TotalReceiveVideoBitRateKb** を 420 kbps 未満に設定しないようにします。ギャラリー ビューの **EnableMultiviewJoin** 設定が False に設定されている場合、**TotalReceiveVideoBitRateKb** を 100 kbps 未満に設定しないようにします。**EnableMultiviewJoin** が True に設定されており、値を 420 kbps 未満に設定した場合は、既定では、値はしきい値に設定されます。このしきい値によって、ユーザー エクスペリエンスの低下の原因となる予想外の構成ミスを防ぐことができます。
    
    > [!NOTE]
    > <strong>EnableMultiviewJoin</strong> 設定の詳細については、「<a href="lync-server-2013-configuring-gallery-view.md">ギャラリー ビューの構成</a>」を参照してください。


  - **MaxVideoConferencingResolution**   このパラメーターは、Lync Server 2013 会議の Lync Server 2013 クライアントで現在使用されていません。Lync Server 2013 会議では、このセクションで前述したビット レート コントロールを使用します。この設定は、Lync Server 2013 会議に参加する従来のクライアントで引き続き使用されます。このパラメーターによって、Lync Server 2013 に所属するユーザーによって組織された会議の従来のクライアントに対して許可される最大解像度が決まります。つまり、従来のクライアントは、以前のバージョンの Lync Server または Office Communications Server に所属しているのと同様に扱われます。

ユーザーに適用される会議ポリシー設定のほかに、メディア構成設定を評価します。これらの設定を表示または変更するときは、次のコマンドレットの 1 つを使用します。

  - **Get-CsMediaConfiguration**

  - **Set- CsMediaConfiguration**

  - **New- CsMediaConfiguration**

次の設定を確認します。

  - **MaxVideoRateAllowed**   このプールごとの設定では、クライアント エンドポイントでのビデオ信号転送の最高速度を指定します。これは、以前のバージョンの Lync Server クライアントにのみ適用されます。
    
    > [!NOTE]
    > Lync Server 2013 クライアントはこの設定を無視し、代わりに、会議ポリシーの TotalReceiveVideoBitRateKb 設定を使用します。
    
    既定値は HD720P です。有効な値は、HD720p15M、VGA600K、および CIF250K です。
    
    例: 1500 kbps を指定すると、プール内の従来のクライアントすべてが、2 者間会議またはマルチパーティ会議で 1500 kbps までのビデオを受信できます。

以下に、Lync Server 管理シェルを使用してこのセクションで説明した設定を変更する手順の例を示します。

## ビデオ設定の会議ポリシーを変更するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  コマンド ラインで次のコマンドレットを実行して、会議ポリシーを編集します。
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

## 従来のクライアント向けのメディア構成を変更するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  コマンド ラインで次のコマンドレットを実行して、メディア構成を編集します。
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

