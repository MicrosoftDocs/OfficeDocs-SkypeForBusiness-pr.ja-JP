---
title: VoipDetails テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: 各レコードは、少なくとも1人のユーザーが VoIP ユーザーである 1 2 パーティーの通話を表します。
ms.openlocfilehash: 65bf3b4d7a815434b21b761030a7ac514d9bd803
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814785"
---
# <a name="voipdetails-table"></a>VoipDetails テーブル
 
各レコードは、少なくとも1人のユーザーが VoIP ユーザーである 1 2 パーティーの通話を表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**セッション Id** <br/> |datetime  <br/> |Primary  <br/> |セッション要求の時刻。 セッションを一意に識別するために**Sessionidseq**と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するために**Sessionidtime**と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**Fromnumber Id** <br/> |int  <br/> |外部  <br/> |発信者の**PhoneId** 。 詳細については、「電話」の[表](phones.md)を参照してください。 Not NULL と**Fromgatewayid**が null でない場合は、発信者は PSTN ユーザーです。 <br/> |
|**Connected番号 Id** <br/> |int  <br/> |外部  <br/> |通話受信者の**PhoneId** 。 詳細については、「電話」の[表](phones.md)を参照してください。 Not NULL と**Togatewayid**が null でない場合は、通話レシーバーは PSTN ユーザーでした。 <br/> |
|**FromMediationServerId** <br/> |int  <br/> |外部  <br/> |通話が発信される仲介サーバー。 詳細については、 [Mediationservers テーブル](mediationservers.md)を参照してください。 <br/> |
|**ToMediationServerId** <br/> |int  <br/> |外部  <br/> |仲介サーバーが呼び出されます。 詳細については、 [Mediationservers テーブル](mediationservers.md)を参照してください。 <br/> |
|**FromGatewayId** <br/> |int  <br/> |外部  <br/> |ゲートウェイ通話の発信元です。 詳細については、「 [Skype For Business Server 2015 のゲートウェイの表](gateways.md)」を参照してください。 <br/> |
|**ToGatewayId** <br/> |int  <br/> |外部  <br/> |通話の発信先のゲートウェイ。 詳細については、「 [Skype For Business Server 2015 のゲートウェイの表](gateways.md)」を参照してください。 <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |外部  <br/> |ユーザーが URI を持っている場合に、通話を切断したユーザーの URI。 詳細については、「ユーザー」の[表](users.md)を参照してください。 <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |外部  <br/> |通話を切断した電話の ID が電話から切断されました。 詳細については、「電話」の[表](phones.md)を参照してください。 <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||監視サービスで内部的に使用されます。  <br/> このフィールドは、Skype for Business Server 2015 で導入されました。  <br/> |
   

