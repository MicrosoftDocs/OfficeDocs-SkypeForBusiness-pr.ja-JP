---
title: Skype for Business Server 2019 で廃止された機能
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: これらの機能は、Skype for Business Server 2019 から削除されました。'
ms.openlocfilehash: 40a202f802ec8ac1a0f880f92ad9cf59ce68a627
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42125220"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>Skype for Business Server 2019 で廃止された機能

Skype for Business Server 2019 で廃止された機能について説明します。 Skype for business Server 2019 の新機能の詳細については、「 [skype For Business server 2019 の内容](whats-new.md)」を参照してください。

以前の製品バージョンとの互換性のために、いくつかの重要な機能が Skype for Business Server 2019 に含まれています。

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Skype for Business Server 2019 で廃止された機能 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Skype for business Server 用の XMPP ゲートウェイ

Skype for Business Server 2015 とその先行機能により、エッジサーバー上に拡張可能なメッセージングとプレゼンスプロトコル (XMPP) プロキシを構成し、フロントエンドサーバーまたはフロントエンドプールに XMPP ゲートウェイを構成することができました。 この機能は、Skype for Business Server 2019 では使用できなくなりました。

### <a name="persistent-chat-for-skype-for-business-server"></a>Skype for Business Server の常設チャット

常設チャットサーバーは、組織内の複数のユーザーが時間の経過と共に持続するチャットルームの会話に参加できるようにするオプションの役割です。 常設チャットは、Skype for Business Server 2019 では展開できません。 このサーバーの役割は、トポロジビルダー、およびコードから削除されます。 

Teams でも同じ機能を使用できます。 詳細については、「 [Microsoft Teams のアップグレードの概要](/microsoftteams/upgrade-start-here)」を参照してください。

### <a name="sql-mirroring-for-skype-for-business-server"></a>Skype for Business Server の SQL ミラーリング

SQL ミラーリングは、Skype for Business Server 2019 では展開できません。 高可用性と障害復旧を提供するその他のオプションもサポートされていますが、それらの中から選択する必要があります。 オプションを確認するには、「 [Plan for high availability and disaster recovery In Skype For Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 」を参照してください。

### <a name="in-place-upgrades"></a>一括アップグレード 

一括アップグレードは Skype for business Server 2015 で利用できましたが、Skype for Business Server 2019 ではサポートされなくなりました。 サイドバイサイドアップグレードと共存使用はサポートされています。詳細については、「 [Skype for business Server 2019 への移行](migration/migration-to-skype-for-business-server-2019.md)」を参照してください。

### <a name="mobility-service-mcx"></a>Mobility Service (Mcx)

従来のモバイルクライアントで使用されていた Mobility Service のサポートは、Skype for Business Server 2019 では利用できなくなりました。 これは Skype for Business Server 2015 で既に発表されています。

現在の Skype for Business mobile クライアントはすべて、既に統合コミュニケーション Web API (UCWA) を使用して、インスタントメッセージング (IM)、プレゼンス、および連絡先をサポートしています。 Mcx を使用しているレガシクライアントを使用しているユーザーは、現在のクライアントにアップグレードする必要があります。

詳細については、「skype for business [Server のプランを計画](../SfbServer/plan-your-deployment/mobility.md)する」および「skype for Business[のモバイルクライアント機能の比較](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)」を参照してください。

## <a name="tools"></a>ツール

次のツールは、Skype for Business Server 2019 の最初のリリースでは使用できません。

- Skype for Business Server の容量計画の計算機
- Skype for Business Server デバッグツール
- Skype for Business Server リソースキットツール (一部のツールは削除されます)
    - コール Par・メータ計
    - 参照ユーザーコンソール
    - 割り当てられていない番号アナウンスの移行

次のツールは、Skype for Business Server 2019 ではサポートされていません。

- 通話品質の方法論 (通話品質ダッシュボードではない)
- Microsoft 通話品質の方法スコアカード、v2.0
- Skype for Business Server 2015 計画ツール
- Skype for Business Server 2015 ストレスおよびパフォーマンスツール

### <a name="see-also"></a>関連項目

[Skype for Business Server 2019 の新機能](whats-new.md)

[XMPP フェデレーションの移行](migration/migrating-xmpp-federation.md)
