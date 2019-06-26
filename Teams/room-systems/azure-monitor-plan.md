---
title: Azure モニターを使用して Microsoft Teams の会議室の管理を計画する
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection: M365-voice
description: この記事では、Azure モニターを使用して、Skype for Business または Teams の実装で Microsoft Teams 室のデバイスを管理する際の計画の考慮事項について説明します。
ms.openlocfilehash: 6536ee07ef64119d3529c7b9f279df3a7bbbdaed
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221388"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a><span data-ttu-id="f84b6-103">Azure モニターを使用して Microsoft Teams の会議室の管理を計画する</span><span class="sxs-lookup"><span data-stu-id="f84b6-103">Plan Microsoft Teams Rooms management with Azure Monitor</span></span>
 
 <span data-ttu-id="f84b6-104">この記事では、Microsoft Teams または Skype for Business の実装で Azure モニターを使用して Microsoft Teams のルームデバイスを管理する場合の計画に関する考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="f84b6-104">This article discusses planning considerations for using Azure Monitor to administer Microsoft Teams Rooms devices in your Microsoft Teams or Skype for Business implementation.</span></span>
  
<span data-ttu-id="f84b6-105">[Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview)は、最初からクラウドで設計された管理サービスのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="f84b6-105">[Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) is a collection of management services that were designed in the cloud from the start.</span></span> <span data-ttu-id="f84b6-106">オンプレミスのリソースを展開して管理する代わりに、Azure Monitor コンポーネントはすべて Azure でホストされます。</span><span class="sxs-lookup"><span data-stu-id="f84b6-106">Rather than deploying and managing on-premise resources, Azure Monitor components are entirely hosted in Azure.</span></span> <span data-ttu-id="f84b6-107">構成は最小限で、わずかな時間ですぐに起動して実行できます。</span><span class="sxs-lookup"><span data-stu-id="f84b6-107">Configuration is minimal, and you can be up and running literally in a matter of minutes.</span></span> <span data-ttu-id="f84b6-108">一部のカスタマイズ作業では、Microsoft Teams の会議システムを管理するために、個々の room システムのシステム正常性またはフォールトに関するリアルタイムの通知が提供されます。また、多くの Microsoft Teams の管理にも対応できる場合があります会議室の会議室。</span><span class="sxs-lookup"><span data-stu-id="f84b6-108">With some customization work, it can aid in managing Microsoft Teams Rooms conferencing systems by providing real-time notifications of system health or faults for individual room systems, and it can potentially scale up to managing thousands of Microsoft Teams Rooms conference rooms.</span></span>
  
<span data-ttu-id="f84b6-109">この記事では、Microsoft Teams 室の会議デバイスの Azure Monitor ベースの管理を実装するために必要な要件、設計、アーキテクチャ、実装のベストプラクティスについて説明し、詳細な記事へのリンクを提供します。microsoft Teams 室の管理と、Microsoft Teams ルームの継続的な監視に関する重要なリファレンス情報に対する Azure モニターの実装。</span><span class="sxs-lookup"><span data-stu-id="f84b6-109">This article provides a discussion of the requirements, design/architecture, and implementation best practices needed to implement Azure Monitor based management of Microsoft Teams Rooms conference devices, and provides links to detailed articles on implementing Azure Monitor for Microsoft Teams Rooms and critical reference information for ongoing monitoring of Microsoft Teams Rooms rooms.</span></span> 
  
## <a name="functional-overview"></a><span data-ttu-id="f84b6-110">機能の概要</span><span class="sxs-lookup"><span data-stu-id="f84b6-110">Functional overview</span></span>

![Azure モニターを使用した Microsoft Teams のルーム管理の図](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
<span data-ttu-id="f84b6-112">コンソールデバイス上の Microsoft Teams 会議アプリは、Windows イベントログにイベントを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="f84b6-112">The Microsoft Teams Rooms app on the console device writes events to its Windows Event Log.</span></span> <span data-ttu-id="f84b6-113">Microsoft Monitoring agent をインストールすると、その情報が Azure Monitor サービスに渡されます。</span><span class="sxs-lookup"><span data-stu-id="f84b6-113">A Microsoft Monitoring agent, once installed, passes the information to Azure Monitor service.</span></span> 
  
<span data-ttu-id="f84b6-114">適切に構成されたら、ログ解析は、イベントの説明に埋め込まれた JSON ペイロードを解析して、Microsoft Teams の各ルームシステムがどのように機能しているか、検出されたエラーを説明します。</span><span class="sxs-lookup"><span data-stu-id="f84b6-114">Once properly configured, Log Analytics parses the JSON payload embedded in the event descriptions to describe how each Microsoft Teams Rooms system is functioning and what faults are detected.</span></span> 
  
<span data-ttu-id="f84b6-115">Azure モニターを使用している管理者は、Microsoft Teams の会議室システムについて、オフラインになっている、またはアプリ、接続、ハードウェアの障害が発生していること、またシステムを再起動する必要があるかどうかを確認する通知を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="f84b6-115">An administrator using Azure Monitor can get notifications of Microsoft Teams Rooms systems that are offline or are experiencing app, connectivity, or hardware failures as well as knowing if a system needs to be restarted.</span></span> <span data-ttu-id="f84b6-116">各システム状態は頻繁に更新されるため、これらの通知はリアルタイムの更新プログラムに近い状態になります。</span><span class="sxs-lookup"><span data-stu-id="f84b6-116">Each system status is updated frequently, so these notifications are close to real-time updates.</span></span>
  
## <a name="azure-monitor-requirements"></a><span data-ttu-id="f84b6-117">Azure モニターの要件</span><span class="sxs-lookup"><span data-stu-id="f84b6-117">Azure Monitor requirements</span></span>

<span data-ttu-id="f84b6-118">ログ分析機能を使用するには、Azure モニター用の有効な Azure サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="f84b6-118">You must have a valid Azure subscription for Azure Monitor to use Log Analytics feature.</span></span> <span data-ttu-id="f84b6-119">組織のサブスクリプションを作成するには、「[ログ分析ワークスペースの使用を開始](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f84b6-119">See [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) to create a subscription for your organization.</span></span>
  
<span data-ttu-id="f84b6-120">ログ分析ビューデザイナーの使用方法については、必要に応じて理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="f84b6-120">You should familiarize yourself as necessary on how to use the Log Analytics View Designer.</span></span> <span data-ttu-id="f84b6-121">詳細については、「[ログ分析のビュー」を](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)参照してください。</span><span class="sxs-lookup"><span data-stu-id="f84b6-121">See [Views in Log Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) for those details.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="f84b6-122">関連タスク</span><span class="sxs-lookup"><span data-stu-id="f84b6-122">Related Tasks</span></span>

1. <span data-ttu-id="f84b6-123">Azure Monitor ログ分析にサブスクライブしたら、Microsoft Teams ルーム本体から送信される情報を解析するのに必要なカスタムフィールドを作成します ([[マップのユーザー設定フィールド](azure-monitor-deploy.md#Custom_fields)] で説明されています)。</span><span class="sxs-lookup"><span data-stu-id="f84b6-123">Once subscribed to Azure Monitor Log Analytics, create custom fields (as described in [Map custom fields](azure-monitor-deploy.md#Custom_fields)) needed to parse the information that will be sent from Microsoft Teams Rooms consoles.</span></span> <span data-ttu-id="f84b6-124">これには、「[ログエントリについて理解](azure-monitor-manage.md#understand-the-log-entries)する」で説明されている JSON スキーマの概要が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f84b6-124">This includes understanding the JSON schema documented in [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries).</span></span>
    
2. <span data-ttu-id="f84b6-125">ログ分析で Microsoft Teams のルーム管理ビューを開発します。</span><span class="sxs-lookup"><span data-stu-id="f84b6-125">Develop a Microsoft Teams Rooms management view in Log Analytics.</span></span> <span data-ttu-id="f84b6-126">[Microsoft teams のルームダッシュボードを作成するには、インポート方法を使用](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method)するか、 [Microsoft teams のルームダッシュボードを手動で作成](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)します。</span><span class="sxs-lookup"><span data-stu-id="f84b6-126">You can either [Create a Microsoft Teams Rooms dashboard by using the import method](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) or [Create a Microsoft Teams Rooms dashboard manually](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).</span></span>
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a><span data-ttu-id="f84b6-127">個々の Microsoft Teams 室のコンソール要件</span><span class="sxs-lookup"><span data-stu-id="f84b6-127">Individual Microsoft Teams Rooms Console requirements</span></span>

<span data-ttu-id="f84b6-128">Microsoft Teams の各ルームコンソールは、キオスクモードで Surface Pro デバイスで実行されているアプリです (通常は、デバイスで実行できる唯一のアプリとして構成されています)。</span><span class="sxs-lookup"><span data-stu-id="f84b6-128">Each Microsoft Teams Rooms console is an app running on a Surface Pro device in kiosk mode (normally, it's configured to be the only app that can run on the device).</span></span> <span data-ttu-id="f84b6-129">他の Windows アプリと同じように、Microsoft Teams の会議アプリでは、起動やハードウェアの障害などのイベントを Windows イベントログに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="f84b6-129">As with any Windows app, the Microsoft Teams Rooms app writes events like startup and hardware faults to the Windows Event Log.</span></span> <span data-ttu-id="f84b6-130">Microsoft Teams のルームデバイスに Microsoft Monitor エージェントを追加すると、これらのイベントを収集できます。</span><span class="sxs-lookup"><span data-stu-id="f84b6-130">Adding an Microsoft Monitor agent on your Microsoft Teams Rooms device allows these events to be collected.</span></span> <span data-ttu-id="f84b6-131">(詳細については[、「Windows コンピューターを Azure のログ分析サービスに接続する」を](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)参照してください。)</span><span class="sxs-lookup"><span data-stu-id="f84b6-131">(See [Connect Windows computers to the Log Analytics service in Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) for details.)</span></span>
  
## <a name="ongoing-management"></a><span data-ttu-id="f84b6-132">進行中の管理</span><span class="sxs-lookup"><span data-stu-id="f84b6-132">Ongoing management</span></span>

<span data-ttu-id="f84b6-133">Azure モニターを使用して Microsoft Teams の会議室のデバイスを管理しているときに、Azure モニターで使用されるイベントログに含まれる情報について理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f84b6-133">While using Azure Monitor to manage your Microsoft Teams Rooms devices, you'll need to understand the information contained in the event logs used by Azure Monitor.</span></span> <span data-ttu-id="f84b6-134">これらの正常性メッセージの詳細について[は、「ログエントリについ](azure-monitor-manage.md#understand-the-log-entries)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f84b6-134">See [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries) for details on these health messages.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="f84b6-135">関連タスク</span><span class="sxs-lookup"><span data-stu-id="f84b6-135">Related Tasks</span></span>

- <span data-ttu-id="f84b6-136">Microsoft Teams のルームによって生成されるアラートとその解決方法について説明します (「[ログエントリを理解](azure-monitor-manage.md#understand-the-log-entries)する」のセクションを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="f84b6-136">Understand the Alerts generated by Microsoft Teams Rooms and how to resolve them (see the section titled [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries))</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f84b6-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="f84b6-137">See also</span></span>

[<span data-ttu-id="f84b6-138">Azure モニターを使用して Microsoft Teams のルーム管理を展開する</span><span class="sxs-lookup"><span data-stu-id="f84b6-138">Deploy Microsoft Teams Rooms management with Azure Monitor</span></span>](azure-monitor-deploy.md)
  
[<span data-ttu-id="f84b6-139">Azure モニターを使用して Microsoft Teams 室のデバイスを管理する</span><span class="sxs-lookup"><span data-stu-id="f84b6-139">Manage Microsoft Teams Rooms devices with Azure Monitor</span></span>](azure-monitor-manage.md)