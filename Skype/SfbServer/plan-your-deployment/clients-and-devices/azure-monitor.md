---
title: Azure のモニターを使用して Microsoft チームの会議室の管理を計画します。
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection: M365-voice
description: この資料では、Azure のモニターを使用して企業やチームの実装については、Skype でマイクロソフト チームの会議室のデバイスを管理するための計画に関する考慮事項について説明します。
ms.openlocfilehash: dfa65435da63eb9783422e1e7ee10e66ba33b891
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214574"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a><span data-ttu-id="bd849-103">Azure のモニターを使用して Microsoft チームの会議室の管理を計画します。</span><span class="sxs-lookup"><span data-stu-id="bd849-103">Plan Microsoft Teams Rooms management with Azure Monitor</span></span>
 
 <span data-ttu-id="bd849-104">この資料では、Azure のモニターを使用してビジネス サーバーの実装については、Skype でマイクロソフト チームの会議室のデバイスを管理するための計画に関する考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="bd849-104">This article discusses planning considerations for using Azure Monitor to administer Microsoft Teams Rooms devices in your Skype for Business Server implementation.</span></span>
  
<span data-ttu-id="bd849-105">[Azure のモニター](https://docs.microsoft.com/azure/azure-monitor/overview)は、最初からクラウドのように設計された管理サービスのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="bd849-105">[Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) is a collection of management services that were designed in the cloud from the start.</span></span> <span data-ttu-id="bd849-106">展開して、オンプレミスのリソースを管理するのではなく Azure モニターのコンポーネント完全 Azure でホストされます。</span><span class="sxs-lookup"><span data-stu-id="bd849-106">Rather than deploying and managing on-premise resources, Azure Monitor components are entirely hosted in Azure.</span></span> <span data-ttu-id="bd849-107">構成は最小限とする起動してそのまま数分で。</span><span class="sxs-lookup"><span data-stu-id="bd849-107">Configuration is minimal, and you can be up and running literally in a matter of minutes.</span></span> <span data-ttu-id="bd849-108">カスタマイズのいくつかの作業では、個々 の部屋のシステムでは、システムの稼働状態や障害のリアルタイムの通知を提供することによって Microsoft チームの会議室の会議システムを管理することも役に立ち、何千ものマイクロソフトのチームを管理するに拡張できる可能性があります。会議室の会議室です。</span><span class="sxs-lookup"><span data-stu-id="bd849-108">With some customization work, it can aid in managing Microsoft Teams Rooms conferencing systems by providing real-time notifications of system health or faults for individual room systems, and it can potentially scale up to managing thousands of Microsoft Teams Rooms conference rooms.</span></span>
  
<span data-ttu-id="bd849-109">この資料は、要件、設計とアーキテクチャ、およびマイクロソフト チーム ルーム会議デバイスでは、Azure のモニター ベースの管理を実装するために必要な実装のベスト プラクティスの説明が用意されていての詳細な記事へのリンクが用意されていますマイクロソフト チームの会議室とマイクロソフト チームの会議室の会議室の継続的な監視の重要な参照情報は Azure のモニターを実装します。</span><span class="sxs-lookup"><span data-stu-id="bd849-109">This article provides a discussion of the requirements, design/architecture, and implementation best practices needed to implement Azure Monitor based management of Microsoft Teams Rooms conference devices, and provides links to detailed articles on implementing Azure Monitor for Microsoft Teams Rooms and critical reference information for ongoing monitoring of Microsoft Teams Rooms rooms.</span></span> 
  
## <a name="functional-overview"></a><span data-ttu-id="bd849-110">機能の概要</span><span class="sxs-lookup"><span data-stu-id="bd849-110">Functional overview</span></span>

![Azure のモニターを使用して Microsoft チームの会議室の管理の図](../../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
<span data-ttu-id="bd849-112">コンソール デバイス上のマイクロソフト チーム ルーム アプリケーションは、Windows イベント ログにイベントを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="bd849-112">The Microsoft Teams Rooms app on the console device writes events to its Windows Event Log.</span></span> <span data-ttu-id="bd849-113">Microsoft の監視のエージェントをインストールすると、Azure 監視サービスに情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="bd849-113">A Microsoft Monitoring agent, once installed, passes the information to Azure Monitor service.</span></span> 
  
<span data-ttu-id="bd849-114">1 回正しく構成されている、JSON ペイロードがマイクロソフト チームの会議室の各システムが機能していると、どのような障害が検出されたを記述する説明で埋め込みイベントのログの分析解析します。</span><span class="sxs-lookup"><span data-stu-id="bd849-114">Once properly configured, Log Analytics parses the JSON payload embedded in the event descriptions to describe how each Microsoft Teams Rooms system is functioning and what faults are detected.</span></span> 
  
<span data-ttu-id="bd849-115">Azure のモニターを使用して管理者オフラインになっているマイクロソフト チームの会議室のシステムの通知を受け取ることができますまたは、アプリケーション、接続、またはハードウェアの障害が発生しているだけでなく、システムを再起動する必要があるかどうかを知ること。</span><span class="sxs-lookup"><span data-stu-id="bd849-115">An administrator using Azure Monitor can get notifications of Microsoft Teams Rooms systems that are offline or are experiencing app, connectivity, or hardware failures as well as knowing if a system needs to be restarted.</span></span> <span data-ttu-id="bd849-116">各システムのステータスは、これらの通知は、更新をリアルタイムに近いので、頻繁に更新されます。</span><span class="sxs-lookup"><span data-stu-id="bd849-116">Each system status is updated frequently, so these notifications are close to real-time updates.</span></span>
  
## <a name="azure-monitor-requirements"></a><span data-ttu-id="bd849-117">Azure の監視要件</span><span class="sxs-lookup"><span data-stu-id="bd849-117">Azure Monitor requirements</span></span>

<span data-ttu-id="bd849-118">Azure の監視ログ分析機能を使用するのに有効な Azure サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="bd849-118">You must have a valid Azure subscription for Azure Monitor to use Log Analytics feature.</span></span> <span data-ttu-id="bd849-119">[ログ分析機能のワークスペースを使い始める](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)が、組織用のサブスクリプションを作成するを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd849-119">See [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) to create a subscription for your organization.</span></span>
  
<span data-ttu-id="bd849-120">ログ分析ビュー デザイナーを使用する方法を必要に応じて、理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd849-120">You should familiarize yourself as necessary on how to use the Log Analytics View Designer.</span></span> <span data-ttu-id="bd849-121">詳細についてはこれらの[ログ分析のビュー](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd849-121">See [Views in Log Analytics ](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) for those details.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="bd849-122">関連タスク</span><span class="sxs-lookup"><span data-stu-id="bd849-122">Related Tasks</span></span>

1. <span data-ttu-id="bd849-123">購読すると、Azure 監視ログ分析して、作成カスタム フィールド ([ユーザー設定フィールドをマップ](../../deploy/deploy-clients/azure-monitor.md#Custom_fields)に記載されている) 必要なマイクロソフト チームの会議室のコンソールから送られる情報を解析します。</span><span class="sxs-lookup"><span data-stu-id="bd849-123">Once subscribed to Azure Monitor Log Analytics, create custom fields (as described in [Map custom fields](../../deploy/deploy-clients/azure-monitor.md#Custom_fields)) needed to parse the information that will be sent from Microsoft Teams Rooms consoles.</span></span> <span data-ttu-id="bd849-124">[ログ エントリを理解するの](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries)に記載されている JSON のスキーマを理解することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bd849-124">This includes understanding the JSON schema documented in [Understand the log entries](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries).</span></span>
    
2. <span data-ttu-id="bd849-125">ログ分析のマイクロソフト チームの会議室の管理ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="bd849-125">Develop a Microsoft Teams Rooms management view in Log Analytics.</span></span> <span data-ttu-id="bd849-126">[Import メソッドを使用して Microsoft チームの会議室のダッシュ ボードを作成](../../deploy/deploy-clients/azure-monitor.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method)するか、[マイクロソフト チームの会議室のダッシュ ボードを手動で作成する](../../deploy/deploy-clients/azure-monitor.md#create-a-microsoft-teams-rooms-dashboard-manually)ことができます。</span><span class="sxs-lookup"><span data-stu-id="bd849-126">You can either [Create a Microsoft Teams Rooms dashboard by using the import method](../../deploy/deploy-clients/azure-monitor.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) or [Create a Microsoft Teams Rooms dashboard manually](../../deploy/deploy-clients/azure-monitor.md#create-a-microsoft-teams-rooms-dashboard-manually).</span></span>
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a><span data-ttu-id="bd849-127">個々 のマイクロソフト チームの会議室のコンソールの要件</span><span class="sxs-lookup"><span data-stu-id="bd849-127">Individual Microsoft Teams Rooms Console requirements</span></span>

<span data-ttu-id="bd849-128">各マイクロソフト チームの会議室のコンソールには、キオスク モードで Surface Pro デバイスで実行されているアプリケーション (通常は、その構成されているデバイスで実行できる唯一のアプリケーション)。</span><span class="sxs-lookup"><span data-stu-id="bd849-128">Each Microsoft Teams Rooms console is an app running on a Surface Pro device in kiosk mode (normally, it's configured to be the only app that can run on the device).</span></span> <span data-ttu-id="bd849-129">同様にすべての Windows アプリケーションでは、チームの会議室をマイクロソフトのアプリケーションは Windows イベント ログに起動し、ハードウェアの障害などのイベントを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="bd849-129">As with any Windows app, the Microsoft Teams Rooms app writes events like startup and hardware faults to the Windows Event Log.</span></span> <span data-ttu-id="bd849-130">マイクロソフト チーム室デバイスに Microsoft モニター エージェントを追加することにより、これらのイベントを収集します。</span><span class="sxs-lookup"><span data-stu-id="bd849-130">Adding an Microsoft Monitor agent on your Microsoft Teams Rooms device allows these events to be collected.</span></span> <span data-ttu-id="bd849-131">(詳細については[接続の Windows コンピューター](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="bd849-131">(See [Connect Windows computers to the Log Analytics service in Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) for details.)</span></span>
  
## <a name="ongoing-management"></a><span data-ttu-id="bd849-132">進行中の管理</span><span class="sxs-lookup"><span data-stu-id="bd849-132">Ongoing management</span></span>

<span data-ttu-id="bd849-133">Azure のモニターを使用して、マイクロソフト チームの会議室のデバイスを管理するために、Azure のモニターで使用されているイベント ログに含まれている情報を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd849-133">While using Azure Monitor to manage your Microsoft Teams Rooms devices, you'll need to understand the information contained in the event logs used by Azure Monitor.</span></span> <span data-ttu-id="bd849-134">これらの状態メッセージの詳細については、[ログ エントリを理解する](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd849-134">See [Understand the log entries](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries) for details on these health messages.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="bd849-135">関連タスク</span><span class="sxs-lookup"><span data-stu-id="bd849-135">Related Tasks</span></span>

- <span data-ttu-id="bd849-136">([ログのエントリを理解する](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries)」のセクションを参照してください) を解決するのにはマイクロソフト チームの会議室で生成された警告を理解します。</span><span class="sxs-lookup"><span data-stu-id="bd849-136">Understand the Alerts generated by Microsoft Teams Rooms and how to resolve them (see the section titled [Understand the log entries](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries))</span></span>
    
## <a name="see-also"></a><span data-ttu-id="bd849-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd849-137">See also</span></span>

[<span data-ttu-id="bd849-138">Azure のモニターを使用して Microsoft チームの会議室の管理を展開します。</span><span class="sxs-lookup"><span data-stu-id="bd849-138">Deploy Microsoft Teams Rooms management with Azure Monitor</span></span>](../../deploy/deploy-clients/azure-monitor.md)
  
[<span data-ttu-id="bd849-139">Azure のモニターを使用して Microsoft チームの会議室のデバイスを管理します。</span><span class="sxs-lookup"><span data-stu-id="bd849-139">Manage Microsoft Teams Rooms devices with Azure Monitor</span></span>](../../manage/skype-room-systems-v2/azure-monitor.md)