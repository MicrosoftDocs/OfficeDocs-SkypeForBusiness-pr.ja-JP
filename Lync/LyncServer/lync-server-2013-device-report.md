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
ms.openlocfilehash: 93e750d66f3c18ee0960237ab5ffdfb37784f157
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="device-report-in-lync-server-2013"></a><span data-ttu-id="e0779-102">Lync Server 2013 のデバイスレポート</span><span class="sxs-lookup"><span data-stu-id="e0779-102">Device Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0779-103">_**トピックの最終更新日:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="e0779-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="e0779-104">デバイス レポートは、通話に関連した指標 (低品質通話のパーセンテージ、エコー、音声切り替え時間など) を通話で使用されたマイクとスピーカーによってグループ化して取得するため、マイクとスピーカーのレポートと呼んだほうが良いかもしれません。</span><span class="sxs-lookup"><span data-stu-id="e0779-104">The Device Report might be better titled the Microphone and Speakers Report; that's because the Device Report retrieves call-related metrics (such as poor call percentage, echo, and voice switch time) grouped by the microphones and speakers used in the call.</span></span> <span data-ttu-id="e0779-105">IP 電話 (一般に "デバイス" とも呼ばれます) について知りたい場合は、代わりに[Lync Server 2013 の Ip 電話インベントリレポート](lync-server-2013-ip-phone-inventory-report.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0779-105">If you are interested in IP phones (also commonly referred to as "devices"), use the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) instead.</span></span>

<span data-ttu-id="e0779-p102">デバイス レポートは、特定のタイプのデバイスで低品質通話が他のデバイスより多く発生しているかどうかを管理者が確認するのに非常に役立ちます。これは、新規デバイスを購入したり既存デバイスの置き換えたりする際に行わなければならない決定に影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e0779-p102">The Device Report is extremely useful for administrators in determining if a specific type of device is experiencing high volumes of poor quality calls than others. In turn, this could influence any decisions you must make when it comes time to buy new devices or to replace existing devices.</span></span>

<span data-ttu-id="e0779-p103">既定では、デバイス レポートに表示される情報は、通話で使用されたマイク (キャプチャ デバイス) とスピーカー/ヘッドセット (レンダー デバイス) にも基づいています。たとえば、以下のキャプチャ デバイスとレンダー デバイスを使用する複数のユーザーがいるとします。</span><span class="sxs-lookup"><span data-stu-id="e0779-p103">By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call. For example, suppose you have several users who use the following capture device and the following render device: By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call. For example, suppose you have several users who use the following capture device and the following render device:</span></span>

  - <span data-ttu-id="e0779-111">キャプチャ デバイス -- マイク (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="e0779-111">Capture device -- Microphone (SoundMAX Integrated Digital HD Audio)</span></span>

  - <span data-ttu-id="e0779-112">レンダー デバイス -- ヘッドセット イヤホン (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="e0779-112">Render device -- Headset Earphone (Microsoft LifeChat LX-3000)</span></span>

<span data-ttu-id="e0779-113">これらのユーザーが合計 254 回の通話を行ったとすると、レポートには以下のようなエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0779-113">If those users made a total of 254 calls you'll see an entry like this in the report:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0779-114">キャプチャ デバイス</span><span class="sxs-lookup"><span data-stu-id="e0779-114">Capture device</span></span></th>
<th><span data-ttu-id="e0779-115">レンダー デバイス</span><span class="sxs-lookup"><span data-stu-id="e0779-115">Render device</span></span></th>
<th><span data-ttu-id="e0779-116">[通話ボリューム]</span><span class="sxs-lookup"><span data-stu-id="e0779-116">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0779-117">マイク (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="e0779-117">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="e0779-118">ヘッドセット イヤホン (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="e0779-118">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="e0779-119">254</span><span class="sxs-lookup"><span data-stu-id="e0779-119">254</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e0779-p104">次に、同じキャプチャ デバイスを使用するがレンダー デバイスは異なる複数のユーザーがいるとします。その場合、レポートにはキャプチャ デバイスとレンダー デバイスのその独自の組み合わせに関する 2 行目のエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0779-p104">Now, suppose you have a number of users who use that same capture device but a different render device. In that case, you'll have a second line entry in the report, one for that unique combination of capture device and render device:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0779-122">キャプチャ デバイス</span><span class="sxs-lookup"><span data-stu-id="e0779-122">Capture device</span></span></th>
<th><span data-ttu-id="e0779-123">レンダー デバイス</span><span class="sxs-lookup"><span data-stu-id="e0779-123">Render device</span></span></th>
<th><span data-ttu-id="e0779-124">[通話ボリューム]</span><span class="sxs-lookup"><span data-stu-id="e0779-124">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0779-125">マイク (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="e0779-125">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="e0779-126">ヘッドセット イヤホン (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="e0779-126">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="e0779-127">254</span><span class="sxs-lookup"><span data-stu-id="e0779-127">254</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0779-128">マイク (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="e0779-128">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="e0779-129">スピーカー (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="e0779-129">Speakers (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="e0779-130">319</span><span class="sxs-lookup"><span data-stu-id="e0779-130">319</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e0779-p105">特定のデバイスに関する合計 (たとえば、使用されたレンダー デバイスにかかわらず SoundMAX キャプチャ デバイスに関する合計) を表示するには、[デバイスの種類] ドロップダウン リストから適切なオプション ([キャプチャ デバイス] か [レンダー デバイス]) を選択します。この例で [キャプチャ デバイス] を選択すると、出力は以下のようになります。</span><span class="sxs-lookup"><span data-stu-id="e0779-p105">If you would rather see combined totals for a given device (for example, for the SoundMAX capture device, regardless of the render device used), select the appropriate option from the Device type dropdown list (either Capture device or Render device). If you select Capture device in this example, that will give you output similar to this:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0779-133">キャプチャ デバイス</span><span class="sxs-lookup"><span data-stu-id="e0779-133">Capture device</span></span></th>
<th><span data-ttu-id="e0779-134">通話ボリューム</span><span class="sxs-lookup"><span data-stu-id="e0779-134">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0779-135">マイク (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="e0779-135">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="e0779-136">573</span><span class="sxs-lookup"><span data-stu-id="e0779-136">573</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a><span data-ttu-id="e0779-137">デバイス レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="e0779-137">Accessing the Device Report</span></span>

<span data-ttu-id="e0779-138">デバイス レポートは通常、監視レポート ホーム ページからアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="e0779-138">The Device Report is typically accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="e0779-139">ただし、 [Lync Server 2013 で通話詳細レポート](lync-server-2013-call-detail-report.md)を表示している場合は、次のいずれかの指標をクリックすることで、特定のデバイスのデバイスレポートにドリルダウンできます。</span><span class="sxs-lookup"><span data-stu-id="e0779-139">However, if you are viewing the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) you can drill down to the Device Report for a specific device by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="e0779-140">キャプチャ デバイス</span><span class="sxs-lookup"><span data-stu-id="e0779-140">Capture Device</span></span>

  - <span data-ttu-id="e0779-141">レンダー デバイス</span><span class="sxs-lookup"><span data-stu-id="e0779-141">Render Device</span></span>

<span data-ttu-id="e0779-142">[デバイスレポート] では、次のいずれかの指標をクリックすることによって、 [Lync Server 2013 の通話リストレポート](lync-server-2013-call-list-report.md)にドリルダウンできます。</span><span class="sxs-lookup"><span data-stu-id="e0779-142">From the Device Report you can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="e0779-143">[通話ボリューム]</span><span class="sxs-lookup"><span data-stu-id="e0779-143">Call volume</span></span>

  - <span data-ttu-id="e0779-144">低品質通話のパーセンテージ</span><span class="sxs-lookup"><span data-stu-id="e0779-144">Poor call percentage</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a><span data-ttu-id="e0779-145">デバイス レポートの活用</span><span class="sxs-lookup"><span data-stu-id="e0779-145">Making the Best Use of the Device Report</span></span>

<span data-ttu-id="e0779-146">デバイス名に関して、デバイス レポートは非常に詳細です。たとえば、以下のキャプチャ デバイスがあるとします。</span><span class="sxs-lookup"><span data-stu-id="e0779-146">When it comes to device names, the Device Report is extremely detailed; for example, suppose you have the following capture devices:</span></span>

  - <span data-ttu-id="e0779-147">Aastra 3002 マイク (2- Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="e0779-147">Aastra 3002 Microphone (2- Aastra 3002)</span></span>

  - <span data-ttu-id="e0779-148">Aastra 3002 マイク (3- Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="e0779-148">Aastra 3002 Microphone (3- Aastra 3002)</span></span>

  - <span data-ttu-id="e0779-149">Aastra 3002 マイク (Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="e0779-149">Aastra 3002 Microphone (Aastra 3002)</span></span>

  - <span data-ttu-id="e0779-150">Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="e0779-150">Aastra 6725ip</span></span>

  - <span data-ttu-id="e0779-151">Aastra 6725ip マイク (10- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="e0779-151">Aastra 6725ip Microphone (10- Aastra 6725ip)</span></span>

  - <span data-ttu-id="e0779-152">Aastra 6725ip マイク (10- Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="e0779-152">Aastra 6725ip Microphone (10- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="e0779-153">Aastra 6725ip マイク (2- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="e0779-153">Aastra 6725ip Microphone (2- Aastra 6725ip)</span></span>

  - <span data-ttu-id="e0779-154">Aastra 6725ip マイク (3- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="e0779-154">Aastra 6725ip Microphone (3- Aastra 6725ip)</span></span>

  - <span data-ttu-id="e0779-155">Aastra 6725ip マイク (4- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="e0779-155">Aastra 6725ip Microphone (4- Aastra 6725ip)</span></span>

  - <span data-ttu-id="e0779-156">Aastra 6725ip マイク (5- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="e0779-156">Aastra 6725ip Microphone (5- Aastra 6725ip)</span></span>

  - <span data-ttu-id="e0779-157">Aastra 6725ip マイク (6- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="e0779-157">Aastra 6725ip Microphone (6- Aastra 6725ip)</span></span>

  - <span data-ttu-id="e0779-158">Aastra 6725ip マイク (7- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="e0779-158">Aastra 6725ip Microphone (7- Aastra 6725ip)</span></span>

  - <span data-ttu-id="e0779-159">Aastra 6725ip マイク (9- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="e0779-159">Aastra 6725ip Microphone (9- Aastra 6725ip)</span></span>

  - <span data-ttu-id="e0779-160">Aastra 6725ip マイク (9- Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="e0779-160">Aastra 6725ip Microphone (9- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="e0779-161">Aastra 6725ip マイク (Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="e0779-161">Aastra 6725ip Microphone (Aastra 6725ip)</span></span>

  - <span data-ttu-id="e0779-162">Aastra 6725ip マイク (Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="e0779-162">Aastra 6725ip Microphone (Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="e0779-163">Aastra 6725ip マイク (USB オーディオ デバイス)</span><span class="sxs-lookup"><span data-stu-id="e0779-163">Aastra 6725ip Microphone (USB Audio Device)</span></span>

  - <span data-ttu-id="e0779-164">Aastra 6725ip マイク (USB オーディオ デバイス)-V0</span><span class="sxs-lookup"><span data-stu-id="e0779-164">Aastra 6725ip Microphone (USB Audio Device)-V0</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e0779-165">ローカライズ版の Lync Server 2013 を実行している場合は、デバイス名をキャプチャすることは同じではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e0779-165">Keep in mind that capture device names might not be the same if you are running localized versions of Lync Server 2013.</span></span> <span data-ttu-id="e0779-166">米国英語で Aastra 6725ip Microphone (Aastra 6725ip)-V0 という名前のデバイスは、フランス語やスペイン語では名前が異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e0779-166">A device named Aastra 6725ip Microphone (Aastra 6725ip)-V0 in US English could have a different name in French or Spanish.</span></span>



</div>

<span data-ttu-id="e0779-167">このレベルの詳細度が必要な場合は多くありますが、別の場合には、モデル番号にかかわらず Aastra マイクを使用した通話の数がわかればそれで良い可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e0779-167">Often times you'll want that level of detail; at other times, however, you might only be interested in how many calls use any Aastra microphone, regardless of model number.</span></span> <span data-ttu-id="e0779-168">そのような情報を取得する方法の1つとして、デバイスレポートデータを Microsoft Excel にエクスポートし、そのデータをコンマ区切り値ファイル (たとえば、\\C\\:\_data Devices Report .csv) に保存する方法があります。</span><span class="sxs-lookup"><span data-stu-id="e0779-168">One way to get information like that is to export the Device Report data to Microsoft Excel and then save that data to a comma-separated values file (for example, C:\\Data\\Devices\_Report.csv).</span></span> <span data-ttu-id="e0779-169">その後、その .CSV ファイルを以下のような一連のコマンドを使用して Windows PowerShell にインポートし、Aastra キャプチャ デバイスを使用して行われた通話の合計数を戻します。</span><span class="sxs-lookup"><span data-stu-id="e0779-169">You can then use a set of commands similar to these to import the .CSV file into Windows PowerShell and report back the total number of calls made using an Aastra capture device:</span></span>

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

<span data-ttu-id="e0779-p109">これは、Aastra キャプチャ デバイスを使用して行われた通話の合計数を表す単一の値を戻します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e0779-p109">That will return a single value representing the total number of calls made using an Aastra capture device. For example:</span></span>

    384

</div>

<div>

## <a name="filters"></a><span data-ttu-id="e0779-172">フィルター</span><span class="sxs-lookup"><span data-stu-id="e0779-172">Filters</span></span>

<span data-ttu-id="e0779-p110">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。たとえば、デバイスレポートでは、通話の種類 (つまりクライアント通話かどうか)、電話会議、公衆交換電話網 (PSTN) 通話などに基づくフィルターを行えます。また、データをグループ化する方法を選択することもできます。この場合は、時間、日、週、または月を基準にデバイスがグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="e0779-p110">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Device Report enables you to filter on such things as call type (that is, was the call a client call), a conference call, or a public switched telephone network (PSTN) call. You can also choose how data should be grouped. In this case, devices are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="e0779-177">次の表に、デバイス レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="e0779-177">The following table lists the filters that you can use with the Device Report.</span></span>

### <a name="device-report-filters"></a><span data-ttu-id="e0779-178">デバイス レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="e0779-178">Device Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0779-179">名前</span><span class="sxs-lookup"><span data-stu-id="e0779-179">Name</span></span></th>
<th><span data-ttu-id="e0779-180">説明</span><span class="sxs-lookup"><span data-stu-id="e0779-180">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0779-181"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="e0779-181"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="e0779-p111">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="e0779-p111">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="e0779-184">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e0779-184">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e0779-p112">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="e0779-p112">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e0779-187">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e0779-187">7/7/2012</span></span></p>
<p><span data-ttu-id="e0779-188">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="e0779-188">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e0779-189">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e0779-189">7/3/2012</span></span></p>
<p><span data-ttu-id="e0779-190">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="e0779-190">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0779-191"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="e0779-191"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="e0779-p113">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="e0779-p113">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="e0779-194">7/7/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="e0779-194">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e0779-p114">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="e0779-p114">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e0779-197">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e0779-197">7/7/2012</span></span></p>
<p><span data-ttu-id="e0779-198">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="e0779-198">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e0779-199">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e0779-199">7/3/2012</span></span></p>
<p><span data-ttu-id="e0779-200">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="e0779-200">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0779-201">[<strong>音声切り替えの原因</strong>]</span><span class="sxs-lookup"><span data-stu-id="e0779-201"><strong>Voice switch cause</strong></span></span></p></td>
<td><p><span data-ttu-id="e0779-p115">エコーを防ぐために通話が半二重モードになった理由。半二重モードでは、トランシーバーで会話するときと同じように、通信は一方向ずつでのみ行えます。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0779-p115">Reason why a call had to be placed into half duplex mode in order to prevent echo. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-205">いずれ</span><span class="sxs-lookup"><span data-stu-id="e0779-205">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-206">なし</span><span class="sxs-lookup"><span data-stu-id="e0779-206">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-207">誤ったタイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="e0779-207">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-208">Echo</span><span class="sxs-lookup"><span data-stu-id="e0779-208">Echo</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-209">DNLP (Dynamic Nonlinear Processor)</span><span class="sxs-lookup"><span data-stu-id="e0779-209">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-210">低い複雑度</span><span class="sxs-lookup"><span data-stu-id="e0779-210">Low complexity</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-211">不良なデバイス状態</span><span class="sxs-lookup"><span data-stu-id="e0779-211">Bad device state</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-212">AEC 後のエコー (アコーステック エコー キャンセレーション)</span><span class="sxs-lookup"><span data-stu-id="e0779-212">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0779-213">[<strong>エコーの原因</strong>]</span><span class="sxs-lookup"><span data-stu-id="e0779-213"><strong>Echo cause</strong></span></span></p></td>
<td><p><span data-ttu-id="e0779-p116">容認されるレベルを超えるエコーが検出された理由。(通信のエコーとは音の反響のことで、井戸の底に向かって叫んだときに聞こえるのと同じ現象です)。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0779-p116">Reason why echo above the accepted level was detected in a call. (In telecommunications, echo is a reflection of sound, the same phenomenon you will hear if you yell down to the bottom of a well.) Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-216">いずれ</span><span class="sxs-lookup"><span data-stu-id="e0779-216">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-217">なし</span><span class="sxs-lookup"><span data-stu-id="e0779-217">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-218">誤ったタイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="e0779-218">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-219">AEC 後のエコー (アコーステック エコー キャンセレーション)</span><span class="sxs-lookup"><span data-stu-id="e0779-219">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-220">ANLP (Adaptive Nonlinear Processor)</span><span class="sxs-lookup"><span data-stu-id="e0779-220">ANLP (adaptive nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-221">DNLP (Dynamic Nonlinear Processor)</span><span class="sxs-lookup"><span data-stu-id="e0779-221">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-222">マイクのクリッピング</span><span class="sxs-lookup"><span data-stu-id="e0779-222">Microphone clipping</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0779-223">[<strong>通話の種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="e0779-223"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="e0779-p117">行われた通話の種類を示します。次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0779-p117">Indicates the type of call that was made. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-226">いずれ</span><span class="sxs-lookup"><span data-stu-id="e0779-226">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-227">クライアント通話</span><span class="sxs-lookup"><span data-stu-id="e0779-227">Client call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-228">PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="e0779-228">PSTN call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-229">電話会議</span><span class="sxs-lookup"><span data-stu-id="e0779-229">Conference call</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0779-230">[<strong>アクセスの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="e0779-230"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="e0779-p118">クライアントが通話時に内部ネットワークにログオンしたか、外部ネットワークにログオンしたかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0779-p118">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-233">いずれ</span><span class="sxs-lookup"><span data-stu-id="e0779-233">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-234">内部</span><span class="sxs-lookup"><span data-stu-id="e0779-234">Internal</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-235">External</span><span class="sxs-lookup"><span data-stu-id="e0779-235">External</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0779-236">[<strong>ネットワークの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="e0779-236"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="e0779-p119">通話時にクライアントが接続したネットワークの種類を示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0779-p119">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-239">いずれ</span><span class="sxs-lookup"><span data-stu-id="e0779-239">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-240">有線</span><span class="sxs-lookup"><span data-stu-id="e0779-240">Wired</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-241">通信</span><span class="sxs-lookup"><span data-stu-id="e0779-241">Wireless</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0779-242"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="e0779-242"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="e0779-p120">通話時に外部クライアントが仮想プライベート ネットワーク (VPN) 接続を使用したかどうかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0779-p120">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-245">いずれ</span><span class="sxs-lookup"><span data-stu-id="e0779-245">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-246">VPN</span><span class="sxs-lookup"><span data-stu-id="e0779-246">VPN</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-247">非 VPN</span><span class="sxs-lookup"><span data-stu-id="e0779-247">Non-VPN</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0779-248">[<strong>デバイスの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="e0779-248"><strong>Device type</strong></span></span></p></td>
<td><p><span data-ttu-id="e0779-p121">デバイスの種類を示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0779-p121">Indicates the type of device. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-251">キャプチャ デバイス</span><span class="sxs-lookup"><span data-stu-id="e0779-251">Capture device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-252">レンダー デバイス</span><span class="sxs-lookup"><span data-stu-id="e0779-252">Render device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="e0779-253">キャプチャ/レンダー デバイスのペア</span><span class="sxs-lookup"><span data-stu-id="e0779-253">Capture/Render device pair</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0779-254">[<strong>デバイス名</strong>]</span><span class="sxs-lookup"><span data-stu-id="e0779-254"><strong>Device name</strong></span></span></p></td>
<td><p><span data-ttu-id="e0779-p122">キャプチャまたはレンダー デバイスの名前。デバイス名の全体または一部を指定できます。たとえば、Microphone (Microsoft LifeCam VX-1000.) というデバイスを検索する場合には、次のように名前全体を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e0779-p122">Name of the capture or render device. You can enter the complete device name or any portion of the device name. For example, to find the device Microphone (Microsoft LifeCam VX-1000.), you can enter the complete device name as follows:</span></span></p>
<p><span data-ttu-id="e0779-258">Microphone (Microsoft LifeCam VX-1000.)</span><span class="sxs-lookup"><span data-stu-id="e0779-258">Microphone (Microsoft LifeCam VX-1000.)</span></span></p>
<p><span data-ttu-id="e0779-p123">または、名前の一部のみを指定することもできます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e0779-p123">Or, you can enter just a portion of the name. For example:</span></span></p>
<p><span data-ttu-id="e0779-261">LifeCam</span><span class="sxs-lookup"><span data-stu-id="e0779-261">LifeCam</span></span></p>
<p><span data-ttu-id="e0779-262">このフィルターでは、名前のどこかに文字列&quot;LifeCam&quot;が格納されているすべてのデバイスが返されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e0779-262">Note that the preceding filter returns any device that contains the string &quot;LifeCam&quot; anywhere in its name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="e0779-263">指標</span><span class="sxs-lookup"><span data-stu-id="e0779-263">Metrics</span></span>

<span data-ttu-id="e0779-264">次の表に、デバイス レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="e0779-264">The following table lists the information provided in the Device Report.</span></span>

### <a name="device-report-metrics"></a><span data-ttu-id="e0779-265">デバイス レポートの指標</span><span class="sxs-lookup"><span data-stu-id="e0779-265">Device Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0779-266">名前</span><span class="sxs-lookup"><span data-stu-id="e0779-266">Name</span></span></th>
<th><span data-ttu-id="e0779-267">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="e0779-267">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e0779-268">説明</span><span class="sxs-lookup"><span data-stu-id="e0779-268">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0779-269">[<strong>キャプチャ デバイス</strong>]</span><span class="sxs-lookup"><span data-stu-id="e0779-269"><strong>Capture device</strong></span></span></p></td>
<td><p><span data-ttu-id="e0779-270">はい</span><span class="sxs-lookup"><span data-stu-id="e0779-270">Yes</span></span></p></td>
<td><p><span data-ttu-id="e0779-271">音声の送信に使用されたデバイス (たとえばマイクや Web カメラ)。</span><span class="sxs-lookup"><span data-stu-id="e0779-271">Device (for example, a microphone or webcam) used for transmitting audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0779-272">[<strong>レンダー デバイス</strong>]</span><span class="sxs-lookup"><span data-stu-id="e0779-272"><strong>Render device</strong></span></span></p></td>
<td><p><span data-ttu-id="e0779-273">はい</span><span class="sxs-lookup"><span data-stu-id="e0779-273">Yes</span></span></p></td>
<td><p><span data-ttu-id="e0779-274">音声の受信に使用されたデバイス (たとえばヘッドセットやスピーカー)。</span><span class="sxs-lookup"><span data-stu-id="e0779-274">Device (for example, a headset or speakers) used for receiving audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0779-275">[<strong>通話ボリューム</strong>]</span><span class="sxs-lookup"><span data-stu-id="e0779-275"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="e0779-276">はい</span><span class="sxs-lookup"><span data-stu-id="e0779-276">Yes</span></span></p></td>
<td><p><span data-ttu-id="e0779-277">発信された通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="e0779-277">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0779-278">[<strong>低品質通話のパーセンテージ</strong>]</span><span class="sxs-lookup"><span data-stu-id="e0779-278"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="e0779-279">はい</span><span class="sxs-lookup"><span data-stu-id="e0779-279">Yes</span></span></p></td>
<td><p><span data-ttu-id="e0779-280">低品質として&quot;分類された通話のパーセンテージ。&quot;低品質通話とは、少なくとも1つの測定指標が許容値を超えている通話 (過度なジッターが発生した通話など) です。</span><span class="sxs-lookup"><span data-stu-id="e0779-280">Percentage of calls that were classified as &quot;poor.&quot; A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0779-281">[<strong>一意なユーザー</strong>]</span><span class="sxs-lookup"><span data-stu-id="e0779-281"><strong>Unique users</strong></span></span></p></td>
<td><p><span data-ttu-id="e0779-282">はい</span><span class="sxs-lookup"><span data-stu-id="e0779-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="e0779-p124">デバイスを使用した一意なユーザーの数。同じユーザーがデバイスを 13 回使用した場合でも、デバイスを 1 回のみ使用したユーザーと同じように、1 人の一意なユーザーとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="e0779-p124">Unique users who used the device. If a user used the device 13 times he or she would count as one unique user, the same as a user who only used the device a single time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0779-285">[<strong>音声切り替え時間の比率</strong>]</span><span class="sxs-lookup"><span data-stu-id="e0779-285"><strong>Ratio of voice switch time</strong></span></span></p></td>
<td><p><span data-ttu-id="e0779-286">はい</span><span class="sxs-lookup"><span data-stu-id="e0779-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="e0779-p125">エコーを防ぐために半二重モードでの実行が必要になった通話の比率。半二重モードでは、トランシーバーで会話するときと同じように、通信は一方向ずつでのみ行えます。</span><span class="sxs-lookup"><span data-stu-id="e0779-p125">Percentage of the call that had to be conducted in half duplex mode in order to prevent echo. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0779-289">[<strong>動作していないマイクの比率</strong>]</span><span class="sxs-lookup"><span data-stu-id="e0779-289"><strong>Ratio of microphone not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="e0779-290">はい</span><span class="sxs-lookup"><span data-stu-id="e0779-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="e0779-p126">キャプチャ デバイスが容認可能なレベルで機能していなかった通話の比率。この値が大きい場合、通話品質の問題の主な原因は、キャプチャ デバイスが想定どおりに機能しなかったことにあります。</span><span class="sxs-lookup"><span data-stu-id="e0779-p126">Percentage of the call in which the capture device was not functioning at an acceptable level. A high values suggests that quality issues with the call were primarily due to the capture device not working as expected.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0779-293">[<strong>動作していないスピーカーの比率</strong>]</span><span class="sxs-lookup"><span data-stu-id="e0779-293"><strong>Ratio of speaker not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="e0779-294">はい</span><span class="sxs-lookup"><span data-stu-id="e0779-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="e0779-p127">レンダー デバイスが容認可能なレベルで機能していなかった通話の比率。この値が大きい場合、通話品質の問題の主な原因は、レンダー デバイスが想定どおりに機能しなかったことにあります。</span><span class="sxs-lookup"><span data-stu-id="e0779-p127">Percentage of the call in which the render device was not functioning at an acceptable level. A high values suggests that quality issues with the call were primarily due to the render device not working as expected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0779-297">[<strong>音声切り替えが発生した通話 (%)</strong>]</span><span class="sxs-lookup"><span data-stu-id="e0779-297"><strong>Calls with voice switch (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="e0779-298">はい</span><span class="sxs-lookup"><span data-stu-id="e0779-298">Yes</span></span></p></td>
<td><p><span data-ttu-id="e0779-p128">半二重モードへの移行が必要になった通話全体のパーセンテージ。半二重モードでは、トランシーバーで会話するときと同じように、通信は一方向ずつでのみ行えます。</span><span class="sxs-lookup"><span data-stu-id="e0779-p128">Percentage of the total calls which had to be placed into half duplex mode. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0779-301">[<strong>エコー マイク (%)</strong>]</span><span class="sxs-lookup"><span data-stu-id="e0779-301"><strong>Echo microphone in (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="e0779-302">はい</span><span class="sxs-lookup"><span data-stu-id="e0779-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="e0779-303">マイクキャプチャストリームでエコーが検出された時間の割合。</span><span class="sxs-lookup"><span data-stu-id="e0779-303">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="e0779-304">通常、ヘッドホンまたはハンドセットの値は低く、スピーカーフォンまたはスタンドアロンスピーカーでは高です。</span><span class="sxs-lookup"><span data-stu-id="e0779-304">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="e0779-305">オンボード音響エコーキャンセレーションをサポートするデバイスでは、値が大きいと、エコーリークが発生します。</span><span class="sxs-lookup"><span data-stu-id="e0779-305">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="e0779-306">その他のデバイスでは、この指標を使用してデバイスの品質を評価することはできません。</span><span class="sxs-lookup"><span data-stu-id="e0779-306">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0779-307">[<strong>エコー送信 (%)</strong>]</span><span class="sxs-lookup"><span data-stu-id="e0779-307"><strong>Echo send (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="e0779-308">はい</span><span class="sxs-lookup"><span data-stu-id="e0779-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="e0779-309">他のユーザーに送信されたエコーのパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="e0779-309">Percentage of echo transmitted to other users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0779-310">[<strong>エコーが発生した通話 (%)</strong>]</span><span class="sxs-lookup"><span data-stu-id="e0779-310"><strong>Calls with echo (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="e0779-311">はい</span><span class="sxs-lookup"><span data-stu-id="e0779-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="e0779-312">容認可能なレベルを超えるエコーが発生した通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="e0779-312">Percentage of the total calls that had echo exceeding the acceptable level.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

