---
title: Skype for Business Server 2015 での E9-1-1 の展開
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: ビジネス サーバーのエンタープライズ VoIP は、Skype で ~ 9-1-1 を展開します。 前提条件と展開プロセスのチェックリストも掲載しています。
ms.openlocfilehash: 0994bb3b1c0cd5b4c4ce1dcc1c0a46b4e97b76b1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-emergency-services-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での E9-1-1 の展開
 
ビジネス サーバーのエンタープライズ VoIP は、Skype で ~ 9-1-1 を展開します。 前提条件と展開プロセスのチェックリストも掲載しています。
  
拡張 9-1-1 (~ 9-1-1) は、発呼側の電話番号、都市、または所在地の住所に関連付ける緊急通知機能です。 緊急応答機関 (PSAP) はこの情報を使用して、支援を必要とする発信者に緊急サービスをすぐに派遣できます。
  
~ 9-1-1 をサポートするために Skype ビジネス サーバーをクライアントを使用して場所を正しく関連付けるに最も近い PSAP 緊急通話をルーティングするのにはこの情報を使用するかどうかを確認することが可能にする必要があります。
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>E9-1-1 の展開前提条件

~ 9-1-1 を展開する前に、内部のサーバーを中央管理ストア、フロント エンド プールまたは Standard Edition サーバーを含むため、Skype を展開が既に必要があります。 1 つまたは複数仲介サーバー、スタンドアロンのいずれかを配置する必要がありますか、フロント エンド サーバーと同じ場所にします。 さらに、E9-1-1 の展開では、認定された E9-1-1 サービス プロバイダーへの SIP トランク、または公衆交換電話網 (PSTN) への緊急位置識別番号 (ELIN) ゲートウェイも必要とします。
  
## <a name="deployment-process"></a>展開プロセス

次の表に、E9-1-1 展開プロセスの概要を示します。
  
|**フェーズ**|**手順**|**ロール**|**展開に関するドキュメント**|
|:-----|:-----|:-----|:-----|
|音声使用、ルート、およびトランクを構成する  <br/> |1. 新しい PSTN 使用法レコードを作成します。 これは、場所のポリシーの [**PSTN の使用法**] 設定で使用する名前と同じです。 <br/> 2. 作成やボイス ルートを前の手順で作成した PSTN 使用法レコードに割り当てる ~ 9-1-1 が SIP トランクまたは ELIN ゲートウェイ ゲートウェイの属性をポイントします。  <br/> 3. SIP トランク ~ 9-1-1 サービス ・ プロバイダーの**セット CsTrunkConfiguration EnablePIDFLOSupport**コマンドレットを使用して、PIDF-LO データを渡すための SIP の上 ~ 9-1-1 の呼び出しを処理するトランクを設定します。 <br/> 4. 必要に応じて、SIP トランク ~ 9-1-1 サービス プロバイダーの作成、または ~ 9-1-1 サービス プロバイダーの SIP トランクによって処理されない通話のローカルの PSTN ルートを割り当てます。 このルートは、E9-1-1 サービス プロバイダーへの接続が利用できない場合に使用されます。 E9-1-1 サービス プロバイダーがサポートしている場合は、911 ダイヤル文字列を国または地域の Emergency Call Response Center (ECRC) の Direct Inward Dialing (DID) 番号に変換するトランク構成ルールをゲートウェイに割り当てます。  <br/> |CSVoiceAdmin  <br/> |[ビジネス サーバー 2015 の Skype で ~ 9-1-1 のボイス ルートを構成します。](configure-an-e9-1-1-voice-route.md) <br/> |
|場所のポリシーを作成し、ユーザーおよびサブネットに割り当てる  <br/> |1. グローバルの場所のポリシーを確認します。  <br/> 2.。 ユーザー レベルのスコープを持つ場所ポリシーを作成します。または、組織にさまざまな緊急時の使用法を備えた 1 つ以上のサイトがある場合は、ネットワーク レベルのスコープを持つ場所のポリシーを作成します。  <br/> 3. 場所ポリシーをネットワーク サイトに割り当てます。  <br/> 4. 適切なサブネットをネットワーク サイトに追加します。  <br/> 5. (オプション) 割り当てユーザー ポリシーへの場所のポリシーです。  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin (場所のポリシーの作成を除く)  <br/> |[ビジネス サーバー 2015 の Skype での場所のポリシーを作成します。](create-location-policies.md) <br/> [ビジネス サーバー 2015 の Skype のネットワークのサイトに場所のポリシーを追加します。](add-a-location-policy-to-a-network-site.md) <br/> [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|場所データベースを構成する  <br/> |1. 場所へのネットワーク要素のマッピングを使用してデータベースを設定します。  <br/> 2. ELIN ゲートウェイを追加する ELINs、 \<[得意先名]\>列です。  <br/> 3. アドレスを検証するために ~ 9-1-1 のサービス ・ プロバイダーへの接続を構成します。  <br/> 4 ~ 9-1-1 サービスのプロバイダーのアドレスを検証します。  <br/> 5. 更新したデータベースを公開します。  <br/> 6. の ELIN ゲートウェイでは、PSTN 電話会社の自動ロケーション識別 (ALI) データベースに、ELINs をアップロードします。  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[ビジネス サーバー 2015 の Skype での場所のデータベースを構成します。](configure-the-location-database.md) <br/> |
|高度な機能を構成する (オプション)  <br/> |1. SNMP アプリケーションの URL を構成します。  <br/> 2. セカンダリ場所情報サービスの場所の URL を構成します。  <br/> |CSVoiceAdmin  <br/> |[ビジネス サーバー 2015 の Skype で SNMP アプリケーションを構成します。](configure-an-snmp-application.md) <br/> [ビジネス サーバー 2015 の Skype でセカンダリ場所情報サービスを構成します。](secondary-location-information-service.md) <br/> |
   

