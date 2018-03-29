---
title: Skype for Business Server 2015 でのトランクの構成
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: '概要: は、Skype のビジネス サーバー 2015 の仲介サーバーとエンタープライズ VoIP のピア間のトランクを構成する方法について説明します。'
ms.openlocfilehash: a2630d3e37e6ab15a0e88593549e9365ac69a3e7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-trunks-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 でのトランクの構成
 
**の概要:**ビジネス サーバー 2015 の Skype での仲介サーバーとエンタープライズ VoIP のピア間のトランクを構成する方法について説明します。
  
エンタープライズ VoIP 展開の一部として、仲介サーバーと 1 つ以上のエンタープライズ VoIP クライアントと、組織内のデバイスの公衆交換電話網 (PSTN) 接続を提供する次のピア間のトランクを構成できます。
  
- インターネット テレフォニー サービス プロバイダー (ITSP) への SIP トランク接続
    
- PSTN ゲートウェイ
    
- 構内交換機 (PBX)
    
詳細については、 [Skype のビジネス サーバー 2015 の PSTN への接続の計画](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)を参照してください。
  
ビジネス サーバーの機能のための Skype では、ゲートウェイと仲介サーバーの間で複数のアソシエーションをサポートします。 これらの関連付けは、仲介サーバー プールと公衆交換電話網 (PSTN) ゲートウェイ、セッション ボーダー コント ローラー (SBC)、または IP PBX との間の論理的な関連付けには、トランクを定義することによって行われます。 ゲートウェイを仲介サーバー (つまり、トランクなど) に関連付けるには、トポロジ ビルダーを使用します。
  
- 割り当てまたはトランクを Skype のビジネス サーバーの削除、最初にトポロジ ビルダーでトランクを定義する必要があります。 トランクは、次の関連で構成されています: ドメイン名 (FQDN)、仲介サーバーのリッスン ポート、ゲートウェイの FQDN、およびゲートウェイ リッスン ポートを仲介サーバーの完全修飾します。
    
- 複数のトランクを構成するには、同じゲートウェイと仲介サーバーとの間の複数の関連付けを作成できます。 これは、構内交換 (機 PBX) の interoperational のシナリオで特に便利ですが、エンタープライズ VoIP インフラストラクチャに追加の復元機能を提供します。 
    
トランクを定義するときは、工順に関連付けられている場合があります。 ルートにトランクを関連付けるには、トポロジ ビルダーでは、トランクの簡易名を定義します。 この単純な名前は、ビジネス サーバーのコントロール パネル]、トランクできるルートに関連付けられているに、Skype でトランクの名前として使用されます。 トランクの単純な名前は、サーバー管理シェルのビジネスに、Skype からゲートウェイの名前として使用されます。 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

管理者は、仲介サーバーに関連付けられている既定のトランクを選択してください。 トポロジ ビルダーでは、関連付けられている仲介サーバーを右クリックし、し、[**プロパティ**] をクリックします。 仲介サーバーのデフォルト ゲートウェイを指定します。 
  

