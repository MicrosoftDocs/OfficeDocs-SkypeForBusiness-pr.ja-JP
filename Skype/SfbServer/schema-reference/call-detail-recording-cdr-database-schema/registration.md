---
title: Registration テーブル
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
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: 各レコードは、1つのユーザー登録イベントを表します。
ms.openlocfilehash: bca31b85a0b88854760c2a79528792ee82bd272e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814945"
---
# <a name="registration-table"></a>Registration テーブル
 
各レコードは、1つのユーザー登録イベントを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**セッション Id** <br/> |datetime  <br/> |プライマリ、外部  <br/> |セッション要求の時刻。 セッションを一意に識別するために**Sessionidseq**と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |プライマリ、外部  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するために**Sessionidtime**と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**UserId** <br/> |int  <br/> |外部  <br/> |ユーザー ID。 詳細については、「ユーザー」の[表](users.md)を参照してください。 <br/> |
|**EndpointId** <br/> |長さ  <br/> ||登録エンドポイントを識別する GUID。 通常、同じユーザーの同じコンピューターの register イベントには、同じエンドポイント ID があります。 各コンピューターには、別のエンドポイント ID があります。  <br/> |
|**Endポインタ a** <br/> |長さ  <br/> ||同じユーザーと同じエンドポイントを含む登録を区別するために使用される ID です。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ClientVersionId** <br/> |int  <br/> |外部  <br/> |現在のユーザーのクライアントバージョン。 詳細については、「 [Skype For Business Server 2015 の Clientversions](clientversions.md) 」の表を参照してください。 <br/> |
|**RegistrarId** <br/> |int  <br/> |外部  <br/> |登録に使用されるレジストラーサーバーの ID です。 詳細については、「Servers」の[表](servers.md)を参照してください。 <br/> |
|**PoolId** <br/> |int  <br/> |外部  <br/> |セッションがキャプチャされたプールの ID です。 詳細については、「プール」の[表](pools.md)を参照してください。 <br/> |
|**EdgeServerId** <br/> |int  <br/> |外部  <br/> |エッジサーバーの登録が進行中です。 詳細については、「 [Skype For Business Server 2015 の EdgeServers テーブル](edgeservers.md)」を参照してください。 <br/> |
|**IsInternal** <br/> |わずか  <br/> ||ユーザーが内部からログオンしているかどうか。  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||UserService が利用できるかどうか。  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||プライマリレジストラーに登録するかどうかを指定します。  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||ユーザーが survivable branch アプライアンスに登録されているかどうかを示します。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RegisterTime** <br/> |datetime  <br/> ||登録時間。  <br/> |
|**DeRegisterTime** <br/> |datetime  <br/> ||登録解除時間。  <br/> |
|**返信** <br/> |int  <br/> ||Register 要求の応答コード。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||Register 要求の診断 ID。 これにより、診断情報の種類が示されます。  <br/> |
|**DeviceId** <br/> |int  <br/> |外部  <br/> |Register 要求の取得元のデバイス。 詳細については、「 [Skype For Business Server 2015 の Devices テーブル](devices.md)」を参照してください。 <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |外部  <br/> |"ユーザーが開始しました"、"登録の期限切れ"、"クライアントが失敗しました" などの de レジスタの理由。 詳細については、「 [Skype For Business Server 2015 の DeRegisterType テーブル](deregistertype.md)」を参照してください。 <br/> |
|**IPAddress** <br/> |nvarchar(256)  <br/> ||ユーザーが登録したエンドポイントの IP アドレス。 これは IPv4 アドレスまたは IPv6 アドレスにすることができます。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||監視サービスで内部的に使用されます。  <br/> このフィールドは、Skype for Business Server 2015 で導入されました。  <br/> |
   

