---
title: Skype for Business Server で trunks を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: '概要: Skype for Business Server で仲介サーバーとエンタープライズボイスのピアの間でトランクを構成する方法について説明します。'
ms.openlocfilehash: 5e5fc044e5217ef4661e716ba02ba286c7a631f8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289098"
---
# <a name="configure-trunks-in-skype-for-business-server"></a>Skype for Business Server で trunks を構成する
 
**概要:** Skype for Business Server で仲介サーバーとエンタープライズボイスのピアの間でトランクを構成する方法について説明します。
  
エンタープライズ Voip の展開の一部として、仲介サーバーと次のピアの1つ以上にトランクを構成して、組織内のエンタープライズボイスクライアントとデバイスの公衆交換電話網 (PSTN) 接続を提供できます。
  
- インターネット テレフォニー サービス プロバイダー (ITSP) への SIP トランク接続
    
- PSTN ゲートウェイ
    
- 構内交換機 (PBX)
    
詳細については、「 [Skype For Business Server での PSTN 接続の計画](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)」を参照してください。
  
Skype for Business Server 機能は、ゲートウェイと仲介サーバー間の複数の関連付けをサポートしています。 これらの関連付けは、仲介サーバープールと公衆交換電話網 (PSTN) ゲートウェイ、セッション境界コントローラー (SBC)、または ip-pbx との間の論理的な関連付けであるトランクを定義することによって行われます。 トポロジビルダーを使用して、ゲートウェイを仲介サーバーに関連付けます (つまり、trunks)。
  
- Skype for Business Server でトランクを割り当てまたは削除するには、まず、トポロジビルダーで樹幹を定義する必要があります。 トランクは、仲介サーバーの完全修飾ドメイン名 (FQDN)、仲介サーバーのリッスンポート、ゲートウェイの FQDN、ゲートウェイのリスニングポートで構成されます。
    
- 複数の trunks を構成するために、同じゲートウェイと仲介サーバー間に複数の関連付けを作成することができます。 これにより、エンタープライズ Voip インフラストラクチャのさらなる弾力性が提供されます。これは、プライベート支店交換 (PBX) 間の運用シナリオで特に便利です。 
    
トランクが定義されている場合は、ルートに関連付ける必要があります。 トランクをルートに関連付けるには、トポロジビルダーでトランクの単純な名前を定義します。 この簡易名は、Skype for Business Server コントロールパネルでトランク名として使用されます。ここでは、trunks をルートに関連付けることができます。 簡単なトランク名は、Skype for Business Server 管理シェルのゲートウェイ名として使用されます。 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

管理者は、仲介サーバーに関連付けられている既定のトランクを選択する必要があります。 トポロジビルダーで、関連する仲介サーバーを右クリックし、[**プロパティ**] をクリックします。 仲介サーバーの既定のゲートウェイを指定します。 
  

