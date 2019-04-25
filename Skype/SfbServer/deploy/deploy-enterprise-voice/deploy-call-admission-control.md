---
title: ビジネス サーバーの Skype で通話受付制御を展開します。
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: 呼び出しの受付制御 (CAC) は、リアルタイム セッションを確立できるかどうかを決定するためのソリューションは、混雑したネットワーク上のユーザーのオーディオ/ビデオ品質の低下を防止するために利用可能な帯域幅に基づいています。
ms.openlocfilehash: 52fcedaab781e9ed76222afb32b56840a3b07c1c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223142"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>ビジネス サーバーの Skype で通話受付制御を展開します。
 
呼び出しの受付制御 (CAC) は、リアルタイム セッションを確立できるかどうかを決定するためのソリューションは、混雑したネットワーク上のユーザーのオーディオ/ビデオ品質の低下を防止するために利用可能な帯域幅に基づいています。 詳細については、[ビジネス サーバーの Skype で通話受付制御の計画](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)を参照してください。
  
### <a name="to-deploy-call-admission-control"></a>通話管理受付サービスを展開するには

1.  説明したように、エンタープライズ ネットワーク トポロジに必要な情報のすべてを収集[の使用例: ビジネス サーバー Skype の呼受付制御の要件の収集](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。
    
2. まだ行っていない場合は、ネットワーク地域とサイトを定義して、サブネットをネットワーク サイトに関連付ける必要があります。 詳細については、[ネットワークの領域を展開、サイトとサブネットでビジネス用の Skype](deploy-network.md)を参照してください。
    
3. 帯域幅[ビジネス サーバーの Skype で帯域幅ポリシー プロファイルを作成する](create-bandwidth-policy-profiles.md)を参考に、ポリシー プロファイルの作成します。
    
4. [Skype ビジネス サーバー用のネットワーク地域リンクの作成](create-network-region-links.md)の詳細と、ネットワーク地域リンクを作成します。
    
5. [Skype ビジネス サーバー用のネットワーク interregional ルートの作成](create-network-interregional-routes.md)の参考に、ネットワーク間の地域ルートを作成します。
    
6. [Skype ビジネス サーバー用のネットワーク サイト間ポリシーの作成](create-network-intersite-policies.md)の参考に、ネットワーク サイト間ポリシーを作成します。
    
7. [ビジネス サーバーの Skype で通話受付制御を有効にする](enable-call-admission-control.md)を参考に、呼び出しの受付制御を有効にします。
    
8. いくつかの最終設定をチェックして、すべてが正しく設定されていることを確認します。 詳細についてを参照してください[電話受付制御の展開: ビジネス サーバーの Skype の最終チェックリスト](final-checklist.md)。
    

