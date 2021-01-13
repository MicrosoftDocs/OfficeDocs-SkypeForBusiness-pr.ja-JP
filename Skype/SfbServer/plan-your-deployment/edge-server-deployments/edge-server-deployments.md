---
title: Skype for Business Server でのエッジ サーバーの展開を計画する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: '概要: Skype for Business Server Edge 環境を計画します。 このトピックでは、Edge の概念について説明し、より詳細なトピックを整理できます。'
ms.openlocfilehash: 277e344448f5229d15addf965695f19ec2884649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813807"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>Skype for Business Server でのエッジ サーバーの展開を計画する
 
**概要:** Skype for Business Server Edge 環境を計画します。 このトピックでは、Edge の概念について説明し、より詳細なトピックを整理できます。
  
Skype for Business Server 環境が内部でうまく機能している場合は、次の手順として、エッジ サーバーまたはエッジ プールを環境に導入します。 この役割は、内部ネットワークの外部のユーザーが Skype for Business Server によって提供されるサービスを使用する場合に非常に重要です。 次のような場合があります。
  
- リモート ユーザー: 一時的または継続的な方法でオフサイトの従業員。
    
- フェデレーション ユーザー: パートナー組織の従業員。
    
- モバイル ユーザー。
    
- 潜在的な顧客、パートナー、会議やプレゼンテーションに招待する匿名ユーザー。
    
エッジ サーバーが提供する外部ユーザー アクセスにより、このすべてが可能になります。 内部ユーザーは、Skype for Business Server 展開でホストされている次のサービスを利用できます。
  
- 通信用の IM とプレゼンス: 承認された外部ユーザーは、IM 会話および会議に参加できます。 他のユーザー (自分のプレゼンス情報も取得するユーザー) のプレゼンス情報を取得できます。 パブリック IM プロバイダーを使用している場合、マルチパーティ会議を行うのは、厳密にはピアツーピア通信です。 ただし、SIP プロトコルと XMPP プロトコルの両方がサポートされます。
    
- 音声ビデオ (A/V) 会議: 承認された外部ユーザーは、Skype for Business Server の音声ビデオ会議に参加できます。
    
- Web 会議: 承認された外部ユーザーは、Skype for Business 会議に参加できます。 必要に合った場合は、リモート ユーザー、フェデレーション ユーザー、および匿名ユーザーの参加を有効にできます。 パブリック IM ユーザーは会議に参加できません。 また、これらのユーザーがアプリケーションとデスクトップの共有に参加したり、会議の開催者や発表者として機能したりするためのオプションも用意されています。
    
モバイル デバイスのアクセスは、次の場合と同様にエンタープライズ VoIP。 外部ユーザーにアクセス許可を付与する場合は、外部ユーザーを招待して、匿名ユーザーを含め、出席を希望する会議に招待できます。
  
組織に必要なもののように思える場合は、エッジ環境の計画が展開の大きな助けになります。 詳細については、以下のトピックを参照してください。

> [!NOTE]
> XMPP ゲートウェイとプロキシは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 詳細 [については、「XMPP フェデレーションの移行](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 」を参照してください。 
  
## <a name="planning-topics"></a>計画に関するトピック:

計画に関する記事は次のとおりです。
  
- [Skype for Business Server 2015 のエッジ サーバーのシステム要件](system-requirements.md)
    
- [Skype for Business Server 2015 のエッジ サーバーの環境要件](edge-environmental-requirements.md)
    
- [Skype for Business Server 2015 のエッジ サーバーのシナリオ](scenarios.md)
    

