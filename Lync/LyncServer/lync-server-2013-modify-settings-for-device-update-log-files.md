---
title: 'Lync Server 2013: デバイス更新ログファイルの設定の変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify settings for Device Update log files
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48184975
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 770682cfed17d9b029688275469351c1cfdf9f4d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="5cf9d-102">Lync Server 2013 のデバイス更新ログファイルの設定を変更する</span><span class="sxs-lookup"><span data-stu-id="5cf9d-102">Modify settings for Device Update log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5cf9d-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="5cf9d-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="5cf9d-104">Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、組織内でのデバイス更新情報のログ記録方法の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-104">You can change settings for how device update information is logged in your organization by using Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="5cf9d-105">次の表に、変更可能な設定と、設定の変更に使用するツールを示します。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-105">The following table shows which settings are modifiable, and which tool(s) you use to modify the settings.</span></span>

<span data-ttu-id="5cf9d-106">ログ設定は、グローバルに、またはサイトごとに変更することができます。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-106">Log settings can be changed and applied globally, or per site.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5cf9d-107">を変更する</span><span class="sxs-lookup"><span data-stu-id="5cf9d-107">To change</span></span></th>
<th><span data-ttu-id="5cf9d-108">使用法</span><span class="sxs-lookup"><span data-stu-id="5cf9d-108">Use</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5cf9d-109">ログファイルの最大サイズ (バイト単位)</span><span class="sxs-lookup"><span data-stu-id="5cf9d-109">The maximum size (in bytes) for a log file</span></span></p></td>
<td><p><span data-ttu-id="5cf9d-110">Lync Server コントロール パネル</span><span class="sxs-lookup"><span data-stu-id="5cf9d-110">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="5cf9d-111">または</span><span class="sxs-lookup"><span data-stu-id="5cf9d-111">-or-</span></span></p>
<p><span data-ttu-id="5cf9d-112">Lync Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="5cf9d-112">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cf9d-113">キャッシュに保持できる情報の最大量 (バイト単位)</span><span class="sxs-lookup"><span data-stu-id="5cf9d-113">The maximum amount of information (in bytes) that can be held in the cache</span></span></p></td>
<td><p><span data-ttu-id="5cf9d-114">Lync Server コントロール パネル</span><span class="sxs-lookup"><span data-stu-id="5cf9d-114">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="5cf9d-115">または</span><span class="sxs-lookup"><span data-stu-id="5cf9d-115">-or-</span></span></p>
<p><span data-ttu-id="5cf9d-116">Lync Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="5cf9d-116">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cf9d-117">キャッシュされた情報をログファイルに書き込む頻度 (分単位)</span><span class="sxs-lookup"><span data-stu-id="5cf9d-117">How often (in minutes) to write cached information to the log file</span></span></p></td>
<td><p><span data-ttu-id="5cf9d-118">Lync Server コントロール パネル</span><span class="sxs-lookup"><span data-stu-id="5cf9d-118">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="5cf9d-119">または</span><span class="sxs-lookup"><span data-stu-id="5cf9d-119">-or-</span></span></p>
<p><span data-ttu-id="5cf9d-120">Lync Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="5cf9d-120">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cf9d-121">ログファイルを保持する時間 (日数)</span><span class="sxs-lookup"><span data-stu-id="5cf9d-121">How long (in days) to keep log files</span></span></p></td>
<td><p><span data-ttu-id="5cf9d-122">Lync Server コントロール パネル</span><span class="sxs-lookup"><span data-stu-id="5cf9d-122">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="5cf9d-123">または</span><span class="sxs-lookup"><span data-stu-id="5cf9d-123">-or-</span></span></p>
<p><span data-ttu-id="5cf9d-124">Lync Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="5cf9d-124">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cf9d-125">削除する必要のある期限切れファイルがあるかどうかをチェックする時間 (日)</span><span class="sxs-lookup"><span data-stu-id="5cf9d-125">When (time of day) to check for expired files that should be deleted</span></span></p></td>
<td><p><span data-ttu-id="5cf9d-126">Lync Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="5cf9d-126">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cf9d-127">許可するログファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="5cf9d-127">What log file extensions to permit</span></span></p></td>
<td><p><span data-ttu-id="5cf9d-128">Lync Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="5cf9d-128">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cf9d-129">保持するログファイルの種類</span><span class="sxs-lookup"><span data-stu-id="5cf9d-129">Which log file types to retain</span></span></p></td>
<td><p><span data-ttu-id="5cf9d-130">Lync Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="5cf9d-130">Lync Server Management Shell</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="5cf9d-131">Lync Server コントロールパネルを使用してログ設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="5cf9d-131">To change logging settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="5cf9d-132">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-132">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5cf9d-133">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-133">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="5cf9d-134">左側のナビゲーション バーで **[クライアント]** をクリックし、**[デバイス ログ構成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-134">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="5cf9d-135">**[デバイス ログ構成]** ページで、変更する構成をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-135">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="5cf9d-136">[**ログ設定の編集**] ダイアログボックスで、次のいずれかの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-136">In the **Edit Log Setting** dialog box, change any of the following settings:</span></span>
    
      - <span data-ttu-id="5cf9d-137">**[最大ファイルサイズ (バイト)**   ] ログファイルが削除されるまでの最大サイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-137">**Maximum file size (bytes)**   Specifies the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="5cf9d-138">既定値は1024000バイト (1 MB) です。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-138">The default is 1,024,000 bytes (1 MB).</span></span>
    
      - <span data-ttu-id="5cf9d-139">**[最大キャッシュサイズ (バイト)**   ] は、キャッシュがクリアされてデータがログファイルに書き込まれる前に、ログファイルキャッシュに保持できる最大情報量 (バイト単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-139">**Maximum cache size (bytes)**   Specifies the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="5cf9d-140">既定値は512000バイト (0.5 MB) です。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-140">The default is 512,000 bytes (0.5 MB).</span></span>
    
      - <span data-ttu-id="5cf9d-141">**キャッシュをフラッシュする時間 (分) (1-60)**   は、ログファイルキャッシュに格納されている情報が実際のログファイルに書き込まれる頻度を示します。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-141">**Number of minutes to flush cache (1-60)**   Indicates how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="5cf9d-142">データがログに記録されると、キャッシュはクリアされます。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-142">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="5cf9d-143">既定値は5分です。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-143">The default is five minutes.</span></span>
    
      - <span data-ttu-id="5cf9d-144">**ログファイルを保持する日数 (1-365)**   削除されるまでにログファイルを保持する日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-144">**Number of days to keep log files (1-365)**   Specifies the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="5cf9d-145">既定値は10日です。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-145">The default is 10 days.</span></span>

5.  <span data-ttu-id="5cf9d-146">**[確定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-146">Click **Commit**.</span></span>

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5cf9d-147">Windows PowerShell コマンドレットを使用してログ設定を変更する</span><span class="sxs-lookup"><span data-stu-id="5cf9d-147">Changing Logging Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5cf9d-148">デバイス更新のログファイルの設定を変更するには、Windows PowerShell と、 **-CsDeviceUpdateConfiguration 設定**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-148">Device update log file settings can be modified by using Windows PowerShell and the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="5cf9d-149">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-149">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5cf9d-150">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-150">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="5cf9d-151">次の例は、設定を変更するために、 **Set-CsDeviceUpdateConfiguration**を使用するいくつかの方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-151">The following examples show a couple of the ways that you can use **Set-CsDeviceUpdateConfiguration** to modify settings.</span></span>

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a><span data-ttu-id="5cf9d-152">ログファイルの最大サイズとログのクリーンアップ間隔を変更するには</span><span class="sxs-lookup"><span data-stu-id="5cf9d-152">To modify the maximum log file size and the log cleanup interval</span></span>

  - <span data-ttu-id="5cf9d-153">次のコマンドは、Redmond サイトに適用されているデバイス更新ログ設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-153">The following command modifies the device update log settings applied to the Redmond site.</span></span> <span data-ttu-id="5cf9d-154">この例では、ログファイルの最大サイズを204800バイトに設定し、ログのクリーンアップ間隔を14日に設定します。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-154">In this example, the maximum log file size is set to 204800 bytes and the log cleanup interval is set to 14 days.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a><span data-ttu-id="5cf9d-155">ログのクリーンアップ時間 (日) を変更するには</span><span class="sxs-lookup"><span data-stu-id="5cf9d-155">To modify the log cleanup time of day</span></span>

  - <span data-ttu-id="5cf9d-156">このコマンドは、Redmond サイトのログのクリーンアップ時間を 3:00 AM に設定します。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-156">This command sets the log cleanup time for the Redmond site to 3:00 AM.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

<span data-ttu-id="5cf9d-157">詳細につい[ては、このコマンドレット](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration)のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cf9d-157">For details, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

