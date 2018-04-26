---
title: OMS を使用して Skype Room Systems バージョン 2 の管理を計画する
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
description: この記事では、Skype for Business Server 2015 の実装において Skype Room Systems バージョン 2 デバイスを管理するための Operations Management Suite の使用についてのプランニングの検討事項について考えます。
ms.openlocfilehash: b117b243b638c9e06b21901f14515b51d6931d23
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="plan-skype-room-systems-v2-management-with-oms"></a><span data-ttu-id="dc267-103">OMS を使用して Skype Room Systems バージョン 2 の管理を計画する</span><span class="sxs-lookup"><span data-stu-id="dc267-103">Plan Skype Room Systems v2 management with OMS</span></span>
 
 <span data-ttu-id="dc267-104">この記事では、Skype for Business Server 2015 の実装において Skype Room Systems バージョン 2 デバイスを管理するための Operations Management Suite の使用についてのプランニングの検討事項について考えます。</span><span class="sxs-lookup"><span data-stu-id="dc267-104">This article discusses planning considerations for using Operations Management Suite to administer Skype Room Systems v2 devices in your Skype for Business Server 2015 implementation.</span></span>
  
<span data-ttu-id="dc267-105">[操作の管理スイート](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview)(OMS) は、最初からクラウドのように設計された管理サービスのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="dc267-105">[Operations Management Suite](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview) (OMS) is a collection of management services that were designed in the cloud from the start.</span></span> <span data-ttu-id="dc267-106">展開して、オンプレミスのリソースを管理するのではなく OMS のコンポーネントは完全 Azure でホストされます。</span><span class="sxs-lookup"><span data-stu-id="dc267-106">Rather than deploying and managing on-premise resources, OMS components are entirely hosted in Azure.</span></span> <span data-ttu-id="dc267-107">構成は最小限とする起動してそのまま数分で。</span><span class="sxs-lookup"><span data-stu-id="dc267-107">Configuration is minimal, and you can be up and running literally in a matter of minutes.</span></span> <span data-ttu-id="dc267-108">カスタマイズのいくつかの作業では、個々 の部屋のシステムでは、システムの稼働状態や障害のリアルタイムの通知を提供することによって Skype ルーム システム v2 の会議システムを管理することも役に立ち、数千の Skype ルームのシステムを管理するに拡張できる可能性があります。v2 の会議室です。</span><span class="sxs-lookup"><span data-stu-id="dc267-108">With some customization work, it can aid in managing Skype Room Systems v2 conferencing systems by providing real-time notifications of system health or faults for individual room systems, and it can potentially scale up to managing thousands of Skype Room Systems v2 conference rooms.</span></span>
  
<span data-ttu-id="dc267-109">この資料は、要件、設計とアーキテクチャ、および Skype ルーム システム v2 の会議デバイスの OMS の管理を実装するために必要な実装のベスト プラクティスの説明を提供し、OMS の実装に関する詳細な記事へのリンクが用意されていますSkype ルーム システム v2 と Skype ルーム システム v2 ルーム OMS の継続的な管理の重要な参照情報を管理します。</span><span class="sxs-lookup"><span data-stu-id="dc267-109">This article provides a discussion of the requirements, design/architecture, and implementation best practices needed to implement OMS management of Skype Room Systems v2 conference devices, and provides links to detailed articles on implementing OMS management for Skype Room Systems v2 and critical reference information for ongoing OMS management of Skype Room Systems v2 rooms.</span></span> 
  
## <a name="functional-overview"></a><span data-ttu-id="dc267-110">機能の概要</span><span class="sxs-lookup"><span data-stu-id="dc267-110">Functional overview</span></span>

![OMS を使用した SRS 管理の図](../../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
<span data-ttu-id="dc267-112">Skype ルーム システムがコンソール デバイス上のアプリケーションを v2 では、Windows イベント ログにイベントを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="dc267-112">The Skype Room Systems v2 app on the console device writes events to its Windows Event Log.</span></span> <span data-ttu-id="dc267-113">OMS エージェントはインストールされると情報を OMS に渡します。</span><span class="sxs-lookup"><span data-stu-id="dc267-113">An OMS agent, once installed, passes the information to OMS.</span></span> 
  
<span data-ttu-id="dc267-114">1 回が正しく構成されて、イベントの各 Skype ルーム システム v2 のシステムが機能している方法と、どのような障害が検出されたを記述する説明に埋め込まれた JSON ペイロード OMS 解析します。</span><span class="sxs-lookup"><span data-stu-id="dc267-114">Once properly configured, OMS parses the JSON payload embedded in the event descriptions to describe how each Skype Room Systems v2 system is functioning and what faults are detected.</span></span> 
  
<span data-ttu-id="dc267-115">OMS を使用して管理者オフラインになっている Skype ルーム システム v2 のシステムの通知を受け取ることができますまたは、アプリケーション、接続、またはハードウェアの障害が発生しているだけでなく、システムを再起動する必要があるかどうかを知ること。</span><span class="sxs-lookup"><span data-stu-id="dc267-115">An administrator using OMS can get notifications of Skype Room Systems v2 systems that are offline or are experiencing app, connectivity, or hardware failures as well as knowing if a system needs to be restarted.</span></span> <span data-ttu-id="dc267-116">各システムのステータス更新 5 分ごとに、リアルタイム更新に近いので、これらの通知されます。</span><span class="sxs-lookup"><span data-stu-id="dc267-116">Each system status is updated every five minutes, so these notifications are close to real-time updates.</span></span>
  
## <a name="oms-requirements"></a><span data-ttu-id="dc267-117">OMS の要件</span><span class="sxs-lookup"><span data-stu-id="dc267-117">OMS requirements</span></span>

<span data-ttu-id="dc267-118">この機能を使用するには、OMS の有効なサブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="dc267-118">You must have a valid subscription for OMS to use this feature.</span></span> <span data-ttu-id="dc267-119">[ログ分析機能のワークスペースを使い始める](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started?toc=%2fazure%2foperations-management-suite%2ftoc.json)が、組織用のサブスクリプションを作成するを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc267-119">See [Get started with a Log Analytics workspace](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started?toc=%2fazure%2foperations-management-suite%2ftoc.json) to create a subscription for your organization.</span></span>
  
<span data-ttu-id="dc267-120">必要に応じて、OMS ビュー デザイナーの使用方法について理解を深めておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc267-120">You should familiarize yourself as necessary on how to use the OMS View Designer.</span></span> <span data-ttu-id="dc267-121">その詳細については、[管理ソリューションの運用管理スイート (OMS) 内のビュー](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-solutions-resources-views)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc267-121">See [Views in Operations Management Suite (OMS) management solutions](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-solutions-resources-views) for those details.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="dc267-122">関連タスク</span><span class="sxs-lookup"><span data-stu-id="dc267-122">Related Tasks</span></span>

1. <span data-ttu-id="dc267-123">OMS を購読して、作成カスタム フィールド ([ユーザー設定フィールドをマップ](../../deploy/deploy-clients/with-oms.md#Custom_fields)に記載されている) 必要な Skype ルーム システム v2 本体から送信される情報を解析します。</span><span class="sxs-lookup"><span data-stu-id="dc267-123">Once subscribed to OMS, create custom fields (as described in [Map custom fields](../../deploy/deploy-clients/with-oms.md#Custom_fields)) needed to parse the information that will be sent from Skype Room Systems v2 consoles.</span></span> <span data-ttu-id="dc267-124">[ログ エントリを理解するの](../../manage/skype-room-systems-v2/oms.md#Telemetry)に記載されている JSON のスキーマを理解することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dc267-124">This includes understanding the JSON schema documented in [Understand the log entries](../../manage/skype-room-systems-v2/oms.md#Telemetry).</span></span>
    
2. <span data-ttu-id="dc267-125">OMS の Skype ルーム システム v2 の管理ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="dc267-125">Develop a Skype Room Systems v2 management view in OMS.</span></span> <span data-ttu-id="dc267-126">いずれかの[インポート メソッドを使用して Skype ルーム システム v2 のダッシュ ボードを作成する](../../deploy/deploy-clients/with-oms.md#create-a-skype-room-systems-v2-dashboard-by-using-the-import-method)ことができます) [Skype ルーム システム v2 のダッシュ ボード](../../deploy/deploy-clients/with-oms.md#create-a-skype-room-systems-v2-dashboard-manually)を手動で作成します。</span><span class="sxs-lookup"><span data-stu-id="dc267-126">You can either [Create a Skype Room Systems v2 dashboard by using the import method](../../deploy/deploy-clients/with-oms.md#create-a-skype-room-systems-v2-dashboard-by-using-the-import-method) ) or [Create a Skype Room Systems v2 dashboard manually](../../deploy/deploy-clients/with-oms.md#create-a-skype-room-systems-v2-dashboard-manually).</span></span>
    
## <a name="individual-skype-room-systems-v2-console-requirements"></a><span data-ttu-id="dc267-127">Skype ルーム システム v2 コンソールの個々 の要件</span><span class="sxs-lookup"><span data-stu-id="dc267-127">Individual Skype Room Systems v2 Console requirements</span></span>

<span data-ttu-id="dc267-128">各 Skype ルーム システム v2 のコンソールには、キオスク モードでサーフェスの 4 のデバイスで実行されているアプリケーション (通常は、その構成されているデバイスで実行できる唯一のアプリケーション)。</span><span class="sxs-lookup"><span data-stu-id="dc267-128">Each Skype Room Systems v2 console is an app running on a Surface 4 device in kiosk mode (normally, it's configured to be the only app that can run on the device).</span></span> <span data-ttu-id="dc267-129">同様にすべての Windows アプリケーションでは、Skype ルーム システム v2 アプリケーションは、Windows イベント ログに起動し、ハードウェアの障害などのイベントを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="dc267-129">As with any Windows app, the Skype Room Systems v2 app writes events like startup and hardware faults to the Windows Event Log.</span></span> <span data-ttu-id="dc267-130">OMS を収集するこれらのイベントを Skype ルーム システム v2 デバイスの OMS エージェントを追加できます。</span><span class="sxs-lookup"><span data-stu-id="dc267-130">Adding an OMS agent on your Skype Room Systems v2 device allows these events to be collected by OMS.</span></span> <span data-ttu-id="dc267-131">(詳細については[接続の Windows コンピューター](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="dc267-131">(See [Connect Windows computers to the Log Analytics service in Azure](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents) for details.)</span></span>
  
## <a name="ongoing-management"></a><span data-ttu-id="dc267-132">進行中の管理</span><span class="sxs-lookup"><span data-stu-id="dc267-132">Ongoing management</span></span>

<span data-ttu-id="dc267-133">OMS を使用すると、Skype ルーム システム v2 の会議デバイスを管理するために、中には、OMS を使用するイベント ログに含まれる情報を理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc267-133">While using OMS to manage your Skype Room Systems v2 conference devices, you'll need to understand the information contained in the event logs used by OMS.</span></span> <span data-ttu-id="dc267-134">これらの状態メッセージの詳細については、[ログ エントリを理解する](../../manage/skype-room-systems-v2/oms.md#Telemetry)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc267-134">See [Understand the log entries](../../manage/skype-room-systems-v2/oms.md#Telemetry) for details on these health messages.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="dc267-135">関連タスク</span><span class="sxs-lookup"><span data-stu-id="dc267-135">Related Tasks</span></span>

- <span data-ttu-id="dc267-136">Skype ルーム システム v2 と ([ログのエントリを理解する](../../manage/skype-room-systems-v2/oms.md#Telemetry)」のセクションを参照してください) を解決するための方法で生成された警告を理解します。</span><span class="sxs-lookup"><span data-stu-id="dc267-136">Understand the Alerts generated by Skype Room Systems v2 and how to resolve them (see the section titled [Understand the log entries](../../manage/skype-room-systems-v2/oms.md#Telemetry))</span></span>
    
## <a name="see-also"></a><span data-ttu-id="dc267-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc267-137">See also</span></span>

#### 

[<span data-ttu-id="dc267-138">OMS を使用して Skype ルーム システム v2 の管理を展開します。</span><span class="sxs-lookup"><span data-stu-id="dc267-138">Deploy Skype Room Systems v2 management with OMS</span></span>](../../deploy/deploy-clients/with-oms.md)
  
[<span data-ttu-id="dc267-139">OMS を使用して Skype ルーム システム v2 のデバイスを管理します。</span><span class="sxs-lookup"><span data-stu-id="dc267-139">Manage Skype Room Systems v2 devices with OMS</span></span>](../../manage/skype-room-systems-v2/oms.md)

