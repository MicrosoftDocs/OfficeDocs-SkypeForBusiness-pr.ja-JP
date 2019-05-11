---
title: ビジネス サーバー用の Skype でトランクを構成します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: '概要: は、Skype のビジネス サーバーの仲介サーバーとエンタープライズ VoIP のピア間のトランクを構成する方法について説明します。'
ms.openlocfilehash: 503d9da7b0a2680cd784c3d3c495bed7bfd50dfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893029"
---
# <a name="configure-trunks-in-skype-for-business-server"></a>ビジネス サーバー用の Skype でトランクを構成します。
 
**の概要:** Skype のビジネス サーバーの仲介サーバーとエンタープライズ VoIP のピア間のトランクを構成する方法について説明します。
  
エンタープライズ VoIP 展開の一部として、仲介サーバーと 1 つ以上のエンタープライズ VoIP クライアントと、組織内のデバイスの公衆交換電話網 (PSTN) 接続を提供する次のピア間のトランクを構成できます。
  
- インターネット テレフォニー サービス プロバイダー (ITSP) への SIP トランク接続
    
- PSTN ゲートウェイ
    
- 構内交換機 (PBX)
    
詳細については、 [Skype のビジネス サーバーの PSTN への接続の計画](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)を参照してください。
  
ビジネス サーバーの機能のための Skype では、ゲートウェイと仲介サーバーの間で複数のアソシエーションをサポートします。 これらの関連付けは、仲介サーバー プールと公衆交換電話網 (PSTN) ゲートウェイ、セッション ボーダー コント ローラー (SBC)、または IP PBX との間の論理的な関連付けには、トランクを定義することによって行われます。 ゲートウェイを仲介サーバー (つまり、トランクなど) に関連付けるには、トポロジ ビルダーを使用します。
  
- 割り当てまたはトランクを Skype のビジネス サーバーの削除、最初にトポロジ ビルダーでトランクを定義する必要があります。 トランクは、次の関連で構成されています: ドメイン名 (FQDN)、仲介サーバーのリッスン ポート、ゲートウェイの FQDN、およびゲートウェイ リッスン ポートを仲介サーバーの完全修飾します。
    
- 複数のトランクを構成するには、同じゲートウェイと仲介サーバーとの間の複数の関連付けを作成できます。 これは、構内交換 (機 PBX) の interoperational のシナリオで特に便利ですが、エンタープライズ VoIP インフラストラクチャに追加の復元機能を提供します。 
    
トランクを定義するときは、工順に関連付けられている場合があります。 ルートにトランクを関連付けるには、トポロジ ビルダーでは、トランクの簡易名を定義します。 この単純な名前は、ビジネス サーバーのコントロール パネル]、トランクできるルートに関連付けられているに、Skype でトランクの名前として使用されます。 トランクの単純な名前は、サーバー管理シェルのビジネスに、Skype からゲートウェイの名前として使用されます。 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

管理者は、仲介サーバーに関連付けられている既定のトランクを選択してください。 トポロジ ビルダーでは、関連付けられている仲介サーバーを右クリックし、し、[**プロパティ**] をクリックします。 仲介サーバーのデフォルト ゲートウェイを指定します。 
  

