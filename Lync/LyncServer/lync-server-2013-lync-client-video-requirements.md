---
title: 'Lync Server 2013: Lync クライアントのビデオの要件'
description: 'Lync Server 2013: Lync クライアントのビデオの要件。'
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
ms.openlocfilehash: ea1d4a993650ec8102d8b66ea5aa936ad1613f20
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570483"
---
# <a name="lync-client-video-requirements-for-lync-server-2013"></a><span data-ttu-id="6fdfd-103">Lync Server 2013 の lync クライアントのビデオ要件</span><span class="sxs-lookup"><span data-stu-id="6fdfd-103">Lync client video requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fdfd-104">_**トピックの最終更新日:** 2016-01-29_</span><span class="sxs-lookup"><span data-stu-id="6fdfd-104">_**Topic Last Modified:** 2016-01-29_</span></span>

<span data-ttu-id="6fdfd-105">このセクションでは、Lync 2013 ビデオ通話のビデオハードウェアサポートについて説明し、さまざまなコンピューター、タブレット、およびモバイルデバイス構成について予想されるビデオ品質を判断する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-105">This section describes video hardware support for Lync 2013 video calls and describes how to determine the expected video quality for various computer, tablet, and mobile device configurations.</span></span>

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a><span data-ttu-id="6fdfd-106">Windows デスクトップおよびタブレットのビデオの要件と機能</span><span class="sxs-lookup"><span data-stu-id="6fdfd-106">Windows Desktop and Tablet Video Requirements and Capabilities</span></span>

<span data-ttu-id="6fdfd-107">Lync 2013 では、ビデオのエンコードとデコードに関するハードウェアアクセラレータが、「264/MPEG-2 Part 10 Advanced Video コーディング標準」に基づいて導入されています。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-107">Lync 2013 introduces hardware acceleration for video encoding and decoding based on the H.264/MPEG-4 Part 10 Advanced Video Coding standard.</span></span> <span data-ttu-id="6fdfd-108">この機能により、CPU クロック速度が低いコンピューターが高い解像度のビデオをエンコードおよびデコードできます。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-108">This feature allows computers with lower CPU clock speeds to encode and decode higher resolution video.</span></span> <span data-ttu-id="6fdfd-109">ビデオ ハードウェア要件は、コンピューター構成と必要なビデオ解像度によって異なります。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-109">Video hardware requirements vary depending on the computer configuration and the video resolution wanted.</span></span>

<div>

## <a name="video-hardware-requirements"></a><span data-ttu-id="6fdfd-110">ビデオ ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="6fdfd-110">Video Hardware Requirements</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6fdfd-111">機能</span><span class="sxs-lookup"><span data-stu-id="6fdfd-111">Feature</span></span></th>
<th><span data-ttu-id="6fdfd-112">要件</span><span class="sxs-lookup"><span data-stu-id="6fdfd-112">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fdfd-113">DirectX Video Acceleration (DXVA) を使用したハードウェア アクセラレータ H.264 デコード</span><span class="sxs-lookup"><span data-stu-id="6fdfd-113">Hardware accelerated H.264 decoding using DirectX Video Acceleration (DXVA)</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6fdfd-114">グラフィック カードでは、DirectX 9.0 がサポートされ、DXVA2_ModeH264_VLD_NoFGT デコード モードが公開される必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-114">Graphics card must support DirectX 9.0 and must expose the DXVA2_ModeH264_VLD_NoFGT decoding mode.</span></span></p></li>
<li><p><span data-ttu-id="6fdfd-115">最新のグラフィック カード ドライバーがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-115">The latest graphics card driver must be installed.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="6fdfd-116">デコードモードの詳細については、「」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A> 。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-116">For details about decoding modes, see <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A>.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fdfd-117">ハードウェア アクセラレータ H.264 エンコード: チップセット要件</span><span class="sxs-lookup"><span data-stu-id="6fdfd-117">Hardware accelerated H.264 encoding: Chipset Requirements</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-118">次のインテルハードウェアアクセラレータビデオエンコードソリューションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-118">The following Intel hardware accelerated video encoding solutions are supported:</span></span></p>
<ul>
<li><p><span data-ttu-id="6fdfd-119">統合ハードウェア ビデオ エンコーダーを搭載した第 2 および第 3 世代の Intel HD Graphics 2000、2500、3000、および 4000 チップセット (またはそれ以降のバージョン)。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-119">Second and third generation Intel HD Graphics 2000, 2500, 3000, and 4000 chipsets (or later versions) with integrated hardware video encoders.</span></span> <span data-ttu-id="6fdfd-120">Intel HD Graphics driver 15.28.9.2884 または次のものを含む最新ドライバーがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-120">Installation of the Intel HD Graphics driver 15.28.9.2884 or the latest driver containing the following is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="6fdfd-121">ディスプレイドライバー9.17.10.2884 または最新ドライバー</span><span class="sxs-lookup"><span data-stu-id="6fdfd-121">Display driver 9.17.10.2884 or the latest driver</span></span></p></li>
<li><p><span data-ttu-id="6fdfd-122">ハードウェアメディアファンデーション変換 (HMFT) バージョン3.12.10.31 または最新の HMFT</span><span class="sxs-lookup"><span data-stu-id="6fdfd-122">Hardware media foundation transform (HMFT) version 3.12.10.31 or the latest HMFT</span></span></p></li>
</ul></li>
</ul>
<p><span data-ttu-id="6fdfd-123">次の AMD ハードウェアアクセラレータビデオエンコードソリューションがサポートされています (Lync Server 2013 の CU1 更新プログラムが必要です)。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-123">The following AMD hardware accelerated video encoding solutions are supported (requires CU1 Updates for Lync Server 2013):</span></span></p>
<ul>
<li><p><span data-ttu-id="6fdfd-124">AMD ビデオコーデックエンジン。これは、いくつかの個別のグラフィックスカードと、AMD A シリーズの高速プロセッサの統合された高速処理ユニットで利用できます。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-124">AMD Video Codec Engine, which is available in several discrete graphics cards and in integrated accelerated processing units of AMD A-Series Accelerated Processors.</span></span> <span data-ttu-id="6fdfd-125">AMD Video コーデックエンジンドライバー9.12.0.0 以上がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-125">The AMD Video Codec Engine driver 9.12.0.0 or higher must be installed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fdfd-126">ハードウェア アクセラレータ H.264 エンコード: カメラ要件</span><span class="sxs-lookup"><span data-stu-id="6fdfd-126">Hardware accelerated H.264 encoding: Camera Requirements</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-127">USB ビデオ クラス (UVC) 仕様バージョン 1.5 に準拠する統合 H.264 ハードウェア エンコーダーを搭載した USB ビデオ カメラ。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-127">USB video cameras with integrated H.264 hardware encoder that conforms to the USB Video Class (UVC) specification version 1.5.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6fdfd-128">Lync 2013 は、Windows 8 または Windows 8.1 で UVC 1.5 カメラをサポートします。これには UVC 1.5 のサポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-128">Lync 2013 supports UVC 1.5 cameras with Windows 8 or Windows 8.1, which includes support for UVC 1.5.</span></span> <span data-ttu-id="6fdfd-129">Windows 7 には UVC 1.5 のサポートが含まれないため、Lync 2013 は UVC 1.5 カメラをハードウェア エンコード サポートのない通常のカメラとして扱います。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-129">Because Windows 7 does not include support for UVC 1.5, Lync 2013 treats UVC 1.5 cameras as regular cameras with no hardware encoding support.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a><span data-ttu-id="6fdfd-130">H.264 ビデオ エンコードおよびデコード機能の決定</span><span class="sxs-lookup"><span data-stu-id="6fdfd-130">Determining H.264 Video Encoding and Decoding Capabilities</span></span>

<span data-ttu-id="6fdfd-131">一般に、特定のコンピューター構成の最大エンコードおよびデコード機能を決定する主な要因として、次の 4 つがあります。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-131">Generally, there are four major factors that determine the maximum encoding and decoding capability of a particular computer configuration:</span></span>

  - <span data-ttu-id="6fdfd-132">DXVA を使用したハードウェア アクセラレータ デコードのサポート</span><span class="sxs-lookup"><span data-stu-id="6fdfd-132">Support for hardware accelerated decoding by using DXVA</span></span>

  - <span data-ttu-id="6fdfd-133">ハードウェア アクセラレータ エンコードのサポート</span><span class="sxs-lookup"><span data-stu-id="6fdfd-133">Support for hardware accelerated encoding</span></span>

  - <span data-ttu-id="6fdfd-134">物理コアの数</span><span class="sxs-lookup"><span data-stu-id="6fdfd-134">Number of physical cores</span></span>

  - <span data-ttu-id="6fdfd-135">Windows エクスペリエンス インデックス (WEI)</span><span class="sxs-lookup"><span data-stu-id="6fdfd-135">Windows Experience Index (WEI)</span></span>

<span data-ttu-id="6fdfd-136">Windows システム評価ツール (WinSAT) は、WEI を決定します。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-136">The Windows System Assessment Tool (WinSAT) determines the WEI.</span></span> <span data-ttu-id="6fdfd-137">WinSAT ツールを実行すると、% windir% \\ Performance \\ WinSAT \\ DataStore ディレクトリにあるコンピューター上に、正式な評価の XML ドキュメントが生成されます。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-137">When you run the WinSAT tool, it generates a Formal.Assessment XML document on the computer in the %windir%\\Performance\\WinSAT\\DataStore directory.</span></span> <span data-ttu-id="6fdfd-138">この XML ファイルには、エンコードおよびデコード機能を決定するために特に重要な次の 2 つのスコアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-138">This XML file contains the following two scores that are of particular importance for determining encoding and decoding capabilities:</span></span>

  - <span data-ttu-id="6fdfd-139">VideoEncodeScore は、コンピューターのソフトウェア ベースのビデオ エンコード機能を示します。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-139">The VideoEncodeScore indicates the software-based video encoding capability of the computer.</span></span>

  - <span data-ttu-id="6fdfd-140">GraphicsScore 値は、コンピューターのハードウェア アクセラレータ エンコード機能を示します。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-140">The GraphicsScore value indicates the hardware accelerated encoding capability of the computer.</span></span>

<span data-ttu-id="6fdfd-p106">次の 3 つの表で、サポートされるハードウェア アクセラレータによる、異なる種類の PC の最大エンコードおよびデコード機能を説明します。640x360 以上の解像度では、サポートされる最大フレーム レートは 30 フレーム/秒 (fps) です。640x360 より低い解像度では、サポートされる最大フレーム レートは 15 fps です。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-p106">The following three tables explain the maximum encoding and decoding capability for different PC types depending on what hardware acceleration they support. For resolutions of 640x360 and higher, the maximum supported frame rate is 30 frames per second (fps). For resolutions lower than 640x360, the maximum supported frame rate is 15 fps.</span></span>

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a><span data-ttu-id="6fdfd-144">DXVA とハードウェア アクセラレータ エンコーダーのないコンピューター</span><span class="sxs-lookup"><span data-stu-id="6fdfd-144">Computer Without DXVA And Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6fdfd-145">可能なエンコーダー解像度</span><span class="sxs-lookup"><span data-stu-id="6fdfd-145">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="6fdfd-146">可能なデコーダー解像度</span><span class="sxs-lookup"><span data-stu-id="6fdfd-146">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="6fdfd-147">要件</span><span class="sxs-lookup"><span data-stu-id="6fdfd-147">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fdfd-148">424x240</span><span class="sxs-lookup"><span data-stu-id="6fdfd-148">424x240</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-149">424x240 (受信のみのシナリオでは 15fps で 640x360)</span><span class="sxs-lookup"><span data-stu-id="6fdfd-149">424x240 (640x360 at 15fps for receive only scenarios)</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-150">1 コアと VideoEncodeScore ≥ 4.0</span><span class="sxs-lookup"><span data-stu-id="6fdfd-150">1 Core and VideoEncodeScore ≥ 4.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fdfd-151">640x360</span><span class="sxs-lookup"><span data-stu-id="6fdfd-151">640x360</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-152">640x360</span><span class="sxs-lookup"><span data-stu-id="6fdfd-152">640x360</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-153">2 コアと VideoEncodeScore ≥ 4.5</span><span class="sxs-lookup"><span data-stu-id="6fdfd-153">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fdfd-154">640x360</span><span class="sxs-lookup"><span data-stu-id="6fdfd-154">640x360</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-155">1280x720</span><span class="sxs-lookup"><span data-stu-id="6fdfd-155">1280x720</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-156">2 コアと VideoEncodeScore ≥ 4.5</span><span class="sxs-lookup"><span data-stu-id="6fdfd-156">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fdfd-157">640x360</span><span class="sxs-lookup"><span data-stu-id="6fdfd-157">640x360</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-158">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6fdfd-158">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-159">4 コアと VideoEncodeScore ≥ 4.5</span><span class="sxs-lookup"><span data-stu-id="6fdfd-159">4 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fdfd-160">1280x720</span><span class="sxs-lookup"><span data-stu-id="6fdfd-160">1280x720</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-161">1280x720</span><span class="sxs-lookup"><span data-stu-id="6fdfd-161">1280x720</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-162">4 コアと VideoEncodeScore ≥ 7.3</span><span class="sxs-lookup"><span data-stu-id="6fdfd-162">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fdfd-163">1280x720</span><span class="sxs-lookup"><span data-stu-id="6fdfd-163">1280x720</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-164">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6fdfd-164">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-165">4 コアと VideoEncodeScore ≥ 7.3</span><span class="sxs-lookup"><span data-stu-id="6fdfd-165">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fdfd-166">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6fdfd-166">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-167">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6fdfd-167">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-168">該当なし</span><span class="sxs-lookup"><span data-stu-id="6fdfd-168">N/A</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a><span data-ttu-id="6fdfd-169">DXVA があり、ハードウェア アクセラレータ エンコーダーのないコンピューター</span><span class="sxs-lookup"><span data-stu-id="6fdfd-169">Computer With DXVA But Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6fdfd-170">可能なエンコーダー解像度</span><span class="sxs-lookup"><span data-stu-id="6fdfd-170">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="6fdfd-171">可能なデコーダー解像度</span><span class="sxs-lookup"><span data-stu-id="6fdfd-171">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="6fdfd-172">要件</span><span class="sxs-lookup"><span data-stu-id="6fdfd-172">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fdfd-173">424x240</span><span class="sxs-lookup"><span data-stu-id="6fdfd-173">424x240</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-174">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6fdfd-174">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-175">1 コアと and VideoEncodeScore ≥ 3.0</span><span class="sxs-lookup"><span data-stu-id="6fdfd-175">1 Core and VideoEncodeScore ≥ 3.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fdfd-176">640x360</span><span class="sxs-lookup"><span data-stu-id="6fdfd-176">640x360</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-177">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6fdfd-177">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-178">2 コアと VideoEncodeScore ≥ 4.5</span><span class="sxs-lookup"><span data-stu-id="6fdfd-178">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fdfd-179">960x540</span><span class="sxs-lookup"><span data-stu-id="6fdfd-179">960x540</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-180">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6fdfd-180">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-181">2 コアと VideoEncodeScore ≥ 6.0</span><span class="sxs-lookup"><span data-stu-id="6fdfd-181">2 Cores and VideoEncodeScore ≥ 6.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fdfd-182">1280x720</span><span class="sxs-lookup"><span data-stu-id="6fdfd-182">1280x720</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-183">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6fdfd-183">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-184">4 コアと VideoEncodeScore ≥ 6.7</span><span class="sxs-lookup"><span data-stu-id="6fdfd-184">4 Cores and VideoEncodeScore ≥ 6.7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fdfd-185">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6fdfd-185">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-186">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6fdfd-186">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-187">4 コアと VideoEncodeScore ≥ 8.2</span><span class="sxs-lookup"><span data-stu-id="6fdfd-187">4 Cores and VideoEncodeScore ≥ 8.2</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="6fdfd-188">Windows 7 での WinSAT スコアは最大 7.9 に制限されます。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-188">The WinSAT score on Windows 7 is limited to a maximum of 7.9.</span></span> <span data-ttu-id="6fdfd-189">そのため、ハードウェアアクセラレータエンコーダーを使用していないコンピューターのエンコード機能は、Windows 8 または Windows 8.1 でのみ実現できます。これは、最大 WinSAT スコアは9.9 です。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-189">Therefore, the encoding capability for a computer without a hardware accelerated encoder can only be achieved on Windows 8 or Windows 8.1, where the maximum WinSAT score is 9.9.</span></span>



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a><span data-ttu-id="6fdfd-190">DXVA と Intel HD グラフィック ハードウェア アクセラレータ エンコーダーがあるコンピューター</span><span class="sxs-lookup"><span data-stu-id="6fdfd-190">Computer With DXVA And With Intel HD Graphics Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6fdfd-191">可能なエンコーダー解像度</span><span class="sxs-lookup"><span data-stu-id="6fdfd-191">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="6fdfd-192">可能なデコーダー解像度</span><span class="sxs-lookup"><span data-stu-id="6fdfd-192">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="6fdfd-193">要件</span><span class="sxs-lookup"><span data-stu-id="6fdfd-193">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fdfd-194">1280x720</span><span class="sxs-lookup"><span data-stu-id="6fdfd-194">1280x720</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-195">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6fdfd-195">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-196">すべての第 2 および第 3 世代 Intel HD Graphics</span><span class="sxs-lookup"><span data-stu-id="6fdfd-196">All 2nd and 3rd generation Intel HD Graphics</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fdfd-197">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6fdfd-197">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-198">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6fdfd-198">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-199">第 2 および第 3 世代 Intel HD Graphics と GraphicsScore ≥ 5.0</span><span class="sxs-lookup"><span data-stu-id="6fdfd-199">2nd and 3rd generation Intel HD Graphics and GraphicsScore ≥ 5.0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a><span data-ttu-id="6fdfd-200">モバイルデバイスのビデオ機能</span><span class="sxs-lookup"><span data-stu-id="6fdfd-200">Mobile Device Video Capabilities</span></span>

<span data-ttu-id="6fdfd-201">次の表では、サポートされているモバイルデバイスの最大ビデオ機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-201">The following table describes the maximum video capabilities for supported mobile devices.</span></span> <span data-ttu-id="6fdfd-202">モバイルデバイスのサポートの詳細については、「 [Lync Server 2013 でモバイルクライアントを計画する](lync-server-2013-planning-for-mobile-clients.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fdfd-202">For more information about mobile device support, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>


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
<th><span data-ttu-id="6fdfd-203">機能</span><span class="sxs-lookup"><span data-stu-id="6fdfd-203">Feature</span></span></th>
<th><span data-ttu-id="6fdfd-204">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="6fdfd-204">Windows Phone</span></span></th>
<th><span data-ttu-id="6fdfd-205">iPhone</span><span class="sxs-lookup"><span data-stu-id="6fdfd-205">iPhone</span></span></th>
<th><span data-ttu-id="6fdfd-206">iPad</span><span class="sxs-lookup"><span data-stu-id="6fdfd-206">iPad</span></span></th>
<th><span data-ttu-id="6fdfd-207">Android</span><span class="sxs-lookup"><span data-stu-id="6fdfd-207">Android</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fdfd-208">.H エンコードの最大解像度</span><span class="sxs-lookup"><span data-stu-id="6fdfd-208">H.264 encoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-209">VGA</span><span class="sxs-lookup"><span data-stu-id="6fdfd-209">VGA</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-210">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="6fdfd-210">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="6fdfd-211">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="6fdfd-211">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="6fdfd-212">720p: iPhone 5S 以降</span><span class="sxs-lookup"><span data-stu-id="6fdfd-212">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-213">VGA: iPad 2 以降/iPad mini 1 以降</span><span class="sxs-lookup"><span data-stu-id="6fdfd-213">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="6fdfd-214">720p: iPad Air/iPad mini 2/iPad Pro 以降</span><span class="sxs-lookup"><span data-stu-id="6fdfd-214">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-215">デバイスモデルによっては最大 VGA</span><span class="sxs-lookup"><span data-stu-id="6fdfd-215">Up to VGA depending on device model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fdfd-216">.H デコードの最大解像度</span><span class="sxs-lookup"><span data-stu-id="6fdfd-216">H.264 decoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-217">VGA</span><span class="sxs-lookup"><span data-stu-id="6fdfd-217">VGA</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-218">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="6fdfd-218">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="6fdfd-219">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="6fdfd-219">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="6fdfd-220">720p: iPhone 5S 以降</span><span class="sxs-lookup"><span data-stu-id="6fdfd-220">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-221">VGA: iPad 2 以降/iPad mini 1 以降</span><span class="sxs-lookup"><span data-stu-id="6fdfd-221">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="6fdfd-222">720p: iPad Air/iPad mini 2/iPad Pro 以降</span><span class="sxs-lookup"><span data-stu-id="6fdfd-222">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="6fdfd-223">デバイスモデルによっては最大 VGA</span><span class="sxs-lookup"><span data-stu-id="6fdfd-223">Up to VGA depending on device model</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

