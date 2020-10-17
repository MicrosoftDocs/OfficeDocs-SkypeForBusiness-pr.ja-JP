---
title: 'Lync Server 2013: ビデオ帯域幅の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3e1c4b0dab165c43e873c49039896f0af80f7f3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516984"
---
# <a name="configuring-video-bandwidth-in-lync-server-2013"></a>Lync Server 2013 でのビデオ帯域幅の構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-02_

Lync Server 2013 には、2者間通話とマルチパーティ会議のビデオを管理するための設定がいくつか含まれています。 Lync Server 2013 を展開する場合は、既定の設定が組織に適しているかどうかを評価し、必要に応じて変更する必要があります。

このセクションで説明するパラメーターは、2 者間通話とマルチパーティ会議の両方に適用されます。これらの設定を表示または変更するときは、次のコマンドレットの 1 つを使用します。

  - **Get-CsConferencingPolicy**

  - **Get-csconferencingpolicy**

  - **Get-csconferencingpolicy**

会議ポリシーの次の設定を確認します。

  - **VideoBitRateKb**    この設定では、ユーザーによって送信されるビデオに対して使用されるビデオの最大ビットレート (キロビット/秒 (kbps)) を指定します。 既定値は 50000 kbps です。 有効な値は 0 から 50000 です。
    
    この設定は、メイン ビデオと	パノラマ ビデオに別々に適用されます。
    
    例: 2000 kbps を指定すると、Lync Server は、メインビデオストリームに 2000 kbps を送信し、パノラマビデオストリームについては 2000 kbps を送信できます。
    
    <div>
    

    > [!NOTE]  
    > Lync 2013 エンドポイントの最大ビデオネットワーク帯域幅は、メインビデオの場合は 8000 kbps、パノラマビデオの場合は 2500 kbps です。 こらの最大値に達するのは、複数のビデオが送受信される場合に限ります。 詳細については、「 <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Lync Server 2013 のメディアトラフィックのネットワーク帯域幅要件</A>」の「メディアトラフィックネットワークの使用率」セクションを参照してください。 このセクションでは、サポートされているすべての解像度に関して、最大かつ一般的なビデオ ストリーム帯域幅を示します。

    
    </div>

  - **TotalReceiveVideoBitRateKb**    この設定は、Lync Server 2013 で新しく追加されたもので、クライアントが受信するすべてのビデオストリームの最大許容ビットレート (1 秒あたりのキロビット) を指定します。 つまり、クライアントが受信できる全ビデオ ストリーム (パノラマ ビデオ ストリームは除く) の合計値を指定します。 たとえば 1500 kbps を指定すると、クライアントは複数のビデオ ストリームまたは単一のビデオ ストリームから構成される最大 1500 kbps のビデオを受信できます。 この設定は、Lync Server 2013 クライアントにのみ適用されます。
    
    **TotalReceiveVideoBitRateKb** の既定値は 50000 kbps です。ギャラリー ビューの **EnableMultiviewJoin** 設定が True に設定されている場合、**TotalReceiveVideoBitRateKb** を 420 kbps 未満に設定しないようにします。ギャラリー ビューの **EnableMultiviewJoin** 設定が False に設定されている場合、**TotalReceiveVideoBitRateKb** を 100 kbps 未満に設定しないようにします。**EnableMultiviewJoin** が True に設定されており、値を 420 kbps 未満に設定した場合は、既定では、値はしきい値に設定されます。このしきい値によって、ユーザー エクスペリエンスの低下の原因となる予想外の構成ミスを防ぐことができます。
    
    <div>
    

    > [!NOTE]  
    > <STRONG>EnableMultiviewJoin</STRONG>の設定の詳細については、「 <A href="lync-server-2013-configuring-gallery-view.md">Lync Server 2013 でのギャラリービューの構成</A>」を参照してください。

    
    </div>

  - **MaxVideoConferencingResolution**    このパラメーターは、Lync server 2013 会議の Lync Server 2013 クライアントでは使用されなくなりました。 Lync Server 2013 会議では、このセクションで前述したビットレートコントロールを使用します。 この設定は、Lync Server 2013 会議に参加しているレガシクライアントでも使用されます。 このパラメーターは、Lync Server 2013 に所属するユーザーが開催する、電話会議のレガシクライアントに許可される最大解像度を指定します。 つまり、従来のクライアントは、以前のバージョンの Lync Server または Office Communications Server と同じように処理されます。

ユーザーに適用される会議ポリシー設定のほかに、メディア構成設定を評価します。これらの設定を表示または変更するときは、次のコマンドレットの 1 つを使用します。

  - **Get-csmediaconfiguration**

  - **Get-csmediaconfiguration**

  - **Get-csmediaconfiguration**

次の設定を確認します。

  - **MaxVideoRateAllowed**    このプールごとの設定では、クライアントエンドポイントでビデオ信号を転送する最大速度を指定します。 これは、以前のバージョンの Lync Server クライアントにのみ適用されます。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 クライアントはこの設定を無視し、代わりに会議ポリシーの TotalReceiveVideoBitRateKb 設定を使用します。

    
    </div>
    
    既定値は HD720P です。有効な値は、HD720p15M、VGA600K、および CIF250K です。
    
    例: 1500 kbps を指定すると、プール内の従来のクライアントすべてが、2 者間会議またはマルチパーティ会議で 1500 kbps までのビデオを受信できます。

次の手順では、このセクションで説明する設定を Lync Server 管理シェルを使用して変更する例を示します。

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a>ビデオ設定の会議ポリシーを変更するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  コマンド ラインで次のコマンドレットを実行して、会議ポリシーを編集します。
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a>従来のクライアント向けのメディア構成を変更するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  コマンド ラインで次のコマンドレットを実行して、メディア構成を編集します。
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

