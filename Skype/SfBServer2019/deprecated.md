---
title: 2019 年から廃止Skype for Business Server
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
description: '概要: これらの機能は、2019 年Skype for Business Serverされています。'
ms.openlocfilehash: 43fa8bae64e65fcba1aaf21c75e06d396d3c47eee8df40cec0db0eb1d5d646eb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282470"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>2019 年から廃止Skype for Business Server

2019 年に廃止された機能についてSkype for Business Server。 2019 年 2019 年Skype for Business Server新機能の詳細については[、「What's in Skype for Business Server 2019」を参照](whats-new.md)してください。

以前の製品バージョンとの互換性のために、2019 Skype for Business Serverにいくつかの強調されていない機能が含まれています。

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>2019 年 2019 年Skype for Business Server機能 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>XMPP Gateways for Skype for Business Server

Skype for Business Server 2015 とその先行タスクでは、エッジ サーバー上の拡張可能メッセージングとプレゼンス プロトコル (XMPP) プロキシと、フロントエンド サーバーまたはフロントエンド プール上の XMPP ゲートウェイを構成できます。 この機能は、2019 年Skype for Business Serverなくなりました。

### <a name="persistent-chat-for-skype-for-business-server"></a>ユーザーの常設チャットSkype for Business Server

常設チャット サーバーは、組織内の複数のユーザーがチャット ルームの会話に参加し、時間の長い間保持できるオプションの役割です。 常設チャットは、2019 年にSkype for Business Serverされません。 このサーバーの役割は、トポロジ ビルダーだけでなく、コードから削除されます。 

同じ機能は、Teams。 詳細については、「アップグレードの開始[方法」をMicrosoft Teamsしてください](/microsoftteams/upgrade-start-here)。

### <a name="sql-mirroring-for-skype-for-business-server"></a>SQLサーバーのミラーリングSkype for Business Server

SQL2019 年にミラーリングを展開Skype for Business Server。 高可用性と障害復旧を提供するためのその他のオプションは引き続きサポートされ、その中から選択する必要があります。 オプション[を確認するには、「高可用性と障害復旧を計画する」を参照Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)を参照してください。

### <a name="in-place-upgrades"></a>一括アップグレード 

インプレイス アップグレードは 2015 年Skype for Business Serverでしたが、2019 年Skype for Business Serverではサポートされていません。 サイド バイ サイド アップグレードと共存がサポートされています。詳細については[、「migration to Skype for Business Server 2019」](migration/migration-to-skype-for-business-server-2019.md)を参照してください。

### <a name="mobility-service-mcx"></a>モビリティ サービス (Mcx)

従来のモバイル クライアントで使用される Mobility Service のサポートは、2019 年Skype for Business Serverできません。 これは、2015 年Skype for Business Server発表されました。

現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。 Mcx を使用している従来のクライアントを持つユーザーは、現在のクライアントにアップグレードする必要があります。

詳細については、「Plan [for Mobility for Skype for Business Server」および「](../SfbServer/plan-your-deployment/mobility.md)モバイル クライアント機能の比較」[を参照](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)Skype for Business。

## <a name="tools"></a>ツール

次のツールは、2019 年の最初のリリースではSkype for Business Serverできません。

- Skype for Business Server の容量計画計算ツール
- Skype for Business Serverデバッグ ツール
- Skype for Business Serverリソース キット ツール (一部のツールは削除されます)
    - Call Parkometer
    - ユーザー コンソールの参照
    - 割り当てられていない番号アナウンスの移行

次のツールは、2019 年Skype for Business Serverサポートされていません。

- 通話品質の方法 (ただし、通話品質ダッシュボードは呼び出ししない)
- Microsoft Call Quality Methodology Scorecard, v1.5
- Skype for Business Server 2015 計画ツール
- Skype for Business Server 2015 ストレスとパフォーマンス ツール

### <a name="see-also"></a>関連項目

[2019 年の新機能Skype for Business Server](whats-new.md)

[XMPP フェデレーションの移行](migration/migrating-xmpp-federation.md)
