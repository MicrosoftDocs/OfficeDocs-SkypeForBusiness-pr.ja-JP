---
title: OMS を使用した Skype Room Systems バージョン 2 の管理を展開する
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: この資料では、マイクロソフトの運用管理スイートを使用して、エンド ・ ツー ・ エンドの統合された方法で Skype ルーム システム v2 のデバイスの管理を展開する方法について説明します。
ms.openlocfilehash: 0d0490d92a5513dad38a9ff6348a957204274878
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-management-with-oms"></a><span data-ttu-id="9a58a-103">OMS を使用した Skype Room Systems バージョン 2 の管理を展開する</span><span class="sxs-lookup"><span data-stu-id="9a58a-103">Deploy Skype Room Systems v2 management with OMS</span></span>
 
<span data-ttu-id="9a58a-104">この資料では、マイクロソフトの運用管理スイートを使用して、エンド ・ ツー ・ エンドの統合された方法で Skype ルーム システム v2 のデバイスの管理を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9a58a-104">This article discusses how to deploy management of Skype Room Systems v2 devices in an integrated, end-to-end manner using Microsoft Operations Management Suite.</span></span> 
  
<span data-ttu-id="9a58a-p101">Skype 会議室デバイスを管理するのに役立つ基本的なテレメトリを提供するように、Microsoft Operations Management Suite (OMS) を構成することができます。お使いの管理ソリューションでは、時間の経過とともに、デバイスのパフォーマンスのより詳細なビューを作成するために追加データや管理機能を購入できます。</span><span class="sxs-lookup"><span data-stu-id="9a58a-p101">You can configure Microsoft Operations Management Suite (OMS) to provide basic telemetry that will help you manage Skype meeting room devices. As your management solution matures, you can purchase additional data and management capabilities to create a more detailed view of device performance.</span></span>
  
<span data-ttu-id="9a58a-107">高いレベルでは、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a58a-107">At a high level, you need to perform the following tasks:</span></span>
  
1. [<span data-ttu-id="9a58a-108">OMS 管理のデバイスを構成する </span><span class="sxs-lookup"><span data-stu-id="9a58a-108">Configure devices for OMS Management </span></span>](with-oms.md#config_devices)
    
2. [<span data-ttu-id="9a58a-109">カスタム フィールドをマップする</span><span class="sxs-lookup"><span data-stu-id="9a58a-109">Map custom fields</span></span>](with-oms.md#Custom_fields)
    
3. [<span data-ttu-id="9a58a-110">OMS　での SRS v2 ビューを定義する</span><span class="sxs-lookup"><span data-stu-id="9a58a-110">Define the SRS v2 views in OMS</span></span>](with-oms.md#Views)
    
## <a name="find-and-record-device-locations-capabilities-and-configurations"></a><span data-ttu-id="9a58a-111">デバイスの場所、機能、構成を検索して記録する</span><span class="sxs-lookup"><span data-stu-id="9a58a-111">Find and record device locations, capabilities, and configurations</span></span>
<span data-ttu-id="9a58a-112"><a name="find_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="9a58a-112"></span></span>

<span data-ttu-id="9a58a-p102">最初のステップは、システム内のすべての装置、機能と構成の詳細、およびその場所についての詳細なデータベースを作成することです。小規模から中規模の組織では、この作業はスプレッドシートを使用することで十分対処できるでしょう。より大規模な組織の場合は、資産管理ツールやサードパーティのサービスを検討する必要があるかもしれません。いずれにしても、それぞれのデバイスについて、場所と関連情報をすべて記録することが重要になります。</span><span class="sxs-lookup"><span data-stu-id="9a58a-p102">The first step is to create a detailed database of all of the equipment in the system, the details of its capabilities and configuration, and its location. A spreadsheet may be adequate for this task in small to medium organizations. If you work at a larger organization, you may need to consider asset management tools and third-party services. What is important is that you record the location and all the relevant details of every device.</span></span>
  
<span data-ttu-id="9a58a-117">作業が完了したら、その情報を使用して、技術者を派遣したり、デバイスパッチやアップグレードを管理したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="9a58a-117">Once that work is done, you can use this information to dispatch technicians and manage device patches and upgrades.</span></span>
  
## <a name="configure-devices-for-oms-management"></a><span data-ttu-id="9a58a-118">OMS 管理のデバイスを構成する </span><span class="sxs-lookup"><span data-stu-id="9a58a-118">Configure devices for OMS Management</span></span>
<span data-ttu-id="9a58a-119"><a name="config_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="9a58a-119"></span></span>

<span data-ttu-id="9a58a-120">SRS の各デバイスの[接続の Windows Azure のログ分析サービス コンピューター](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents)に指示に従います。</span><span class="sxs-lookup"><span data-stu-id="9a58a-120">For each SRS device, follow the instructions found in [Connect Windows computers to the Log Analytics service in Azure](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents).</span></span>
  
## <a name="configure-oms-to-collect-device-event-logs"></a><span data-ttu-id="9a58a-121">デバイスのイベント ログを収集するよう OMS を構成する</span><span class="sxs-lookup"><span data-stu-id="9a58a-121">Configure OMS to collect device event logs</span></span>
<span data-ttu-id="9a58a-122"><a name="config_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="9a58a-122"></span></span>

<span data-ttu-id="9a58a-123">[ログ分析では、Windows イベント ログ データ ソース](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)にある手順を使用して、SRS のデバイスからのイベント ログを収集するために OMS を特別に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a58a-123">You will need to specifically configure OMS to collect event logs from SRS devices using the steps at [Windows event log data sources in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events).</span></span> <span data-ttu-id="9a58a-124">SRS イベント ログを選択するのには「Skype ルーム システム」は、すべての種類のオプションのボックスをチェックする必要があります: エラー、警告、および情報です。</span><span class="sxs-lookup"><span data-stu-id="9a58a-124">The SRS event log to select is "Skype Room System" and you should check the option boxes for all types: Error, Warning and Information.</span></span>
  
## <a name="map-custom-fields"></a><span data-ttu-id="9a58a-125">カスタム フィールドをマップする</span><span class="sxs-lookup"><span data-stu-id="9a58a-125">Map custom fields</span></span>
<span data-ttu-id="9a58a-126"><a name="Custom_fields"> </a></span><span class="sxs-lookup"><span data-stu-id="9a58a-126"></span></span>

<span data-ttu-id="9a58a-127">[OMS でビューを定義する SRS v2](with-oms.md#Views)で作成したタイルを使用するには、ビューのユーザー設定フィールドを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a58a-127">Before the tiles created in the [Define the SRS v2 views in OMS](with-oms.md#Views) can be used, you'll need to create custom fields for your view.</span></span> <span data-ttu-id="9a58a-128">カスタム フィールドの作成の詳細については、[ログの分析でユーザー設定フィールド](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-custom-fields)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a58a-128">see [Custom fields in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-custom-fields) for details on creating custom fields.</span></span>
  
<span data-ttu-id="9a58a-129">OMS が自動的に追加、_CF、新しいフィールドを定義するとき、以下のマッピングを使用します。</span><span class="sxs-lookup"><span data-stu-id="9a58a-129">Use the mappings shown below, OMS will automatically add the _CF when defining the new field.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="9a58a-130">すべての JSON フィールドおよび OMS フィールドでは大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="9a58a-130">Remember that all JSON and OMS fields are case sensitive.</span></span> 
  
<span data-ttu-id="9a58a-131">**カスタム フィールドのマッピング**</span><span class="sxs-lookup"><span data-stu-id="9a58a-131">**Custom fields mapping**</span></span>

|<span data-ttu-id="9a58a-132">**JSON フィールド**</span><span class="sxs-lookup"><span data-stu-id="9a58a-132">**JSON field**</span></span>|<span data-ttu-id="9a58a-133">**OMS ユーザー設定フィールド**</span><span class="sxs-lookup"><span data-stu-id="9a58a-133">**OMS custom field**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9a58a-134">説明</span><span class="sxs-lookup"><span data-stu-id="9a58a-134">Description</span></span>  <br/> |<span data-ttu-id="9a58a-135">SRSEventDescription_CF</span><span class="sxs-lookup"><span data-stu-id="9a58a-135">SRSEventDescription_CF</span></span>  <br/> |
|<span data-ttu-id="9a58a-136">ResourceState</span><span class="sxs-lookup"><span data-stu-id="9a58a-136">ResourceState</span></span>  <br/> |<span data-ttu-id="9a58a-137">SRSResourceState_CF</span><span class="sxs-lookup"><span data-stu-id="9a58a-137">SRSResourceState_CF</span></span>  <br/> |
|<span data-ttu-id="9a58a-138">OperationName</span><span class="sxs-lookup"><span data-stu-id="9a58a-138">OperationName</span></span>  <br/> |<span data-ttu-id="9a58a-139">SRSOperationName_CF</span><span class="sxs-lookup"><span data-stu-id="9a58a-139">SRSOperationName_CF</span></span>  <br/> |
|<span data-ttu-id="9a58a-140">OperationResult</span><span class="sxs-lookup"><span data-stu-id="9a58a-140">OperationResult</span></span>  <br/> |<span data-ttu-id="9a58a-141">SRSOperationResult_CF</span><span class="sxs-lookup"><span data-stu-id="9a58a-141">SRSOperationResult_CF</span></span>  <br/> |
|<span data-ttu-id="9a58a-142">OS</span><span class="sxs-lookup"><span data-stu-id="9a58a-142">OS</span></span>  <br/> |<span data-ttu-id="9a58a-143">SRSOSVersion_CF</span><span class="sxs-lookup"><span data-stu-id="9a58a-143">SRSOSVersion_CF</span></span>  <br/> |
|<span data-ttu-id="9a58a-144">OSVersion</span><span class="sxs-lookup"><span data-stu-id="9a58a-144">OSVersion</span></span>  <br/> |<span data-ttu-id="9a58a-145">SRSOSLongVersion_CF</span><span class="sxs-lookup"><span data-stu-id="9a58a-145">SRSOSLongVersion_CF</span></span>  <br/> |
|<span data-ttu-id="9a58a-146">Alias</span><span class="sxs-lookup"><span data-stu-id="9a58a-146">Alias</span></span>  <br/> |<span data-ttu-id="9a58a-147">SRSAlias_CF</span><span class="sxs-lookup"><span data-stu-id="9a58a-147">SRSAlias_CF</span></span>  <br/> |
|<span data-ttu-id="9a58a-148">表示名</span><span class="sxs-lookup"><span data-stu-id="9a58a-148">DisplayName</span></span>  <br/> |<span data-ttu-id="9a58a-149">SRSDisplayName_CF</span><span class="sxs-lookup"><span data-stu-id="9a58a-149">SRSDisplayName_CF</span></span>  <br/> |
|<span data-ttu-id="9a58a-150">AppVersion</span><span class="sxs-lookup"><span data-stu-id="9a58a-150">AppVersion</span></span>  <br/> |<span data-ttu-id="9a58a-151">SRSAppVersion_CF</span><span class="sxs-lookup"><span data-stu-id="9a58a-151">SRSAppVersion_CF</span></span>  <br/> |
|<span data-ttu-id="9a58a-152">IPv4Address</span><span class="sxs-lookup"><span data-stu-id="9a58a-152">IPv4Address</span></span>  <br/> |<span data-ttu-id="9a58a-153">SRSIPv4Address_CF</span><span class="sxs-lookup"><span data-stu-id="9a58a-153">SRSIPv4Address_CF</span></span>  <br/> |
|<span data-ttu-id="9a58a-154">IPv6Address</span><span class="sxs-lookup"><span data-stu-id="9a58a-154">IPv6Address</span></span>  <br/> |<span data-ttu-id="9a58a-155">SRSIPv6Address_CF</span><span class="sxs-lookup"><span data-stu-id="9a58a-155">SRSIPv6Address_CF</span></span>  <br/> |
   
## <a name="define-the-srs-v2-views-in-oms"></a><span data-ttu-id="9a58a-156">OMS での SRS v2 ビューを定義する</span><span class="sxs-lookup"><span data-stu-id="9a58a-156">Define the SRS v2 views in OMS</span></span>
<span data-ttu-id="9a58a-157"><a name="Views"> </a></span><span class="sxs-lookup"><span data-stu-id="9a58a-157"></span></span>

<span data-ttu-id="9a58a-158">データが収集され、カスタム フィールドがマップされると、OMS ビュー デザイナーを使用して SRS v2 イベントを監視するためのタイルを含んでいるダッシュボードを開発することができます。</span><span class="sxs-lookup"><span data-stu-id="9a58a-158">Once data is collected and custom fields are mapped, you can use OMS View Designer to develop a Dashboard containing Tiles to monitor SRS v2 events.</span></span> <span data-ttu-id="9a58a-159">ビュー デザイナーを使用して、次のタイルを作成するには、必要に応じて、[ログ分析機能でカスタム ビューを作成するビュー デザイナーの使用](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-view-designer)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a58a-159">Use View Designer to create the following tiles, refer to [Use View Designer to create custom views in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-view-designer) as necessary.</span></span>
  
### <a name="create-a-tile-that-shows-healthy-devices"></a><span data-ttu-id="9a58a-160">正常なデバイスを示すタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="9a58a-160">Create a tile that shows healthy devices</span></span>

1. <span data-ttu-id="9a58a-161">ケースを定義します。</span><span class="sxs-lookup"><span data-stu-id="9a58a-161">Define the case:</span></span> 
    
    <span data-ttu-id="9a58a-162">このタイルは、最近 10 分間にハートビート メッセージを送信したすべてのデバイスを表示します。</span><span class="sxs-lookup"><span data-stu-id="9a58a-162">This tile displays all devices that have sent a heartbeat message in the last 10 minutes.</span></span>
    
2. <span data-ttu-id="9a58a-163">グループ タイトルを割り当てます </span><span class="sxs-lookup"><span data-stu-id="9a58a-163">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="9a58a-164">新しいグループ ボックスを選択します</span><span class="sxs-lookup"><span data-stu-id="9a58a-164">Check the new group box</span></span>
    
4. <span data-ttu-id="9a58a-165">タイルの凡例のテキストを追加します</span><span class="sxs-lookup"><span data-stu-id="9a58a-165">Add the Tile legend text</span></span>
    
   ```
   All healthy devices (Heartbeat sent in last 10 minutes)
   ```

5. <span data-ttu-id="9a58a-166">タイルのクエリを入力します</span><span class="sxs-lookup"><span data-stu-id="9a58a-166">Enter the tile query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" TimeGenerated >NOW-10MINUTES|measure count() by SRSDisplayName_CF 
   ```

6. <span data-ttu-id="9a58a-167">リストのクエリを入力します</span><span class="sxs-lookup"><span data-stu-id="9a58a-167">Enter the list query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by SRSDisplayName_CF |Where LastHB>NOW-10MINUTES
   ```

7. <span data-ttu-id="9a58a-168">列のタイトル名を定義します</span><span class="sxs-lookup"><span data-stu-id="9a58a-168">Define column titles name</span></span>
    
   ```
   Display Name
   ```

8. <span data-ttu-id="9a58a-169">列のタイトルの値を定義します</span><span class="sxs-lookup"><span data-stu-id="9a58a-169">Define Column titles value</span></span>
    
   ```
   Last HB
   ```

9. <span data-ttu-id="9a58a-170">ナビゲーションのクエリを入力します</span><span class="sxs-lookup"><span data-stu-id="9a58a-170">Enter Navigation query</span></span>
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat"|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="create-the-tile-that-shows-devices-with-connectivity-issues"></a><span data-ttu-id="9a58a-171">接続に関する問題があるデバイスを示すタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="9a58a-171">Create the tile that shows devices with connectivity issues</span></span>

1. <span data-ttu-id="9a58a-172">ケースを定義します。</span><span class="sxs-lookup"><span data-stu-id="9a58a-172">Define the case:</span></span> 
    
    <span data-ttu-id="9a58a-p106">このタイルは、最近　10 分間にハートビート メッセージを送信していないデバイスをすべて表示します。これらのデバイスでは、ネットワーク接続、Exchange の接続、Skype for Business の接続に問題が発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9a58a-p106">This tile displays all devices that have not sent a heartbeat message in the last 10 minutes. These devices may be experiencing issues with network connectivity, Exchange connectivity, or Skype for Business connectivity.</span></span>
    
2. <span data-ttu-id="9a58a-175">グループ タイトルを割り当てます </span><span class="sxs-lookup"><span data-stu-id="9a58a-175">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="9a58a-176">新しいグループ ボックスを選択しません。</span><span class="sxs-lookup"><span data-stu-id="9a58a-176">Do not check the new group box.</span></span> <span data-ttu-id="9a58a-177">これは既にタイル 1 の作成時に済んでいるので、再び行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9a58a-177">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="9a58a-178">タイルの凡例のテキストを追加します</span><span class="sxs-lookup"><span data-stu-id="9a58a-178">Add the Tile legend text</span></span>
    
   ```
   Devices no longer sending Heartbeat messages
   ```

5. <span data-ttu-id="9a58a-179">タイルのクエリを入力します</span><span class="sxs-lookup"><span data-stu-id="9a58a-179">Enter the tile query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

6. <span data-ttu-id="9a58a-180">リストのクエリを入力します</span><span class="sxs-lookup"><span data-stu-id="9a58a-180">Enter the list query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

7. <span data-ttu-id="9a58a-181">列のタイトル名を定義します</span><span class="sxs-lookup"><span data-stu-id="9a58a-181">Define column titles name</span></span>
    
   ```
   Device Name
   ```

8. <span data-ttu-id="9a58a-182">列のタイトルの値を定義します</span><span class="sxs-lookup"><span data-stu-id="9a58a-182">Define Column titles Value</span></span> 
    
   ```
   Last HB
   ```

9. <span data-ttu-id="9a58a-183">ナビゲーションのクエリを入力します</span><span class="sxs-lookup"><span data-stu-id="9a58a-183">Enter Navigation query</span></span>
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-a-hardware-error"></a><span data-ttu-id="9a58a-184">ハードウェア エラーがあるデバイスを一覧表示する </span><span class="sxs-lookup"><span data-stu-id="9a58a-184">List devices with a hardware error</span></span>

1. <span data-ttu-id="9a58a-185">ケースを定義します。</span><span class="sxs-lookup"><span data-stu-id="9a58a-185">Define the case:</span></span> 
    
   <span data-ttu-id="9a58a-186">このタイルには、最後の 10 分の 1 つまたは複数のハードウェア コンポーネントの問題を示すメッセージを送信するすべてのデバイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9a58a-186">This tile displays all devices that sent a message indicating a one or more hardware component issues in the last 10 minutes.</span></span> 
    
2. <span data-ttu-id="9a58a-187">グループ タイトルを割り当てます</span><span class="sxs-lookup"><span data-stu-id="9a58a-187">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="9a58a-188">新しいグループ ボックスを選択しません。</span><span class="sxs-lookup"><span data-stu-id="9a58a-188">Do not check the new group box.</span></span> <span data-ttu-id="9a58a-189">これは既にタイル 1 の作成時に済んでいるので、再び行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9a58a-189">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="9a58a-190">タイルの凡例: </span><span class="sxs-lookup"><span data-stu-id="9a58a-190">Tile legend:</span></span> 
    
   ```
   Devices with a Hardware Error
   ```

5. <span data-ttu-id="9a58a-191">タイルのクエリ:</span><span class="sxs-lookup"><span data-stu-id="9a58a-191">Tile Query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure count() by SRSDisplayName_CF
   ```

6. <span data-ttu-id="9a58a-192">リストのクエリ:</span><span class="sxs-lookup"><span data-stu-id="9a58a-192">List query:</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by SRSDisplayName_CF
   ```

7. <span data-ttu-id="9a58a-193">列のタイトル名: </span><span class="sxs-lookup"><span data-stu-id="9a58a-193">Column titles Name:</span></span> 
    
   ```
   Display Name
   ```

8. <span data-ttu-id="9a58a-194">列のタイトル名: </span><span class="sxs-lookup"><span data-stu-id="9a58a-194">Column titles Value:</span></span> 
    
   ```
   Last Error
   ```

9. <span data-ttu-id="9a58a-195">ナビゲーションのクエリ: </span><span class="sxs-lookup"><span data-stu-id="9a58a-195">Navigation query:</span></span> 
    
   ```
   {selected item}  EventLevelName:Error EventID:3001|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-an-app-error"></a><span data-ttu-id="9a58a-196">アプリのエラーがあるデバイスを一覧表示する </span><span class="sxs-lookup"><span data-stu-id="9a58a-196">List devices with an App error</span></span>

1. <span data-ttu-id="9a58a-197">ケースを定義します。</span><span class="sxs-lookup"><span data-stu-id="9a58a-197">Define the case:</span></span> 
    
   <span data-ttu-id="9a58a-198">このタイルは最近 10 分間に 1 つまたは複数のアプリ コンポーネントのエラーを報告したすべての SRS デバイスを表示します</span><span class="sxs-lookup"><span data-stu-id="9a58a-198">This tile displays all SRS devices that report 1 or more app component errors within the last 10 minutes</span></span>
    
2. <span data-ttu-id="9a58a-199">グループ タイトルを割り当てます</span><span class="sxs-lookup"><span data-stu-id="9a58a-199">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="9a58a-200">新しいグループ ボックスを選択しません。</span><span class="sxs-lookup"><span data-stu-id="9a58a-200">Do not check the new group box.</span></span> <span data-ttu-id="9a58a-201">これは既にタイル 1 の作成時に済んでいるので、再び行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9a58a-201">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="9a58a-202">タイルの凡例: </span><span class="sxs-lookup"><span data-stu-id="9a58a-202">Tile legend:</span></span> 
   ``` 
    Device with App Errors (in prior 10 minutes)
   ``` 
5. <span data-ttu-id="9a58a-203">タイルのクエリ: </span><span class="sxs-lookup"><span data-stu-id="9a58a-203">Tile Query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure count() by Computer
   ```

6. <span data-ttu-id="9a58a-204">リストのクエリ: </span><span class="sxs-lookup"><span data-stu-id="9a58a-204">List query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by Computer
   ```

7. <span data-ttu-id="9a58a-205">列のタイトル名: </span><span class="sxs-lookup"><span data-stu-id="9a58a-205">Column titles Name:</span></span> 
    
   ```
   Device Name
   ```

8. <span data-ttu-id="9a58a-206">列のタイトル名: </span><span class="sxs-lookup"><span data-stu-id="9a58a-206">Column titles Value:</span></span> 
    
   ```
   Last Error
   ```

9. <span data-ttu-id="9a58a-207">ナビゲーションのクエリ:</span><span class="sxs-lookup"><span data-stu-id="9a58a-207">Navigation query:</span></span>
    
   ```
   {selected item} EventLevelName:Error|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-requiring-a-restart"></a><span data-ttu-id="9a58a-208">再起動を必要とするデバイスを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="9a58a-208">List devices requiring a restart</span></span>

1. <span data-ttu-id="9a58a-209">ケースを定義します。</span><span class="sxs-lookup"><span data-stu-id="9a58a-209">Define the case:</span></span> 
    
   <span data-ttu-id="9a58a-210">このタイルは過去 24 時間以内に再起動したすべての SRS デバイスと、再起動の回数を表示します。</span><span class="sxs-lookup"><span data-stu-id="9a58a-210">This tile displays all SRS devices that have been restarted in the past 24 hours and number of restarts</span></span>
    
2. <span data-ttu-id="9a58a-211">グループ タイトルを割り当てます</span><span class="sxs-lookup"><span data-stu-id="9a58a-211">Assign Group Title</span></span> 
    
  ```
  SRS v2
  ```

3. <span data-ttu-id="9a58a-212">新しいグループ ボックスを選択しません。</span><span class="sxs-lookup"><span data-stu-id="9a58a-212">Do not check the new group box.</span></span> <span data-ttu-id="9a58a-213">これは既にタイル 1 の作成時に済んでいるので、再び行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9a58a-213">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="9a58a-214">タイルの凡例: </span><span class="sxs-lookup"><span data-stu-id="9a58a-214">Tile legend:</span></span> 
    
   ```
   Devices with App restarted (past 24 hours)
   ```

5. <span data-ttu-id="9a58a-215">タイルのクエリ: </span><span class="sxs-lookup"><span data-stu-id="9a58a-215">Tile Query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count() by Computer
   ```

6. <span data-ttu-id="9a58a-216">リストのクエリ: </span><span class="sxs-lookup"><span data-stu-id="9a58a-216">List query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count(EventID) by SRSDisplayName_CF
   ```

7. <span data-ttu-id="9a58a-217">列のタイトル名: </span><span class="sxs-lookup"><span data-stu-id="9a58a-217">Column titles Name:</span></span> 
    
   ```
   Display Name
   ```

8. <span data-ttu-id="9a58a-218">列のタイトル名: </span><span class="sxs-lookup"><span data-stu-id="9a58a-218">Column titles Value:</span></span> 
    
   ```
   Number of restarts
   ```

9. <span data-ttu-id="9a58a-219">ナビゲーションのクエリ: </span><span class="sxs-lookup"><span data-stu-id="9a58a-219">Navigation query:</span></span> 
    
   ```
   {selected item} EventID:4000 TimeGenerated >NOW-24HOURS|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

<span data-ttu-id="9a58a-p111">これでビューの作成は完了です。現在利用できるアラートはすべてこれらの 1 つまたは複数のタイルで反映されます。</span><span class="sxs-lookup"><span data-stu-id="9a58a-p111">That completes view creation. The alerts currently available are all reflected in one or more of these tiles.</span></span>
## <a name="see-also"></a><span data-ttu-id="9a58a-222">この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。</span><span class="sxs-lookup"><span data-stu-id="9a58a-222">See also</span></span>
<span data-ttu-id="9a58a-223"><a name="Views"> </a></span><span class="sxs-lookup"><span data-stu-id="9a58a-223"></span></span>

#### 

[<span data-ttu-id="9a58a-224">OMS を使用して Skype ルーム システム v2 の管理を計画します。</span><span class="sxs-lookup"><span data-stu-id="9a58a-224">Plan Skype Room Systems v2 management with OMS</span></span>](../../plan-your-deployment/clients-and-devices/oms-management.md)
  
[<span data-ttu-id="9a58a-225">OMS を使用して Skype ルーム システム v2 のデバイスを管理します。</span><span class="sxs-lookup"><span data-stu-id="9a58a-225">Manage Skype Room Systems v2 devices with OMS</span></span>](../../manage/skype-room-systems-v2/oms.md)

