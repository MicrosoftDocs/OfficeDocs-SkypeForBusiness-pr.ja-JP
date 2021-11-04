---
title: セキュリティと構成の前提条件は、エンタープライズ VoIPのSkype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: '概要: 詳細については、「セキュリティと構成の前提条件」を参照エンタープライズ VoIPをSkype for Business Server。'
ms.openlocfilehash: 48cb415208008441f306dd0384c494149f65c4e4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778917"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a>セキュリティと構成の前提条件は、エンタープライズ VoIPのSkype for Business Server
 
**概要:** 詳細については、「セキュリティと構成の前提条件」のエンタープライズ VoIPをSkype for Business Server。
  
アプリケーションを展開エンタープライズ VoIP、インフラストラクチャが次のセキュリティ、ユーザー構成、シナリオ固有のハードウェア前提条件を満たしていることを確認してください。 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>管理者権限と証明書インフラストラクチャ

展開する前に、次の情報を確認してください。
  
- エンタープライズ VoIP を展開する管理者が RTCUniversalServerAdmins グループのメンバーであること。
    
- 構成タスクを実行する管理者に十分な権限があること。
    
  - **CsVoiceAdministrator:** この管理者の役割では、音声構成タスクの実行、音声アプリケーションの管理、エンド ユーザーへの音声ポリシーの割り当てができます。
    
  - **CsUserAdministrator:** この管理者の役割では、ユーザーのエンタープライズ VoIP を有効にするなど、ユーザーのプロパティを管理できます。 また、この管理者の役割では、ユーザー単位のポリシーの割り当て (アーカイブ ポリシー以外)、ユーザーの移動、共通領域電話やアナログ デバイスの管理を行うこともできます。
    
  - **CsAdministrator:** この管理者の役割では、CsVoiceAdministrator と CsUserAdministrator のすべてのタスクを実行できます。
    
- マイクロソフトまたはサードパーティの CA (証明機関) インフラストラクチャのいずれかを使用して、MKI (Managed key infrastructure) が展開され、構成されていること。
    
    > [!NOTE]
    > Skype for Business Server の証明書要件の詳細については[、「Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)の環境要件」または「Skype for Business Server [2019](../../../SfBServer2019/plan/system-requirements.md)のサーバー要件」を参照してください。 
  
## <a name="user-configuration"></a>ユーザー構成

フロントエンドの展開中に仲介サーバーを各フロントエンド プールまたは Standard Edition サーバーと一緒に配置した場合、エンタープライズ VoIP に必要なユーザー設定は、それらのサーバーの役割のファイルのインストール中に自動的に構成されます。
  
この時点でエンタープライズ VoIP のワークロードを新たに展開する場合、展開プロセスを開始する前に、エンタープライズ VoIP を有効にする各ユーザーの主要電話番号を指定します。 管理者は、この番号が一意であることを確認する責任があります。 実装する前に、すべてのプライマリ電話番号を正規化 (正しく書式設定) し、コントロール パネルを使用して各ユーザーの **Line URI** プロパティSkype for Business Serverする必要があります。
  
> [!NOTE]
> 展開に必要なプライマリ電話番号の例については、「エンタープライズ VoIP正規化ルール[」を参照してください](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules)。 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>次の手順: ファイルのインストールまたは PSTN 接続の構成

ソフトウェアと環境の前提条件を確認エンタープライズ VoIP、次のいずれかを実行できます。
  
- [「Skype for Business Server](deploy-a-mediation-server.md)のトポロジ ビルダーでの仲介サーバーの展開」の説明に従って仲介サーバーをインストールしますが、仲介サーバーは、接続時にフロントエンド プールまたは Standard Edition サーバー展開プロセスの一部としてインストールされますので、スタンドアロンの仲介サーバーまたはプールを展開する場合にのみインストールします。
    
- または、「デバイスでトランクを構成する」の説明に従って、エンタープライズ VoIP ユーザーの呼び出しをルーティングするための設定[の構成をSkype for Business Server。](configure-trunks.md)
    

