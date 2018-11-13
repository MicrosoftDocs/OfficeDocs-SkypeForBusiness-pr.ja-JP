---
title: OMS を使用して Skype Room Systems バージョン 2 の管理を計画する
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
description: この資料では、ビジネスのサーバーの実装については、Skype で Skype ルーム システム v2 デバイスを管理する運用管理スイートを使用するための計画に関する考慮事項について説明します。
ms.openlocfilehash: 14f6ba95e5b2bcf7619002bb2dbc1e9ae3eb474a
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295626"
---
# <a name="plan-skype-room-systems-v2-management-with-oms"></a>OMS を使用して Skype Room Systems バージョン 2 の管理を計画する
 
 この資料では、ビジネスのサーバーの実装については、Skype で Skype ルーム システム v2 デバイスを管理する運用管理スイートを使用するための計画に関する考慮事項について説明します。
  
[操作の管理スイート](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview)(OMS) は、最初からクラウドのように設計された管理サービスのコレクションです。 展開して、オンプレミスのリソースを管理するのではなく OMS のコンポーネントは完全 Azure でホストされます。 構成は最小限とする起動してそのまま数分で。 カスタマイズのいくつかの作業では、個々 の部屋のシステムでは、システムの稼働状態や障害のリアルタイムの通知を提供することによって Skype ルーム システム v2 の会議システムを管理することも役に立ち、数千の Skype ルームのシステムを管理するに拡張できる可能性があります。v2 の会議室です。
  
この資料は、要件、設計とアーキテクチャ、および Skype ルーム システム v2 の会議デバイスの OMS の管理を実装するために必要な実装のベスト プラクティスの説明を提供し、OMS の実装に関する詳細な記事へのリンクが用意されていますSkype ルーム システム v2 と Skype ルーム システム v2 ルーム OMS の継続的な管理の重要な参照情報を管理します。 
  
## <a name="functional-overview"></a>機能の概要

![OMS を使用した SRS 管理の図](../../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
Skype ルーム システムがコンソール デバイス上のアプリケーションを v2 では、Windows イベント ログにイベントを書き込みます。 OMS エージェントはインストールされると情報を OMS に渡します。 
  
1 回が正しく構成されて、イベントの各 Skype ルーム システム v2 のシステムが機能している方法と、どのような障害が検出されたを記述する説明に埋め込まれた JSON ペイロード OMS 解析します。 
  
OMS を使用して管理者オフラインになっている Skype ルーム システム v2 のシステムの通知を受け取ることができますまたは、アプリケーション、接続、またはハードウェアの障害が発生しているだけでなく、システムを再起動する必要があるかどうかを知ること。 各システムのステータス更新 5 分ごとに、リアルタイム更新に近いので、これらの通知されます。
  
## <a name="oms-requirements"></a>OMS の要件

この機能を使用するには、OMS の有効なサブスクリプションが必要です。 所属する組織のためにサブスクリプションを用意するには、「[Log Analytics ワークスペースを使って作業を開始する](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started?toc=%2fazure%2foperations-management-suite%2ftoc.json)」を参照してください。
  
必要に応じて、OMS ビュー デザイナーの使用方法について理解を深めておく必要があります。 詳細については「[Operations Management Suite (OMS) 管理ソリューションのビュー](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-solutions-resources-views)」を参照してください。
  
### <a name="related-tasks"></a>関連タスク

1. OMS を購読して、作成カスタム フィールド ([ユーザー設定フィールドをマップ](../../deploy/deploy-clients/with-oms.md#Custom_fields)に記載されている) 必要な Skype ルーム システム v2 本体から送信される情報を解析します。 [ログ エントリを理解するの](../../manage/skype-room-systems-v2/oms.md#Telemetry)に記載されている JSON のスキーマを理解することが含まれます。
    
2. OMS の Skype ルーム システム v2 の管理ビューを作成します。 いずれかの[インポート メソッドを使用して Skype ルーム システム v2 のダッシュ ボードを作成する](../../deploy/deploy-clients/with-oms.md#create-a-skype-room-systems-v2-dashboard-by-using-the-import-method)ことができます) [Skype ルーム システム v2 のダッシュ ボード](../../deploy/deploy-clients/with-oms.md#create-a-skype-room-systems-v2-dashboard-manually)を手動で作成します。
    
## <a name="individual-skype-room-systems-v2-console-requirements"></a>Skype ルーム システム v2 コンソールの個々 の要件

各 Skype ルーム システム v2 のコンソールには、キオスク モードでサーフェスの 4 のデバイスで実行されているアプリケーション (通常は、その構成されているデバイスで実行できる唯一のアプリケーション)。 同様にすべての Windows アプリケーションでは、Skype ルーム システム v2 アプリケーションは、Windows イベント ログに起動し、ハードウェアの障害などのイベントを書き込みます。 OMS を収集するこれらのイベントを Skype ルーム システム v2 デバイスの OMS エージェントを追加できます。 (詳細については[接続の Windows コンピューター](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents)を参照してください)。
  
## <a name="ongoing-management"></a>進行中の管理

OMS を使用すると、Skype ルーム システム v2 の会議デバイスを管理するために、中には、OMS を使用するイベント ログに含まれる情報を理解しておく必要があります。 これらの状態メッセージの詳細については、[ログ エントリを理解する](../../manage/skype-room-systems-v2/oms.md#Telemetry)を参照してください。
  
### <a name="related-tasks"></a>関連タスク

- Skype ルーム システム v2 と ([ログのエントリを理解する](../../manage/skype-room-systems-v2/oms.md#Telemetry)」のセクションを参照してください) を解決するための方法で生成された警告を理解します。
    
## <a name="see-also"></a>関連項目

[OMS を使用した Skype Room Systems バージョン 2 の管理を展開する](../../deploy/deploy-clients/with-oms.md)
  
[OMS を使用した Skype Room Systems のデバイスを管理する](../../manage/skype-room-systems-v2/oms.md)