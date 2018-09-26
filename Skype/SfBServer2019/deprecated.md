---
title: ビジネス サーバー 2019 の Skype からどのような使用されなくなりました
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/10/2018
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: これらの機能がなくなる Skype からビジネス サーバー 2019 のです。'
ms.openlocfilehash: cf91b468fe1482c7348634553b6e9b196b864b2c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028762"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>ビジネス サーバー 2019 の Skype からどのような使用されなくなりました 

[!INCLUDE [disclaimer](disclaimer.md)]

ビジネス サーバー 2019 の Skype で廃止された機能について説明します。 ビジネス サーバー 2019 の Skype の新機能については、[ビジネス サーバー 2019 の Skype では、何](whats-new.md)を参照してください。

Emphasised の機能の一部に含まれて Skype ビジネス サーバー 2019 製品の以前のバージョンとの互換性のためです。 

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>ビジネス サーバー 2019 の Skype では非推奨の機能 

        The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>ビジネス サーバーの Skype の XMPP ゲートウェイ

ビジネス サーバー 2015 と、以前のバージョンの Skype には、エッジ サーバーとフロント エンド サーバーまたはフロント エンド プールに、XMPP ゲートウェイの拡張可能なメッセージングおよびプレゼンス プロトコル (XMPP) プロキシを構成することができました。 この機能は、ビジネス サーバー 2019 の Skype で利用可能ではありません。


### <a name="persistent-chat-for-skype-for-business-server"></a>Skype のビジネス サーバー用の永続的なチャット

永続的なチャット サーバーは、組織内の複数のユーザーをできるようにするオプションのロールは、時間の経過と共に永続化するチャット ルームの会話に参加します。 ビジネス サーバー 2019 Skype で永続的なチャットに展開することはできません。 トポロジ ビルダー、およびコードからは、このサーバーの役割が削除されます。 

同じ機能は、チームで使用できます。 詳細については、[マイクロソフトのチームにビジネス用の Skype からの旅](/microsoftteams/journey-skypeforbusiness-teams)を参照してください。   

### <a name="sql-mirroring-for-skype-for-business-server"></a>SQL が Skype のビジネス サーバーのミラーリング

SQL のミラーリングを展開できません Skype でのビジネス サーバー 2019。 高可用性と災害復旧を提供するその他のオプションがサポートされていて、その中から選択する必要があります。 オプションを確認するのには[高可用性とビジネスのサーバー用の Skype での災害復旧の計画](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)を参照してください。

### <a name="in-place-upgrades"></a>インプレース アップグレード 

インプレース アップグレードはビジネス サーバー 2015 の Skype で利用できるが、ビジネス サーバー 2019 の Skype でサポートされていません。 アップグレードおよび coexistance のサポートに並べて、[ビジネス サーバー 2019 の Skype への移行](migration/migration-to-skype-for-business-server-2019.md)の詳細についてを参照してください。

###  <a name="mobility-service-mcx"></a>モビリティ サービス (Mcx)

モビリティ サービスのサポートが従来のモバイル クライアントによって使用されるがビジネス サーバー 2019 の Skype で利用可能ではありません。 以前、Skype のビジネス サーバー 2015 のこの発表されました。

ビジネスのモバイル クライアントのすべての現在 Skype は、インスタント メッセージング (IM)、プレゼンス、および取引先担当者をサポートするために既にユニファイド コミュニケーション Web API (UCWA) を使用します。 Mcx を使用する従来のクライアントを持つユーザーは、現在のクライアントにアップグレードする必要があります。

詳細については、 [Skype ビジネス サーバーの移動を計画](../SfbServer/plan-your-deployment/mobility.md)し、[ビジネスの Skype のモバイル クライアントの機能の比較](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)を参照してください。

## <a name="tools"></a>ツール

次のツールはビジネス サーバー 2019 Skype の初期のリリースで使用できません。

- Skype ビジネス サーバーの容量計画の計算について
- Skype ビジネス サーバーのデバッグ ツールの
- Skype のビジネス サーバーのリソース キット ツールは (いくつかのツールは削除されます)
    - Call Parkometer
    - 参照ユーザー コンソール
    - 割り当てられていない番号移行のお知らせ

ビジネス サーバー 2019 の Skype で、次のツールがサポートされていません。

- 品質方法論のダッシュ ボードを呼び出す
- Microsoft 呼び出し品質方法論のスコアカード、v1.5
- Skype for Business Server 2015 計画ツール
- Skype ビジネス 2015 のサーバの負荷およびパフォーマンス ツール

### <a name="see-also"></a>関連項目

[ビジネス サーバー 2019 の Skype の新機能](whats-new.md)

[XMPP フェデレーションを移行します。](migration/migrating-xmpp-federation.md)