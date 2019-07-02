---
title: Skype for Business Server 2019 で廃止される機能
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: これらの機能は、Skype for Business Server 2019 から削除されました。'
ms.openlocfilehash: 9fd6ddc28a3b75b8d4c411aa7909516d4b5c0ab8
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418362"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>Skype for Business Server 2019 で廃止される機能

Skype for Business Server 2019 で廃止された機能について説明します。 Skype for Business Server 2019 の新機能の詳細については、「Skype for business [server 2019](whats-new.md)の機能」を参照してください。

以前の製品バージョンとの互換性を確保するために、いくつかの強調機能が Skype for Business Server 2019 に含まれています。

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Skype for Business Server 2019 で廃止された機能 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Skype for Business Server 用 XMPP ゲートウェイ

Skype for Business Server 2015 とその先行機能を使用すると、エッジサーバー上の拡張メッセージングとプレゼンスプロトコル (XMPP) プロキシ、およびフロントエンドサーバーまたはフロントエンドプールの XMPP ゲートウェイを構成することができます。 この機能は、Skype for Business Server 2019 では利用できなくなりました。

### <a name="persistent-chat-for-skype-for-business-server"></a>Skype for Business Server の常設チャット

常設チャットサーバーは、組織内の複数のユーザーが、時間を経て持続するチャットルームの会話に参加できるようにする、オプションの役割です。 常設チャットを Skype for Business Server 2019 で展開することはできません。 このサーバーロールは、コードからではなく、トポロジビルダーからも削除されます。 

Teams でも同じ機能を使用できます。 詳細については、「 [Microsoft Teams のアップグレードの](/microsoftteams/upgrade-start-here)概要」を参照してください。

### <a name="sql-mirroring-for-skype-for-business-server"></a>Skype for Business Server の SQL ミラーリング

SQL ミラーリングは、Skype for Business Server 2019 と共に展開することはできません。 高可用性と障害回復を実現するその他のオプションもサポートされていますが、それらの中から選択することをお勧めします。 オプションを確認するには、「 [Skype For Business Server で高可用性と障害回復を計画](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)する」を参照してください。

### <a name="in-place-upgrades"></a>インプレースアップグレード 

インプレースアップグレードは、Skype for Business Server 2015 で使用できましたが、Skype for Business Server 2019 ではサポートされなくなりました。 サイドバイサイドアップグレードと coexistance 使用はサポートされています。詳細については、「 [Skype For Business Server 2019 への移行](migration/migration-to-skype-for-business-server-2019.md)」を参照してください。

### <a name="mobility-service-mcx"></a>モビリティーサービス (Mcx)

従来のモバイルクライアントで使用されているモバイルサービスのサポートは、Skype for Business Server 2019 では利用できなくなりました。 これは、Skype for Business Server 2015 で以前に発表されました。

現在のすべての Skype for Business のモバイルクライアントでは、インスタントメッセージング (IM)、プレゼンス、連絡先をサポートするために、既にユニファイドコミュニケーション Web API (UCWA) を使用しています。 Mcx を使用するレガシクライアントを使っているユーザーは、現在のクライアントにアップグレードする必要があります。

詳細については、「skype for business [Server のモビリティの計画](../SfbServer/plan-your-deployment/mobility.md)」および「 [skype For business のモバイルクライアント機能の比較](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)」を参照してください。

## <a name="tools"></a>ツール

以下のツールは、Skype for Business Server 2019 の最初のリリースでは使用できません。

- Skype for Business Server の容量計画計算ツール
- Skype for Business Server のデバッグツール
- Skype for Business Server リソースキットツール (一部のツールは削除されます)
    - Call Parkometer
    - ユーザーコンソールを参照する
    - 未割り当ての番号の移行

以下のツールは、Skype for Business Server 2019 ではサポートされていません。

- 通話品質の方法 (通話品質ダッシュボードではありません)
- Microsoft 通話品質の方法スコアカード、v 1.5
- Skype for Business Server 2015 計画ツール
- Skype for Business Server 2015 Stress and Performance Tool

### <a name="see-also"></a>関連項目

[Skype for Business Server 2019 の新機能](whats-new.md)

[XMPP フェデレーションの移行](migration/migrating-xmpp-federation.md)
