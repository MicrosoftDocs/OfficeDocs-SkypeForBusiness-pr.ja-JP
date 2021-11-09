---
title: サーバーでトランクを構成Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: '概要: 仲介サーバーとピア間のトランクを構成する方法について、エンタープライズ VoIPをSkype for Business Server。'
ms.openlocfilehash: f2d88d71476e428230aac0298cb0445844757e1c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839109"
---
# <a name="configure-trunks-in-skype-for-business-server"></a>サーバーでトランクを構成Skype for Business Server
 
**概要:** 仲介サーバーとピア間のトランクを構成する方法について、エンタープライズ VoIPをSkype for Business Server。
  
エンタープライズ VoIP 展開の一環として、仲介サーバーと 1 つ以上の次のピア間のトランクを構成して、組織内の エンタープライズ VoIP クライアントおよびデバイスに公衆交換電話網 (PSTN) 接続を提供できます。
  
- インターネット テレフォニー サービス プロバイダー (ITSP) への SIP トランク接続
    
- PSTN ゲートウェイ
    
- 構内交換機 (PBX)
    
詳細については、「Plan [for PSTN connectivity in Skype for Business Server」 を参照してください](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)。
  
Skype for Business Server機能は、ゲートウェイと仲介サーバー間の複数の関連付けをサポートします。 これらの関連付けは、仲介サーバー プールと公衆交換電話網 (PSTN) ゲートウェイ、セッション ボーダー コントローラー (SBC)、または IP-PBX の間の論理的な関連付けであるトランクを定義することで行います。 トポロジ ビルダーを使用して、ゲートウェイを仲介サーバー (トランク) に関連付けます。
  
- トポロジ ビルダーでトランクを割り当Skype for Business Server削除するには、まずトポロジ ビルダーでトランクを定義する必要があります。 トランクは、仲介サーバーの完全修飾ドメイン名 (FQDN)、仲介サーバーリスニング ポート、ゲートウェイ FQDN、ゲートウェイ リスニング ポートの関連付けで構成されます。
    
- 複数のトランクを構成するには、同じゲートウェイと仲介サーバーの間に複数の関連付けを作成できます。 これにより、プライベート ブランチ 交換 (PBX) エンタープライズ VoIPのシナリオで特に役立つ、インフラストラクチャに対する追加の復元性が提供されます。 
    
トランクが定義されている場合は、ルートに関連付けられている必要があります。 トランクをルートに関連付けるには、トポロジ ビルダーでトランクの単純な名前を定義します。 この単純な名前は、トランクをルートに関連付Skype for Business Serverコントロール パネルのトランク名として使用されます。 単純なトランク名は、管理シェルのゲートウェイ名Skype for Business Serverされます。 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

管理者は、仲介サーバーに関連付けられている既定のトランクを選択する必要があります。 トポロジ ビルダーで、関連付けられた仲介サーバーを右クリックし、[プロパティ] を **クリックします**。 仲介サーバーの既定のゲートウェイを指定します。 
  

