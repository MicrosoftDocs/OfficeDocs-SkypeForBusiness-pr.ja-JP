---
title: 'Lync Server 2013: 会議、アプリケーション、および仲介サーバーのポート範囲を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring port ranges for your Conferencing, Application, and Mediation servers
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
ms.date: 05/01/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5402da56fa646c6ae6e2247baa70a5ef03b851cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a>Lync Server 2013 での、会議、アプリケーション、および仲介サーバー向けのポート範囲の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2015-04-30_

サービスの品質を実現するには、会議、アプリケーション、および仲介サーバー上で音声、ビデオ、およびアプリケーション共有用に同一のポート範囲を構成する必要があります。さらに、これらのポート範囲は、何らかの方法でオーバーラップすることはできません。 簡単な例を使用するには、電話会議サーバー上のビデオに 1万 ~ 10999 のポートを使用しているとします。 つまり、アプリケーションや仲介サーバー上のビデオ用に、1万 ~ 10999 のポートを予約する必要があります。 そうしないと、QoS は期待どおりに動作しません。

同様に、1万 ~ 10999 のビデオ用にポートを予約していて、オーディオ用にポート10500から11999を予約したとします。 これにより、ポートの範囲が重複するため、サービスの品質に関する問題が発生する可能性があります。 QoS では、各モダリティに固有のポートセットが必要です。ビデオ用に 1万 ~ 10999 のポートを使用している場合は、別の範囲を使用する必要があります (たとえば、11000から11999を使用してください)。

既定では、オーディオとビデオのポート範囲は Microsoft Lync Server 2013 では重複しません。ただし、アプリケーション共有に割り当てられているポート範囲は、オーディオポート範囲とビデオポート範囲の両方と重複しています。 (これにより、これらの範囲のいずれも一意ではないことを意味します)。Lync Server 2013 管理シェル内から次の3つのコマンドを実行して、会議、アプリケーション、および仲介サーバーの既存のポート範囲を確認できます。

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> 上に示したように、各ポートの種類 (オーディオ、ビデオ、およびアプリケーションの共有) には、ポートの開始とポート数という2つの個別のプロパティ値が割り当てられています。 ポート start は、そのモダリティで使用される最初のポートを示します。たとえば、オーディオポートの start が5万に等しい場合、オーディオトラフィックに使われる最初のポートがポート5万であることを意味します。 オーディオポート数が 2 (有効な値ではありませんが、ここでは説明のために使用されます) である場合、オーディオには2つのポートしか割り当てられないことを意味します。 第1のポートがポート5万であり、合計2つのポートがある場合は、2番目のポートがポート 50001 (ポート範囲は連続している必要があります) であることを意味します。 その結果、オーディオのポート範囲は、5万 ~ 50001 のポートになります。<BR>また、アプリケーションサーバーと仲介サーバーは、オーディオの場合にのみ QoS をサポートしていることに注意してください。アプリケーションサーバーまたは仲介サーバーで、ビデオまたはアプリケーションの共有ポートを変更する必要はありません。



</div>

上記の3つのコマンドを実行すると、Lync Server 2013 の既定のポート値が次のように構成されていることがわかります。


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
<th>会議サーバー</th>
<th>アプリケーションサーバー</th>
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


前に説明したように、QoS のために Lync Server のポートを構成する場合は、お客様の会議、アプリケーション、および仲介サーバーで、オーディオポートの設定が同じであることを確認する必要があります。and、2) ポート範囲は重なりません。 上記の表をよく見ると、3種類のサーバー間でポート範囲が同じであることがわかります。 たとえば、[開始オーディオ] ポートは各サーバーの種類で [port 49152] に設定されています。また、各サーバーのオーディオ用に予約されているポートの合計数も8348と同じです。 ただし、ポートの範囲が重複しています。オーディオポートはポート49152から始まりますが、アプリケーション共有用にポートが設定されています。 サービスの品質を最大限に活用するために、固有のポート範囲を使用するようにアプリケーション共有を再構成する必要があります。 たとえば、ポート40803で開始するようにアプリケーション共有を構成し、8348ポートを使用することができます。 (8348 ポートの理由 これらの値を一緒に追加した場合は 8348 40803、アプリケーションの共有でポート40803からポート49150が使用されることを意味します。 オーディオポートはポート49152まで開始されないため、重複するポート範囲はなくなります。)

アプリケーション共有用の新しいポート範囲を選んだら、CsConferencingServer コマンドレットを使用して変更を行うことができます。 この変更は、アプリケーションサーバーまたは仲介サーバーで行う必要はありません。これらのサーバーは、アプリケーション共有トラフィックを処理しないためです。 オーディオトラフィック用に使用されているポートを再割り当てする場合は、これらのサーバーでポートの値を変更する必要があります。

単一の会議サーバーでアプリケーション共有のポート値を変更するには、Lync Server 管理シェルで次のようなコマンドを実行します。

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

すべての会議サーバーでこれらの変更を行う場合は、代わりに次のコマンドを実行します。

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

ポート設定を変更した後で、変更の影響を受ける各サービスを停止してから再起動する必要があります。

会議サーバー、アプリケーションサーバー、および仲介サーバーがまったく同じポート範囲を共有していることは必須ではありません。唯一の条件として、すべてのサーバーで固有のポート範囲を確保する必要があります。 ただし、すべてのサーバーで同じポートセットを使用すると、通常、管理が簡単になります。

</div>

<span> </span>

</div>

</div>

</div>

