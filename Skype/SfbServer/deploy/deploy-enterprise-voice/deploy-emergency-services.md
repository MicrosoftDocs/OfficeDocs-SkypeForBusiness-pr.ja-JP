---
title: 緊急サービスをSkype for Business Server
ms.reviewer: ''
ms.author: v-cichur
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
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: E9-1-1 を展開Skype for Business Server エンタープライズ VoIP。 前提条件と展開プロセスのチェックリストが含まれています。
ms.openlocfilehash: 51c877fd285bd9db31de697e72458a44d44d0b71
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58600712"
---
# <a name="deploy-emergency-services-in-skype-for-business-server"></a>緊急サービスをSkype for Business Server
 
E9-1-1 を展開Skype for Business Server エンタープライズ VoIP。 前提条件と展開プロセスのチェックリストが含まれています。
  
拡張 9-1-1 (E9-1-1) は、発信側の電話番号を市民または住所に関連付ける緊急通知機能です。 緊急応答機関 (PSAP) はこの情報を使用して、支援を必要とする発信者に緊急サービスをすぐに派遣できます。
  
E9-1-1 をサポートするには、Skype for Business Server が場所をクライアントに正しく関連付け、この情報を使用して緊急通話を最も近い PSAP にルーティングできる必要があります。
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>E9-1-1 の展開前提条件

E9-1-1 を展開する前に、中央管理ストア、フロントエンド プール、Standard Edition サーバーなど、Skype for Business Server 内部サーバーを既に展開している必要があります。 また、1 つ以上の仲介サーバー (スタンドアロンまたはフロントエンド サーバーと同一配置) を展開する必要があります。 E9-1-1 の展開はさらに、認定された緊急サービス サービス プロバイダーへの SIP トランク、または公衆交換電話網 (PSTN) への緊急位置識別番号 (ELIN) ゲートウェイも必要とします。
  
## <a name="deployment-process"></a>展開プロセス

次の表に、E9-1-1 展開プロセスの概要を示します。
  
|**フェーズ**|**手順**|**役割**|**展開のドキュメント**|
|:-----|:-----|:-----|:-----|
|音声使用、ルート、およびトランクを構成する  <br/> |1. 新しい PSTN 使用法レコードを作成します。 これは、場所のポリシーの [**PSTN の使用法**] 設定で使用する名前と同じです。 <br/> 2. 前の手順で作成した PSTN 使用法レコードに音声ルートを作成または割り当て、ゲートウェイ属性を E9-1-1 SIP トランクまたは ELIN ゲートウェイにポイントします。  <br/> 3. SIP トランク E9-1-1 サービス プロバイダーの場合は **、Set-CsTrunkConfiguration -EnablePIDFLOSupport** コマンドレットを使用して、SIP 上で E9-1-1 通話を処理するトランクを設定して、PIDF-LO データを渡します。 <br/> 4. 必要に応じて、SIP トランク E9-1-1 サービス プロバイダーの場合は、E9-1-1 サービス プロバイダーの SIP トランクで処理されない通話のローカル PSTN ルートを作成または割り当てる必要があります。 このルートは、E9-1-1 サービス プロバイダーへの接続が利用できない場合に使用されます。 E9-1-1 サービス プロバイダーがサポートしている場合は、911 ダイヤル文字列を国または地域の Emergency Call Response Center (ECRC) の Direct Inward Dialing (DID) 番号に変換するトランク構成ルールをゲートウェイに割り当てます。  <br/> |CSVoiceAdmin  <br/> |[E9-1-1 音声ルートを構成Skype for Business Server](configure-an-e9-1-1-voice-route.md) <br/> |
|場所のポリシーを作成し、ユーザーおよびサブネットに割り当てる  <br/> |1. グローバルな場所ポリシーを確認します。  <br/> 2. ユーザー レベルのスコープを持つ場所ポリシーを作成します。または、組織が複数のサイトに異なる緊急使用を持つ場合は、ネットワーク レベルのスコープを持つ場所ポリシーを作成します。  <br/> 3. 場所ポリシーをネットワーク サイトに割り当てる。  <br/> 4. 適切なサブネットをネットワーク サイトに追加します。  <br/> 5. (オプション) ユーザー ポリシーに場所ポリシーを割り当てる。  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin (場所のポリシーの作成を除く)  <br/> |[[場所ポリシーを作成する] Skype for Business Server](create-location-policies.md) <br/> [サイト内のネットワーク サイトに場所ポリシーを追加Skype for Business Server](add-a-location-policy-to-a-network-site.md) <br/> [サブネットをネットワーク サイトに関連付ける](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|場所データベースの構成  <br/> |1. ネットワーク要素の場所へのマッピングをデータベースに設定します。  <br/> 2. ELIN ゲートウェイの場合は、列に ELIN を追加 \<CompanyName\> します。  <br/> 3. アドレスを検証するための E9-1-1 サービス プロバイダーへの接続を構成します。  <br/> 4. E9-1-1 サービス プロバイダーでアドレスを検証します。  <br/> 5. 更新されたデータベースを発行します。  <br/> 6. ELIN ゲートウェイの場合は、ELIN を PSTN キャリアの自動場所識別 (ALI) データベースにアップロードします。  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[場所データベースを構成Skype for Business Server](configure-the-location-database.md) <br/> |
|高度な機能を構成する (オプション)  <br/> |1. SNMP アプリケーションの URL を構成します。  <br/> 2. セカンダリ位置情報サービスの場所の URL を構成します。  <br/> |CSVoiceAdmin  <br/> |[サーバーで SNMP アプリケーションを構成Skype for Business Server](configure-an-snmp-application.md) <br/> [サーバーでセカンダリ位置情報サービスを構成Skype for Business Server](secondary-location-information-service.md) <br/> |
   

