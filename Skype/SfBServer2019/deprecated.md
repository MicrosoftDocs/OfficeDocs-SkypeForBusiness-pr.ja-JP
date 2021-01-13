---
title: Skype for Business Server 2019 で廃止された機能
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: これらの機能は Skype for Business Server 2019 から削除されました。'
ms.openlocfilehash: 5c5914493d7e2f4da4fd72d6acf7ff2b979d8e88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808727"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>Skype for Business Server 2019 で廃止された機能

Skype for Business Server 2019 で廃止された機能について説明します。 Skype for Business Server 2019 の新機能の詳細については [、「Skype for Business Server 2019](whats-new.md)の機能」を参照してください。

Skype for Business Server 2019 には、以前の製品バージョンとの互換性のために、重視されていない機能がいくつか含まれています。

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Skype for Business Server 2019 で廃止された機能 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>XMPP Gateways for Skype for Business Server

Skype for Business Server 2015 とその先行タスクでは、エッジ サーバー上の XMPP (Extensible Messaging and Presence Protocol) プロキシと、フロントエンド サーバーまたはフロントエンド プール上の XMPP ゲートウェイを構成できます。 この機能は、Skype for Business Server 2019 では使用できなくなりました。

### <a name="persistent-chat-for-skype-for-business-server"></a>Skype for Business Server の常設チャット

常設チャット サーバーはオプションの役割で、組織内の複数のユーザーがチャット ルームの会話に参加できます。チャット ルームの会話は、時間の長い間持続します。 常設チャットは Skype for Business Server 2019 では展開できません。 このサーバーの役割は、トポロジ ビルダーおよびコードから削除されます。 

Teams でも同じ機能を使用できます。 詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。

### <a name="sql-mirroring-for-skype-for-business-server"></a>SQL Skype for Business Server のミラーリング

SQL Skype for Business Server 2019 ではミラーリングを展開できません。 高可用性と障害復旧を提供するためのその他のオプションも引き続きサポートされ、その中から選択する必要があります。 オプション [を確認するには、「Plan for high availability and disaster recovery in Skype for Business Server」](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) を参照してください。

### <a name="in-place-upgrades"></a>一括アップグレード 

一時アップグレードは Skype for Business Server 2015 で利用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 サイド バイ サイド アップグレードと共存がサポートされています。詳細については [、「Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) への移行」を参照してください。

### <a name="mobility-service-mcx"></a>Mobility Service (Mcx)

従来のモバイル クライアントで使用される Mobility Service のサポートは、Skype for Business Server 2019 では使用できなくなりました。 これは、Skype for Business Server 2015 で以前に発表されました。

現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。 Mcx を使用するレガシ クライアントを持つユーザーは、現在のクライアントにアップグレードする必要があります。

詳細については [、「Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and Mobile client feature comparison for Skype for Business 」を [参照してください](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)。

## <a name="tools"></a>ツール

次のツールは、Skype for Business Server 2019 の最初のリリースでは使用できません。

- Skype for Business Server の容量計画計算ツール
- Skype for Business Server デバッグ ツール
- Skype for Business Server リソース キット ツール (一部のツールは削除されます)
    - Call Parkometer
    - ユーザー コンソールを参照する
    - 割り当てられていない番号のアナウンスの移行

次のツールは、Skype for Business Server 2019 ではサポートされていません。

- 通話品質の方法論 (通話品質ダッシュボードではない)
- Microsoft Call Quality Methodology Scorecard、v1.5
- Skype for Business Server 2015 計画ツール
- Skype for Business Server 2015 Stress and Performance Tool

### <a name="see-also"></a>関連項目

[Skype for Business Server 2019 の新機能](whats-new.md)

[XMPP フェデレーションの移行](migration/migrating-xmpp-federation.md)
