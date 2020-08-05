---
title: Azure Monitor を使用して Microsoft Teams ミーティング管理を計画する
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection:
- M365-collaboration
description: この記事では、Skype for Business または Teams の実装で、Azure Monitor を使用して Microsoft Teams ミーティング デバイスを管理する場合の計画上の考慮事項について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 16a962d7414407cf5f2f5734b7a2f39a56f7d281
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137607"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a><span data-ttu-id="5820a-103">Azure Monitor を使用して Microsoft Teams ミーティング管理を計画する</span><span class="sxs-lookup"><span data-stu-id="5820a-103">Plan Microsoft Teams Rooms management with Azure Monitor</span></span>
 
 <span data-ttu-id="5820a-104">この記事では、Microsoft Teams や Skype for Business の実装で、Azure Monitor を使用して Microsoft Teams ミーティング デバイスを管理する場合の計画上の考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="5820a-104">This article discusses planning considerations for using Azure Monitor to administer Microsoft Teams Rooms devices in your Microsoft Teams or Skype for Business implementation.</span></span>
  
<span data-ttu-id="5820a-105">[Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) は、最初からクラウドに設計された管理サービスのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="5820a-105">[Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) is a collection of management services that were designed in the cloud from the start.</span></span> <span data-ttu-id="5820a-106">Azure Monitor コンポーネントでは、オンプレミスのリソースをデプロイおよび管理するのではなく、すべて Azure でホストされます。</span><span class="sxs-lookup"><span data-stu-id="5820a-106">Rather than deploying and managing on-premise resources, Azure Monitor components are entirely hosted in Azure.</span></span> <span data-ttu-id="5820a-107">構成が最小限に抑えられ、わずか数分で稼働させることができます。</span><span class="sxs-lookup"><span data-stu-id="5820a-107">Configuration is minimal, and you can be up and running literally in a matter of minutes.</span></span> <span data-ttu-id="5820a-108">特定のカスタマイズ機能を使用すると、個々の会議室システムのシステム正常性やフォールトをリアルタイムで通知することで、Microsoft Teams ミーティングの会議システムの管理に役立ち、数千の Microsoft Teams ミーティングの会議室の管理にスケールアップできる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5820a-108">With some customization work, it can aid in managing Microsoft Teams Rooms conferencing systems by providing real-time notifications of system health or faults for individual room systems, and it can potentially scale up to managing thousands of Microsoft Teams Rooms conference rooms.</span></span>
  
<span data-ttu-id="5820a-109">この記事では、Microsoft Teams ミーティングの会議デバイスのための Azure Monitor ベースの管理を実装するために必要な要件、設計やアーキテクチャ、実装のベストプラクティスについて説明し、Microsoft Teams ミーティング用の Azure Monitor の実装に関する詳細な記事へのリンクを提供します。また、Microsoft Teams ミーティングの会議室を継続的に監視するための重要な参照情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="5820a-109">This article provides a discussion of the requirements, design/architecture, and implementation best practices needed to implement Azure Monitor based management of Microsoft Teams Rooms conference devices, and provides links to detailed articles on implementing Azure Monitor for Microsoft Teams Rooms and critical reference information for ongoing monitoring of Microsoft Teams Rooms rooms.</span></span> 
  
## <a name="functional-overview"></a><span data-ttu-id="5820a-110">機能の概要</span><span class="sxs-lookup"><span data-stu-id="5820a-110">Functional overview</span></span>

![Azure Monitor を使用した Microsoft Teams ミーティング管理の図](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
<span data-ttu-id="5820a-112">コンソール デバイス上の Microsoft Teams ミーティング アプリは Windows イベント ログにイベントを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="5820a-112">The Microsoft Teams Rooms app on the console device writes events to its Windows Event Log.</span></span> <span data-ttu-id="5820a-113">Microsoft Monitoring エージェントは、インストール後、情報を Azure Monitor サービスに渡します。</span><span class="sxs-lookup"><span data-stu-id="5820a-113">A Microsoft Monitoring agent, once installed, passes the information to Azure Monitor service.</span></span> 
  
<span data-ttu-id="5820a-114">Log Analytics は、適切に構成されると、イベントの説明に埋め込まれた JSON ペイロードを解析して、各 Microsoft Teams ミーティング システムがどのように機能しているか、および検出されたエラーが何であるかを説明します。</span><span class="sxs-lookup"><span data-stu-id="5820a-114">Once properly configured, Log Analytics parses the JSON payload embedded in the event descriptions to describe how each Microsoft Teams Rooms system is functioning and what faults are detected.</span></span> 
  
<span data-ttu-id="5820a-115">Azure Monitor を使用している管理者は、Microsoft Teams ミーティング システムがオフラインであること、問題が発生しているアプリ、接続、ハードウェアの障害が発生していること、およびシステムの再起動が必要かどうかを知らせるシステムの通知を受信できます。</span><span class="sxs-lookup"><span data-stu-id="5820a-115">An administrator using Azure Monitor can get notifications of Microsoft Teams Rooms systems that are offline or are experiencing app, connectivity, or hardware failures as well as knowing if a system needs to be restarted.</span></span> <span data-ttu-id="5820a-116">各システムの状態は頻繁に更新されるため、これらの通知はほぼリアルタイムの更新情報となります。</span><span class="sxs-lookup"><span data-stu-id="5820a-116">Each system status is updated frequently, so these notifications are close to real-time updates.</span></span>
  
## <a name="azure-monitor-requirements"></a><span data-ttu-id="5820a-117">Azure Monitor の要件</span><span class="sxs-lookup"><span data-stu-id="5820a-117">Azure Monitor requirements</span></span>

<span data-ttu-id="5820a-118">Log Analytics 機能を使用するには、Azure Monitor 用の有効な Azure サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="5820a-118">You must have a valid Azure subscription for Azure Monitor to use Log Analytics feature.</span></span> <span data-ttu-id="5820a-119">組織のサブスクリプションを作成するには、「[Log Analytics ワークスペースの使用を開始する](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5820a-119">See [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) to create a subscription for your organization.</span></span>
  
<span data-ttu-id="5820a-120">必要に応じて、Log Analytics ビュー デザイナーの使用方法について理解を深めておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="5820a-120">You should familiarize yourself as necessary on how to use the Log Analytics View Designer.</span></span> <span data-ttu-id="5820a-121">これらの詳細については、「[Log Analytics のビュー](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5820a-121">See [Views in Log Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) for those details.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="5820a-122">関連作業</span><span class="sxs-lookup"><span data-stu-id="5820a-122">Related Tasks</span></span>

1. <span data-ttu-id="5820a-123">Azure Monitor Log Analytics の登録後、Microsoft Teams ミーティング コンソールから送信される情報を解析するのに必要なカスタム フィールドを作成します (「[カスタム フィールドをマップする](azure-monitor-deploy.md#Custom_fields)」に説明されています)。</span><span class="sxs-lookup"><span data-stu-id="5820a-123">Once subscribed to Azure Monitor Log Analytics, create custom fields (as described in [Map custom fields](azure-monitor-deploy.md#Custom_fields)) needed to parse the information that will be sent from Microsoft Teams Rooms consoles.</span></span> <span data-ttu-id="5820a-124">これには、「[ログ エントリを理解する](azure-monitor-manage.md#understand-the-log-entries)」で説明されている JSON スキーマについて理解することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5820a-124">This includes understanding the JSON schema documented in [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries).</span></span>
    
2. <span data-ttu-id="5820a-125">Log Analytics の [Microsoft Teams ミーティング管理] ビューを開発します。</span><span class="sxs-lookup"><span data-stu-id="5820a-125">Develop a Microsoft Teams Rooms management view in Log Analytics.</span></span> <span data-ttu-id="5820a-126">「[インポート メソッドを使用して Microsoft Teams ミーティング ダッシュボードを作成する](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method)」ことも、「[Microsoft Teams ミーティング ダッシュボードを手動で作成する](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)」こともできます。</span><span class="sxs-lookup"><span data-stu-id="5820a-126">You can either [Create a Microsoft Teams Rooms dashboard by using the import method](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) or [Create a Microsoft Teams Rooms dashboard manually](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).</span></span>
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a><span data-ttu-id="5820a-127">個々の Microsoft Teams ミーティング コンソールの要件</span><span class="sxs-lookup"><span data-stu-id="5820a-127">Individual Microsoft Teams Rooms Console requirements</span></span>

<span data-ttu-id="5820a-128">Microsoft Teams ミーティングの各コンソールは、キオスク モードの Surface Pro デバイスで実行されているアプリです (通常、デバイスで実行できるアプリのみが構成されています)。</span><span class="sxs-lookup"><span data-stu-id="5820a-128">Each Microsoft Teams Rooms console is an app running on a Surface Pro device in kiosk mode (normally, it's configured to be the only app that can run on the device).</span></span> <span data-ttu-id="5820a-129">他の Windows アプリと同様に、Microsoft Teams ミーティング アプリは、起動やハードウェア障害などのイベントを Windows イベント ログに記録します。</span><span class="sxs-lookup"><span data-stu-id="5820a-129">As with any Windows app, the Microsoft Teams Rooms app writes events like startup and hardware faults to the Windows Event Log.</span></span> <span data-ttu-id="5820a-130">Microsoft Teams ミーティング デバイス に Microsoft Monitor エージェントを追加すると、これらのイベントを収集できます。</span><span class="sxs-lookup"><span data-stu-id="5820a-130">Adding an Microsoft Monitor agent on your Microsoft Teams Rooms device allows these events to be collected.</span></span> <span data-ttu-id="5820a-131">(詳細については、「[Windows コンピューターを Azure の Log Analytics サービスに接続する](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)」を参照してください。)</span><span class="sxs-lookup"><span data-stu-id="5820a-131">(See [Connect Windows computers to the Log Analytics service in Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) for details.)</span></span>
  
## <a name="ongoing-management"></a><span data-ttu-id="5820a-132">継続的な管理</span><span class="sxs-lookup"><span data-stu-id="5820a-132">Ongoing management</span></span>

<span data-ttu-id="5820a-133">Azure Monitor を使用してお使いの Microsoft Teams ミーティング デバイスを管理するときに、Azure Monitor によって使用されているイベント ログに含まれる情報を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5820a-133">While using Azure Monitor to manage your Microsoft Teams Rooms devices, you'll need to understand the information contained in the event logs used by Azure Monitor.</span></span> <span data-ttu-id="5820a-134">これらの正常性メッセージの詳細については、「[ログ エントリを理解する](azure-monitor-manage.md#understand-the-log-entries)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5820a-134">See [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries) for details on these health messages.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="5820a-135">関連作業</span><span class="sxs-lookup"><span data-stu-id="5820a-135">Related Tasks</span></span>

- <span data-ttu-id="5820a-136">Microsoft Teams ミーティングにより生成されたアラートとそれらの解決方法を理解する (「[ログ エントリを理解する](azure-monitor-manage.md#understand-the-log-entries)」というタイトルのセクションを参照)</span><span class="sxs-lookup"><span data-stu-id="5820a-136">Understand the Alerts generated by Microsoft Teams Rooms and how to resolve them (see the section titled [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries))</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5820a-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="5820a-137">See also</span></span>

[<span data-ttu-id="5820a-138">Azure Monitor を使用して Microsoft Teams ミーティング管理をデプロイする</span><span class="sxs-lookup"><span data-stu-id="5820a-138">Deploy Microsoft Teams Rooms management with Azure Monitor</span></span>](azure-monitor-deploy.md)
  
[<span data-ttu-id="5820a-139">Azure Monitorを使用して Microsoft Teams ミーティング デバイスをデプロイする</span><span class="sxs-lookup"><span data-stu-id="5820a-139">Manage Microsoft Teams Rooms devices with Azure Monitor</span></span>](azure-monitor-manage.md)