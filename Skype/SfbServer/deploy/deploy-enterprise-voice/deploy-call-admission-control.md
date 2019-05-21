---
title: Skype for Business Server で通話受付制御を展開する
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
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: 通話受付制御 (CAC) は、使用可能な帯域幅に基づいてリアルタイムのセッションを確立して、混雑したネットワークのユーザーに対して低品質のオーディオ/ビデオ品質を防ぐことができるかどうかを決定するソリューションです。
ms.openlocfilehash: 7f7f8dee4e25061533564ce517f797281bef042e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280440"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>Skype for Business Server で通話受付制御を展開する
 
通話受付制御 (CAC) は、使用可能な帯域幅に基づいてリアルタイムのセッションを確立して、混雑したネットワークのユーザーに対して低品質のオーディオ/ビデオ品質を防ぐことができるかどうかを決定するソリューションです。 詳細については、「 [Skype For Business Server での通話受付制御の計画](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)」を参照してください。
  
### <a name="to-deploy-call-admission-control"></a>通話管理受付サービスを展開するには

1.  「[例: Skype For Business Server での通話受付制御の要件の収集](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)」の説明に従って、エンタープライズネットワークトポロジに必要なすべての情報を収集します。
    
2. まだ行っていない場合は、ネットワーク地域とサイトを定義して、サブネットをネットワーク サイトに関連付ける必要があります。 詳細については、「 [Skype For business でネットワークのリージョン、サイト、サブネットを展開](deploy-network.md)する」を参照してください。
    
3. 「 [Skype For Business Server での帯域幅ポリシープロファイルの作成](create-bandwidth-policy-profiles.md)」で詳しく説明するように、帯域幅ポリシープロファイルを作成します。
    
4. 「 [Skype For Business Server でのネットワーク領域リンクの作成](create-network-region-links.md)」で詳しく説明するように、ネットワーク領域のリンクを作成します。
    
5. 「 [Skype For Business Server でネットワーク間の地域ルートを作成する](create-network-interregional-routes.md)」で詳しく説明するように、ネットワーク間のネットワーク間ルートを作成します。
    
6. 「 [Skype For Business Server でのネットワークのサイト間ポリシーの作成](create-network-intersite-policies.md)」で詳しく説明するように、ネットワークのサイト間ポリシーを作成します。
    
7. 「 [Skype For Business Server で通話受付制御を有効にする](enable-call-admission-control.md)」で詳しく説明するように、通話受付制御を有効にします。
    
8. いくつかの最終設定をチェックして、すべてが正しく設定されていることを確認します。 詳細については、「[通話受付制御の展開: Skype For Business Server の最終チェックリスト](final-checklist.md)」を参照してください。
    

