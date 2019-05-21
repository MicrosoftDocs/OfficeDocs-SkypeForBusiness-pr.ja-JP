---
title: Skype for Business Server で Edge Server の展開を計画する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: '概要: Skype for Business Server Edge 環境を計画します。 このトピックでは、エッジの概念を紹介し、より詳細なトピックで体系的に学習できるようにします。'
ms.openlocfilehash: 536ab82ec6845c55a0ee067ad8c1a4f5d9b9e153
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277161"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>Skype for Business Server で Edge Server の展開を計画する
 
**概要:** Skype for Business Server Edge 環境を計画します。 このトピックでは、エッジの概念を紹介し、より詳細なトピックで体系的に学習できるようにします。
  
社内で動作する Skype for Business Server 環境がある場合、次の手順では、Edge サーバーまたはエッジプールを環境に導入することをお勧めします。 この役割は、Skype for Business Server によって提供されるサービスを内部ネットワークの外部ユーザーが使用できるようにする場合に非常に重要です。 次の種類のユーザーが含まれる可能性があります。
  
- リモート ユーザー: 一時的または継続的にオフサイトで作業している従業員。
    
- フェデレーションされたユーザー: パートナー組織の従業員。
    
- モバイル ユーザー。
    
- 会議やプレゼンテーションに招待する必要がある潜在的な顧客やパートナー、および場合によっては匿名ユーザー。
    
外部ユーザーアクセス (エッジサーバーが提供する機能) により、すべての操作が可能になります。 組織内のユーザーは、Skype for Business Server の展開によってホストされている次のサービスを利用することができます。
  
- 通信の IM とプレゼンス: 承認された外部ユーザーは、IM 会話と会議に参加できます。 他のユーザーのプレゼンス情報を取得することができます (自分のプレゼンス情報も取得します)。 パブリック IM プロバイダーを使用している場合は、ピアツーピア通信であるため、マルチパーティ会議を実行することはできません。 ただし、SIP と XMPP の両方のプロトコルがサポートされています。
    
- 音声/ビデオ (A/V) 会議: 承認された外部ユーザーは、Skype for Business Server の音声とビデオ会議に参加できます。
    
- Web 会議: 承認された外部ユーザーは、Skype for Business 会議に参加することができます。 必要に応じて、リモートユーザー、フェデレーションユーザー、匿名ユーザーへの参加を有効にすることもできます。 パブリック IM ユーザーは、会議に参加できません。 これらのユーザーのアプリケーションおよびデスクトップ共有への参加や、場合によっては会議の開催者または発表者の役割を可能にするオプションもあります。
    
エンタープライズ Voip として、モバイルデバイスのアクセスがサポートされています。 外部ユーザーにアクセス許可を付与する必要があれば、場合によっては匿名ユーザーを含め、外部ユーザーの参加が必要な会議に招待することができます。
  
上記の機能が組織で必要であると考えられる場合は、エッジ環境を計画すると、その機能を展開するのに大いに役立ちます。その他の資料としては、以下のトピックがあります。

> [!NOTE]
> XMPP ゲートウェイとプロキシは、Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 詳細については、「 [XMPP フェデレーションを移行](../../../SfBServer2019/migration/migrating-xmpp-federation.md)する」を参照してください。 
  
## <a name="planning-topics"></a>計画に関するトピック:

計画に関する記事:
  
- [Skype for Business Server 2015 のエッジ サーバーのシステム要件](system-requirements.md)
    
- [Skype for Business Server 2015 のエッジ サーバーの環境要件](edge-environmental-requirements.md)
    
- [Skype for Business Server 2015 のエッジ サーバーのシナリオ](scenarios.md)
    

