---
title: 登録テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: 各レコードは 1 つのユーザー登録イベントを表します。
ms.openlocfilehash: df06364cc466d40ec571328089a7fab5d4970761
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394889"
---
# <a name="registration-table"></a>登録テーブル
 
各レコードは 1 つのユーザー登録イベントを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |主/プライマリ、外部  <br/> |セッション要求の時刻。 セッションを一意に識別するために **SessionIdSeq** と併用されます。 詳細については[、2015 Skype for Business Serverの](dialogs.md) Dialogs テーブルを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主/プライマリ、外部  <br/> |セッションを識別するための ID 番号。 セッションを一意に識別するために **SessionIdTime** と併用されます。 詳細については[、2015 Skype for Business Serverの](dialogs.md) Dialogs テーブルを参照してください。 <br/> |
|**UserId** <br/> |int  <br/> |外部  <br/> |ユーザー ID。 詳細については [、「Users」テーブル](users.md) を参照してください。 <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> ||登録エンドポイントを識別するための GUID。通常、同じユーザーの同じコンピューターからの登録イベントは、同じエンドポイント ID になります。コンピューターが異なると、エンドポイント ID も異なります。  <br/> |
|**EndpointEra** <br/> |uniqueIdentifier  <br/> ||同じユーザーと同じエンドポイントを含む登録を区別するために使用される ID。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ClientVersionId** <br/> |int  <br/> |外部  <br/> |現在のユーザーのクライアントのバージョン。 詳細については[、2015 年Skype for Business Server ClientVersions](clientversions.md) テーブルを参照してください。 <br/> |
|**RegistrarId** <br/> |int  <br/> |外部  <br/> |登録に使用されたレジストラー サーバーの ID。 詳細については [、「サーバー」の表](servers.md) を参照してください。 <br/> |
|**PoolId** <br/> |int  <br/> |外部  <br/> |セッションが取得されたプールの ID。 詳細については [、「Pools」の表](pools.md) を参照してください。 <br/> |
|**EdgeServerId** <br/> |int  <br/> |外部  <br/> |登録が通過するエッジ サーバー。 詳細については[、2015 Skype for Business Serverの EdgeServers](edgeservers.md) テーブルを参照してください。 <br/> |
|**IsInternal** <br/> |ビット  <br/> ||ユーザーが内部からログオンしているかどうか。  <br/> |
|**IsUserServiceAvailable** <br/> |ビット  <br/> ||UserService が利用できるかどうか。  <br/> |
|**IsPrimaryRegistrar** <br/> |ビット  <br/> ||プライマリ レジストラーに対する登録かどうか。  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |ビット  <br/> ||ユーザーが存続可能ブランチ アプライアンスに登録されているかどうかを示します。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RegisterTime** <br/> |日付型  <br/> ||登録日時。  <br/> |
|**DeRegisterTime** <br/> |日付型  <br/> ||登録解除日時。  <br/> |
|**ResponseCode** <br/> |int  <br/> ||登録要求の応答コード。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||登録要求の診断 ID。その診断情報の種類を示します。  <br/> |
|**DeviceId** <br/> |int  <br/> |外部  <br/> |登録要求の送信元のデバイス。 詳細については[、「デバイス」の表Skype for Business Server 2015](devices.md) を参照してください。 <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |外部  <br/> |'usered'、'registration expired'、'client fail'など、登録を無効にした理由。 詳細については[、2015 年の DeRegisterType Skype for Business Serverを](deregistertype.md)参照してください。 <br/> |
|**IPAddress** <br/> |nvarchar(256)  <br/> ||ユーザーが登録されているエンドポイントの IP アドレス。 IPv4 アドレスまたは IPv6 アドレスのどちらかになります。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||監視サービスの内部用テーブル。  <br/> このフィールドは、2015 年Skype for Business Serverされました。  <br/> |
   

