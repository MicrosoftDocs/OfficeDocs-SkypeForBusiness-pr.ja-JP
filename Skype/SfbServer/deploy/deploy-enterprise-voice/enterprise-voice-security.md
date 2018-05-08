---
title: Skype for Business Server 2015 のエンタープライズ VoIP のセキュリティおよび構成の前提条件
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: '概要: は、ビジネス サーバー 2015 の Skype でエンタープライズ VoIP のセキュリティおよび構成の前提条件について説明します。'
ms.openlocfilehash: 2ece3aaa99c1e81afd9241e8d435ac0ab3328893
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 のエンタープライズ VoIP のセキュリティおよび構成の前提条件
 
**の概要:** ビジネス サーバー 2015 の Skype でエンタープライズ VoIP のセキュリティおよび構成の前提条件について説明します。
  
エンタープライズ VoIP を展開するには、前に、インフラストラクチャが次のセキュリティ、ユーザー構成、およびシナリオ固有のハードウェアの前提条件を満たしていることを確認します。 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>管理者権限と証明書インフラストラクチャ

展開する前に、次を確認します。
  
- RTCUniversalServerAdmins グループのメンバーがエンタープライズ VoIP を展開する管理者にあります。
    
- 構成タスクを実行する管理者に十分な権限があること。
    
  - **CsVoiceAdministrator:** この管理者の役割では、音声構成タスクの実行、音声アプリケーションの管理、エンド ユーザーへの音声ポリシーの割り当てができます。
    
  - **CsUserAdministrator:** この管理者の役割では、ユーザーのエンタープライズ VoIP を有効にするなど、ユーザーのプロパティを管理できます。 また、この管理者の役割では、ユーザー単位のポリシーの割り当て (アーカイブ ポリシー以外)、ユーザーの移動、共通領域電話やアナログ デバイスの管理を行うこともできます。
    
  - **CsAdministrator:** この管理者の役割では、CsVoiceAdministrator と CsUserAdministrator のすべてのタスクを実行できます。
    
- マイクロソフトまたはサードパーティの CA (証明機関) インフラストラクチャのいずれかを使用して、MKI (Managed key infrastructure) が展開され、構成されていること。
    
    > [!NOTE]
    > Skype のビジネス サーバー用の証明書の要件に関する詳細については、 [Skype のビジネス サーバー 2015 の環境の要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)を参照してください。 
  
## <a name="user-configuration"></a>ユーザー構成

フロント エンドの展開時に各フロント エンド プールに仲介サーバーまたは Standard Edition サーバーを併設されている場合、それらのサーバーの役割用のファイルのインストール中にユーザー設定のエンタープライズ VoIP に必要なが自動的に構成されました。
  
展開プロセスを開始する前に、この時点でエンタープライズ VoIP のワークロードを新しく導入する場合は、エンタープライズ VoIP を有効にする各ユーザーのプライマリ電話番号を指定します。 管理者は、この番号が一意であることを確認する責任があります。 実装では、前にすべてのプライマリ ・は電話番号を正規化する必要があります (正しく書式設定された) とビジネス サーバーのコントロール パネルの Skype を使用して各ユーザーの**回線 URI**のプロパティにコピーします。
  
> [!NOTE]
> エンタープライズ VoIP の展開に必要な主要電話番号の例については、「[Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules)」を参照してください。 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>次のステップ: ファイルのインストールや PSTN 接続の構成

ソフトウェアとエンタープライズ VoIP に必要な環境を確認した後ことができますか。
  
- [ビジネス サーバー 2015 の Skype でトポロジ ビルダーでは、仲介サーバーの展開](deploy-a-mediation-server.md)] で説明されているようですが、前面の一部として仲介サーバーがインストールされているために、スタンドアロンの仲介サーバーまたはプールを展開する場合に、仲介サーバーをインストールします。プールまたは Standard Edition サーバーの展開プロセスは 1 か所を終了します。
    
- または、[ビジネス サーバー 2015 の Skype でトランクを構成する](configure-trunks.md)で説明したようにエンタープライズ VoIP ユーザーは、ルートの呼び出しに設定の構成を開始します。
    

