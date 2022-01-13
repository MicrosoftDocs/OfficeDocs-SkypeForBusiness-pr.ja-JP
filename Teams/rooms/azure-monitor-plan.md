---
title: Azure Monitor Microsoft Teams会議室の監視を計画する
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection:
- M365-collaboration
description: この記事では、Azure Monitor を使用して、お使Microsoft Teams実装内の Skype for Business 会議室を監視Teams説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 13c16234773792f9dc394723521224123c5e2141
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015207"
---
# <a name="plan-microsoft-teams-rooms-monitoring-with-azure-monitor"></a>Azure Monitor Microsoft Teams会議室の監視を計画する
 
 この記事では、Microsoft Teams や Skype for Business の実装で、Azure Monitor を使用して Microsoft Teams Rooms デバイスを管理する場合の計画上の考慮事項について説明します。

> [!NOTE]
> 管理センター[を使用して、会議室Teams正常性](../alerts/device-health-status.md)Teams設定できます。

[Azure Monitor](/azure/azure-monitor/overview) は、最初からクラウドで設計された監視サービスのコレクションです。 Azure Monitor コンポーネントでは、オンプレミスのリソースをデプロイおよび管理するのではなく、すべて Azure でホストされます。 構成は最小限で、数分で稼働できます。 カスタマイズ作業によっては、個々のルーム システムにシステムの正常性または障害の通知を提供することで Microsoft Teams 会議室の監視を支援し、数千の Microsoft Teams 会議室を管理するためにスケールアップできます。
  
この記事では、Microsoft Teams Rooms の Azure Monitor ベースの監視を実装するために必要な要件、設計/アーキテクチャ、実装のベスト プラクティスについて説明します。 また、Azure Monitor for Microsoft Teams Rooms の実装に関する詳細な記事と、Microsoft Teams 会議室の継続的な監視に関する重要なリファレンス情報へのリンクも提供します。
  
## <a name="functional-overview"></a>機能の概要

![Azure Monitor をMicrosoft Teams会議室管理の図。](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
Microsoft Teams Rooms アプリは、イベントをイベント ログにWindowsします。 Microsoft Monitoring エージェントがインストールされ、Azure Monitor サービスに情報が渡されます。
  
適切に構成されると、Log Analytics はイベントの説明に埋め込まれた JSON ペイロードを解析して、Microsoft Teams Rooms がどのように機能し、どのような障害が検出されるのかを説明します。
  
Azure Monitor を使用する管理者は、オフラインの Microsoft Teams 会議室またはアプリ、接続、またはハードウェアの障害が発生している Microsoft Teams 会議室の通知を受け取り、システムを再起動する必要がある場合に知らせます。 各システムの状態は頻繁に更新されるため、これらの通知はほぼリアルタイムの更新情報となります。
  
## <a name="azure-monitor-requirements"></a>Azure Monitor の要件

Log Analytics 機能を使用するには、Azure Monitor の有効な Azure サブスクリプションが必要です。 組織のサブスクリプションを作成するには、「[Log Analytics ワークスペースの使用を開始する](/azure/azure-monitor/learn/quick-create-workspace)」を参照してください。
  
Log Analytics ビュー デザイナーの使い方を理解する必要があります。 これらの詳細については、「[Log Analytics のビュー](/azure/azure-monitor/platform/view-designer)」をご覧ください。
  
### <a name="related-tasks"></a>関連作業

1. Azure Monitor Log Analytics をサブスクライブしたら、Microsoft Teams Rooms[](azure-monitor-deploy.md#Custom_fields)から送信される情報を解析するために必要なカスタム フィールドを作成します (「カスタム フィールドのマップ」を参照)。 これには、「[ログ エントリを理解する](azure-monitor-manage.md#understand-the-log-entries)」で説明されている JSON スキーマについて理解することが含まれます。
    
2. Log Analytics の [Microsoft Teams Rooms 管理] ビューを開発します。 [会議室[] ダッシュボードMicrosoft Teams手動で作成できます](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)。
    
## <a name="individual-microsoft-teams-rooms-requirements"></a>個々Microsoft Teamsルームの要件

Microsoft Teams会議室は、キオスク モードのコンピューティング デバイスで実行されているアプリです。 他の Windows アプリと同様に、Microsoft Teams Rooms アプリは、起動やハードウェア障害などのイベントを Windows イベント ログに記録します。 Microsoft Teams Rooms に Microsoft Monitor エージェントを追加すると、これらのイベントを収集できます。 (詳細については、「[Windows コンピューターを Azure の Log Analytics サービスに接続する](/azure/azure-monitor/platform/agent-windows)」を参照してください。)
  
## <a name="ongoing-management"></a>継続的な管理

Azure Monitor を使用して Microsoft Teams 会議室を監視する場合は、Azure Monitor で使用されるイベント ログに含まれる情報を理解する必要があります。 これらの正常性メッセージの詳細については、「[ログ エントリを理解する](azure-monitor-manage.md#understand-the-log-entries)」を参照してください。
  
### <a name="related-tasks"></a>関連作業

- Microsoft Teams Rooms により生成されたアラートとそれらの解決方法を理解する (「[ログ エントリを理解する](azure-monitor-manage.md#understand-the-log-entries)」というタイトルのセクションを参照)
    
## <a name="see-also"></a>関連項目

[Azure Monitor を使用して Microsoft Teams Rooms 管理をデプロイする](azure-monitor-deploy.md)
  
[Azure Monitorを使用して Microsoft Teams Rooms デバイスをデプロイする](azure-monitor-manage.md)
