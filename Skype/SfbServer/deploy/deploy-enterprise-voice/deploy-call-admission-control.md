---
title: Skype for Business Server での通話受付管理の展開
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
description: 通話受付管理 (CAC) は、混雑したネットワーク上のユーザーの音声/ビデオ品質の低下を防ぐために、使用可能な帯域幅に基づいてリアルタイム セッションを確立できるかどうかを決定するソリューションです。
ms.openlocfilehash: af08afe02b1dc138aa38ded654d567aed6a09247
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836887"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>Skype for Business Server での通話受付管理の展開
 
通話受付管理 (CAC) は、混雑したネットワーク上のユーザーの音声/ビデオ品質の低下を防ぐために、使用可能な帯域幅に基づいてリアルタイム セッションを確立できるかどうかを決定するソリューションです。 詳細については [、「Plan for call admission control in Skype for Business Server 」を参照してください](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。
  
### <a name="to-deploy-call-admission-control"></a>通話受付管理を展開するには

1.  「例: Skype for Business Server での通話受付管理の要件の収集」で説明するように、エンタープライズ ネットワーク トポロジに必要なすべての [情報を収集します](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。
    
2. まだ定義していない場合は、ネットワーク地域とサイトを定義し、サブネットをネットワーク サイトに関連付ける必要があります。 詳細については [、「Skype for Business でのネットワーク地域、サイト、サブネットの展開」を参照してください](deploy-network.md)。
    
3. 「Skype for Business Server での帯域幅ポリシー プロファイルの作成」の説明に示されている帯域幅ポリシー プロファイル [の作成](create-bandwidth-policy-profiles.md)
    
4. 「Skype for Business Server でのネットワーク地域リンクの作成 [」で説明されているネットワーク地域リンクを作成します](create-network-region-links.md)。
    
5. 「Skype for Business Server でのネットワーク地域間ルートの作成」で説明されているネットワーク地域間ルート [を作成します](create-network-interregional-routes.md)。
    
6. 「Skype for Business Server でネットワーク サイト間ポリシーを作成する」の説明に従って、 [ネットワーク サイト間ポリシーを作成します](create-network-intersite-policies.md)。
    
7. 「Skype for Business Server で通話受付管理を有効にする」の説明に示されている方法で、 [通話受付管理を有効にします](enable-call-admission-control.md)。
    
8. 最終的な設定を確認して、すべてが正しく設定されていることを確認します。 詳細については、「 [通話受付管理の展開: Skype for Business Server の最終チェックリスト」を参照してください](final-checklist.md)。
    

