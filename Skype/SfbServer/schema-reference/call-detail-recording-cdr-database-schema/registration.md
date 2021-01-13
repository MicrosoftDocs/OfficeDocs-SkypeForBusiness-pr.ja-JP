---
title: 登録テーブル
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
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: 各レコードは 1 つのユーザー登録イベントを表します。
ms.openlocfilehash: 1ab9c4b80d7bdbbc379c202978d7639e286128fe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823117"
---
# <a name="registration-table"></a>登録テーブル
 
各レコードは 1 つのユーザー登録イベントを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |主/プライマリ、外部  <br/> |セッション要求の時刻。 セッションを一意に識別するために **SessionIdSeq** と併用されます。 詳細については [、Skype for Business Server 2015](dialogs.md) の Dialogs テーブルを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主/プライマリ、外部  <br/> |セッションを識別するための ID 番号。 セッションを一意に識別するために **SessionIdTime** と併用されます。 詳細については [、Skype for Business Server 2015](dialogs.md) の Dialogs テーブルを参照してください。 <br/> |
|**UserId** <br/> |int  <br/> |外部  <br/> |ユーザー ID。 詳細については [、Users の表](users.md) を参照してください。 <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> ||登録エンドポイントを識別するための GUID。通常、同じユーザーの同じコンピューターからの登録イベントは、同じエンドポイント ID になります。コンピューターが異なると、エンドポイント ID も異なります。  <br/> |
|**EndpointEra** <br/> |uniqueIdentifier  <br/> ||同じユーザーと同じエンドポイントを含む登録を区別するために使用される ID。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ClientVersionId** <br/> |int  <br/> |外部  <br/> |現在のユーザーのクライアントのバージョン。 詳細については [、Skype for Business Server 2015 の ClientVersions テーブル](clientversions.md) を参照してください。 <br/> |
|**RegistrarId** <br/> |int  <br/> |外部  <br/> |登録に使用されたレジストラー サーバーの ID。 詳細については [、Servers の表](servers.md) を参照してください。 <br/> |
|**PoolId** <br/> |int  <br/> |外部  <br/> |セッションが取得されたプールの ID。 詳細については [、Pools の表](pools.md) を参照してください。 <br/> |
|**EdgeServerId** <br/> |int  <br/> |外部  <br/> |登録が通過するエッジ サーバー。 詳細については [、Skype for Business Server 2015 の EdgeServers テーブル](edgeservers.md) を参照してください。 <br/> |
|**IsInternal** <br/> |ビット  <br/> ||ユーザーが内部からログオンしているかどうか。  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||UserService が利用できるかどうか。  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||プライマリ レジストラーに対する登録かどうか。  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||ユーザーが存続可能ブランチ アプライアンスに登録されているかどうかを示します。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RegisterTime** <br/> |日付型  <br/> ||登録日時。  <br/> |
|**DeRegisterTime** <br/> |日付型  <br/> ||登録解除日時。  <br/> |
|**ResponseCode** <br/> |int  <br/> ||登録要求の応答コード。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||登録要求の診断 ID。その診断情報の種類を示します。  <br/> |
|**DeviceId** <br/> |int  <br/> |外部  <br/> |登録要求の送信元のデバイス。 詳細については [、Skype for Business Server 2015](devices.md) の Devices の表を参照してください。 <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |外部  <br/> |登録を取りやめした理由 ("ユーザーが開始しました"、"登録が期限切れ"、"クライアントが失敗しました"など)。 詳細については [、Skype for Business Server 2015 の DeRegisterType テーブル](deregistertype.md) を参照してください。 <br/> |
|**IPAddress** <br/> |nvarchar(256)  <br/> ||ユーザーが登録されているエンドポイントの IP アドレス。 IPv4 アドレスまたは IPv6 アドレスのどちらかになります。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||監視サービスの内部用テーブル。  <br/> このフィールドは、Skype for Business Server 2015 で導入されました。  <br/> |
   

