---
title: 'Lync Server 2013: Lync クライアントのビデオ要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync client video requirements
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49733731
ms.date: 01/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d174b73bd4369220ae83bc8365267a626849e235
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-client-video-requirements-for-lync-server-2013"></a>Lync Server 2013 の lync クライアントのビデオ要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-01-29_

このセクションでは、Lync 2013 ビデオ通話向けのビデオハードウェアのサポートについて説明し、さまざまなコンピューター、タブレット、モバイルデバイスの構成に対して予想されるビデオ品質を決定する方法について説明します。

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a>Windows デスクトップとタブレットのビデオの要件と機能

Lync 2013 では、ビデオのエンコードとデコードのために、高度なビデオコーディング標準の3つに基づいて、ビデオのエンコードとデコードのためのハードウェアアクセラレータが導入されています。 この機能により、CPU クロック速度が低いコンピューターが高い解像度のビデオをエンコードおよびデコードできます。 ビデオ ハードウェア要件は、コンピューター構成と必要なビデオ解像度によって異なります。

<div>

## <a name="video-hardware-requirements"></a>ビデオハードウェア要件


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>機能</th>
<th>要件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DirectX Video Acceleration (DXVA) を使用したハードウェア アクセラレータ H.264 デコード</p></td>
<td><ul>
<li><p>グラフィック カードでは、DirectX 9.0 がサポートされ、DXVA2_ModeH264_VLD_NoFGT デコード モードが公開される必要があります。</p></li>
<li><p>最新のグラフィック カード ドライバーがインストールされている必要があります。</p></li>
</ul>
<div>

> [!NOTE]  
> デコードモードの詳細について<A href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</A>は、を参照してください。


</div></td>
</tr>
<tr class="even">
<td><p>ハードウェア アクセラレータ H.264 エンコード: チップセット要件</p></td>
<td><p>次の Intel ハードウェア アクセラレータ ビデオ エンコード ソリューションがサポートされます。</p>
<ul>
<li><p>第2世代および第3世代 Intel HD グラフィックス2000、2500、3000、4000チップセット (またはそれ以降のバージョン) と、統合されたハードウェアビデオエンコーダー。 Intel HD Graphics ドライバー 15.28.9.2884 または以下を含む最新ドライバーが必要です。</p>
<ul>
<li><p>ディスプレイ ドライバー 9.17.10.2884 または最新ドライバー</p></li>
<li><p>HMFT (Hardware Media Foundation Transform) バージョン 3.12.10.31 または最新 HMFT</p></li>
</ul></li>
</ul>
<p>次の AMD ハードウェアアクセラレータに対応したビデオエンコードソリューションがサポートされています (Lync Server 2013 の CU1 の更新が必要です)。</p>
<ul>
<li><p>AMD Video Codec Engine は、いくつかの個別のグラフィック カードおよび AMD A-Series Accelerated Processor の統合 APU (Accelerated Processing Unit) で利用できます。AMD Video Codec Engine ドライバー 9.12.0.0 またはそれ以上がインストールされている必要があります。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>ハードウェア アクセラレータ H.264 エンコード: カメラ要件</p></td>
<td><p>USB ビデオ クラス (UVC) 仕様バージョン 1.5 に準拠する統合 H.264 ハードウェア エンコーダーを搭載した USB ビデオ カメラ。</p>
<div>

> [!NOTE]  
> Lync 2013 は、Windows 8 または Windows 8.1 で UVC 1.5 カメラをサポートしています。 UVC 1.5 のサポートが含まれています。 Windows 7 には UVC 1.5 のサポートが含まれていないため、Lync 2013 は UVC 1.5 カメラを標準カメラとして扱うため、ハードウェアエンコードはサポートされていません。


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>.H ビデオのエンコード機能とデコード機能を決定する

一般に、特定のコンピューター構成の最大エンコードおよびデコード機能を決定する主な要因として、次の 4 つがあります。

  - DXVA を使用したハードウェア アクセラレータ デコードのサポート

  - ハードウェア アクセラレータ エンコードのサポート

  - 物理コアの数

  - Windows エクスペリエンス インデックス (WEI)

Windows システム評価ツール (WinSAT) は、WEI を決定します。 WinSAT ツールを実行すると、% windir%\\Performance\\WinSAT\\DataStore ディレクトリにあるコンピューター上に、正式な評価の XML ドキュメントが生成されます。 この XML ファイルには、エンコードおよびデコード機能を決定するために特に重要な次の 2 つのスコアが含まれます。

  - VideoEncodeScore は、コンピューターのソフトウェア ベースのビデオ エンコード機能を示します。

  - GraphicsScore 値は、コンピューターのハードウェア アクセラレータ エンコード機能を示します。

次の 3 つの表で、サポートされるハードウェア アクセラレータによる、異なる種類の PC の最大エンコードおよびデコード機能を説明します。640x360 以上の解像度では、サポートされる最大フレーム レートは 30 フレーム/秒 (fps) です。640x360 より低い解像度では、サポートされる最大フレーム レートは 15 fps です。

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a>DXVA とハードウェア アクセラレータ エンコーダーのないコンピューター

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>可能なエンコーダー解像度</th>
<th>可能なデコーダー解像度</th>
<th>要件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>424x240 (受信のみのシナリオでは 15fps で 640x360)</p></td>
<td><p>1 コアと VideoEncodeScore ≥ 4.0</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>640x360</p></td>
<td><p>2 コアと VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="odd">
<td><p>640x360</p></td>
<td><p>1280x720</p></td>
<td><p>2 コアと VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>4 コアと VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1280x720</p></td>
<td><p>4 コアと VideoEncodeScore ≥ 7.3</p></td>
</tr>
<tr class="even">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>4 コアと VideoEncodeScore ≥ 7.3</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>該当なし</p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a>DXVA があり、ハードウェア アクセラレータ エンコーダーのないコンピューター

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>可能なエンコーダー解像度</th>
<th>可能なデコーダー解像度</th>
<th>要件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>1920x1080</p></td>
<td><p>1 コアと VideoEncodeScore ≥ 3.0</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>2 コアと VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="odd">
<td><p>960x540</p></td>
<td><p>1920x1080</p></td>
<td><p>2 コアと VideoEncodeScore ≥ 6.0</p></td>
</tr>
<tr class="even">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>4 コアと VideoEncodeScore ≥ 6.7</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>4 コアと VideoEncodeScore ≥ 8.2</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Windows 7 での WinSAT スコアは最大 7.9 に制限されます。したがって、ハードウェア アクセラレータ エンコーダーのないコンピューターのエンコード能力は、Windows 8 または Windows 8.1 でのみ実現でき、その場合の最大 WinSAT スコアは 9.9 です。



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a>DXVA と Intel HD グラフィック ハードウェア アクセラレータ エンコーダーがあるコンピューター

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>可能なエンコーダー解像度</th>
<th>可能なデコーダー解像度</th>
<th>要件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>すべての第 2 世代および第 3 世代の Intel HD Graphics</p></td>
</tr>
<tr class="even">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>第 2 世代および第 3 世代の Intel HD Graphics と GraphicsScore ≥ 5.0</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a>モバイルデバイスのビデオ機能

次の表は、サポートされるモバイル デバイスの最高レベルのビデオ機能を示しています。 モバイルデバイスのサポートについて詳しくは、「 [Lync Server 2013 でのモバイルクライアントの計画](lync-server-2013-planning-for-mobile-clients.md)」をご覧ください。


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>機能</th>
<th>Windows Phone</th>
<th>iPhone</th>
<th>iPad</th>
<th>Android</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>H.264 エンコードの最大解像度</p></td>
<td><p>VGA</p></td>
<td><p>QVGA: iPhone 4S</p>
<p>VGA: iPhone 5</p>
<p>720p: iPhone 5S 以降</p></td>
<td><p>VGA: iPad 2 以降/iPad mini 1 以降</p>
<p>720p: iPad Air/iPad mini 2/iPad Pro 以降</p></td>
<td><p>デバイスのモデルに応じて VGA を最大にする</p></td>
</tr>
<tr class="even">
<td><p>H.264 デコードの最大解像度</p></td>
<td><p>VGA</p></td>
<td><p>QVGA: iPhone 4S</p>
<p>VGA: iPhone 5</p>
<p>720p: iPhone 5S 以降</p></td>
<td><p>VGA: iPad 2 以降/iPad mini 1 以降</p>
<p>720p: iPad Air/iPad mini 2/iPad Pro 以降</p></td>
<td><p>デバイスのモデルに応じて VGA を最大にする</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

