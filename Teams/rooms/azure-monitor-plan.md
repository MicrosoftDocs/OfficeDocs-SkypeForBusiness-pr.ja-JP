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
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>Azure Monitor を使用して Microsoft Teams ミーティング管理を計画する
 
 この記事では、Microsoft Teams や Skype for Business の実装で、Azure Monitor を使用して Microsoft Teams ミーティング デバイスを管理する場合の計画上の考慮事項について説明します。
  
[Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) は、最初からクラウドに設計された管理サービスのコレクションです。 Azure Monitor コンポーネントでは、オンプレミスのリソースをデプロイおよび管理するのではなく、すべて Azure でホストされます。 構成が最小限に抑えられ、わずか数分で稼働させることができます。 特定のカスタマイズ機能を使用すると、個々の会議室システムのシステム正常性やフォールトをリアルタイムで通知することで、Microsoft Teams ミーティングの会議システムの管理に役立ち、数千の Microsoft Teams ミーティングの会議室の管理にスケールアップできる可能性があります。
  
この記事では、Microsoft Teams ミーティングの会議デバイスのための Azure Monitor ベースの管理を実装するために必要な要件、設計やアーキテクチャ、実装のベストプラクティスについて説明し、Microsoft Teams ミーティング用の Azure Monitor の実装に関する詳細な記事へのリンクを提供します。また、Microsoft Teams ミーティングの会議室を継続的に監視するための重要な参照情報を提供します。 
  
## <a name="functional-overview"></a>機能の概要

![Azure Monitor を使用した Microsoft Teams ミーティング管理の図](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
コンソール デバイス上の Microsoft Teams ミーティング アプリは Windows イベント ログにイベントを書き込みます。 Microsoft Monitoring エージェントは、インストール後、情報を Azure Monitor サービスに渡します。 
  
Log Analytics は、適切に構成されると、イベントの説明に埋め込まれた JSON ペイロードを解析して、各 Microsoft Teams ミーティング システムがどのように機能しているか、および検出されたエラーが何であるかを説明します。 
  
Azure Monitor を使用している管理者は、Microsoft Teams ミーティング システムがオフラインであること、問題が発生しているアプリ、接続、ハードウェアの障害が発生していること、およびシステムの再起動が必要かどうかを知らせるシステムの通知を受信できます。 各システムの状態は頻繁に更新されるため、これらの通知はほぼリアルタイムの更新情報となります。
  
## <a name="azure-monitor-requirements"></a>Azure Monitor の要件

Log Analytics 機能を使用するには、Azure Monitor 用の有効な Azure サブスクリプションが必要です。 組織のサブスクリプションを作成するには、「[Log Analytics ワークスペースの使用を開始する](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)」を参照してください。
  
必要に応じて、Log Analytics ビュー デザイナーの使用方法について理解を深めておく必要があります。 これらの詳細については、「[Log Analytics のビュー](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)」をご覧ください。
  
### <a name="related-tasks"></a>関連作業

1. Azure Monitor Log Analytics の登録後、Microsoft Teams ミーティング コンソールから送信される情報を解析するのに必要なカスタム フィールドを作成します (「[カスタム フィールドをマップする](azure-monitor-deploy.md#Custom_fields)」に説明されています)。 これには、「[ログ エントリを理解する](azure-monitor-manage.md#understand-the-log-entries)」で説明されている JSON スキーマについて理解することが含まれます。
    
2. Log Analytics の [Microsoft Teams ミーティング管理] ビューを開発します。 「[インポート メソッドを使用して Microsoft Teams ミーティング ダッシュボードを作成する](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method)」ことも、「[Microsoft Teams ミーティング ダッシュボードを手動で作成する](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)」こともできます。
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>個々の Microsoft Teams ミーティング コンソールの要件

Microsoft Teams ミーティングの各コンソールは、キオスク モードの Surface Pro デバイスで実行されているアプリです (通常、デバイスで実行できるアプリのみが構成されています)。 他の Windows アプリと同様に、Microsoft Teams ミーティング アプリは、起動やハードウェア障害などのイベントを Windows イベント ログに記録します。 Microsoft Teams ミーティング デバイス に Microsoft Monitor エージェントを追加すると、これらのイベントを収集できます。 (詳細については、「[Windows コンピューターを Azure の Log Analytics サービスに接続する](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)」を参照してください。)
  
## <a name="ongoing-management"></a>継続的な管理

Azure Monitor を使用してお使いの Microsoft Teams ミーティング デバイスを管理するときに、Azure Monitor によって使用されているイベント ログに含まれる情報を理解する必要があります。 これらの正常性メッセージの詳細については、「[ログ エントリを理解する](azure-monitor-manage.md#understand-the-log-entries)」を参照してください。
  
### <a name="related-tasks"></a>関連作業

- Microsoft Teams ミーティングにより生成されたアラートとそれらの解決方法を理解する (「[ログ エントリを理解する](azure-monitor-manage.md#understand-the-log-entries)」というタイトルのセクションを参照)
    
## <a name="see-also"></a>関連項目

[Azure Monitor を使用して Microsoft Teams ミーティング管理をデプロイする](azure-monitor-deploy.md)
  
[Azure Monitorを使用して Microsoft Teams ミーティング デバイスをデプロイする](azure-monitor-manage.md)