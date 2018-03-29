---
title: 登録の表示
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: 登録ビューは、ユーザー登録に関する情報を格納します。 このビューは、Lync Server 2013 で導入されました。
ms.openlocfilehash: e116c2609f1f26268eaaa3413c3a4491da096585
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="registration-view"></a>登録の表示
 
登録ビューは、ユーザー登録に関する情報を格納します。 このビューは、Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |セッションの要求の時間です。 セッションを一意に識別するのには SessionIdSeq と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するのには SessionIdTime と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**RegisterTime** <br/> |datetime  <br/> |登録が発生した時刻です。  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |登録したユーザーの URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |登録したユーザーの URI の種類です。 詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。 <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |登録したユーザーのテナントです。 詳細については[テナントのテーブル](tenants.md)を参照してください。 <br/> |
|**EndpointId** <br/> |一意識別子  <br/> |登録されているユーザーのエンドポイントの一意の識別子です。  <br/> |
|**EndpointEra** <br/> |一意識別子  <br/> |同じユーザーと同じエンドポイントに関連する登録を区別するために使用される一意の識別子です。  <br/> |
|**DeRegisterType** <br/> |datetime  <br/> |時刻を登録解除が発生しました。  <br/> |
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> |登録解除の理由です。  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |登録したユーザーが使用するクライアントのバージョンです。  <br/> |
|**顧客タイプ** <br/> |int  <br/> |登録されているユーザーによって使用されるクライアントです。 詳細については、 [UserAgentDef テーブル](useragentdef.md)を参照してください。 <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |クライアントのユーザーが登録されているカテゴリです。  <br/> |
|**Ip アドレス** <br/> |nvarchar(256)  <br/> |ユーザーの IP アドレスに登録されています。 IPv4 または IPv6 アドレスがあります。  <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |SIP ダイアログの id。 フォーマット、です。  <br/> ダイアログ; タグからタグに  <br/> |
|**ResponseCode** <br/> |int  <br/> |セッションへの招待に SIP 応答コード。 このフィールドは通常、セッションの初期の INVITE メッセージから生成されたデータが設定されます。 招待メッセージが表示されない場合は、日付と時刻の最初の関連する SIP メッセージ (BYE、[キャンセル]、メッセージ、または情報) を持つフィールドが設定されます。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |SIP ヘッダーから取得された ID を診断します。  <br/> |
|**レジストラー** <br/> |nvarchar(256)  <br/> |レジストラーの FQDN。  <br/> |
|**[プール]** <br/> |nvarchar(256)  <br/> |セッションのデータをキャプチャするプールの FQDN です。  <br/> |
|**Edgeserver があります。** <br/> |nvarchar(256)  <br/> |登録したユーザーで使用されているエッジ サーバーの FQDN です。  <br/> |
|**IsInternal** <br/> |bit  <br/> |内部ネットワークからユーザーにログインするかどうかを示します。  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> |登録時に、UserService を使用したかどうかを示します。  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> |プライマリ レジストラーに登録をしたかどうかを示します。  <br/> |
|**DeviceMacAddress** <br/> |bigint 型の値  <br/> |デバイスの MAC アドレスが登録されています。  <br/> |
|**DeviceManufacturer** <br/> |nvarchar(256)  <br/> |デバイスの製造元が登録されています。 詳細については、 [Skype のビジネス サーバー 2015 の製造元テーブル](manufacturers.md)を参照してください。 <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar(256)  <br/> |デバイスのハードウェアのバージョンが登録されています。 詳細については、 [Skype のビジネス サーバー 2015 で HardwareVersions テーブル](hardwareversions.md)を参照してください。 <br/> |
   

