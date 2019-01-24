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
# <a name="plan-skype-room-systems-v2-management-with-azure-monitor"></a>Azure のモニターを使用して Skype ルーム システム v2 の管理を計画します。
 
 この資料では、Azure のモニターを使用してビジネス サーバーの実装については、Skype の Skype ルーム システム v2 デバイスを管理するための計画に関する考慮事項について説明します。
  
[Azure のモニター](https://docs.microsoft.com/azure/azure-monitor/overview)は、最初からクラウドのように設計された管理サービスのコレクションです。 展開して、オンプレミスのリソースを管理するのではなく Azure モニターのコンポーネント完全 Azure でホストされます。 構成は最小限とする起動してそのまま数分で。 カスタマイズのいくつかの作業では、個々 の部屋のシステムでは、システムの稼働状態や障害のリアルタイムの通知を提供することによって Skype ルーム システム v2 の会議システムを管理することも役に立ち、数千の Skype ルームのシステムを管理するに拡張できる可能性があります。v2 の会議室です。
  
この資料は、要件、設計とアーキテクチャ、および Skype ルーム システム v2 の会議デバイス、Azure のモニター ベースの管理を実装するために必要な実装のベスト プラクティスの説明が用意されていての詳細な記事へのリンクが用意されていますSkype ルーム システム v2 と Skype ルーム システム v2 の会議室の継続的な監視の重要な参照情報には、Azure のモニターを実装します。 
  
## <a name="functional-overview"></a>機能の概要

![Azure のモニターを使用した管理の SRS の図](../../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
Skype ルーム システムがコンソール デバイス上のアプリケーションを v2 では、Windows イベント ログにイベントを書き込みます。 Microsoft の監視のエージェントをインストールすると、Azure 監視サービスに情報を渡します。 
  
1 回が正しく構成されて、イベントの各 Skype ルーム システム v2 のシステムが機能している方法と、どのような障害が検出されたを記述する説明に埋め込まれた JSON ペイロード ログ分析解析します。 
  
Azure のモニターを使用して管理者オフラインになっている Skype ルーム システム v2 のシステムの通知を受け取ることができますまたは、アプリケーション、接続、またはハードウェアの障害が発生しているだけでなく、システムを再起動する必要があるかどうかを知ること。 各システムのステータスは、これらの通知は、更新をリアルタイムに近いので、頻繁に更新されます。
  
## <a name="azure-monitor-requirements"></a>Azure の監視要件

Azure の監視ログ分析機能を使用するのに有効な Azure サブスクリプションが必要です。 所属する組織のためにサブスクリプションを用意するには、「Log Analytics ワークスペースを使って作業を開始する」を参照してください。
  
ログ分析ビュー デザイナーを使用する方法を必要に応じて、理解しておく必要があります。 詳細についてはこれらの[ログ分析のビュー](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)を参照してください。
  
### <a name="related-tasks"></a>関連タスク

1. 購読すると、Azure 監視ログ分析機能をカスタム作成のフィールド ([ユーザー設定フィールドをマップ](../../deploy/deploy-clients/azure-monitor.md#Custom_fields)に記載されている) 必要な Skype ルーム システム v2 本体から送信される情報を解析します。 [ログ エントリを理解するの](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries)に記載されている JSON のスキーマを理解することが含まれます。
    
2. ログ分析で Skype ルーム システム v2 の管理ビューを作成します。 いずれかの[インポート メソッドを使用して Skype ルーム システム v2 のダッシュ ボードを作成する](../../deploy/deploy-clients/azure-monitor.md#create-a-skype-room-systems-v2-dashboard-by-using-the-import-method)ことができます) [Skype ルーム システム v2 のダッシュ ボード](../../deploy/deploy-clients/azure-monitor.md#create-a-skype-room-systems-v2-dashboard-manually)を手動で作成します。
    
## <a name="individual-skype-room-systems-v2-console-requirements"></a>Skype ルーム システム v2 コンソールの個々 の要件

各 Skype ルーム システム v2 のコンソールには、キオスク モードで Surface Pro デバイスで実行されているアプリケーション (通常は、その構成されているデバイスで実行できる唯一のアプリケーション)。 同様にすべての Windows アプリケーションでは、Skype ルーム システム v2 アプリケーションは、Windows イベント ログに起動し、ハードウェアの障害などのイベントを書き込みます。 Skype ルーム システム v2 デバイスに Microsoft の監視エージェントを追加するには、これらのイベントを収集することができます。 (詳細については[接続の Windows コンピューター](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)を参照してください)。
  
## <a name="ongoing-management"></a>進行中の管理

Azure のモニターを使用して、Skype ルーム システム v2 のデバイスを管理するために、Azure のモニターで使用されているイベント ログに含まれている情報を理解する必要があります。 これらの状態メッセージの詳細については、[ログ エントリを理解する](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries)を参照してください。
  
### <a name="related-tasks"></a>関連タスク

- Skype ルーム システム v2 と ([ログのエントリを理解する](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries)」のセクションを参照してください) を解決するための方法で生成された警告を理解します。
    
## <a name="see-also"></a>関連項目

[Azure のモニターを使用して Skype ルーム システム v2 の管理を展開します。](../../deploy/deploy-clients/azure-monitor.md)
  
[Azure のモニターを使用して Skype ルーム システム v2 のデバイスを管理します。](../../manage/skype-room-systems-v2/azure-monitor.md)