---
title: Skype でビジネス サーバー用のエッジ サーバー展開の計画
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: '概要: は、サーバーのエッジをビジネス環境に、Skype を計画します。 このトピックでは、エッジの概念を紹介し、より詳細なトピックで体系的に学習できるようにします。'
ms.openlocfilehash: 41a1d2771e43a4e217aa8bac6b98331a31d67c92
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20965444"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>Skype でビジネス サーバー用のエッジ サーバー展開の計画
 
**の概要:** サーバー エッジのビジネス環境について、Skype を計画します。 このトピックでは、エッジの概念を紹介し、より詳細なトピックで体系的に学習できるようにします。
  
Skype の内部で適切に動作しているサーバーのビジネス環境がある場合は、エッジ サーバーまたはエッジ プールを環境に導入する次の手順があります。 この役割は、内部ネットワークの外にいる人が使用するサーバーをビジネスの Skype が提供するサービスをする場合に重要になります。 次の種類のユーザーが含まれる可能性があります。
  
- リモート ユーザー: 一時的または継続的にオフサイトで作業している従業員。
    
- : フェデレーションのユーザー、パートナー企業の従業員です。
    
- モバイル ユーザー。
    
- 会議やプレゼンテーションに招待する必要がある潜在的な顧客やパートナー、および場合によっては匿名ユーザー。
    
、エッジ トランスポート サーバーが提供するものでは、外部ユーザー アクセスを許可すると、このようです。 内部ユーザーはビジネスのサーバーの展開に、Skype でホストされている次のサービスを利用することになります。
  
- IM とプレゼンスの通信: 許可された外部ユーザーは、IM 会話および会議に参加できます。 (ユーザーが自分のプレゼンス情報を取得する) 他のユーザーのプレゼンス情報を受けることができます。 厳密にピア ツー ピア通信には、パブリック IM プロバイダーを使用する場合は、マルチパーティの会議を行うことはできません。 SIP および XMPP プロトコルをサポートします。
    
- オーディオ/ビデオ (A/V) 会議: 許可された外部ユーザーは、ビジネスのサーバーの音声およびビデオ会議用、Skype に参加できます。
    
- Web 会議: ビジネス会議は、Skype で、許可された外部ユーザーが参加できます。 希望の場合も、リモート ユーザー、フェデレーション ユーザー、および匿名ユーザーの参加を有効にできます。 パブリック IM ユーザーは、会議に参加できません。 これらのユーザーのアプリケーションおよびデスクトップ共有への参加や、場合によっては会議の開催者または発表者の役割を可能にするオプションもあります。
    
モバイル デバイスへのアクセスをサポートすると、エンタープライズ VoIP では。 外部ユーザーにアクセス許可を付与する必要があれば、場合によっては匿名ユーザーを含め、外部ユーザーの参加が必要な会議に招待することができます。
  
上記の機能が組織で必要であると考えられる場合は、エッジ環境を計画すると、その機能を展開するのに大いに役立ちます。その他の資料としては、以下のトピックがあります。

> [!NOTE]
> XMPP ゲートウェイとプロキシ サーバー 2015 のビジネス用の Skype では利用ビジネス サーバー 2019 の Skype でサポートされていません。 詳細については、[移行する XMPP フェデレーション](../../../SfBServer2019/migration/migrating-xmpp-federation.md)を参照してください。 
  
## <a name="planning-topics"></a>計画に関するトピック:

計画に関する記事:
  
- [Skype for Business Server 2015 のエッジ サーバーのシステム要件](system-requirements.md)
    
- [Skype for Business Server 2015 のエッジ サーバーの環境要件](edge-environmental-requirements.md)
    
- [Skype for Business Server 2015 のエッジ サーバーのシナリオ](scenarios.md)
    

