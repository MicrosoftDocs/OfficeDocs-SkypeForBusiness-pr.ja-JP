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
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>Azure のモニターを使用して Microsoft チームの会議室の管理を計画します。
 
 この資料では、Azure のモニターを使用してビジネス サーバーの実装については、Skype でマイクロソフト チームの会議室のデバイスを管理するための計画に関する考慮事項について説明します。
  
[Azure のモニター](https://docs.microsoft.com/azure/azure-monitor/overview)は、最初からクラウドのように設計された管理サービスのコレクションです。 展開して、オンプレミスのリソースを管理するのではなく Azure モニターのコンポーネント完全 Azure でホストされます。 構成は最小限とする起動してそのまま数分で。 カスタマイズのいくつかの作業では、個々 の部屋のシステムでは、システムの稼働状態や障害のリアルタイムの通知を提供することによって Microsoft チームの会議室の会議システムを管理することも役に立ち、何千ものマイクロソフトのチームを管理するに拡張できる可能性があります。会議室の会議室です。
  
この資料は、要件、設計とアーキテクチャ、およびマイクロソフト チーム ルーム会議デバイスでは、Azure のモニター ベースの管理を実装するために必要な実装のベスト プラクティスの説明が用意されていての詳細な記事へのリンクが用意されていますマイクロソフト チームの会議室とマイクロソフト チームの会議室の会議室の継続的な監視の重要な参照情報は Azure のモニターを実装します。 
  
## <a name="functional-overview"></a>機能の概要

![Azure のモニターを使用して Microsoft チームの会議室の管理の図](../../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
コンソール デバイス上のマイクロソフト チーム ルーム アプリケーションは、Windows イベント ログにイベントを書き込みます。 Microsoft の監視のエージェントをインストールすると、Azure 監視サービスに情報を渡します。 
  
1 回正しく構成されている、JSON ペイロードがマイクロソフト チームの会議室の各システムが機能していると、どのような障害が検出されたを記述する説明で埋め込みイベントのログの分析解析します。 
  
Azure のモニターを使用して管理者オフラインになっているマイクロソフト チームの会議室のシステムの通知を受け取ることができますまたは、アプリケーション、接続、またはハードウェアの障害が発生しているだけでなく、システムを再起動する必要があるかどうかを知ること。 各システムのステータスは、これらの通知は、更新をリアルタイムに近いので、頻繁に更新されます。
  
## <a name="azure-monitor-requirements"></a>Azure の監視要件

Azure の監視ログ分析機能を使用するのに有効な Azure サブスクリプションが必要です。 [ログ分析機能のワークスペースを使い始める](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)が、組織用のサブスクリプションを作成するを参照してください。
  
ログ分析ビュー デザイナーを使用する方法を必要に応じて、理解しておく必要があります。 詳細についてはこれらの[ログ分析のビュー](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)を参照してください。
  
### <a name="related-tasks"></a>関連タスク

1. 購読すると、Azure 監視ログ分析して、作成カスタム フィールド ([ユーザー設定フィールドをマップ](../../deploy/deploy-clients/azure-monitor.md#Custom_fields)に記載されている) 必要なマイクロソフト チームの会議室のコンソールから送られる情報を解析します。 [ログ エントリを理解するの](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries)に記載されている JSON のスキーマを理解することが含まれます。
    
2. ログ分析のマイクロソフト チームの会議室の管理ビューを作成します。 [Import メソッドを使用して Microsoft チームの会議室のダッシュ ボードを作成](../../deploy/deploy-clients/azure-monitor.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method)するか、[マイクロソフト チームの会議室のダッシュ ボードを手動で作成する](../../deploy/deploy-clients/azure-monitor.md#create-a-microsoft-teams-rooms-dashboard-manually)ことができます。
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>個々 のマイクロソフト チームの会議室のコンソールの要件

各マイクロソフト チームの会議室のコンソールには、キオスク モードで Surface Pro デバイスで実行されているアプリケーション (通常は、その構成されているデバイスで実行できる唯一のアプリケーション)。 同様にすべての Windows アプリケーションでは、チームの会議室をマイクロソフトのアプリケーションは Windows イベント ログに起動し、ハードウェアの障害などのイベントを書き込みます。 マイクロソフト チーム室デバイスに Microsoft モニター エージェントを追加することにより、これらのイベントを収集します。 (詳細については[接続の Windows コンピューター](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)を参照してください)。
  
## <a name="ongoing-management"></a>進行中の管理

Azure のモニターを使用して、マイクロソフト チームの会議室のデバイスを管理するために、Azure のモニターで使用されているイベント ログに含まれている情報を理解する必要があります。 これらの状態メッセージの詳細については、[ログ エントリを理解する](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries)を参照してください。
  
### <a name="related-tasks"></a>関連タスク

- ([ログのエントリを理解する](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries)」のセクションを参照してください) を解決するのにはマイクロソフト チームの会議室で生成された警告を理解します。
    
## <a name="see-also"></a>関連項目

[Azure のモニターを使用して Microsoft チームの会議室の管理を展開します。](../../deploy/deploy-clients/azure-monitor.md)
  
[Azure のモニターを使用して Microsoft チームの会議室のデバイスを管理します。](../../manage/skype-room-systems-v2/azure-monitor.md)