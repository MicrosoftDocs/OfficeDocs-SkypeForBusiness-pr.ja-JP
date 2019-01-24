---
title: Azure のモニターを使用して Skype ルーム システム v2 の管理を計画します。
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
description: この資料では、Azure のモニターを使用してビジネスまたはチームの実装については、Skype の Skype ルーム システム v2 デバイスを管理するための計画に関する考慮事項について説明します。
ms.openlocfilehash: 53f77f1353668e4887a6ff41efd040dc8f418c7e
ms.sourcegitcommit: 09fcd68e30e7f83110f98172382c74f970b339a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2019
ms.locfileid: "29448474"
---
# <a name="plan-skype-room-systems-v2-management-with-azure-monitor"></a><span data-ttu-id="1f983-103">Azure のモニターを使用して Skype ルーム システム v2 の管理を計画します。</span><span class="sxs-lookup"><span data-stu-id="1f983-103">Plan Skype Room Systems v2 management with Azure Monitor</span></span>
 
 <span data-ttu-id="1f983-104">この資料では、Azure のモニターを使用してビジネス サーバーの実装については、Skype の Skype ルーム システム v2 デバイスを管理するための計画に関する考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="1f983-104">This article discusses planning considerations for using Azure Monitor to administer Skype Room Systems v2 devices in your Skype for Business Server implementation.</span></span>
  
<span data-ttu-id="1f983-105">[Azure のモニター](https://docs.microsoft.com/azure/azure-monitor/overview)は、最初からクラウドのように設計された管理サービスのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="1f983-105">[Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) is a collection of management services that were designed in the cloud from the start.</span></span> <span data-ttu-id="1f983-106">展開して、オンプレミスのリソースを管理するのではなく Azure モニターのコンポーネント完全 Azure でホストされます。</span><span class="sxs-lookup"><span data-stu-id="1f983-106">Rather than deploying and managing on-premise resources, Azure Monitor components are entirely hosted in Azure.</span></span> <span data-ttu-id="1f983-107">構成は最小限とする起動してそのまま数分で。</span><span class="sxs-lookup"><span data-stu-id="1f983-107">Configuration is minimal, and you can be up and running literally in a matter of minutes.</span></span> <span data-ttu-id="1f983-108">カスタマイズのいくつかの作業では、個々 の部屋のシステムでは、システムの稼働状態や障害のリアルタイムの通知を提供することによって Skype ルーム システム v2 の会議システムを管理することも役に立ち、数千の Skype ルームのシステムを管理するに拡張できる可能性があります。v2 の会議室です。</span><span class="sxs-lookup"><span data-stu-id="1f983-108">With some customization work, it can aid in managing Skype Room Systems v2 conferencing systems by providing real-time notifications of system health or faults for individual room systems, and it can potentially scale up to managing thousands of Skype Room Systems v2 conference rooms.</span></span>
  
<span data-ttu-id="1f983-109">この資料は、要件、設計とアーキテクチャ、および Skype ルーム システム v2 の会議デバイス、Azure のモニター ベースの管理を実装するために必要な実装のベスト プラクティスの説明が用意されていての詳細な記事へのリンクが用意されていますSkype ルーム システム v2 と Skype ルーム システム v2 の会議室の継続的な監視の重要な参照情報には、Azure のモニターを実装します。</span><span class="sxs-lookup"><span data-stu-id="1f983-109">This article provides a discussion of the requirements, design/architecture, and implementation best practices needed to implement Azure Monitor based management of Skype Room Systems v2 conference devices, and provides links to detailed articles on implementing Azure Monitor for Skype Room Systems v2 and critical reference information for ongoing monitoring of Skype Room Systems v2 rooms.</span></span> 
  
## <a name="functional-overview"></a><span data-ttu-id="1f983-110">機能の概要</span><span class="sxs-lookup"><span data-stu-id="1f983-110">Functional overview</span></span>

![Azure のモニターを使用した管理の SRS の図](../../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
<span data-ttu-id="1f983-112">Skype ルーム システムがコンソール デバイス上のアプリケーションを v2 では、Windows イベント ログにイベントを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="1f983-112">The Skype Room Systems v2 app on the console device writes events to its Windows Event Log.</span></span> <span data-ttu-id="1f983-113">Microsoft の監視のエージェントをインストールすると、Azure 監視サービスに情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="1f983-113">A Microsoft Monitoring agent, once installed, passes the information to Azure Monitor service.</span></span> 
  
<span data-ttu-id="1f983-114">1 回が正しく構成されて、イベントの各 Skype ルーム システム v2 のシステムが機能している方法と、どのような障害が検出されたを記述する説明に埋め込まれた JSON ペイロード ログ分析解析します。</span><span class="sxs-lookup"><span data-stu-id="1f983-114">Once properly configured, Log Analytics parses the JSON payload embedded in the event descriptions to describe how each Skype Room Systems v2 system is functioning and what faults are detected.</span></span> 
  
<span data-ttu-id="1f983-115">Azure のモニターを使用して管理者オフラインになっている Skype ルーム システム v2 のシステムの通知を受け取ることができますまたは、アプリケーション、接続、またはハードウェアの障害が発生しているだけでなく、システムを再起動する必要があるかどうかを知ること。</span><span class="sxs-lookup"><span data-stu-id="1f983-115">An administrator using Azure Monitor can get notifications of Skype Room Systems v2 systems that are offline or are experiencing app, connectivity, or hardware failures as well as knowing if a system needs to be restarted.</span></span> <span data-ttu-id="1f983-116">各システムのステータスは、これらの通知は、更新をリアルタイムに近いので、頻繁に更新されます。</span><span class="sxs-lookup"><span data-stu-id="1f983-116">Each system status is updated frequently, so these notifications are close to real-time updates.</span></span>
  
## <a name="azure-monitor-requirements"></a><span data-ttu-id="1f983-117">Azure の監視要件</span><span class="sxs-lookup"><span data-stu-id="1f983-117">Azure Monitor requirements</span></span>

<span data-ttu-id="1f983-118">Azure の監視ログ分析機能を使用するのに有効な Azure サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="1f983-118">You must have a valid Azure subscription for Azure Monitor to use Log Analytics feature.</span></span> <span data-ttu-id="1f983-119">所属する組織のためにサブスクリプションを用意するには、「Log Analytics ワークスペースを使って作業を開始する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f983-119">See [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) to create a subscription for your organization.</span></span>
  
<span data-ttu-id="1f983-120">ログ分析ビュー デザイナーを使用する方法を必要に応じて、理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f983-120">You should familiarize yourself as necessary on how to use the Log Analytics View Designer.</span></span> <span data-ttu-id="1f983-121">詳細についてはこれらの[ログ分析のビュー](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f983-121">See [Views in Log Analytics ](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) for those details.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="1f983-122">関連タスク</span><span class="sxs-lookup"><span data-stu-id="1f983-122">Related Tasks</span></span>

1. <span data-ttu-id="1f983-123">購読すると、Azure 監視ログ分析機能をカスタム作成のフィールド ([ユーザー設定フィールドをマップ](../../deploy/deploy-clients/azure-monitor.md#Custom_fields)に記載されている) 必要な Skype ルーム システム v2 本体から送信される情報を解析します。</span><span class="sxs-lookup"><span data-stu-id="1f983-123">Once subscribed to Azure Monitor Log Analytics, create custom fields (as described in [Map custom fields](../../deploy/deploy-clients/azure-monitor.md#Custom_fields)) needed to parse the information that will be sent from Skype Room Systems v2 consoles.</span></span> <span data-ttu-id="1f983-124">[ログ エントリを理解するの](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries)に記載されている JSON のスキーマを理解することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1f983-124">This includes understanding the JSON schema documented in [Understand the log entries](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries).</span></span>
    
2. <span data-ttu-id="1f983-125">ログ分析で Skype ルーム システム v2 の管理ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f983-125">Develop a Skype Room Systems v2 management view in Log Analytics.</span></span> <span data-ttu-id="1f983-126">いずれかの[インポート メソッドを使用して Skype ルーム システム v2 のダッシュ ボードを作成する](../../deploy/deploy-clients/azure-monitor.md#create-a-skype-room-systems-v2-dashboard-by-using-the-import-method)ことができます) [Skype ルーム システム v2 のダッシュ ボード](../../deploy/deploy-clients/azure-monitor.md#create-a-skype-room-systems-v2-dashboard-manually)を手動で作成します。</span><span class="sxs-lookup"><span data-stu-id="1f983-126">You can either [Create a Skype Room Systems v2 dashboard by using the import method](../../deploy/deploy-clients/azure-monitor.md#create-a-skype-room-systems-v2-dashboard-by-using-the-import-method) ) or [Create a Skype Room Systems v2 dashboard manually](../../deploy/deploy-clients/azure-monitor.md#create-a-skype-room-systems-v2-dashboard-manually).</span></span>
    
## <a name="individual-skype-room-systems-v2-console-requirements"></a><span data-ttu-id="1f983-127">Skype ルーム システム v2 コンソールの個々 の要件</span><span class="sxs-lookup"><span data-stu-id="1f983-127">Individual Skype Room Systems v2 Console requirements</span></span>

<span data-ttu-id="1f983-128">各 Skype ルーム システム v2 のコンソールには、キオスク モードで Surface Pro デバイスで実行されているアプリケーション (通常は、その構成されているデバイスで実行できる唯一のアプリケーション)。</span><span class="sxs-lookup"><span data-stu-id="1f983-128">Each Skype Room Systems v2 console is an app running on a Surface Pro device in kiosk mode (normally, it's configured to be the only app that can run on the device).</span></span> <span data-ttu-id="1f983-129">同様にすべての Windows アプリケーションでは、Skype ルーム システム v2 アプリケーションは、Windows イベント ログに起動し、ハードウェアの障害などのイベントを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="1f983-129">As with any Windows app, the Skype Room Systems v2 app writes events like startup and hardware faults to the Windows Event Log.</span></span> <span data-ttu-id="1f983-130">Skype ルーム システム v2 デバイスに Microsoft の監視エージェントを追加するには、これらのイベントを収集することができます。</span><span class="sxs-lookup"><span data-stu-id="1f983-130">Adding an Microsoft Monitor agent on your Skype Room Systems v2 device allows these events to be collected.</span></span> <span data-ttu-id="1f983-131">(詳細については[接続の Windows コンピューター](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="1f983-131">(See [Connect Windows computers to the Log Analytics service in Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) for details.)</span></span>
  
## <a name="ongoing-management"></a><span data-ttu-id="1f983-132">進行中の管理</span><span class="sxs-lookup"><span data-stu-id="1f983-132">Ongoing management</span></span>

<span data-ttu-id="1f983-133">Azure のモニターを使用して、Skype ルーム システム v2 のデバイスを管理するために、Azure のモニターで使用されているイベント ログに含まれている情報を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f983-133">While using Azure Monitor to manage your Skype Room Systems v2 devices, you'll need to understand the information contained in the event logs used by Azure Monitor.</span></span> <span data-ttu-id="1f983-134">これらの状態メッセージの詳細については、[ログ エントリを理解する](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f983-134">See [Understand the log entries](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries) for details on these health messages.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="1f983-135">関連タスク</span><span class="sxs-lookup"><span data-stu-id="1f983-135">Related Tasks</span></span>

- <span data-ttu-id="1f983-136">Skype ルーム システム v2 と ([ログのエントリを理解する](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries)」のセクションを参照してください) を解決するための方法で生成された警告を理解します。</span><span class="sxs-lookup"><span data-stu-id="1f983-136">Understand the Alerts generated by Skype Room Systems v2 and how to resolve them (see the section titled [Understand the log entries](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries))</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1f983-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f983-137">See also</span></span>

[<span data-ttu-id="1f983-138">Azure のモニターを使用して Skype ルーム システム v2 の管理を展開します。</span><span class="sxs-lookup"><span data-stu-id="1f983-138">Deploy Skype Room Systems v2 management with Azure Monitor</span></span>](../../deploy/deploy-clients/azure-monitor.md)
  
[<span data-ttu-id="1f983-139">Azure のモニターを使用して Skype ルーム システム v2 のデバイスを管理します。</span><span class="sxs-lookup"><span data-stu-id="1f983-139">Manage Skype Room Systems v2 devices with Azure Monitor</span></span>](../../manage/skype-room-systems-v2/azure-monitor.md)