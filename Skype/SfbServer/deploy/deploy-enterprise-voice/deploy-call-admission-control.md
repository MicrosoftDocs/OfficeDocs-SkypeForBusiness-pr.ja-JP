---
title: Skype for Business Server 2015 での通話受付管理の展開
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: 呼び出しの受付制御 (CAC) は、リアルタイム セッションを確立できるかどうかを決定するためのソリューションは、混雑したネットワーク上のユーザーのオーディオ/ビデオ品質の低下を防止するために利用可能な帯域幅に基づいています。 詳細についてを参照してください計画 Skype の呼受付制御のビジネス サーバー 2015 のです。
ms.openlocfilehash: 471bc7abe8a79f2ef4b4cc322450dbc7c639129f
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-call-admission-control-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での通話受付管理の展開
 
呼び出しの受付制御 (CAC) は、リアルタイム セッションを確立できるかどうかを決定するためのソリューションは、混雑したネットワーク上のユーザーのオーディオ/ビデオ品質の低下を防止するために利用可能な帯域幅に基づいています。 詳細については、[ビジネス サーバー 2015 の Skype の呼受付制御の計画](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)を参照してください。
  
### <a name="to-deploy-call-admission-control"></a>通話管理受付サービスを展開するには

1.  説明したように、エンタープライズ ネットワーク トポロジに必要な情報のすべてを収集[の使用例: ビジネス サーバー 2015 の Skype の呼受付制御の要件を収集する](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)です。
    
2. まだ行っていない場合は、ネットワーク地域とサイトを定義して、サブネットをネットワーク サイトに関連付ける必要があります。 詳細については、[ネットワークの領域を展開、サイト、およびビジネス 2015年の Skype のサブネットを](deploy-network.md)参照してください。
    
3. 帯域幅[ビジネス サーバー 2015 の Skype で帯域幅ポリシー プロファイルを作成する](create-bandwidth-policy-profiles.md)を参考に、ポリシー プロファイルの作成します。
    
4. [ビジネス サーバー 2015 の Skype のネットワーク地域リンクの作成](create-network-region-links.md)の詳細と、ネットワーク地域リンクを作成します。
    
5. [ビジネス サーバー 2015 の Skype のネットワーク interregional ルートの作成](create-network-interregional-routes.md)の参考に、ネットワーク間の地域ルートを作成します。
    
6. [ビジネス サーバー 2015 の Skype のネットワーク サイト間ポリシーの作成](create-network-intersite-policies.md)の参考に、ネットワーク サイト間ポリシーを作成します。
    
7. [ビジネス サーバー 2015 の Skype で通話受付制御を有効にする](enable-call-admission-control.md)を参考に、呼び出しの受付制御を有効にします。
    
8. いくつかの最終設定をチェックして、すべてが正しく設定されていることを確認します。 詳細についてを参照してください[電話受付制御の展開: ビジネス サーバー 2015 の Skype の最終チェックリスト](final-checklist.md)。
    

