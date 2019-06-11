---
title: 'Lync Server 2013: ビデオ帯域幅の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ee374be85bc9427135ff89f3eb75acefd1cf5a8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a>Lync Server 2013 でのビデオ帯域幅の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-02_

Lync Server 2013 には、2パーティーの通話とマルチパーティの会議のビデオを管理するためのいくつかの設定が含まれています。 Lync Server 2013 を展開するときは、既定の設定が組織に適しているかどうかを評価し、必要に応じて変更します。

このセクションで説明するパラメーターは、2人の通話とマルチパーティの会議の両方に適用されます。 これらの設定を表示または変更するには、次のいずれかのコマンドレットを使用します。

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

会議ポリシーで、次の設定を確認します。

  - **VideoBitRateKb**   この設定では、ユーザーが送信したビデオに使用されるビデオの最大ビットレート (kbps) を指定します。 既定値は 5万 kbps です。 有効な値は 0 ~ 5万です。
    
    この設定は、メインビデオとパノラマビデオに個別に適用されます。
    
    例: 2000 kbps を指定した場合、Lync Server は、パノラマビデオストリームについて、メインビデオストリームと 2000 kbps の 2000 kbps を送信できます。
    
    <div>
    

    > [!NOTE]  
    > Lync 2013 エンドポイントの最大ビデオネットワーク帯域幅は、メインビデオでは 8000 kbps、パノラマビデオでは 2500 kbps です。 これらの最大値は、複数のビデオを受信または送信した場合にのみ達成されます。 詳細については、「 <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Lync Server 2013 のメディアトラフィックのネットワーク帯域幅の要件</A>」の「メディアトラフィックのネットワーク使用量」セクションを参照してください。 このセクションでは、サポートされているすべての解像度について、最大と標準的なビデオストリームの帯域幅を一覧表示します。

    
    </div>

  - **** この設定は、Lync Server 2013 の新しい設定であり、クライアントが受信するすべてのビデオストリームに対して許可される最大ビットレート (1 秒あたりのビット数) を指定します。    つまり、クライアントが受け取ることができる、パノラマビデオストリームを除くすべてのビデオストリームの合計が指定されます。 たとえば、1500 kbps を指定した場合、クライアントは最大 1500 kbps のビデオを受信できます。これは、複数のビデオストリームまたは1つのビデオストリームで構成されている可能性があります。 この設定は、Lync Server 2013 クライアントにのみ適用されます。
    
    **TotalReceiveVideoBitRateKb**の既定値は 5万 kbps です。 ギャラリービューの**EnableMultiviewJoin**設定が True に設定されている場合、 **TotalReceiveVideoBitRateKb**は 420 kbps 未満に設定しないでください。 ギャラリービューの**EnableMultiviewJoin**設定が False に設定されている場合、 **TotalReceiveVideoBitRateKb**は 100 kbps 未満に設定しないでください。 **EnableMultiviewJoin**が True に設定されていて、420 kbps 未満の値を設定した場合、値は既定のしきい値に設定されます。 このしきい値は、ユーザーエクスペリエンスが低下する可能性がある偶発的な誤りを防ぐのに役立ちます。
    
    <div>
    

    > [!NOTE]  
    > <STRONG>EnableMultiviewJoin</STRONG>の設定の詳細については、「 <A href="lync-server-2013-configuring-gallery-view.md">Lync Server 2013 でギャラリービューを構成する</A>」を参照してください。

    
    </div>

  - **MaxVideoConferencingResolution**   このパラメーターは、lync server 2013 会議の lync server 2013 クライアントでは使われなくなりました。 Lync Server 2013 会議では、このセクションで既に説明したビットレートコントロールを使用します。 この設定は、Lync Server 2013 会議に参加している従来のクライアントでも使用されます。 このパラメーターは、Lync Server 2013 を使っているユーザーが開催する、会議内のレガシクライアントで許可される最大解像度を決定します。 つまり、従来のクライアントは、以前のバージョンの Lync Server または Office Communications Server と同じように扱われます。

ユーザーに適用される会議ポリシーの設定に加えて、メディア構成の設定を評価します。 これらの設定を表示または変更するには、次のいずれかのコマンドレットを使用します。

  - **Get-CsMediaConfiguration**

  - **Set-CsMediaConfiguration**

  - **新規-CsMediaConfiguration**

次の設定を確認します。

  - ****   [プールごとの MaxVideoRateAllowed] 設定では、クライアントエンドポイントでビデオ信号を転送する最大速度を指定します。 これは、以前のバージョンの Lync Server クライアントにのみ適用されます。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 クライアントでは、この設定は無視され、会議ポリシーの TotalReceiveVideoBitRateKb 設定が使用されます。

    
    </div>
    
    既定値はあることです。 有効な値は、HD720p15M、VGA600K、および CIF250K です。
    
    例: 1500 kbps を指定した場合、プール内のすべてのレガシークライアントは、2パーティまたはマルチパーティの会議で最大 1500 kbps のビデオを受信できます。

次の手順では、このセクションで説明するように、Lync Server 管理シェルを使用して設定を変更する例を示します。

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a>ビデオ設定の会議ポリシーを変更するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  コマンドラインで、次のコマンドレットを実行して会議ポリシーを編集します。
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a>レガシクライアントのメディア構成を変更するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  コマンドラインで次のコマンドレットを実行して、メディアの構成を編集します。
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

