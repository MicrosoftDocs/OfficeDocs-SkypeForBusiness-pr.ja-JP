---
title: Skype for Business Server でトランクを構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: '概要: Skype for Business Server で仲介サーバーとピア間のトランクを構成エンタープライズ VoIPを構成する方法について学習します。'
ms.openlocfilehash: f2e9f3a5e9fa9d89ef9db63aa82b6a3ce3a86c6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824957"
---
# <a name="configure-trunks-in-skype-for-business-server"></a>Skype for Business Server でトランクを構成する
 
**概要:** Skype for Business Server で仲介サーバーとピア間のトランクを構成するエンタープライズ VoIPを確認します。
  
エンタープライズ VoIP 展開の一環として、仲介サーバーと次の 1 つ以上のピア間のトランクを構成して、組織内の エンタープライズ VoIP クライアントおよびデバイスに公衆交換電話網 (PSTN) 接続を提供できます。
  
- インターネット テレフォニー サービス プロバイダー (ITSP) への SIP トランク接続
    
- PSTN ゲートウェイ
    
- 構内交換機 (PBX)
    
詳細については [、「Skype for Business Server での PSTN 接続の計画」を参照してください](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)。
  
Skype for Business Server の機能は、ゲートウェイと仲介サーバー間の複数の関連付けをサポートします。 これらの関連付けは、仲介サーバー プールと公衆交換電話網 (PSTN) ゲートウェイ、セッション ボーダー コントローラー (SBC)、または IP-PBX の間の論理的な関連付けであるトランクを定義することで行います。 トポロジ ビルダーを使用して、ゲートウェイを仲介サーバー (トランク) に関連付けます。
  
- Skype for Business Server でトランクを割り当てるまたは削除するには、最初にトポロジ ビルダーでトランクを定義する必要があります。 トランクは、仲介サーバーの完全修飾ドメイン名 (FQDN)、仲介サーバーリッスン ポート、ゲートウェイ FQDN、およびゲートウェイ リッスン ポートの関連付けで構成されます。
    
- 複数のトランクを構成するには、同じゲートウェイと仲介サーバーの間に複数の関連付けを作成できます。 これにより、PBX (エンタープライズ VoIP) の相互運用シナリオで特に役立つ、ネットワーク インフラストラクチャの回復性が向上します。 
    
トランクが定義されている場合は、ルートに関連付けられている必要があります。 トランクをルートに関連付ける場合は、トポロジ ビルダーでトランクの簡単な名前を定義します。 この簡単な名前は、トランクをルートに関連付けできる Skype for Business Server コントロール パネルのトランク名として使用されます。 単純なトランク名は、Skype for Business Server 管理シェルからのゲートウェイ名として使用されます。 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

管理者は、仲介サーバーに関連付けられている既定のトランクを選択する必要があります。 トポロジ ビルダーで、関連付けられた仲介サーバーを右クリックし、[プロパティ] をクリック **します**。 仲介サーバーの既定のゲートウェイを指定します。 
  

