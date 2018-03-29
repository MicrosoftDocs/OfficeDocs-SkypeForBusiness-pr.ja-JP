---
title: VoipDetails テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: レコードは、ユーザーが少なくとも 1 つ 1 つの 2 パーティ呼び出しは VoIP ユーザーを各です。
ms.openlocfilehash: 8f28ec3ac1d4049f24c5af5b768026bdd8a98486
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="voipdetails-table"></a>VoipDetails テーブル
 
レコードは、ユーザーが少なくとも 1 つ 1 つの 2 パーティ呼び出しは VoIP ユーザーを各です。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |セッションの要求の時間です。 セッションを一意に識別するのには**SessionIdSeq**と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するのには**SessionIdTime**と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**FromNumberId** <br/> |int  <br/> |外部  <br/> |呼び出し元の**PhoneId**にします。 詳細については[電話の表](phones.md)を参照してください。 NULL されず、 **FromGatewayId**が NULL でない場合、呼び出し元は、PSTN のユーザーをしました。 <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |外部  <br/> |呼び出しの受信機の**PhoneId**にします。 詳細については[電話の表](phones.md)を参照してください。 NULL されず、 **ToGatewayId**が NULL でない場合、電話の受信側は、PSTN のユーザーをしました。 <br/> |
|**FromMediationServerId** <br/> |int  <br/> |外部  <br/> |仲介サーバーは、呼び出しが行われるからです。 詳細については、 [MediationServers テーブル](mediationservers.md)を参照してください。 <br/> |
|**ToMediationServerId** <br/> |int  <br/> |外部  <br/> |呼ばれる仲介サーバーになります。 詳細については、 [MediationServers テーブル](mediationservers.md)を参照してください。 <br/> |
|**FromGatewayId** <br/> |int  <br/> |外部  <br/> |ゲートウェイの呼び出しに由来しています。 詳細については、 [Skype のビジネス サーバー 2015 のゲートウェイのテーブル](gateways.md)を参照してください。 <br/> |
|**ToGatewayId** <br/> |int  <br/> |外部  <br/> |ゲートウェイの呼び出しになります。 詳細については、 [Skype のビジネス サーバー 2015 のゲートウェイのテーブル](gateways.md)を参照してください。 <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |外部  <br/> |ユーザーの URI の場合、呼び出しを切断したユーザーの URI。 詳細については[「ユーザー」テーブル](users.md)を参照してください。 <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |外部  <br/> |電話呼び出しを切断するの ID は、携帯電話から切断されました。 詳細については[電話の表](phones.md)を参照してください。 <br/> |
|**LastModifiedTime** <br/> |日付時刻  <br/> ||監視サービスによって内部で使用します。  <br/> このフィールドは、ビジネス サーバー 2015 の Skype で導入されました。  <br/> |
   

