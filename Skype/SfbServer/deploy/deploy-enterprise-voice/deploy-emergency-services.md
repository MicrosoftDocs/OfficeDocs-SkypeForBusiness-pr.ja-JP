---
title: Skype for Business Server での緊急サービスの展開
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
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: Skype for Business Server 2013 で E9-1-1 を展開エンタープライズ VoIP。 前提条件と展開プロセスのチェックリストが含まれます。
ms.openlocfilehash: 8aed5b6462ecf9d5d9fecfb0ffdc5573ca4f2352
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812527"
---
# <a name="deploy-emergency-services-in-skype-for-business-server"></a>Skype for Business Server での緊急サービスの展開
 
Skype for Business Server サービスに E9-1-1 を展開エンタープライズ VoIP。 前提条件と展開プロセスのチェックリストが含まれます。
  
Enhanced 9-1-1 (E9-1-1) は、呼び出し元の電話番号を、公の住所または番前の住所に関連付ける緊急通知機能です。 緊急応答機関 (PSAP) はこの情報を使用して、支援を必要とする発信者に緊急サービスをすぐに派遣できます。
  
E9-1-1 をサポートするには、Skype for Business Server が場所をクライアントに正しく関連付け、この情報を使用して緊急電話を最も近い PSAP にルーティングできる必要があります。
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>E9-1-1 の展開前提条件

E9-1-1 を展開する前に、中央管理ストア、フロントエンド プール、または Standard Edition サーバーを含む Skype for Business Server 内部サーバーを既に展開している必要があります。 また、スタンドアロンまたはフロントエンド サーバーと一緒に配置された 1 つ以上の仲介サーバーも展開する必要があります。 E9-1-1 の展開はさらに、認定された緊急サービス サービス プロバイダーへの SIP トランク、または公衆交換電話網 (PSTN) への緊急位置識別番号 (ELIN) ゲートウェイも必要とします。
  
## <a name="deployment-process"></a>展開プロセス

次の表に、E9-1-1 展開プロセスの概要を示します。
  
|**フェーズ**|**手順**|**Roles**|**展開のドキュメント**|
|:-----|:-----|:-----|:-----|
|音声使用、ルート、およびトランクを構成する  <br/> |1. 新しい PSTN 使用法レコードを作成します。 これは、場所のポリシーの [**PSTN の使用法**] 設定で使用する名前と同じです。 <br/> 2. 前の手順で作成した PSTN 使用法レコードにボイス ルートを作成または割り当て、ゲートウェイ属性が E9-1-1 SIP トランクまたは ELIN ゲートウェイを指す。  <br/> 3. SIP トランク E9-1-1 サービス プロバイダーの場合は **、Set-CsTrunkConfiguration -EnablePIDFLOSupport** コマンドレットを使用して、SIP を使用して E9-1-1 呼び出しを処理するトランクを設定し、PIDF-LO データを渡します。 <br/> 4. 必要に応じて、SIP トランク E9-1-1 サービス プロバイダーの場合は、E9-1-1 サービス プロバイダーの SIP トランクで処理されない通話のローカル PSTN ルートを作成または割り当てる必要があります。 このルートは、E9-1-1 サービス プロバイダーへの接続が利用できない場合に使用されます。 E9-1-1 サービス プロバイダーがサポートしている場合は、911 ダイヤル文字列を国または地域の Emergency Call Response Center (ECRC) の Direct Inward Dialing (DID) 番号に変換するトランク構成ルールをゲートウェイに割り当てます。  <br/> |CSVoiceAdmin  <br/> |[Skype for Business Server で E9-1-1 ボイス ルートを構成する](configure-an-e9-1-1-voice-route.md) <br/> |
|場所のポリシーを作成し、ユーザーおよびサブネットに割り当てる  <br/> |1. グローバルな場所のポリシーを確認します。  <br/> 2. ユーザー レベルのスコープを持つ場所ポリシーを作成します。または、組織が複数のサイトに異なる緊急使用法を持つ場合は、ネットワーク レベルのスコープを持つ場所ポリシーを作成します。  <br/> 3. ネットワーク サイトに場所ポリシーを割り当てる。  <br/> 4. 適切なサブネットをネットワーク サイトに追加します。  <br/> 5. (オプション) 場所ポリシーをユーザー ポリシーに割り当てる。  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin (場所のポリシーの作成を除く)  <br/> |[Skype for Business Server で場所のポリシーを作成する](create-location-policies.md) <br/> [Skype for Business Server のネットワーク サイトに場所ポリシーを追加する](add-a-location-policy-to-a-network-site.md) <br/> [サブネットをネットワーク サイトに関連付ける](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|場所データベースの構成  <br/> |1. ネットワーク要素と場所のマッピングをデータベースに設定します。  <br/> 2. ELIN ゲートウェイの場合は、ELIN を列に追加 \<CompanyName\> します。  <br/> 3. アドレスを検証するための E9-1-1 サービス プロバイダーへの接続を構成します。  <br/> 4. E9-1-1 サービス プロバイダーで住所を検証します。  <br/> 5. 更新されたデータベースを発行します。  <br/> 6. ELIN ゲートウェイの場合は、ELIN を PSTN 通信事業者の自動ロケーション識別 (ALI) データベースにアップロードします。  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[Skype for Business Server で場所データベースを構成する](configure-the-location-database.md) <br/> |
|高度な機能を構成する (オプション)  <br/> |1. SNMP アプリケーションの URL を構成します。  <br/> 2. セカンダリ場所情報サービスの場所の URL を構成します。  <br/> |CSVoiceAdmin  <br/> |[Skype for Business Server で SNMP アプリケーションを構成する](configure-an-snmp-application.md) <br/> [Skype for Business Server でセカンダリの場所情報サービスを構成する](secondary-location-information-service.md) <br/> |
   

