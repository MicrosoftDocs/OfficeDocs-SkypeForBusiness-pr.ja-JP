---
title: 'Lync Server 2013: Lync クライアントのビデオ要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync client video requirements
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49733731
ms.date: 01/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56743abd386cb59b177806eed3d441aaf587ccce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-client-video-requirements-for-lync-server-2013"></a><span data-ttu-id="5f03c-102">Lync Server 2013 の lync クライアントのビデオ要件</span><span class="sxs-lookup"><span data-stu-id="5f03c-102">Lync client video requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f03c-103">_**最終更新日:** 2016-01-29_</span><span class="sxs-lookup"><span data-stu-id="5f03c-103">_**Topic Last Modified:** 2016-01-29_</span></span>

<span data-ttu-id="5f03c-104">このセクションでは、Lync 2013 ビデオ通話向けのビデオハードウェアのサポートについて説明し、さまざまなコンピューター、タブレット、モバイルデバイスの構成に対して予想されるビデオ品質を決定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5f03c-104">This section describes video hardware support for Lync 2013 video calls and describes how to determine the expected video quality for various computer, tablet, and mobile device configurations.</span></span>

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a><span data-ttu-id="5f03c-105">Windows デスクトップとタブレットのビデオの要件と機能</span><span class="sxs-lookup"><span data-stu-id="5f03c-105">Windows Desktop and Tablet Video Requirements and Capabilities</span></span>

<span data-ttu-id="5f03c-106">Lync 2013 では、ビデオのエンコードとデコードのために、高度なビデオコーディング標準の3つに基づいて、ビデオのエンコードとデコードのためのハードウェアアクセラレータが導入されています。</span><span class="sxs-lookup"><span data-stu-id="5f03c-106">Lync 2013 introduces hardware acceleration for video encoding and decoding based on the H.264/MPEG-4 Part 10 Advanced Video Coding standard.</span></span> <span data-ttu-id="5f03c-107">この機能により、CPU クロック速度が低いコンピューターが高い解像度のビデオをエンコードおよびデコードできます。</span><span class="sxs-lookup"><span data-stu-id="5f03c-107">This feature allows computers with lower CPU clock speeds to encode and decode higher resolution video.</span></span> <span data-ttu-id="5f03c-108">ビデオ ハードウェア要件は、コンピューター構成と必要なビデオ解像度によって異なります。</span><span class="sxs-lookup"><span data-stu-id="5f03c-108">Video hardware requirements vary depending on the computer configuration and the video resolution wanted.</span></span>

<div>

## <a name="video-hardware-requirements"></a><span data-ttu-id="5f03c-109">ビデオハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="5f03c-109">Video Hardware Requirements</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f03c-110">機能</span><span class="sxs-lookup"><span data-stu-id="5f03c-110">Feature</span></span></th>
<th><span data-ttu-id="5f03c-111">要件</span><span class="sxs-lookup"><span data-stu-id="5f03c-111">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f03c-112">DirectX Video Acceleration (DXVA) を使用したハードウェア アクセラレータ H.264 デコード</span><span class="sxs-lookup"><span data-stu-id="5f03c-112">Hardware accelerated H.264 decoding using DirectX Video Acceleration (DXVA)</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5f03c-113">グラフィック カードでは、DirectX 9.0 がサポートされ、DXVA2_ModeH264_VLD_NoFGT デコード モードが公開される必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f03c-113">Graphics card must support DirectX 9.0 and must expose the DXVA2_ModeH264_VLD_NoFGT decoding mode.</span></span></p></li>
<li><p><span data-ttu-id="5f03c-114">最新のグラフィック カード ドライバーがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f03c-114">The latest graphics card driver must be installed.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="5f03c-115">デコードモードの詳細について<A href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</A>は、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f03c-115">For details about decoding modes, see <A href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</A>.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f03c-116">ハードウェア アクセラレータ H.264 エンコード: チップセット要件</span><span class="sxs-lookup"><span data-stu-id="5f03c-116">Hardware accelerated H.264 encoding: Chipset Requirements</span></span></p></td>
<td><p><span data-ttu-id="5f03c-117">次の Intel ハードウェア アクセラレータ ビデオ エンコード ソリューションがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="5f03c-117">The following Intel hardware accelerated video encoding solutions are supported:</span></span></p>
<ul>
<li><p><span data-ttu-id="5f03c-118">第2世代および第3世代 Intel HD グラフィックス2000、2500、3000、4000チップセット (またはそれ以降のバージョン) と、統合されたハードウェアビデオエンコーダー。</span><span class="sxs-lookup"><span data-stu-id="5f03c-118">Second and third generation Intel HD Graphics 2000, 2500, 3000, and 4000 chipsets (or later versions) with integrated hardware video encoders.</span></span> <span data-ttu-id="5f03c-119">Intel HD Graphics ドライバー 15.28.9.2884 または以下を含む最新ドライバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="5f03c-119">Installation of the Intel HD Graphics driver 15.28.9.2884 or the latest driver containing the following is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="5f03c-120">ディスプレイ ドライバー 9.17.10.2884 または最新ドライバー</span><span class="sxs-lookup"><span data-stu-id="5f03c-120">Display driver 9.17.10.2884 or the latest driver</span></span></p></li>
<li><p><span data-ttu-id="5f03c-121">HMFT (Hardware Media Foundation Transform) バージョン 3.12.10.31 または最新 HMFT</span><span class="sxs-lookup"><span data-stu-id="5f03c-121">Hardware media foundation transform (HMFT) version 3.12.10.31 or the latest HMFT</span></span></p></li>
</ul></li>
</ul>
<p><span data-ttu-id="5f03c-122">次の AMD ハードウェアアクセラレータに対応したビデオエンコードソリューションがサポートされています (Lync Server 2013 の CU1 の更新が必要です)。</span><span class="sxs-lookup"><span data-stu-id="5f03c-122">The following AMD hardware accelerated video encoding solutions are supported (requires CU1 Updates for Lync Server 2013):</span></span></p>
<ul>
<li><p><span data-ttu-id="5f03c-p103">AMD Video Codec Engine は、いくつかの個別のグラフィック カードおよび AMD A-Series Accelerated Processor の統合 APU (Accelerated Processing Unit) で利用できます。AMD Video Codec Engine ドライバー 9.12.0.0 またはそれ以上がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f03c-p103">AMD Video Codec Engine, which is available in several discrete graphics cards and in integrated accelerated processing units of AMD A-Series Accelerated Processors. The AMD Video Codec Engine driver 9.12.0.0 or higher must be installed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f03c-125">ハードウェア アクセラレータ H.264 エンコード: カメラ要件</span><span class="sxs-lookup"><span data-stu-id="5f03c-125">Hardware accelerated H.264 encoding: Camera Requirements</span></span></p></td>
<td><p><span data-ttu-id="5f03c-126">USB ビデオ クラス (UVC) 仕様バージョン 1.5 に準拠する統合 H.264 ハードウェア エンコーダーを搭載した USB ビデオ カメラ。</span><span class="sxs-lookup"><span data-stu-id="5f03c-126">USB video cameras with integrated H.264 hardware encoder that conforms to the USB Video Class (UVC) specification version 1.5.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="5f03c-127">Lync 2013 は、Windows 8 または Windows 8.1 で UVC 1.5 カメラをサポートしています。 UVC 1.5 のサポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5f03c-127">Lync 2013 supports UVC 1.5 cameras with Windows 8 or Windows 8.1, which includes support for UVC 1.5.</span></span> <span data-ttu-id="5f03c-128">Windows 7 には UVC 1.5 のサポートが含まれていないため、Lync 2013 は UVC 1.5 カメラを標準カメラとして扱うため、ハードウェアエンコードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5f03c-128">Because Windows 7 does not include support for UVC 1.5, Lync 2013 treats UVC 1.5 cameras as regular cameras with no hardware encoding support.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a><span data-ttu-id="5f03c-129">.H ビデオのエンコード機能とデコード機能を決定する</span><span class="sxs-lookup"><span data-stu-id="5f03c-129">Determining H.264 Video Encoding and Decoding Capabilities</span></span>

<span data-ttu-id="5f03c-130">一般に、特定のコンピューター構成の最大エンコードおよびデコード機能を決定する主な要因として、次の 4 つがあります。</span><span class="sxs-lookup"><span data-stu-id="5f03c-130">Generally, there are four major factors that determine the maximum encoding and decoding capability of a particular computer configuration:</span></span>

  - <span data-ttu-id="5f03c-131">DXVA を使用したハードウェア アクセラレータ デコードのサポート</span><span class="sxs-lookup"><span data-stu-id="5f03c-131">Support for hardware accelerated decoding by using DXVA</span></span>

  - <span data-ttu-id="5f03c-132">ハードウェア アクセラレータ エンコードのサポート</span><span class="sxs-lookup"><span data-stu-id="5f03c-132">Support for hardware accelerated encoding</span></span>

  - <span data-ttu-id="5f03c-133">物理コアの数</span><span class="sxs-lookup"><span data-stu-id="5f03c-133">Number of physical cores</span></span>

  - <span data-ttu-id="5f03c-134">Windows エクスペリエンス インデックス (WEI)</span><span class="sxs-lookup"><span data-stu-id="5f03c-134">Windows Experience Index (WEI)</span></span>

<span data-ttu-id="5f03c-135">Windows システム評価ツール (WinSAT) は、WEI を決定します。</span><span class="sxs-lookup"><span data-stu-id="5f03c-135">The Windows System Assessment Tool (WinSAT) determines the WEI.</span></span> <span data-ttu-id="5f03c-136">WinSAT ツールを実行すると、% windir%\\Performance\\WinSAT\\DataStore ディレクトリにあるコンピューター上に、正式な評価の XML ドキュメントが生成されます。</span><span class="sxs-lookup"><span data-stu-id="5f03c-136">When you run the WinSAT tool, it generates a Formal.Assessment XML document on the computer in the %windir%\\Performance\\WinSAT\\DataStore directory.</span></span> <span data-ttu-id="5f03c-137">この XML ファイルには、エンコードおよびデコード機能を決定するために特に重要な次の 2 つのスコアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5f03c-137">This XML file contains the following two scores that are of particular importance for determining encoding and decoding capabilities:</span></span>

  - <span data-ttu-id="5f03c-138">VideoEncodeScore は、コンピューターのソフトウェア ベースのビデオ エンコード機能を示します。</span><span class="sxs-lookup"><span data-stu-id="5f03c-138">The VideoEncodeScore indicates the software-based video encoding capability of the computer.</span></span>

  - <span data-ttu-id="5f03c-139">GraphicsScore 値は、コンピューターのハードウェア アクセラレータ エンコード機能を示します。</span><span class="sxs-lookup"><span data-stu-id="5f03c-139">The GraphicsScore value indicates the hardware accelerated encoding capability of the computer.</span></span>

<span data-ttu-id="5f03c-p106">次の 3 つの表で、サポートされるハードウェア アクセラレータによる、異なる種類の PC の最大エンコードおよびデコード機能を説明します。640x360 以上の解像度では、サポートされる最大フレーム レートは 30 フレーム/秒 (fps) です。640x360 より低い解像度では、サポートされる最大フレーム レートは 15 fps です。</span><span class="sxs-lookup"><span data-stu-id="5f03c-p106">The following three tables explain the maximum encoding and decoding capability for different PC types depending on what hardware acceleration they support. For resolutions of 640x360 and higher, the maximum supported frame rate is 30 frames per second (fps). For resolutions lower than 640x360, the maximum supported frame rate is 15 fps.</span></span>

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a><span data-ttu-id="5f03c-143">DXVA とハードウェア アクセラレータ エンコーダーのないコンピューター</span><span class="sxs-lookup"><span data-stu-id="5f03c-143">Computer Without DXVA And Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f03c-144">可能なエンコーダー解像度</span><span class="sxs-lookup"><span data-stu-id="5f03c-144">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="5f03c-145">可能なデコーダー解像度</span><span class="sxs-lookup"><span data-stu-id="5f03c-145">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="5f03c-146">要件</span><span class="sxs-lookup"><span data-stu-id="5f03c-146">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f03c-147">424x240</span><span class="sxs-lookup"><span data-stu-id="5f03c-147">424x240</span></span></p></td>
<td><p><span data-ttu-id="5f03c-148">424x240 (受信のみのシナリオでは 15fps で 640x360)</span><span class="sxs-lookup"><span data-stu-id="5f03c-148">424x240 (640x360 at 15fps for receive only scenarios)</span></span></p></td>
<td><p><span data-ttu-id="5f03c-149">1 コアと VideoEncodeScore ≥ 4.0</span><span class="sxs-lookup"><span data-stu-id="5f03c-149">1 Core and VideoEncodeScore ≥ 4.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f03c-150">640x360</span><span class="sxs-lookup"><span data-stu-id="5f03c-150">640x360</span></span></p></td>
<td><p><span data-ttu-id="5f03c-151">640x360</span><span class="sxs-lookup"><span data-stu-id="5f03c-151">640x360</span></span></p></td>
<td><p><span data-ttu-id="5f03c-152">2 コアと VideoEncodeScore ≥ 4.5</span><span class="sxs-lookup"><span data-stu-id="5f03c-152">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f03c-153">640x360</span><span class="sxs-lookup"><span data-stu-id="5f03c-153">640x360</span></span></p></td>
<td><p><span data-ttu-id="5f03c-154">1280x720</span><span class="sxs-lookup"><span data-stu-id="5f03c-154">1280x720</span></span></p></td>
<td><p><span data-ttu-id="5f03c-155">2 コアと VideoEncodeScore ≥ 4.5</span><span class="sxs-lookup"><span data-stu-id="5f03c-155">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f03c-156">640x360</span><span class="sxs-lookup"><span data-stu-id="5f03c-156">640x360</span></span></p></td>
<td><p><span data-ttu-id="5f03c-157">1920x1080</span><span class="sxs-lookup"><span data-stu-id="5f03c-157">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="5f03c-158">4 コアと VideoEncodeScore ≥ 4.5</span><span class="sxs-lookup"><span data-stu-id="5f03c-158">4 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f03c-159">1280x720</span><span class="sxs-lookup"><span data-stu-id="5f03c-159">1280x720</span></span></p></td>
<td><p><span data-ttu-id="5f03c-160">1280x720</span><span class="sxs-lookup"><span data-stu-id="5f03c-160">1280x720</span></span></p></td>
<td><p><span data-ttu-id="5f03c-161">4 コアと VideoEncodeScore ≥ 7.3</span><span class="sxs-lookup"><span data-stu-id="5f03c-161">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f03c-162">1280x720</span><span class="sxs-lookup"><span data-stu-id="5f03c-162">1280x720</span></span></p></td>
<td><p><span data-ttu-id="5f03c-163">1920x1080</span><span class="sxs-lookup"><span data-stu-id="5f03c-163">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="5f03c-164">4 コアと VideoEncodeScore ≥ 7.3</span><span class="sxs-lookup"><span data-stu-id="5f03c-164">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f03c-165">1920x1080</span><span class="sxs-lookup"><span data-stu-id="5f03c-165">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="5f03c-166">1920x1080</span><span class="sxs-lookup"><span data-stu-id="5f03c-166">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="5f03c-167">該当なし</span><span class="sxs-lookup"><span data-stu-id="5f03c-167">N/A</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a><span data-ttu-id="5f03c-168">DXVA があり、ハードウェア アクセラレータ エンコーダーのないコンピューター</span><span class="sxs-lookup"><span data-stu-id="5f03c-168">Computer With DXVA But Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f03c-169">可能なエンコーダー解像度</span><span class="sxs-lookup"><span data-stu-id="5f03c-169">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="5f03c-170">可能なデコーダー解像度</span><span class="sxs-lookup"><span data-stu-id="5f03c-170">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="5f03c-171">要件</span><span class="sxs-lookup"><span data-stu-id="5f03c-171">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f03c-172">424x240</span><span class="sxs-lookup"><span data-stu-id="5f03c-172">424x240</span></span></p></td>
<td><p><span data-ttu-id="5f03c-173">1920x1080</span><span class="sxs-lookup"><span data-stu-id="5f03c-173">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="5f03c-174">1 コアと VideoEncodeScore ≥ 3.0</span><span class="sxs-lookup"><span data-stu-id="5f03c-174">1 Core and VideoEncodeScore ≥ 3.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f03c-175">640x360</span><span class="sxs-lookup"><span data-stu-id="5f03c-175">640x360</span></span></p></td>
<td><p><span data-ttu-id="5f03c-176">1920x1080</span><span class="sxs-lookup"><span data-stu-id="5f03c-176">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="5f03c-177">2 コアと VideoEncodeScore ≥ 4.5</span><span class="sxs-lookup"><span data-stu-id="5f03c-177">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f03c-178">960x540</span><span class="sxs-lookup"><span data-stu-id="5f03c-178">960x540</span></span></p></td>
<td><p><span data-ttu-id="5f03c-179">1920x1080</span><span class="sxs-lookup"><span data-stu-id="5f03c-179">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="5f03c-180">2 コアと VideoEncodeScore ≥ 6.0</span><span class="sxs-lookup"><span data-stu-id="5f03c-180">2 Cores and VideoEncodeScore ≥ 6.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f03c-181">1280x720</span><span class="sxs-lookup"><span data-stu-id="5f03c-181">1280x720</span></span></p></td>
<td><p><span data-ttu-id="5f03c-182">1920x1080</span><span class="sxs-lookup"><span data-stu-id="5f03c-182">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="5f03c-183">4 コアと VideoEncodeScore ≥ 6.7</span><span class="sxs-lookup"><span data-stu-id="5f03c-183">4 Cores and VideoEncodeScore ≥ 6.7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f03c-184">1920x1080</span><span class="sxs-lookup"><span data-stu-id="5f03c-184">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="5f03c-185">1920x1080</span><span class="sxs-lookup"><span data-stu-id="5f03c-185">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="5f03c-186">4 コアと VideoEncodeScore ≥ 8.2</span><span class="sxs-lookup"><span data-stu-id="5f03c-186">4 Cores and VideoEncodeScore ≥ 8.2</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="5f03c-p107">Windows 7 での WinSAT スコアは最大 7.9 に制限されます。したがって、ハードウェア アクセラレータ エンコーダーのないコンピューターのエンコード能力は、Windows 8 または Windows 8.1 でのみ実現でき、その場合の最大 WinSAT スコアは 9.9 です。</span><span class="sxs-lookup"><span data-stu-id="5f03c-p107">The WinSAT score on Windows 7 is limited to a maximum of 7.9. Therefore, the encoding capability for a computer without a hardware accelerated encoder can only be achieved on Windows 8 or Windows 8.1, where the maximum WinSAT score is 9.9.</span></span>



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a><span data-ttu-id="5f03c-189">DXVA と Intel HD グラフィック ハードウェア アクセラレータ エンコーダーがあるコンピューター</span><span class="sxs-lookup"><span data-stu-id="5f03c-189">Computer With DXVA And With Intel HD Graphics Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f03c-190">可能なエンコーダー解像度</span><span class="sxs-lookup"><span data-stu-id="5f03c-190">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="5f03c-191">可能なデコーダー解像度</span><span class="sxs-lookup"><span data-stu-id="5f03c-191">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="5f03c-192">要件</span><span class="sxs-lookup"><span data-stu-id="5f03c-192">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f03c-193">1280x720</span><span class="sxs-lookup"><span data-stu-id="5f03c-193">1280x720</span></span></p></td>
<td><p><span data-ttu-id="5f03c-194">1920x1080</span><span class="sxs-lookup"><span data-stu-id="5f03c-194">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="5f03c-195">すべての第 2 世代および第 3 世代の Intel HD Graphics</span><span class="sxs-lookup"><span data-stu-id="5f03c-195">All 2nd and 3rd generation Intel HD Graphics</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f03c-196">1920x1080</span><span class="sxs-lookup"><span data-stu-id="5f03c-196">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="5f03c-197">1920x1080</span><span class="sxs-lookup"><span data-stu-id="5f03c-197">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="5f03c-198">第 2 世代および第 3 世代の Intel HD Graphics と GraphicsScore ≥ 5.0</span><span class="sxs-lookup"><span data-stu-id="5f03c-198">2nd and 3rd generation Intel HD Graphics and GraphicsScore ≥ 5.0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a><span data-ttu-id="5f03c-199">モバイルデバイスのビデオ機能</span><span class="sxs-lookup"><span data-stu-id="5f03c-199">Mobile Device Video Capabilities</span></span>

<span data-ttu-id="5f03c-200">次の表は、サポートされるモバイル デバイスの最高レベルのビデオ機能を示しています。</span><span class="sxs-lookup"><span data-stu-id="5f03c-200">The following table describes the maximum video capabilities for supported mobile devices.</span></span> <span data-ttu-id="5f03c-201">モバイルデバイスのサポートについて詳しくは、「 [Lync Server 2013 でのモバイルクライアントの計画](lync-server-2013-planning-for-mobile-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5f03c-201">For more information about mobile device support, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>


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
<th><span data-ttu-id="5f03c-202">機能</span><span class="sxs-lookup"><span data-stu-id="5f03c-202">Feature</span></span></th>
<th><span data-ttu-id="5f03c-203">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="5f03c-203">Windows Phone</span></span></th>
<th><span data-ttu-id="5f03c-204">iPhone</span><span class="sxs-lookup"><span data-stu-id="5f03c-204">iPhone</span></span></th>
<th><span data-ttu-id="5f03c-205">iPad</span><span class="sxs-lookup"><span data-stu-id="5f03c-205">iPad</span></span></th>
<th><span data-ttu-id="5f03c-206">Android</span><span class="sxs-lookup"><span data-stu-id="5f03c-206">Android</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f03c-207">H.264 エンコードの最大解像度</span><span class="sxs-lookup"><span data-stu-id="5f03c-207">H.264 encoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="5f03c-208">VGA</span><span class="sxs-lookup"><span data-stu-id="5f03c-208">VGA</span></span></p></td>
<td><p><span data-ttu-id="5f03c-209">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="5f03c-209">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="5f03c-210">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="5f03c-210">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="5f03c-211">720p: iPhone 5S 以降</span><span class="sxs-lookup"><span data-stu-id="5f03c-211">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="5f03c-212">VGA: iPad 2 以降/iPad mini 1 以降</span><span class="sxs-lookup"><span data-stu-id="5f03c-212">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="5f03c-213">720p: iPad Air/iPad mini 2/iPad Pro 以降</span><span class="sxs-lookup"><span data-stu-id="5f03c-213">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="5f03c-214">デバイスのモデルに応じて VGA を最大にする</span><span class="sxs-lookup"><span data-stu-id="5f03c-214">Up to VGA depending on device model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f03c-215">H.264 デコードの最大解像度</span><span class="sxs-lookup"><span data-stu-id="5f03c-215">H.264 decoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="5f03c-216">VGA</span><span class="sxs-lookup"><span data-stu-id="5f03c-216">VGA</span></span></p></td>
<td><p><span data-ttu-id="5f03c-217">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="5f03c-217">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="5f03c-218">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="5f03c-218">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="5f03c-219">720p: iPhone 5S 以降</span><span class="sxs-lookup"><span data-stu-id="5f03c-219">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="5f03c-220">VGA: iPad 2 以降/iPad mini 1 以降</span><span class="sxs-lookup"><span data-stu-id="5f03c-220">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="5f03c-221">720p: iPad Air/iPad mini 2/iPad Pro 以降</span><span class="sxs-lookup"><span data-stu-id="5f03c-221">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="5f03c-222">デバイスのモデルに応じて VGA を最大にする</span><span class="sxs-lookup"><span data-stu-id="5f03c-222">Up to VGA depending on device model</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

