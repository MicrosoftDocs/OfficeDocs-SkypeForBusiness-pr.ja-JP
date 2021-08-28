---
title: '[エッジ サーバーの展開を計画する] Skype for Business Server'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: '概要: エッジ環境Skype for Business Server計画します。 このトピックでは、Edge の概念について説明し、より詳細なトピックで整理できます。'
ms.openlocfilehash: 9acdb42e4ebc46fd6597ab047ee523b0ff309fb5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602462"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>[エッジ サーバーの展開を計画する] Skype for Business Server
 
**概要:** エッジ環境Skype for Business Server計画します。 このトピックでは、Edge の概念について説明し、より詳細なトピックで整理できます。
  
内部で動作Skype for Business Server環境がある場合は、エッジ サーバーまたはエッジ プールを環境に導入します。 この役割は、ユーザーが提供するサービスを内部ネットワークSkype for Business Serverユーザーが使用する場合に重要です。 これには、次のものが含まれる可能性があります。
  
- リモート ユーザー: 一時的または継続的な方法でオフサイトの従業員。
    
- フェデレーション ユーザー: パートナー組織の従業員。
    
- モバイル ユーザー。
    
- 会議やプレゼンテーションに招待する潜在的な顧客、パートナー、匿名ユーザー。
    
エッジ サーバーが提供する外部ユーザー アクセスを使用すると、このすべてが実行されます。 内部ユーザーは、ユーザーの展開によってホストされる次のサービスをSkype for Business Serverできます。
  
- IM とコミュニケーションのプレゼンス: 承認された外部ユーザーは、IM の会話や会議に参加できます。 他のユーザー (プレゼンス情報も取得するユーザー) のプレゼンス情報を取得できます。 パブリック IM プロバイダーを使用している場合、マルチパーティ会議は実行できないでしょう。これは厳密にはピアツーピア通信です。 ただし、SIP プロトコルと XMPP プロトコルの両方がサポートされています。
    
- 音声/ビデオ (A/V) 会議: 承認された外部ユーザーは、音声およびビデオSkype for Business Serverに参加できます。
    
- Web 会議: 承認された外部ユーザーは、会議に参加Skype for Businessできます。 必要に合って、リモート ユーザー、フェデレーション ユーザー、匿名ユーザーの参加を有効にできます。 パブリック IM ユーザーは会議に参加できません。 また、これらのユーザーがアプリケーションとデスクトップ共有に参加させ、会議の開催者や発表者として機能するオプションも用意されています。
    
モバイル デバイス アクセスは、モバイル デバイス アクセスと同様にエンタープライズ VoIP。 外部ユーザーにアクセス許可を付与する場合は、匿名ユーザーを含めて、出席を希望する会議に外部ユーザーを招待できます。
  
組織が必要としているような場合は、エッジ環境の計画が展開に大きな助けになります。 詳しくは、以下のトピックをご覧ください。

> [!NOTE]
> XMPP ゲートウェイとプロキシは 2015 年Skype for Business Server使用できますが、2019 年Skype for Business Serverではサポートされていません。 詳細 [については、「XMPP フェデレーションの移行](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 」を参照してください。 
  
## <a name="planning-topics"></a>計画のトピック:

計画に関する記事は次のとおりです。
  
- [2015 年のエッジ サーバーのシステム要件Skype for Business Server](system-requirements.md)
    
- [2015 年のエッジ サーバー Skype for Business Server要件](edge-environmental-requirements.md)
    
- [2015 年のエッジ Skype for Business Serverシナリオ](scenarios.md)
    

