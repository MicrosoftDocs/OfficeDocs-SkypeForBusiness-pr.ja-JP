---
title: 'Lync Server 2013: Lync クライアントのビデオの要件'
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
ms.openlocfilehash: 1e4a8e99c50bc62565ed597e65cef73a6aaddd08
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-client-video-requirements-for-lync-server-2013"></a>Lync Server 2013 の lync クライアントのビデオ要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-01-29_

このセクションでは、Lync 2013 ビデオ通話のビデオハードウェアサポートについて説明し、さまざまなコンピューター、タブレット、およびモバイルデバイス構成について予想されるビデオ品質を判断する方法について説明します。

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a>Windows デスクトップおよびタブレットのビデオの要件と機能

Lync 2013 では、ビデオのエンコードとデコードに関するハードウェアアクセラレータが、「264/MPEG-2 Part 10 Advanced Video コーディング標準」に基づいて導入されています。 この機能により、CPU クロック速度が低いコンピューターが高い解像度のビデオをエンコードおよびデコードできます。 ビデオ ハードウェア要件は、コンピューター構成と必要なビデオ解像度によって異なります。

<div>

## <a name="video-hardware-requirements"></a>ビデオ ハードウェア要件


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
> デコードモードの詳細について<A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A>は、「」を参照してください。


</div></td>
</tr>
<tr class="even">
<td><p>ハードウェア アクセラレータ H.264 エンコード: チップセット要件</p></td>
<td><p>次のインテルハードウェアアクセラレータビデオエンコードソリューションがサポートされています。</p>
<ul>
<li><p>統合ハードウェア ビデオ エンコーダーを搭載した第 2 および第 3 世代の Intel HD Graphics 2000、2500、3000、および 4000 チップセット (またはそれ以降のバージョン)。 Intel HD Graphics driver 15.28.9.2884 または次のものを含む最新ドライバーがインストールされている必要があります。</p>
<ul>
<li><p>ディスプレイドライバー9.17.10.2884 または最新ドライバー</p></li>
<li><p>ハードウェアメディアファンデーション変換 (HMFT) バージョン3.12.10.31 または最新の HMFT</p></li>
</ul></li>
</ul>
<p>次の AMD ハードウェアアクセラレータビデオエンコードソリューションがサポートされています (Lync Server 2013 の CU1 更新プログラムが必要です)。</p>
<ul>
<li><p>AMD ビデオコーデックエンジン。これは、いくつかの個別のグラフィックスカードと、AMD A シリーズの高速プロセッサの統合された高速処理ユニットで利用できます。 AMD Video コーデックエンジンドライバー9.12.0.0 以上がインストールされている必要があります。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>ハードウェア アクセラレータ H.264 エンコード: カメラ要件</p></td>
<td><p>USB ビデオ クラス (UVC) 仕様バージョン 1.5 に準拠する統合 H.264 ハードウェア エンコーダーを搭載した USB ビデオ カメラ。</p>
<div>

> [!NOTE]  
> Lync 2013 は、Windows 8 または Windows 8.1 で UVC 1.5 カメラをサポートします。これには UVC 1.5 のサポートが含まれています。 Windows 7 には UVC 1.5 のサポートが含まれないため、Lync 2013 は UVC 1.5 カメラをハードウェア エンコード サポートのない通常のカメラとして扱います。


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>H.264 ビデオ エンコードおよびデコード機能の決定

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
<td><p>1 コアと and VideoEncodeScore ≥ 3.0</p></td>
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
> Windows 7 での WinSAT スコアは最大 7.9 に制限されます。 そのため、ハードウェアアクセラレータエンコーダーを使用していないコンピューターのエンコード機能は、Windows 8 または Windows 8.1 でのみ実現できます。これは、最大 WinSAT スコアは9.9 です。



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
<td><p>すべての第 2 および第 3 世代 Intel HD Graphics</p></td>
</tr>
<tr class="even">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>第 2 および第 3 世代 Intel HD Graphics と GraphicsScore ≥ 5.0</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a>モバイルデバイスのビデオ機能

次の表では、サポートされているモバイルデバイスの最大ビデオ機能について説明します。 モバイルデバイスのサポートの詳細については、「 [Lync Server 2013 でモバイルクライアントを計画する](lync-server-2013-planning-for-mobile-clients.md)」を参照してください。


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
<td><p>.H エンコードの最大解像度</p></td>
<td><p>VGA</p></td>
<td><p>QVGA: iPhone 4S</p>
<p>VGA: iPhone 5</p>
<p>720p: iPhone 5S 以降</p></td>
<td><p>VGA: iPad 2 以降/iPad mini 1 以降</p>
<p>720p: iPad Air/iPad mini 2/iPad Pro 以降</p></td>
<td><p>デバイスモデルによっては最大 VGA</p></td>
</tr>
<tr class="even">
<td><p>.H デコードの最大解像度</p></td>
<td><p>VGA</p></td>
<td><p>QVGA: iPhone 4S</p>
<p>VGA: iPhone 5</p>
<p>720p: iPhone 5S 以降</p></td>
<td><p>VGA: iPad 2 以降/iPad mini 1 以降</p>
<p>720p: iPad Air/iPad mini 2/iPad Pro 以降</p></td>
<td><p>デバイスモデルによっては最大 VGA</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

