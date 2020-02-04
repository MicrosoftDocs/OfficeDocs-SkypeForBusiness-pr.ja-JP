---
title: 'Lync Server 2013: デバイス更新ログファイルの設定を変更する'
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
ms.openlocfilehash: 88d75086f0532205c2897f7e86d49f50072aaa89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="5f83a-102">Lync Server 2013 でデバイス更新ログファイルの設定を変更する</span><span class="sxs-lookup"><span data-stu-id="5f83a-102">Modify settings for Device Update log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f83a-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="5f83a-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="5f83a-104">Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、デバイスの更新情報が組織でどのように記録されるかに関する設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="5f83a-104">You can change settings for how device update information is logged in your organization by using Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="5f83a-105">次の表では、どの設定が変更可能で、どのツールを使用して設定を変更するかを示しています。</span><span class="sxs-lookup"><span data-stu-id="5f83a-105">The following table shows which settings are modifiable, and which tool(s) you use to modify the settings.</span></span>

<span data-ttu-id="5f83a-106">ログ設定は、グローバルに、またはサイトごとに変更したり、適用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5f83a-106">Log settings can be changed and applied globally, or per site.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f83a-107">変更方法</span><span class="sxs-lookup"><span data-stu-id="5f83a-107">To change</span></span></th>
<th><span data-ttu-id="5f83a-108">使用</span><span class="sxs-lookup"><span data-stu-id="5f83a-108">Use</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f83a-109">ログファイルの最大サイズ (バイト単位)</span><span class="sxs-lookup"><span data-stu-id="5f83a-109">The maximum size (in bytes) for a log file</span></span></p></td>
<td><p><span data-ttu-id="5f83a-110">Lync Server コントロール パネル</span><span class="sxs-lookup"><span data-stu-id="5f83a-110">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="5f83a-111">/</span><span class="sxs-lookup"><span data-stu-id="5f83a-111">-or-</span></span></p>
<p><span data-ttu-id="5f83a-112">Lync Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="5f83a-112">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f83a-113">キャッシュ内に保持できる情報の最大量 (バイト単位)</span><span class="sxs-lookup"><span data-stu-id="5f83a-113">The maximum amount of information (in bytes) that can be held in the cache</span></span></p></td>
<td><p><span data-ttu-id="5f83a-114">Lync Server コントロール パネル</span><span class="sxs-lookup"><span data-stu-id="5f83a-114">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="5f83a-115">/</span><span class="sxs-lookup"><span data-stu-id="5f83a-115">-or-</span></span></p>
<p><span data-ttu-id="5f83a-116">Lync Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="5f83a-116">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f83a-117">キャッシュされた情報をログファイルに書き込む頻度 (分)</span><span class="sxs-lookup"><span data-stu-id="5f83a-117">How often (in minutes) to write cached information to the log file</span></span></p></td>
<td><p><span data-ttu-id="5f83a-118">Lync Server コントロール パネル</span><span class="sxs-lookup"><span data-stu-id="5f83a-118">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="5f83a-119">/</span><span class="sxs-lookup"><span data-stu-id="5f83a-119">-or-</span></span></p>
<p><span data-ttu-id="5f83a-120">Lync Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="5f83a-120">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f83a-121">ログファイルを保持する期間 (日数)</span><span class="sxs-lookup"><span data-stu-id="5f83a-121">How long (in days) to keep log files</span></span></p></td>
<td><p><span data-ttu-id="5f83a-122">Lync Server コントロール パネル</span><span class="sxs-lookup"><span data-stu-id="5f83a-122">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="5f83a-123">/</span><span class="sxs-lookup"><span data-stu-id="5f83a-123">-or-</span></span></p>
<p><span data-ttu-id="5f83a-124">Lync Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="5f83a-124">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f83a-125">削除する必要がある有効期限が切れたファイルをチェックするタイミング (時刻)</span><span class="sxs-lookup"><span data-stu-id="5f83a-125">When (time of day) to check for expired files that should be deleted</span></span></p></td>
<td><p><span data-ttu-id="5f83a-126">Lync Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="5f83a-126">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f83a-127">許可するログファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="5f83a-127">What log file extensions to permit</span></span></p></td>
<td><p><span data-ttu-id="5f83a-128">Lync Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="5f83a-128">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f83a-129">保持するログファイルの種類</span><span class="sxs-lookup"><span data-stu-id="5f83a-129">Which log file types to retain</span></span></p></td>
<td><p><span data-ttu-id="5f83a-130">Lync Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="5f83a-130">Lync Server Management Shell</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="5f83a-131">Lync Server コントロールパネルを使用してログ設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="5f83a-131">To change logging settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="5f83a-132">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5f83a-132">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5f83a-133">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5f83a-133">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="5f83a-134">左側のナビゲーションバーで、[**クライアント**] をクリックし、[**デバイスログの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f83a-134">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="5f83a-135">[**デバイスログの構成**] ページで、変更する構成をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f83a-135">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="5f83a-136">[**ログ設定の編集**] ダイアログボックスで、次のいずれかの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="5f83a-136">In the **Edit Log Setting** dialog box, change any of the following settings:</span></span>
    
      - <span data-ttu-id="5f83a-137">**[ファイルの最大サイズ (バイト)**   ] は、ログファイルが削除されるまでの最大サイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="5f83a-137">**Maximum file size (bytes)**   Specifies the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="5f83a-138">既定値は1024000バイト (1 MB) です。</span><span class="sxs-lookup"><span data-stu-id="5f83a-138">The default is 1,024,000 bytes (1 MB).</span></span>
    
      - <span data-ttu-id="5f83a-139">**[最大キャッシュサイズ (バイト)**   ] は、キャッシュを消去する前にログファイルキャッシュに保持できる情報の最大量 (バイト単位) を指定します。データはログファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="5f83a-139">**Maximum cache size (bytes)**   Specifies the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="5f83a-140">既定値は512000バイト (0.5 MB) です。</span><span class="sxs-lookup"><span data-stu-id="5f83a-140">The default is 512,000 bytes (0.5 MB).</span></span>
    
      - <span data-ttu-id="5f83a-141">**キャッシュをフラッシュする分数 (1-60)**   ログファイルキャッシュに保存されている情報が実際のログファイルに書き込まれる頻度を示します。</span><span class="sxs-lookup"><span data-stu-id="5f83a-141">**Number of minutes to flush cache (1-60)**   Indicates how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="5f83a-142">データをログに記録すると、キャッシュが消去されます。</span><span class="sxs-lookup"><span data-stu-id="5f83a-142">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="5f83a-143">既定値は5分です。</span><span class="sxs-lookup"><span data-stu-id="5f83a-143">The default is five minutes.</span></span>
    
      - <span data-ttu-id="5f83a-144">**ログファイルを保持する日数 (1-365)**   ログファイルが削除されるまで保持される日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="5f83a-144">**Number of days to keep log files (1-365)**   Specifies the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="5f83a-145">既定値は10日です。</span><span class="sxs-lookup"><span data-stu-id="5f83a-145">The default is 10 days.</span></span>

5.  <span data-ttu-id="5f83a-146">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f83a-146">Click **Commit**.</span></span>

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5f83a-147">Windows PowerShell コマンドレットを使用したログ設定の変更</span><span class="sxs-lookup"><span data-stu-id="5f83a-147">Changing Logging Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5f83a-148">デバイス更新ログファイル設定は、Windows PowerShell と**Set-CsDeviceUpdateConfiguration**コマンドレットを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="5f83a-148">Device update log file settings can be modified by using Windows PowerShell and the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="5f83a-149">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="5f83a-149">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5f83a-150">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f83a-150">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="5f83a-151">次の例は、 **Set-CsDeviceUpdateConfiguration**を使って設定を変更するいくつかの方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5f83a-151">The following examples show a couple of the ways that you can use **Set-CsDeviceUpdateConfiguration** to modify settings.</span></span>

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a><span data-ttu-id="5f83a-152">ログファイルの最大サイズとログのクリーンアップ間隔を変更するには</span><span class="sxs-lookup"><span data-stu-id="5f83a-152">To modify the maximum log file size and the log cleanup interval</span></span>

  - <span data-ttu-id="5f83a-153">次のコマンドは、Redmond サイトに適用されるデバイス更新ログの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="5f83a-153">The following command modifies the device update log settings applied to the Redmond site.</span></span> <span data-ttu-id="5f83a-154">この例では、ログファイルの最大サイズは204800バイトに、ログのクリーンアップ間隔は14日間に設定されています。</span><span class="sxs-lookup"><span data-stu-id="5f83a-154">In this example, the maximum log file size is set to 204800 bytes and the log cleanup interval is set to 14 days.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a><span data-ttu-id="5f83a-155">ログのクリーンアップ時間を変更するには</span><span class="sxs-lookup"><span data-stu-id="5f83a-155">To modify the log cleanup time of day</span></span>

  - <span data-ttu-id="5f83a-156">このコマンドは、Redmond サイトのログクリーンアップ時間を 3:00 AM に設定します。</span><span class="sxs-lookup"><span data-stu-id="5f83a-156">This command sets the log cleanup time for the Redmond site to 3:00 AM.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

<span data-ttu-id="5f83a-157">詳細については、「 [Set-CsDeviceUpdateConfiguration 設定](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration)」コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f83a-157">For details, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

