---
title: Skype for Business Server でのエンタープライズ Voip のセキュリティと構成の前提条件
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
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: '概要: Skype for Business Server でのエンタープライズ Voip のセキュリティと構成の前提条件について説明します。'
ms.openlocfilehash: b3fced9ecac9020da9601c2ab6831769b34ae00a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294159"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a>Skype for Business Server でのエンタープライズ Voip のセキュリティと構成の前提条件
 
**概要:** Skype for Business Server でのエンタープライズ Voip のセキュリティと構成の前提条件について説明します。
  
エンタープライズ Voip を展開する前に、インフラストラクチャが以下のセキュリティ、ユーザー構成、およびシナリオ固有のハードウェアの前提条件を満たしていることを確認します。 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>管理者権限と証明書インフラストラクチャ

展開する前に、次を確認します。
  
- エンタープライズボイスを展開する管理者は、RTCUniversalServerAdmins グループのメンバーである必要があります。
    
- 構成タスクを実行する管理者に十分な権限があること。
    
  - **CsVoiceAdministrator:** この管理者の役割では、音声構成タスクの実行、音声アプリケーションの管理、エンド ユーザーへの音声ポリシーの割り当てができます。
    
  - **CsUserAdministrator:** この管理者の役割では、ユーザーのエンタープライズ VoIP を有効にするなど、ユーザーのプロパティを管理できます。 また、この管理者の役割では、ユーザー単位のポリシーの割り当て (アーカイブ ポリシー以外)、ユーザーの移動、共通領域電話やアナログ デバイスの管理を行うこともできます。
    
  - **CsAdministrator:** この管理者の役割では、CsVoiceAdministrator と CsUserAdministrator のすべてのタスクを実行できます。
    
- マイクロソフトまたはサードパーティの CA (証明機関) インフラストラクチャのいずれかを使用して、MKI (Managed key infrastructure) が展開され、構成されていること。
    
    > [!NOTE]
    > Skype for Business Server の証明書の要件の詳細については、「Skype for business [server 2015 の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)」または「 [Skype for business Server 2019 のサーバー要件](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。 
  
## <a name="user-configuration"></a>ユーザー構成

フロントエンドの展開時に、各フロントエンドプールまたは Standard Edition サーバーに仲介サーバーを併置した場合、エンタープライズボイスに必要なユーザー設定は、それらのサーバーロールのファイルのインストール中に自動的に構成されました。
  
現時点でエンタープライズ音声のワークロードを新しく展開している場合は、展開プロセスを開始する前に、エンタープライズ Voip を有効にする予定の各ユーザーのプライマリ電話番号を指定します。 管理者は、この番号が一意であることを確認する責任があります。 実装前に、すべての主要な電話番号が正規化 (適切に書式設定) され、Skype for Business Server コントロールパネルを使用して、各ユーザーの**行 URI**プロパティにコピーされる必要があります。
  
> [!NOTE]
> エンタープライズ VoIP の展開に必要な主要電話番号の例については、「[Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules)」を参照してください。 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>次のステップ: ファイルのインストールや PSTN 接続の構成

エンタープライズ Voip のソフトウェアと環境の前提条件を確認したら、次のいずれかを実行できます。
  
- 「 [Skype For Business Server のトポロジビルダーに仲介サーバーを展開](deploy-a-mediation-server.md)する」の説明に従って、仲介サーバーをインストールします。ただし、仲介サーバーがフロントエンドの一部としてインストールされているため、スタンドアロンの仲介サーバーまたはプールを展開する場合に限ります。併置されている場合は、pool または Standard Edition サーバーの展開プロセス。
    
- または、「 [Skype For Business Server で trunks を構成](configure-trunks.md)する」で説明されているように、エンタープライズ voip ユーザーの通話をルーティングするための設定の構成を開始します。
    

