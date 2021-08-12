---
title: 通話受付管理をユーザーに展開Skype for Business Server
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
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: 通話受付管理 (CAC) は、混雑したネットワーク上のユーザーのオーディオ/ビデオ品質の低下を防ぐために、利用可能な帯域幅に基づいてリアルタイム セッションを確立できるかどうかを決定するソリューションです。
ms.openlocfilehash: eaba53e7c4c908024b3427970c103a3bcc8885036ca3e1dbc657e6c0d78e5d8e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307818"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>通話受付管理をユーザーに展開Skype for Business Server
 
通話受付管理 (CAC) は、混雑したネットワーク上のユーザーのオーディオ/ビデオ品質の低下を防ぐために、利用可能な帯域幅に基づいてリアルタイム セッションを確立できるかどうかを決定するソリューションです。 詳細については、「プラン for call admission control in Skype for Business Server 」[を参照してください](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。
  
### <a name="to-deploy-call-admission-control"></a>通話受付管理を展開するには

1.  「例: 通話受付管理の要件を収集する」の説明に従って、エンタープライズ ネットワーク トポロジに必要なすべての情報を[Skype for Business Server。](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)
    
2. まだ定義していない場合は、ネットワーク領域とサイトを定義し、サブネットをネットワーク サイトに関連付ける必要があります。 詳細については、「ネットワーク領域[、サイト、](deploy-network.md)サブネットを展開する」を参照Skype for Business。
    
3. 帯域幅ポリシー プロファイルの作成(「帯域幅ポリシー プロファイルを作成する」の詳細[に](create-bandwidth-policy-profiles.md)Skype for Business Server
    
4. ネットワーク地域リンクを作成する(「ネットワーク地域リンクを作成する」の[Skype for Business Server。](create-network-region-links.md)
    
5. ネットワーク地域間ルートを作成します。詳細については、「ネットワーク地域間ルートを作成する」を[参照](create-network-interregional-routes.md)Skype for Business Server。
    
6. 「ネットワークサイト間ポリシーを作成する」の詳細に従って、ネットワークサイト間ポリシー[を作成](create-network-intersite-policies.md)Skype for Business Server。
    
7. 「通話受付管理を有効にする」の詳細に示されている通り、通話受付[管理を有効Skype for Business Server。](enable-call-admission-control.md)
    
8. 最終的な設定を確認して、すべてが正しく設定されていることを確認します。 詳細については、「通話受付管理の展開: 通話受付[の最終チェックリスト」を参照](final-checklist.md)Skype for Business Server。
    

