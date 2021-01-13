---
title: VoipDetails テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: それぞれのレコードは、少なくとも 1 人のユーザーが VoIP ユーザーであるような 1 回の 2 者間通話を表します。
ms.openlocfilehash: 900598c99965292e7d349520cc2dfa55443bb5a9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813097"
---
# <a name="voipdetails-table"></a>VoipDetails テーブル
 
それぞれのレコードは、少なくとも 1 人のユーザーが VoIP ユーザーであるような 1 回の 2 者間通話を表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |Primary  <br/> |セッション要求の時刻。 セッションを一意に識別するために **SessionIdSeq** と併用されます。 詳細については [、Skype for Business Server 2015](dialogs.md) の Dialogs テーブルを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |セッションを識別するための ID 番号。 セッションを一意に識別するために **SessionIdTime** と併用されます。 詳細については [、Skype for Business Server 2015](dialogs.md) の Dialogs テーブルを参照してください。 <br/> |
|**FromNumberId** <br/> |int  <br/> |外部  <br/> |発信者の **PhoneId**。 詳細については [、電話の表](phones.md) を参照してください。 この値と **FromGatewayId** がどちらも NULL でない場合、発信者は PSTN ユーザーです。 <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |外部  <br/> |通話の受信者の **PhoneId**。 詳細については [、電話の表](phones.md) を参照してください。 この値と **ToGatewayId** がどちらも NULL でない場合、通話の受信者は PSTN ユーザーです。 <br/> |
|**FromMediationServerId** <br/> |int  <br/> |外部  <br/> |通話の発信元の仲介サーバー。 詳細については [、MediationServers の表](mediationservers.md) を参照してください。 <br/> |
|**ToMediationServerId** <br/> |int  <br/> |外部  <br/> |通話の発信先の仲介サーバー。 詳細については [、MediationServers の表](mediationservers.md) を参照してください。 <br/> |
|**FromGatewayId** <br/> |int  <br/> |外部  <br/> |通話の発信元のゲートウェイ。 詳細については [、Skype for Business Server 2015](gateways.md) のゲートウェイの表を参照してください。 <br/> |
|**ToGatewayId** <br/> |int  <br/> |外部  <br/> |通話の発信先のゲートウェイ。 詳細については [、Skype for Business Server 2015](gateways.md) のゲートウェイの表を参照してください。 <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |外部  <br/> |通話を切断したユーザーの URI (ユーザーが URI を持つ場合)。 詳細については [、Users の表](users.md) を参照してください。 <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |外部  <br/> |別の電話から切断された通話を切断した電話の ID。 詳細については [、電話の表](phones.md) を参照してください。 <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||監視サービスの内部用テーブル。  <br/> このフィールドは、Skype for Business Server 2015 で導入されました。  <br/> |
   

