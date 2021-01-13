---
title: Skype for Business Server での エンタープライズ VoIPのセキュリティと構成の前提条件
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
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: '概要: Skype for Business Server のセキュリティと構成エンタープライズ VoIPについて説明します。'
ms.openlocfilehash: 77efbf231f83c6d3c31254c9ab742de7e2b226e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830847"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a>Skype for Business Server での エンタープライズ VoIPのセキュリティと構成の前提条件
 
**概要:** Skype for Business Server のセキュリティと構成の前提条件エンタープライズ VoIPについて説明します。
  
アプリケーションを展開するエンタープライズ VoIP、インフラストラクチャが次のセキュリティ、ユーザー構成、およびシナリオ固有のハードウェア前提条件を満たしていることを確認します。 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>管理者権限と証明書インフラストラクチャ

展開する前に、次の確認を行います。
  
- エンタープライズ VoIP を展開する管理者が RTCUniversalServerAdmins グループのメンバーであること。
    
- 構成タスクを実行する管理者に十分な権限があること。
    
  - **CsVoiceAdministrator:** この管理者の役割では、音声構成タスクの実行、音声アプリケーションの管理、エンド ユーザーへの音声ポリシーの割り当てができます。
    
  - **CsUserAdministrator:** この管理者の役割では、ユーザーのエンタープライズ VoIP を有効にするなど、ユーザーのプロパティを管理できます。 また、この管理者の役割では、ユーザー単位のポリシーの割り当て (アーカイブ ポリシー以外)、ユーザーの移動、共通領域電話やアナログ デバイスの管理を行うこともできます。
    
  - **CsAdministrator:** この管理者の役割では、CsVoiceAdministrator と CsUserAdministrator のすべてのタスクを実行できます。
    
- マイクロソフトまたはサードパーティの CA (証明機関) インフラストラクチャのいずれかを使用して、MKI (Managed key infrastructure) が展開され、構成されていること。
    
    > [!NOTE]
    > Skype for Business Server の証明書要件の詳細については [、「Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。 
  
## <a name="user-configuration"></a>ユーザー構成

フロントエンドの展開中に仲介サーバーを各フロントエンド プールまたは Standard Edition サーバーと一緒に配置した場合、これらのサーバーの役割のファイルのインストール中に、エンタープライズ VoIP に必要なユーザー設定が自動的に構成されました。
  
この時点でエンタープライズ VoIP のワークロードを新たに展開する場合、展開プロセスを開始する前に、エンタープライズ VoIP を有効にする各ユーザーの主要電話番号を指定します。 管理者は、この番号が一意であることを確認する責任があります。 実装する前に、すべての主要電話番号を正規化 (正しい形式) にし、Skype for Business Server コントロール パネルを使用して各ユーザーの **回線 URI** プロパティにコピーする必要があります。
  
> [!NOTE]
> 展開に必要な主要電話番号の例については、「エンタープライズ VoIP正規化ルール」を [参照してください](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules)。 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>次の手順: ファイルをインストールするか、PSTN 接続を構成する

ソフトウェアと環境の前提条件を確認したエンタープライズ VoIP、次のいずれかを実行できます。
  
- [「Skype for Business Server](deploy-a-mediation-server.md)のトポロジ ビルダーでの仲介サーバーの展開」の説明に従って、仲介サーバーをインストールします。ただし、仲介サーバーは、フロントエンド プールまたは Standard Edition サーバーの展開プロセスの一部としてインストールされる場合に、スタンドアロンの仲介サーバーまたはプールを展開する場合にのみインストールします。
    
- または、「Skype for Business Server でトランクを構成する」の説明に従って、エンタープライズ VoIP ユーザーの通話をルーティングするように設定 [の構成を開始します](configure-trunks.md)。
    

