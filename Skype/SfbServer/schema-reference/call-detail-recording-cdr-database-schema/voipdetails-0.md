---
title: VoipDetails テーブル
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: それぞれのレコードは、少なくとも 1 人のユーザーが VoIP ユーザーであるような 1 回の 2 者間通話を表します。
ms.openlocfilehash: 905d972c680c5541e603b3ee3810c1d6d34e008f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768475"
---
# <a name="voipdetails-table"></a>VoipDetails テーブル
 
それぞれのレコードは、少なくとも 1 人のユーザーが VoIP ユーザーであるような 1 回の 2 者間通話を表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |Primary  <br/> |セッション要求の時刻。 セッションを一意に識別するために **SessionIdSeq** と併用されます。 詳細については[、「ダイアログ」の表Skype for Business Server 2015](dialogs.md)を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |セッションを識別するための ID 番号。 セッションを一意に識別するために **SessionIdTime** と併用されます。 詳細については[、「ダイアログ」の表Skype for Business Server 2015](dialogs.md)を参照してください。 <br/> |
|**FromNumberId** <br/> |int  <br/> |外部  <br/> |発信者の **PhoneId**。 詳細については [、「Phones」テーブル](phones.md) を参照してください。 この値と **FromGatewayId** がどちらも NULL でない場合、発信者は PSTN ユーザーです。 <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |外部  <br/> |通話の受信者の **PhoneId**。 詳細については [、「Phones」テーブル](phones.md) を参照してください。 この値と **ToGatewayId** がどちらも NULL でない場合、通話の受信者は PSTN ユーザーです。 <br/> |
|**FromMediationServerId** <br/> |int  <br/> |外部  <br/> |通話の発信元の仲介サーバー。 詳細については [、「MediationServers」の表](mediationservers.md) を参照してください。 <br/> |
|**ToMediationServerId** <br/> |int  <br/> |外部  <br/> |通話の発信先の仲介サーバー。 詳細については [、「MediationServers」の表](mediationservers.md) を参照してください。 <br/> |
|**FromGatewayId** <br/> |int  <br/> |外部  <br/> |通話の発信元のゲートウェイ。 詳細については[、「2015 Skype for Business Serverゲートウェイ」](gateways.md)の表を参照してください。 <br/> |
|**ToGatewayId** <br/> |int  <br/> |外部  <br/> |通話の発信先のゲートウェイ。 詳細については[、「2015 Skype for Business Serverゲートウェイ」](gateways.md)の表を参照してください。 <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |外部  <br/> |通話を切断したユーザーの URI (ユーザーが URI を持つ場合)。 詳細については [、「Users」テーブル](users.md) を参照してください。 <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |外部  <br/> |別の電話から切断された通話を切断した電話の ID。 詳細については [、「Phones」テーブル](phones.md) を参照してください。 <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||監視サービスの内部用テーブル。  <br/> このフィールドは、2015 年Skype for Business Serverされました。  <br/> |
   

