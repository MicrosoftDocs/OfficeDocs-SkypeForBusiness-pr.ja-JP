---
title: 'Lync Server 2013: Lync クライアント ビデオ要件'
TOCTitle: Lync クライアント ビデオ要件
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49887049
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Lync クライアント ビデオ要件

 

_**トピックの最終更新日:** 2016-12-08_

このセクションでは、Lync 2013 ビデオ通話でのビデオ ハードウェア サポートについて説明し、さまざまなコンピューター、タブレット、およびモバイル デバイス構成で予想されるビデオ品質の判定方法について説明します。

## Windows デスクトップおよびタブレット ビデオの要件と機能

Lync 2013 は、H.264/MPEG-4 Part 10 Advanced Video Coding 規格に基づくビデオのエンコードとデコード用のハードウェア アクセラレータが導入されています。この機能により、CPU クロック速度が低いコンピューターが高い解像度のビデオをエンコードおよびデコードできます。ビデオ ハードウェア要件は、コンピューター構成と必要なビデオ解像度によって異なります。

## ビデオ ハードウェア要件


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

> [!NOTE]
> デコード モードの詳細については、<a href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</a> を参照してください。

</div></td>
</tr>
<tr class="even">
<td><p>ハードウェア アクセラレータ H.264 エンコード: チップセット要件</p></td>
<td><p>次の Intel ハードウェア アクセラレータ ビデオ エンコード ソリューションがサポートされます。</p>
<ul>
<li><p>統合ハードウェア ビデオ エンコーダーを搭載した第 2 および第 3 世代の Intel HD Graphics 2000、2500、3000、および 4000 チップセット (またはそれ以降のバージョン)。Intel HD Graphics ドライバー 15.28.9.2884 または以下を含む最新ドライバーが必要です。</p>
<ul>
<li><p>ディスプレイ ドライバー 9.17.10.2884 または最新ドライバー</p></li>
<li><p>HMFT (Hardware Media Foundation Transform) バージョン 3.12.10.31 または最新 HMFT</p></li>
</ul></li>
</ul>
<p>次の AMD ハードウェア アクセラレータ ビデオ エンコード ソリューションがサポートされます (Lync Server 2013 用の CU1 更新プログラムが必要)。</p>
<ul>
<li><p>AMD Video Codec Engine は、いくつかの個別のグラフィック カードおよび AMD A-Series Accelerated Processor の統合 APU (Accelerated Processing Unit) で利用できます。AMD Video Codec Engine ドライバー 9.12.0.0 またはそれ以上がインストールされている必要があります。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>ハードウェア アクセラレータ H.264 エンコード: カメラ要件</p></td>
<td><p>USB ビデオ クラス (UVC) 仕様バージョン 1.5 に準拠する統合 H.264 ハードウェア エンコーダーを搭載した USB ビデオ カメラ。</p>
<div>

> [!NOTE]
> Lync 2013 は、Windows 8 または Windows 8.1 で UVC 1.5 のサポートを含む UVC 1.5 カメラをサポートします。Windows 7 には UVC 1.5 のサポートが含まれないため、Lync 2013 は UVC 1.5 カメラをハードウェア エンコード サポートのない通常のカメラとして扱います。

</div></td>
</tr>
<tr class="even">
<td><p>DirectX Video Acceleration (DXVA) を使用したハードウェア アクセラレータ H.264 デコード</p></td>
<td><ul>
<li><p>グラフィック カードでは、DirectX 9.0 がサポートされ、DXVA2_ModeH264_VLD_NoFGT デコード モードが公開される必要があります。</p></li>
<li><p>最新のグラフィック カード ドライバーがインストールされている必要があります。</p></li>
</ul>

> [!NOTE]
> デコード モードの詳細については、<a href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</a> を参照してください。

</div></td>
</tr>
<tr class="odd">
<td><p>ハードウェア アクセラレータ H.264 エンコード: チップセット要件</p></td>
<td><p>次の Intel ハードウェア アクセラレータ ビデオ エンコード ソリューションがサポートされます。</p>
<ul>
<li><p>統合ハードウェア ビデオ エンコーダーを搭載した第 2 および第 3 世代の Intel HD Graphics 2000、2500、3000、および 4000 チップセット (またはそれ以降のバージョン)。Intel HD Graphics ドライバー 15.28.9.2884 または以下を含む最新ドライバーが必要です。</p>
<ul>
<li><p>ディスプレイ ドライバー 9.17.10.2884 または最新ドライバー</p></li>
<li><p>HMFT (Hardware Media Foundation Transform) バージョン 3.12.10.31 または最新 HMFT</p></li>
</ul></li>
</ul>
<p>次の AMD ハードウェア アクセラレータ ビデオ エンコード ソリューションがサポートされます (Lync Server 2013 用の CU1 更新プログラムが必要)。</p>
<ul>
<li><p>AMD Video Codec Engine は、いくつかの個別のグラフィック カードおよび AMD A-Series Accelerated Processor の統合 APU (Accelerated Processing Unit) で利用できます。AMD Video Codec Engine ドライバー 9.12.0.0 またはそれ以上がインストールされている必要があります。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>ハードウェア アクセラレータ H.264 エンコード: カメラ要件</p></td>
<td><p>USB ビデオ クラス (UVC) 仕様バージョン 1.5 に準拠する統合 H.264 ハードウェア エンコーダーを搭載した USB ビデオ カメラ。</p>

> [!NOTE]
> Lync 2013 は、Windows 8 または Windows 8.1 で UVC 1.5 のサポートを含む UVC 1.5 カメラをサポートします。Windows 7 には UVC 1.5 のサポートが含まれないため、Lync 2013 は UVC 1.5 カメラをハードウェア エンコード サポートのない通常のカメラとして扱います。

</div></td>
</tr>
</tbody>
</table>


## H.264 ビデオ エンコードおよびデコード機能の決定

一般に、特定のコンピューター構成の最大エンコードおよびデコード機能を決定する主な要因として、次の 4 つがあります。

  - DXVA を使用したハードウェア アクセラレータ デコードのサポート

  - ハードウェア アクセラレータ エンコードのサポート

  - 物理コアの数

  - Windows エクスペリエンス インデックス (WEI)

Windows システム評価ツール (WinSAT) は、WEI を決定します。WinSAT ツールを実行すると、コンピューターの %windir%\\Performance\\WinSAT\\DataStore ディレクトリに Formal.Assessment XML ドキュメントが生成されます。この XML ファイルには、エンコードおよびデコード機能を決定するために特に重要な次の 2 つのスコアが含まれます。

  - VideoEncodeScore は、コンピューターのソフトウェア ベースのビデオ エンコード機能を示します。

  - GraphicsScore 値は、コンピューターのハードウェア アクセラレータ エンコード機能を示します。

次の 3 つの表で、サポートされるハードウェア アクセラレータによる、異なる種類の PC の最大エンコードおよびデコード機能を説明します。640x360 以上の解像度では、サポートされる最大フレーム レートは 30 フレーム/秒 (fps) です。640x360 より低い解像度では、サポートされる最大フレーム レートは 15 fps です。

### DXVA とハードウェア アクセラレータ エンコーダーのないコンピューター

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
<td><p>1 コアおよび VideoEncodeScore ≥ 4.0</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>640x360</p></td>
<td><p>2 コアおよび VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="odd">
<td><p>640x360</p></td>
<td><p>1280x720</p></td>
<td><p>2 コアおよび VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>4 コアおよび VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1280x720</p></td>
<td><p>4 コアおよび VideoEncodeScore ≥ 7.3</p></td>
</tr>
<tr class="even">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>4 コアおよび VideoEncodeScore ≥ 7.3</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="even">
<td><p>424x240</p></td>
<td><p>424x240 (受信のみのシナリオでは 15fps で 640x360)</p></td>
<td><p>1 コアおよび VideoEncodeScore ≥ 4.0</p></td>
</tr>
<tr class="odd">
<td><p>640x360</p></td>
<td><p>640x360</p></td>
<td><p>2 コアおよび VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1280x720</p></td>
<td><p>2 コアおよび VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="odd">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>4 コアおよび VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="even">
<td><p>1280x720</p></td>
<td><p>1280x720</p></td>
<td><p>4 コアおよび VideoEncodeScore ≥ 7.3</p></td>
</tr>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>4 コアおよび VideoEncodeScore ≥ 7.3</p></td>
</tr>
<tr class="even">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>該当なし</p></td>
</tr>
</tbody>
</table>


### DXVA があり、ハードウェア アクセラレータ エンコーダーのないコンピューター

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
<td><p>1 コアおよび VideoEncodeScore ≥ 3.0</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>2 コアおよび VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="odd">
<td><p>960x540</p></td>
<td><p>1920x1080</p></td>
<td><p>2 コアおよび VideoEncodeScore ≥ 6.0</p></td>
</tr>
<tr class="even">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>4 コアおよび VideoEncodeScore ≥ 6.7</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>4 コアおよび VideoEncodeScore ≥ 8.2</p></td>
</tr>
<tr class="even">
<td><p>424x240</p></td>
<td><p>1920x1080</p></td>
<td><p>1 コアおよび VideoEncodeScore ≥ 3.0</p></td>
</tr>
<tr class="odd">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>2 コアおよび VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="even">
<td><p>960x540</p></td>
<td><p>1920x1080</p></td>
<td><p>2 コアおよび VideoEncodeScore ≥ 6.0</p></td>
</tr>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>4 コアおよび VideoEncodeScore ≥ 6.7</p></td>
</tr>
<tr class="even">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>4 コアおよび VideoEncodeScore ≥ 8.2</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Windows 7 での WinSAT スコアは最大 7.9 に制限されます。したがって、ハードウェア アクセラレータ エンコーダーのないコンピューターのエンコード能力は、Windows 8 または Windows 8.1 でのみ実現でき、その場合の最大 WinSAT スコアは 9.9 です。


### DXVA と Intel HD グラフィック ハードウェア アクセラレータ エンコーダーがあるコンピューター

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


## モバイル デバイス ビデオ機能

次の表は、サポートされるモバイル デバイスの最大ビデオ機能について説明しています。モバイル デバイスのサポートの詳細については、「[Lync Server 2013 でのモバイル クライアントの計画](lync-server-2013-planning-for-mobile-clients.md)」を参照してください。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>機能</th>
<th>Windows Phone</th>
<th>iPhone および iPad</th>
<th>Android</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>H.264 エンコード最大解像度</p></td>
<td><p>640x480</p></td>
<td><p>iPhone 4: 192x144</p>
<p>iPad および他のすべてのサポートされる iPhone モデル: 352x288</p></td>
<td><p>320x2401</p></td>
</tr>
<tr class="even">
<td><p>H.264 デコード最大解像度</p></td>
<td><p>640x480</p></td>
<td><p>iPhone および iPad: 352x288</p></td>
<td><p>320x2401</p></td>
</tr>
<tr class="odd">
<td><p>H.264 エンコード最大解像度</p></td>
<td><p>640x480</p></td>
<td><p>iPhone 4: 192x144</p>
<p>iPad および他のすべてのサポートされる iPhone モデル: 352x288</p></td>
<td><p>320x2401</p></td>
</tr>
<tr class="even">
<td><p>H.264 デコード最大解像度</p></td>
<td><p>640x480</p></td>
<td><p>iPhone および iPad: 352x288</p></td>
<td><p>320x2401</p></td>
</tr>
</tbody>
</table>


18x60 チップセットを使用し、Qualcomm Snapdragon S3 または S4 を搭載した Android デバイスの場合、640x480 解像度での送受信に対応しています。

