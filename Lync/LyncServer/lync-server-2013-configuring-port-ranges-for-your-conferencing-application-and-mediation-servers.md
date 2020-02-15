---
title: 'Lync Server 2013: 会議、アプリケーション、および仲介サーバーのポート範囲の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Conferencing, Application, and Mediation servers
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
ms.date: 05/01/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ecd505990b9a060c3b669700ea9192dc1ad6b84c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a>Lync Server 2013 での会議、アプリケーション、および仲介サーバー用のポート範囲の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-04-30_

サービスの品質を実装するには、電話会議、アプリケーション、および仲介サーバー上で音声、ビデオ、アプリケーション共有に対して同一のポート範囲を構成する必要があります。さらに、これらのポート範囲は、どのような方法でも重複してはなりません。 簡単な例を使用するために、電話会議サーバー上のビデオに 1万 ~ 10999 のポートを使用するとします。 そのため、アプリケーションおよび仲介サーバーでは、ビデオ用にポート 1万 ~ 10999 も予約する必要があります。 指定しない場合、QoS は予想どおりに機能しません。

同様に、ビデオ用にポート 1万 ~ 10999 を予約していて、オーディオ用にポート 10500 ~ 11999 を予約しているとします。 これにより、ポート範囲が重複するため、サービスの品質の問題が発生する可能性があります。 QoS では、各モダリティに固有のポートセットが必要です。ポート 1万 ~ 10999 をビデオに使用する場合は、別の範囲 (たとえば、11000 ~ 11999 for audio) を使用する必要があります。

既定では、オーディオおよびビデオのポート範囲は Microsoft Lync Server 2013 では重複していません。ただし、アプリケーション共有に割り当てられているポート範囲は、オーディオポートとビデオポート範囲の両方と重なっています。 (つまり、これらの範囲が一意ではないことを意味します)。Lync Server 2013 管理シェルから次の3つのコマンドを実行することによって、会議、アプリケーション、および仲介サーバーの既存のポート範囲を確認できます。

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> 上記のコマンドでわかるように、各ポートの種類–オーディオ、ビデオ、およびアプリケーション共有–には、ポートの開始とポート数という2つの個別のプロパティ値が割り当てられます。 ポートの開始は、そのモダリティで使用される最初のポートを示します。たとえば、オーディオポートの start が5万の場合は、オーディオトラフィックに使用される最初のポートはポート5万であることを意味します。 オーディオポート数が 2 (有効な値ではありませんが、ここでは説明のために使用されています) の場合は、2つのポートのみがオーディオに割り当てられることを意味します。 最初のポートがポート5万で、合計2つのポートがある場合、2番目のポートはポート50001でなければなりません (ポート範囲は連続している必要があります)。 その結果、音声のポート範囲は 5万 ~ 50001 のポートになります。<BR>また、アプリケーションサーバーと仲介サーバーがオーディオ用に QoS をサポートしていることにも注意してください。アプリケーションサーバーまたは仲介サーバーでは、ビデオまたはアプリケーション共有のポートを変更する必要はありません。



</div>

上記の3つのコマンドを実行すると、Lync Server 2013 の既定のポート値は次のように構成されていることがわかります。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>プロパティ</th>
<th>Conferencing Server</th>
<th>アプリケーション サーバー</th>
<th>仲介サーバー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AudioPortStart</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
</tr>
<tr class="even">
<td><p>AudioPortCount</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>VideoPortStart</p></td>
<td><p>57501</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>VideoPortCount</p></td>
<td><p>8034</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationSharingPortStart</p></td>
<td><p>49152</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>ApplicationSharingPortCount</p></td>
<td><p>16383</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


前述したように、QoS 用に Lync Server ポートを構成する場合は、会議、アプリケーション、および仲介サーバー間でのオーディオポート設定が同一であることを確認する必要があります。and, 2) のポート範囲が重なっていません。 上記の表をよく見ると、3つのサーバーの種類でポート範囲が同一であることがわかります。 たとえば、開始オーディオポートは、各サーバーの種類のポート49152に設定され、各サーバーのオーディオ用に予約されているポートの合計数も8348になります。 ただし、ポートの範囲が重複しています。オーディオポートはポート49152で開始されますが、アプリケーション共有のためにポートが設定されています。 サービスの品質を最大限に利用するためには、一意のポート範囲を使用するようにアプリケーション共有を再構成する必要があります。 たとえば、ポート40803で開始し、8348ポートを使用するようにアプリケーション共有を構成することができます。 (8348 ポートがあるのはなぜですか? これら 8348 40803 の値を一緒に追加すると、アプリケーション共有でポート40803をポート49150が使用されることを意味します。 オーディオポートはポート49152まで開始されないため、重複するポート範囲がなくなります。

アプリケーション共有の新しいポート範囲を選択したら、CsConferencingServer コマンドレットを使用して変更できます。 このようなサーバーはアプリケーション共有トラフィックを処理しないので、アプリケーションサーバーまたは仲介サーバーでこの変更を行う必要はありません。 オーディオトラフィックに使用するポートを再割り当てする場合にのみ、これらのサーバーのポート値を変更する必要があります。

単一の会議サーバーでアプリケーション共有のポート値を変更するには、Lync Server 管理シェルで次のようなコマンドを実行します。

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

すべての会議サーバーでこれらの変更を行う場合は、代わりに次のコマンドを実行します。

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

ポート設定を変更した後は、変更によって影響を受ける各サービスを停止してから再起動する必要があります。

会議サーバー、アプリケーションサーバー、および仲介サーバーが同一のポート範囲を共有していることは必須ではありません。実際に必要なのは、すべてのサーバーに固有のポート範囲を設定することだけです。 ただし、すべてのサーバーで同じポートセットを使用すると、通常、管理が簡単になります。

</div>

<span> </span>

</div>

</div>

</div>

