---
title: Skype for Business Server で緊急サービスを展開する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: Skype for Business Server Enterprise Voice で E9-1 を展開します。 前提条件と展開プロセスのチェックリストも掲載しています。
ms.openlocfilehash: a96d425f39b53c970047eb220e0ae9f61b515089
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233293"
---
# <a name="deploy-emergency-services-in-skype-for-business-server"></a>Skype for Business Server で緊急サービスを展開する
 
Skype for Business Server Enterprise Voice で E9-1 を展開します。 前提条件と展開プロセスのチェックリストも掲載しています。
  
強化された 9-1-1 (E9) は、通話相手の電話番号を市民または住所と関連付ける緊急通知機能です。 緊急応答機関 (PSAP) はこの情報を使用して、支援を必要とする発信者に緊急サービスをすぐに派遣できます。
  
E9-1-1 をサポートするには、Skype for Business Server で、場所とクライアントを正しく関連付け、緊急通話を最も近い PSAP にルーティングするためにこの情報を使用できるようにする必要があります。
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>E9-1-1 の展開前提条件

E9-1 を展開する前に、一元管理ストア、フロントエンドプール、Standard Edition サーバーなど、Skype for Business Server の内部サーバーを既に展開している必要があります。 また、1つ以上の仲介サーバーを、スタンドアロンか、フロントエンドサーバーと共に展開する必要があります。 さらに、E9-1-1 の展開では、認定された E9-1-1 サービス プロバイダーへの SIP トランク、または公衆交換電話網 (PSTN) への緊急位置識別番号 (ELIN) ゲートウェイも必要とします。
  
## <a name="deployment-process"></a>展開プロセス

次の表に、E9-1-1 展開プロセスの概要を示します。
  
|**段階**|**手順**|**Roles**|**「展開」のドキュメント**|
|:-----|:-----|:-----|:-----|
|音声使用、ルート、およびトランクを構成する  <br/> |1. 新しい PSTN 使用状況レコードを作成します。 これは、場所のポリシーの [**PSTN の使用法**] 設定で使用する名前と同じです。 <br/> 2. 前の手順で作成した PSTN 使用状況レコードへのボイスルートを作成または割り当て、[ゲートウェイ] 属性を E9 SIP トランクまたは ELIN gateway にポイントします。  <br/> 3. SIP トランク E9 のサービスプロバイダについては、SIP を介して E9-1-1 の呼び出しを処理するトランクを設定して、 **set-cstrunkconfiguration-EnablePIDFLOSupport**コマンドレットを使用して PIDF-LO データを渡します。 <br/> 4. 必要に応じて、SIP トランク E9 サービスプロバイダの場合は、E9 サービスプロバイダの SIP トランクによって処理されない通話のローカル PSTN ルートを作成または割り当てます。 このルートは、E9-1-1 サービス プロバイダーへの接続が利用できない場合に使用されます。 E9-1-1 サービス プロバイダーがサポートしている場合は、911 ダイヤル文字列を国または地域の Emergency Call Response Center (ECRC) の Direct Inward Dialing (DID) 番号に変換するトランク構成ルールをゲートウェイに割り当てます。  <br/> |CSVoiceAdmin  <br/> |[Skype for Business Server で E9 のボイスルートを設定する](configure-an-e9-1-1-voice-route.md) <br/> |
|場所のポリシーを作成し、ユーザーおよびサブネットに割り当てる  <br/> |1. グローバルな場所のポリシーを確認します。  <br/> 2. ユーザーレベルのスコープを持つ場所のポリシーを作成します。または、緊急対応の異なる複数のサイトが組織にある場合は、ネットワークレベルのスコープを使用して場所のポリシーを作成します。  <br/> 3. 場所のポリシーをネットワークサイトに割り当てます。  <br/> 4. 適切なサブネットをネットワークサイトに追加します。  <br/> 5. (省略可能) ユーザーポリシーに位置情報ポリシーを割り当てます。  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin (場所のポリシーの作成を除く)  <br/> |[Skype for Business Server で場所のポリシーを作成する](create-location-policies.md) <br/> [Skype for Business Server のネットワークサイトに位置情報ポリシーを追加する](add-a-location-policy-to-a-network-site.md) <br/> [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|場所データベースを構成する  <br/> |1. ネットワーク要素と場所をマッピングしてデータベースを設定します。  <br/> 2. ELIN ゲートウェイの場合、[ \<CompanyName\> ] 列に elins を追加します。  <br/> 3. 住所を検証するための E9 サービスプロバイダーへの接続を構成します。  <br/> 4. E9 サービスプロバイダーを使用して、住所を確認します。  <br/> 5. 更新されたデータベースを公開します。  <br/> 6. ELIN ゲートウェイの場合、PSTN キャリアの自動位置情報識別 (ALI) データベースに ELINs をアップロードします。  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[Skype for Business Server で場所データベースを構成する](configure-the-location-database.md) <br/> |
|高度な機能を構成する (オプション)  <br/> |1. SNMP アプリケーションの URL を構成します。  <br/> 2. セカンダリ場所情報サービスの場所の URL を構成します。  <br/> |CSVoiceAdmin  <br/> |[Skype for Business Server で SNMP アプリケーションを構成する](configure-an-snmp-application.md) <br/> [Skype for Business Server でセカンダリ場所情報サービスを構成する](secondary-location-information-service.md) <br/> |
   

