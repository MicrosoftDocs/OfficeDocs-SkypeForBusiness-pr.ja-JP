---
title: 登録ビュー
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: 登録ビューでは、ユーザー登録に関する情報を格納します。 このビューは、Lync Server 2013 で導入されました。
ms.openlocfilehash: ccd868c228b32f69240d6b2c7a10d4c07ac90d56
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384115"
---
# <a name="registration-view"></a>登録ビュー
 
登録ビューでは、ユーザー登録に関する情報を格納します。 このビューは、Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |セッション要求の時間。 セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。 詳細については[、2015 Skype for Business Serverの](dialogs.md) Dialogs テーブルを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |セッションを識別するための ID 番号。 セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。 詳細については[、2015 Skype for Business Serverの](dialogs.md) Dialogs テーブルを参照してください。 <br/> |
|**RegisterTime** <br/> |日付型  <br/> |登録が発生した時間。  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |登録したユーザーの URI  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |登録したユーザーの URI の種類。 詳細については [、UriTypes テーブル](uritypes.md) を参照してください。 <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |登録したユーザーのテナント ID。 詳細については [、「Tenants」テーブル](tenants.md) を参照してください。 <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> |ユーザーの登録に使用するエンドポイントの一意の識別子。  <br/> |
|**EndpointEra** <br/> |uniqueidentifier  <br/> |同じユーザーおよび同じエンドポイントが含まれる登録を区別するための一意の識別子。  <br/> |
|**DeRegisterType** <br/> |日付型  <br/> |登録解除が発生した時間。  <br/> |
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> |登録解除の理由。  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |登録したユーザーが使用しているクライアントのバージョン。  <br/> |
|**ClientType** <br/> |int  <br/> |登録したユーザーが使用しているクライアント。 詳細については [、UserAgentDef の表](useragentdef.md) を参照してください。 <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |登録したユーザーが使用しているクライアントのカテゴリ。  <br/> |
|**IpAddress** <br/> |nvarchar(256)  <br/> |IP ユーザーが登録したアドレス。 これは、IPv4 または IPv6 アドレスです。  <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |SIP ダイアログ ID。形式は次のとおりです。  <br/> dialog;from-tag;to-tag  <br/> |
|**ResponseCode** <br/> |int  <br/> |セッションへの招待に対する SIP 応答コード。このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |SIP ヘッダーから取得された診断 ID。  <br/> |
|**レジストラー** <br/> |nvarchar(256)  <br/> |レジストラーの FQDN。  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |セッションのデータをキャプチャしたプールの FQDN。  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |登録したユーザーが使用しているエッジ サーバーの FQDN。  <br/> |
|**IsInternal** <br/> |ビット  <br/> |ユーザーが内部ネットワークからログオンしているかどうかを示します。  <br/> |
|**IsUserServiceAvailable** <br/> |ビット  <br/> |登録時に UserService が使用可能であったかどうかを示します。  <br/> |
|**IsPrimaryRegistrar** <br/> |ビット  <br/> |登録がプライマリ レジストラーを使用して行われたかどうかを示します。  <br/> |
|**DeviceMacAddress** <br/> |bigint  <br/> |登録されたデバイスの MAC アドレス。  <br/> |
|**DeviceManufacturer** <br/> |nvarchar(256)  <br/> |登録されたデバイスの製造元。 詳細については[、2015 Skype for Business Serverの製造元の](manufacturers.md)表を参照してください。 <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar(256)  <br/> |登録されたデバイスのハードウェア バージョン。 詳細については[、2015 Skype for Business Server HardwareVersions の](hardwareversions.md)表を参照してください。 <br/> |
   

