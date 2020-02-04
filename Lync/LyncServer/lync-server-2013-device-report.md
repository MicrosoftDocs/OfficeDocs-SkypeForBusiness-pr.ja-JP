---
title: 'Lync Server 2013: デバイスレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Report
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615049(v=OCS.15)
ms:contentKeyID: 48185807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc453ca1e83d8077e67ef130ef7a83e03c138be2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-report-in-lync-server-2013"></a><span data-ttu-id="c7a31-102">Lync Server 2013 のデバイスレポート</span><span class="sxs-lookup"><span data-stu-id="c7a31-102">Device Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7a31-103">_**最終更新日:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="c7a31-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="c7a31-104">デバイス レポートは、通話に関連した指標 (低品質通話のパーセンテージ、エコー、音声切り替え時間など) を通話で使用されたマイクとスピーカーによってグループ化して取得するため、マイクとスピーカーのレポートと呼んだほうが良いかもしれません。</span><span class="sxs-lookup"><span data-stu-id="c7a31-104">The Device Report might be better titled the Microphone and Speakers Report; that's because the Device Report retrieves call-related metrics (such as poor call percentage, echo, and voice switch time) grouped by the microphones and speakers used in the call.</span></span> <span data-ttu-id="c7a31-105">IP 電話 (通常は "デバイス" とも呼ばれます) に関心がある場合は、代わりに[Lync Server 2013 の Ip 電話インベントリレポート](lync-server-2013-ip-phone-inventory-report.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-105">If you are interested in IP phones (also commonly referred to as "devices"), use the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) instead.</span></span>

<span data-ttu-id="c7a31-p102">デバイス レポートは、特定のタイプのデバイスで低品質通話が他のデバイスより多く発生しているかどうかを管理者が確認するのに非常に役立ちます。これは、新規デバイスの購入や既存デバイスの置き換えの場合の決定に影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c7a31-p102">The Device Report is extremely useful for administrators in determining if a specific type of device is experiencing high volumes of poor quality calls than others. In turn, this could influence any decisions you must make when it comes time to buy new devices or to replace existing devices.</span></span>

<span data-ttu-id="c7a31-p103">既定では、デバイス レポートに表示される情報は、通話で使用されたマイク (キャプチャ デバイス) とスピーカー/ヘッドセット (レンダー デバイス) にも基づいています。たとえば、以下のキャプチャ デバイスとレンダー デバイスを使用する複数のユーザーがいるとします。</span><span class="sxs-lookup"><span data-stu-id="c7a31-p103">By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call. For example, suppose you have several users who use the following capture device and the following render device: By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call. For example, suppose you have several users who use the following capture device and the following render device:</span></span>

  - <span data-ttu-id="c7a31-111">キャプチャ デバイス -- マイク (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="c7a31-111">Capture device -- Microphone (SoundMAX Integrated Digital HD Audio)</span></span>

  - <span data-ttu-id="c7a31-112">レンダー デバイス -- ヘッドセット イヤホン (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="c7a31-112">Render device -- Headset Earphone (Microsoft LifeChat LX-3000)</span></span>

<span data-ttu-id="c7a31-113">これらのユーザーが合計 254 回の通話を行ったとすると、レポートには以下のようなエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7a31-113">If those users made a total of 254 calls you'll see an entry like this in the report:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7a31-114">キャプチャ デバイス</span><span class="sxs-lookup"><span data-stu-id="c7a31-114">Capture device</span></span></th>
<th><span data-ttu-id="c7a31-115">レンダー デバイス</span><span class="sxs-lookup"><span data-stu-id="c7a31-115">Render device</span></span></th>
<th><span data-ttu-id="c7a31-116">通話ボリューム</span><span class="sxs-lookup"><span data-stu-id="c7a31-116">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-117">マイク (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="c7a31-117">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="c7a31-118">ヘッドセット イヤホン (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="c7a31-118">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="c7a31-119">254</span><span class="sxs-lookup"><span data-stu-id="c7a31-119">254</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c7a31-p104">次に、同じキャプチャ デバイスを使用するがレンダー デバイスは異なる複数のユーザーがいるとします。その場合、レポートにはキャプチャ デバイスとレンダー デバイスのその独自の組み合わせに関する 2 行目のエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7a31-p104">Now, suppose you have a number of users who use that same capture device but a different render device. In that case, you'll have a second line entry in the report, one for that unique combination of capture device and render device:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7a31-122">[キャプチャ デバイス]</span><span class="sxs-lookup"><span data-stu-id="c7a31-122">Capture device</span></span></th>
<th><span data-ttu-id="c7a31-123">レンダー デバイス</span><span class="sxs-lookup"><span data-stu-id="c7a31-123">Render device</span></span></th>
<th><span data-ttu-id="c7a31-124">通話ボリューム</span><span class="sxs-lookup"><span data-stu-id="c7a31-124">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-125">マイク (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="c7a31-125">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="c7a31-126">ヘッドセット イヤホン (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="c7a31-126">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="c7a31-127">254</span><span class="sxs-lookup"><span data-stu-id="c7a31-127">254</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a31-128">マイク (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="c7a31-128">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="c7a31-129">スピーカー (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="c7a31-129">Speakers (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="c7a31-130">319</span><span class="sxs-lookup"><span data-stu-id="c7a31-130">319</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c7a31-p105">特定のデバイスに関する合計 (たとえば、使用されたレンダー デバイスにかかわらず SoundMAX キャプチャ デバイスに関する合計) を表示するには、[デバイスの種類] ドロップダウン リストから適切なオプション ([キャプチャ デバイス] か [レンダー デバイス]) を選択します。この例で [キャプチャ デバイス] を選択すると、出力は以下のようになります。</span><span class="sxs-lookup"><span data-stu-id="c7a31-p105">If you would rather see combined totals for a given device (for example, for the SoundMAX capture device, regardless of the render device used), select the appropriate option from the Device type dropdown list (either Capture device or Render device). If you select Capture device in this example, that will give you output similar to this:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7a31-133">キャプチャ デバイス</span><span class="sxs-lookup"><span data-stu-id="c7a31-133">Capture device</span></span></th>
<th><span data-ttu-id="c7a31-134">通話ボリューム</span><span class="sxs-lookup"><span data-stu-id="c7a31-134">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-135">マイク (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="c7a31-135">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="c7a31-136">573</span><span class="sxs-lookup"><span data-stu-id="c7a31-136">573</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a><span data-ttu-id="c7a31-137">デバイス レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="c7a31-137">Accessing the Device Report</span></span>

<span data-ttu-id="c7a31-138">デバイス レポートは通常、監視レポート ホーム ページからアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="c7a31-138">The Device Report is typically accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="c7a31-139">ただし、 [Lync Server 2013 で [通話の詳細] レポート](lync-server-2013-call-detail-report.md)を表示している場合は、次の指標のいずれかをクリックして、特定のデバイスのデバイスレポートにドリルダウンすることができます。</span><span class="sxs-lookup"><span data-stu-id="c7a31-139">However, if you are viewing the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) you can drill down to the Device Report for a specific device by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="c7a31-140">キャプチャ デバイス</span><span class="sxs-lookup"><span data-stu-id="c7a31-140">Capture Device</span></span>

  - <span data-ttu-id="c7a31-141">レンダー デバイス</span><span class="sxs-lookup"><span data-stu-id="c7a31-141">Render Device</span></span>

<span data-ttu-id="c7a31-142">デバイスレポートでは、次の指標のいずれかをクリックして、 [Lync Server 2013 の通話リストレポート](lync-server-2013-call-list-report.md)にドリルダウンすることができます。</span><span class="sxs-lookup"><span data-stu-id="c7a31-142">From the Device Report you can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="c7a31-143">通話ボリューム</span><span class="sxs-lookup"><span data-stu-id="c7a31-143">Call volume</span></span>

  - <span data-ttu-id="c7a31-144">低品質通話のパーセンテージ</span><span class="sxs-lookup"><span data-stu-id="c7a31-144">Poor call percentage</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a><span data-ttu-id="c7a31-145">デバイス レポートの活用</span><span class="sxs-lookup"><span data-stu-id="c7a31-145">Making the Best Use of the Device Report</span></span>

<span data-ttu-id="c7a31-146">デバイス名に関して、デバイス レポートは非常に詳細です。たとえば、以下のキャプチャ デバイスがあるとします。</span><span class="sxs-lookup"><span data-stu-id="c7a31-146">When it comes to device names, the Device Report is extremely detailed; for example, suppose you have the following capture devices:</span></span>

  - <span data-ttu-id="c7a31-147">Aastra 3002 マイク (2- Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="c7a31-147">Aastra 3002 Microphone (2- Aastra 3002)</span></span>

  - <span data-ttu-id="c7a31-148">Aastra 3002 マイク (3- Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="c7a31-148">Aastra 3002 Microphone (3- Aastra 3002)</span></span>

  - <span data-ttu-id="c7a31-149">Aastra 3002 マイク (Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="c7a31-149">Aastra 3002 Microphone (Aastra 3002)</span></span>

  - <span data-ttu-id="c7a31-150">Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="c7a31-150">Aastra 6725ip</span></span>

  - <span data-ttu-id="c7a31-151">Aastra 6725ip マイク (10- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="c7a31-151">Aastra 6725ip Microphone (10- Aastra 6725ip)</span></span>

  - <span data-ttu-id="c7a31-152">Aastra 6725ip マイク (10- Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="c7a31-152">Aastra 6725ip Microphone (10- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="c7a31-153">Aastra 6725ip マイク (2- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="c7a31-153">Aastra 6725ip Microphone (2- Aastra 6725ip)</span></span>

  - <span data-ttu-id="c7a31-154">Aastra 6725ip マイク (3- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="c7a31-154">Aastra 6725ip Microphone (3- Aastra 6725ip)</span></span>

  - <span data-ttu-id="c7a31-155">Aastra 6725ip マイク (4- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="c7a31-155">Aastra 6725ip Microphone (4- Aastra 6725ip)</span></span>

  - <span data-ttu-id="c7a31-156">Aastra 6725ip マイク (5- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="c7a31-156">Aastra 6725ip Microphone (5- Aastra 6725ip)</span></span>

  - <span data-ttu-id="c7a31-157">Aastra 6725ip マイク (6- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="c7a31-157">Aastra 6725ip Microphone (6- Aastra 6725ip)</span></span>

  - <span data-ttu-id="c7a31-158">Aastra 6725ip マイク (7- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="c7a31-158">Aastra 6725ip Microphone (7- Aastra 6725ip)</span></span>

  - <span data-ttu-id="c7a31-159">Aastra 6725ip マイク (9- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="c7a31-159">Aastra 6725ip Microphone (9- Aastra 6725ip)</span></span>

  - <span data-ttu-id="c7a31-160">Aastra 6725ip マイク (9-Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="c7a31-160">Aastra 6725ip Microphone (9- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="c7a31-161">Aastra 6725ip マイク (Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="c7a31-161">Aastra 6725ip Microphone (Aastra 6725ip)</span></span>

  - <span data-ttu-id="c7a31-162">Aastra 6725ip マイク (Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="c7a31-162">Aastra 6725ip Microphone (Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="c7a31-163">Aastra 6725ip マイク (USB オーディオデバイス)</span><span class="sxs-lookup"><span data-stu-id="c7a31-163">Aastra 6725ip Microphone (USB Audio Device)</span></span>

  - <span data-ttu-id="c7a31-164">Aastra 6725ip マイク (USB オーディオデバイス)-V0</span><span class="sxs-lookup"><span data-stu-id="c7a31-164">Aastra 6725ip Microphone (USB Audio Device)-V0</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7a31-165">ローカライズされたバージョンの Lync Server 2013 を実行している場合、デバイス名のキャプチャは同じではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c7a31-165">Keep in mind that capture device names might not be the same if you are running localized versions of Lync Server 2013.</span></span> <span data-ttu-id="c7a31-166">Aastra 6725ip マイク (Aastra 6725ip) という名前のデバイス (米国英語の V0 はフランス語またはスペイン語で異なる名前を持つ場合があります)。</span><span class="sxs-lookup"><span data-stu-id="c7a31-166">A device named Aastra 6725ip Microphone (Aastra 6725ip)-V0 in US English could have a different name in French or Spanish.</span></span>



</div>

<span data-ttu-id="c7a31-167">多くの場合、詳細レベルが必要になります。ただし、モデル番号に関係なく、複数の通話で Aastra マイクを使用することに関心がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="c7a31-167">Often times you'll want that level of detail; at other times, however, you might only be interested in how many calls use any Aastra microphone, regardless of model number.</span></span> <span data-ttu-id="c7a31-168">そのような情報を取得する方法の1つとして、デバイスレポートデータを Microsoft Excel にエクスポートし、そのデータをコンマ区切り値ファイル (たとえば、\\C\\:\_data Devices Report .csv) に保存します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-168">One way to get information like that is to export the Device Report data to Microsoft Excel and then save that data to a comma-separated values file (for example, C:\\Data\\Devices\_Report.csv).</span></span> <span data-ttu-id="c7a31-169">次のような一連のコマンドを使用して、をインポートできます。CSV ファイルを Windows PowerShell にコピーし、Aastra キャプチャデバイスを使って発信した通話の合計数を報告します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-169">You can then use a set of commands similar to these to import the .CSV file into Windows PowerShell and report back the total number of calls made using an Aastra capture device:</span></span>

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

<span data-ttu-id="c7a31-170">これは、Aastra キャプチャデバイスを使って発信した通話の合計数を表す1つの値を返します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-170">That will return a single value representing the total number of calls made using an Aastra capture device.</span></span> <span data-ttu-id="c7a31-171">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-171">For example:</span></span>

    384

</div>

<div>

## <a name="filters"></a><span data-ttu-id="c7a31-172">フィルター</span><span class="sxs-lookup"><span data-stu-id="c7a31-172">Filters</span></span>

<span data-ttu-id="c7a31-173">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざまな方法で表示したりする方法として利用できます。</span><span class="sxs-lookup"><span data-stu-id="c7a31-173">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="c7a31-174">たとえば、デバイスレポートでは、通話の種類 (クライアント呼び出しの呼び出し)、電話会議、公衆交換電話網 (PSTN) 通話など、さまざまな機能についてフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="c7a31-174">For example, the Device Report enables you to filter on such things as call type (that is, was the call a client call), a conference call, or a public switched telephone network (PSTN) call.</span></span> <span data-ttu-id="c7a31-175">また、データをグループ化する方法を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="c7a31-175">You can also choose how data should be grouped.</span></span> <span data-ttu-id="c7a31-176">この場合、デバイスは時間、日、週、または月でグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="c7a31-176">In this case, devices are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="c7a31-177">次の表に、デバイスレポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-177">The following table lists the filters that you can use with the Device Report.</span></span>

### <a name="device-report-filters"></a><span data-ttu-id="c7a31-178">デバイスレポートフィルター</span><span class="sxs-lookup"><span data-stu-id="c7a31-178">Device Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7a31-179">名前</span><span class="sxs-lookup"><span data-stu-id="c7a31-179">Name</span></span></th>
<th><span data-ttu-id="c7a31-180">説明</span><span class="sxs-lookup"><span data-stu-id="c7a31-180">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-181"><strong>開始</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-181"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-p111">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-p111">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="c7a31-184">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c7a31-184">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c7a31-p112">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-p112">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c7a31-187">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c7a31-187">7/7/2012</span></span></p>
<p><span data-ttu-id="c7a31-188">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="c7a31-188">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c7a31-189">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c7a31-189">7/3/2012</span></span></p>
<p><span data-ttu-id="c7a31-190">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="c7a31-190">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a31-191"><strong>終了</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-191"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-p113">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-p113">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="c7a31-194">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c7a31-194">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c7a31-p114">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-p114">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c7a31-197">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c7a31-197">7/7/2012</span></span></p>
<p><span data-ttu-id="c7a31-198">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="c7a31-198">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c7a31-199">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c7a31-199">7/3/2012</span></span></p>
<p><span data-ttu-id="c7a31-200">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="c7a31-200">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-201"><strong>音声スイッチの原因</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-201"><strong>Voice switch cause</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-202">エコーを防ぐために、通話が半二重モードになっていた理由。</span><span class="sxs-lookup"><span data-stu-id="c7a31-202">Reason why a call had to be placed into half duplex mode in order to prevent echo.</span></span> <span data-ttu-id="c7a31-203">半二重モードでは、トランシーバーを使用して通信している場合と同じように、通信は一度に1つの方向にしか伝達されません。</span><span class="sxs-lookup"><span data-stu-id="c7a31-203">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span> <span data-ttu-id="c7a31-204">次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-204">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-205">[すべて]</span><span class="sxs-lookup"><span data-stu-id="c7a31-205">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-206">なし</span><span class="sxs-lookup"><span data-stu-id="c7a31-206">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-207">不正なタイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="c7a31-207">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-208">Echo</span><span class="sxs-lookup"><span data-stu-id="c7a31-208">Echo</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-209">DNLP (動的非線形プロセッサ)</span><span class="sxs-lookup"><span data-stu-id="c7a31-209">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-210">複雑さが低い</span><span class="sxs-lookup"><span data-stu-id="c7a31-210">Low complexity</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-211">デバイスの状態が正しくない</span><span class="sxs-lookup"><span data-stu-id="c7a31-211">Bad device state</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-212">AEC 後のエコー (アコースティックエコーキャンセル)</span><span class="sxs-lookup"><span data-stu-id="c7a31-212">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a31-213"><strong>エコーの原因</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-213"><strong>Echo cause</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-214">通話で許可されたレベルより上のエコーが検出された理由。</span><span class="sxs-lookup"><span data-stu-id="c7a31-214">Reason why echo above the accepted level was detected in a call.</span></span> <span data-ttu-id="c7a31-215">(通信では、エコーはサウンドの反射になります。これと同じ現象が見られた場合は、通話の一番下まで移動しても聞こえます)。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-215">(In telecommunications, echo is a reflection of sound, the same phenomenon you will hear if you yell down to the bottom of a well.) Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-216">[すべて]</span><span class="sxs-lookup"><span data-stu-id="c7a31-216">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-217">なし</span><span class="sxs-lookup"><span data-stu-id="c7a31-217">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-218">不正なタイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="c7a31-218">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-219">AEC 後のエコー (アコースティックエコーキャンセル)</span><span class="sxs-lookup"><span data-stu-id="c7a31-219">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-220">ANLP (アダプティブ非線形プロセッサ)</span><span class="sxs-lookup"><span data-stu-id="c7a31-220">ANLP (adaptive nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-221">DNLP (動的非線形プロセッサ)</span><span class="sxs-lookup"><span data-stu-id="c7a31-221">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-222">マイクのクリップ</span><span class="sxs-lookup"><span data-stu-id="c7a31-222">Microphone clipping</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-223"><strong>通話の種類</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-223"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-224">行われた通話の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-224">Indicates the type of call that was made.</span></span> <span data-ttu-id="c7a31-225">次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-225">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-226">[すべて]</span><span class="sxs-lookup"><span data-stu-id="c7a31-226">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-227">クライアント通話</span><span class="sxs-lookup"><span data-stu-id="c7a31-227">Client call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-228">PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="c7a31-228">PSTN call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-229">電話会議</span><span class="sxs-lookup"><span data-stu-id="c7a31-229">Conference call</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a31-230"><strong>[アクセスの種類]</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-230"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-p118">クライアントが通話時に内部ネットワークにログオンしたか、外部ネットワークにログオンしたかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-p118">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-233">[すべて]</span><span class="sxs-lookup"><span data-stu-id="c7a31-233">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-234">内部</span><span class="sxs-lookup"><span data-stu-id="c7a31-234">Internal</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-235">外部</span><span class="sxs-lookup"><span data-stu-id="c7a31-235">External</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-236"><strong>[ネットワークの種類]</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-236"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-p119">通話時にクライアントが接続したネットワークの種類を示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-p119">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-239">[すべて]</span><span class="sxs-lookup"><span data-stu-id="c7a31-239">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-240">有線</span><span class="sxs-lookup"><span data-stu-id="c7a31-240">Wired</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-241">ワイヤレス</span><span class="sxs-lookup"><span data-stu-id="c7a31-241">Wireless</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a31-242"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-242"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-p120">通話時に外部クライアントが仮想プライベート ネットワーク (VPN) 接続を使用したかどうかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-p120">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-245">[すべて]</span><span class="sxs-lookup"><span data-stu-id="c7a31-245">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-246">VPN</span><span class="sxs-lookup"><span data-stu-id="c7a31-246">VPN</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-247">非 VPN</span><span class="sxs-lookup"><span data-stu-id="c7a31-247">Non-VPN</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-248"><strong>デバイスの種類</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-248"><strong>Device type</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-249">デバイスの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-249">Indicates the type of device.</span></span> <span data-ttu-id="c7a31-250">次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-250">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-251">キャプチャ デバイス</span><span class="sxs-lookup"><span data-stu-id="c7a31-251">Capture device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-252">レンダー デバイス</span><span class="sxs-lookup"><span data-stu-id="c7a31-252">Render device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c7a31-253">デバイスペアのキャプチャとレンダリング</span><span class="sxs-lookup"><span data-stu-id="c7a31-253">Capture/Render device pair</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a31-254"><strong>デバイス名</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-254"><strong>Device name</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-255">キャプチャまたはレンダーデバイスの名前。</span><span class="sxs-lookup"><span data-stu-id="c7a31-255">Name of the capture or render device.</span></span> <span data-ttu-id="c7a31-256">完全なデバイス名、またはデバイス名の任意の部分を入力できます。</span><span class="sxs-lookup"><span data-stu-id="c7a31-256">You can enter the complete device name or any portion of the device name.</span></span> <span data-ttu-id="c7a31-257">たとえば、デバイスマイク (Microsoft LifeCam VX-1000) を見つけるには、次のように完全なデバイス名を入力します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-257">For example, to find the device Microphone (Microsoft LifeCam VX-1000.), you can enter the complete device name as follows:</span></span></p>
<p><span data-ttu-id="c7a31-258">マイク (Microsoft LifeCam VX-1000)</span><span class="sxs-lookup"><span data-stu-id="c7a31-258">Microphone (Microsoft LifeCam VX-1000.)</span></span></p>
<p><span data-ttu-id="c7a31-259">または、名前の一部だけを入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="c7a31-259">Or, you can enter just a portion of the name.</span></span> <span data-ttu-id="c7a31-260">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-260">For example:</span></span></p>
<p><span data-ttu-id="c7a31-261">LifeCam</span><span class="sxs-lookup"><span data-stu-id="c7a31-261">LifeCam</span></span></p>
<p><span data-ttu-id="c7a31-262">上のフィルターでは、名前の任意の場所に&quot;文字列&quot; LifeCam が含まれているすべてのデバイスが返されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c7a31-262">Note that the preceding filter returns any device that contains the string &quot;LifeCam&quot; anywhere in its name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="c7a31-263">指標</span><span class="sxs-lookup"><span data-stu-id="c7a31-263">Metrics</span></span>

<span data-ttu-id="c7a31-264">次の表は、デバイスレポートに表示される情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="c7a31-264">The following table lists the information provided in the Device Report.</span></span>

### <a name="device-report-metrics"></a><span data-ttu-id="c7a31-265">デバイスレポートのメトリック</span><span class="sxs-lookup"><span data-stu-id="c7a31-265">Device Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7a31-266">名前</span><span class="sxs-lookup"><span data-stu-id="c7a31-266">Name</span></span></th>
<th><span data-ttu-id="c7a31-267">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="c7a31-267">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c7a31-268">説明</span><span class="sxs-lookup"><span data-stu-id="c7a31-268">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-269"><strong>デバイスをキャプチャする</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-269"><strong>Capture device</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-270">はい</span><span class="sxs-lookup"><span data-stu-id="c7a31-270">Yes</span></span></p></td>
<td><p><span data-ttu-id="c7a31-271">デバイス (マイクや web カメラなど) を使ってオーディオを送信します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-271">Device (for example, a microphone or webcam) used for transmitting audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a31-272"><strong>レンダリングデバイス</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-272"><strong>Render device</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-273">はい</span><span class="sxs-lookup"><span data-stu-id="c7a31-273">Yes</span></span></p></td>
<td><p><span data-ttu-id="c7a31-274">オーディオを受信するために使用されるデバイス (ヘッドセットやスピーカーなど)。</span><span class="sxs-lookup"><span data-stu-id="c7a31-274">Device (for example, a headset or speakers) used for receiving audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-275"><strong>通話ボリューム</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-275"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-276">可</span><span class="sxs-lookup"><span data-stu-id="c7a31-276">Yes</span></span></p></td>
<td><p><span data-ttu-id="c7a31-277">発信された通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="c7a31-277">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a31-278"><strong>低品質通話のパーセンテージ</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-278"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-279">可</span><span class="sxs-lookup"><span data-stu-id="c7a31-279">Yes</span></span></p></td>
<td><p><span data-ttu-id="c7a31-280">低品質として&quot;分類された通話の割合。&quot;低品質通話とは、測定されたメトリックの少なくとも1つが許可値 (過大なジッターを経験した呼び出しなど) を超えた呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="c7a31-280">Percentage of calls that were classified as &quot;poor.&quot; A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-281"><strong>一意のユーザー</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-281"><strong>Unique users</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-282">はい</span><span class="sxs-lookup"><span data-stu-id="c7a31-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="c7a31-283">デバイスを使用した一意のユーザー。</span><span class="sxs-lookup"><span data-stu-id="c7a31-283">Unique users who used the device.</span></span> <span data-ttu-id="c7a31-284">ユーザーがデバイスを13回使用した場合、1つの一意のユーザーとしてカウントされます。これは、そのデバイスを1回だけ使用したユーザーと同じです。</span><span class="sxs-lookup"><span data-stu-id="c7a31-284">If a user used the device 13 times he or she would count as one unique user, the same as a user who only used the device a single time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a31-285"><strong>音声切り替え時間の比率</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-285"><strong>Ratio of voice switch time</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-286">はい</span><span class="sxs-lookup"><span data-stu-id="c7a31-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="c7a31-287">エコーを防ぐために、半二重モードで実行する必要があった通話の割合。</span><span class="sxs-lookup"><span data-stu-id="c7a31-287">Percentage of the call that had to be conducted in half duplex mode in order to prevent echo.</span></span> <span data-ttu-id="c7a31-288">半二重モードでは、トランシーバーを使用して通信している場合と同じように、通信は一度に1つの方向にしか伝達されません。</span><span class="sxs-lookup"><span data-stu-id="c7a31-288">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-289"><strong>マイクの比率が機能しない</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-289"><strong>Ratio of microphone not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-290">はい</span><span class="sxs-lookup"><span data-stu-id="c7a31-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="c7a31-291">キャプチャデバイスが許容レベルで機能していなかった通話の割合。</span><span class="sxs-lookup"><span data-stu-id="c7a31-291">Percentage of the call in which the capture device was not functioning at an acceptable level.</span></span> <span data-ttu-id="c7a31-292">大きい値を指定すると、主に、キャプチャデバイスが予期したとおりに動作しないことが原因で、通話の品質の問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-292">A high values suggests that quality issues with the call were primarily due to the capture device not working as expected.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a31-293"><strong>スピーカーが機能しない場合の比率</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-293"><strong>Ratio of speaker not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-294">はい</span><span class="sxs-lookup"><span data-stu-id="c7a31-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="c7a31-295">レンダーデバイスが許容レベルで機能していなかった通話の割合。</span><span class="sxs-lookup"><span data-stu-id="c7a31-295">Percentage of the call in which the render device was not functioning at an acceptable level.</span></span> <span data-ttu-id="c7a31-296">高い値を指定すると、主に、レンダリングデバイスが予期したとおりに動作しないことが原因となって、通話の品質の問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-296">A high values suggests that quality issues with the call were primarily due to the render device not working as expected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-297"><strong>音声スイッチを使った通話 (%)</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-297"><strong>Calls with voice switch (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-298">はい</span><span class="sxs-lookup"><span data-stu-id="c7a31-298">Yes</span></span></p></td>
<td><p><span data-ttu-id="c7a31-299">半二重モードに設定された合計通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="c7a31-299">Percentage of the total calls which had to be placed into half duplex mode.</span></span> <span data-ttu-id="c7a31-300">半二重モードでは、トランシーバーを使用して通信している場合と同じように、通信は一度に1つの方向にしか伝達されません。</span><span class="sxs-lookup"><span data-stu-id="c7a31-300">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a31-301"><strong>エコーマイク (%)</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-301"><strong>Echo microphone in (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-302">はい</span><span class="sxs-lookup"><span data-stu-id="c7a31-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="c7a31-303">マイクのキャプチャストリームでエコーが検出された時間の割合。</span><span class="sxs-lookup"><span data-stu-id="c7a31-303">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="c7a31-304">一般的に、ヘッドセットまたはハンドセットの値は低く、スピーカーフォンやスタンドアロンスピーカーでは高くなります。</span><span class="sxs-lookup"><span data-stu-id="c7a31-304">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="c7a31-305">オンボード音響エコーキャンセルをサポートしているデバイスでは、高値を指定するとエコーリークが発生します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-305">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="c7a31-306">その他のデバイスでは、デバイスの品質を評価するためにこのメトリックを使用しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7a31-306">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-307"><strong>エコー送信 (%)</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-307"><strong>Echo send (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-308">はい</span><span class="sxs-lookup"><span data-stu-id="c7a31-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="c7a31-309">他のユーザーに送信されたエコーのパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="c7a31-309">Percentage of echo transmitted to other users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a31-310"><strong>エコー (%) で通話</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-310"><strong>Calls with echo (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-311">はい</span><span class="sxs-lookup"><span data-stu-id="c7a31-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="c7a31-312">エコーが許容レベルを超えていた合計通話の割合。</span><span class="sxs-lookup"><span data-stu-id="c7a31-312">Percentage of the total calls that had echo exceeding the acceptable level.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

