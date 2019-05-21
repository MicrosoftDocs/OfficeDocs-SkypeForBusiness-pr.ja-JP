---
title: 登録表示
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: 登録ビューには、ユーザー登録に関する情報が格納されます。 このビューは、Lync Server 2013 で導入されました。
ms.openlocfilehash: 6202e40e6385fd243f55badd25dbe196452c890a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295868"
---
# <a name="registration-view"></a>登録表示
 
登録ビューには、ユーザー登録に関する情報が格納されます。 このビューは、Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**セッション Id** <br/> |datetime  <br/> |セッション要求の時刻。 セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**RegisterTime** <br/> |datetime  <br/> |登録が発生した時刻。  <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |登録されたユーザーの URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |登録したユーザーの URI の種類。 詳細については、 [UriTypes の表](uritypes.md)を参照してください。 <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |登録したユーザーのテナント。 詳細については、「テナント」の[表](tenants.md)を参照してください。 <br/> |
|**EndpointId** <br/> |長さ  <br/> |登録されているユーザーのエンドポイントの一意の識別子。  <br/> |
|**Endポインタ a** <br/> |長さ  <br/> |同じユーザーと同じエンドポイントを含む登録を区別するために使用される一意の識別子。  <br/> |
|**DeRegisterType** <br/> |datetime  <br/> |登録解除が行われた時刻。  <br/> |
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> |登録解除の理由。  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |登録したユーザーによって使用されたクライアントのバージョン。  <br/> |
|**ClientType** <br/> |int  <br/> |登録したユーザーによって使用されたクライアント。 詳細については、 [Useragentdef テーブル](useragentdef.md)を参照してください。 <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |登録されたユーザーによって使用されたクライアントのカテゴリです。  <br/> |
|**Ip** <br/> |nvarchar(256)  <br/> |ユーザーが登録した IP アドレス。 これは IPv4 または IPv6 アドレスである可能性があります。  <br/> |
|**この Id** <br/> |varstring (775)  <br/> |SIP ダイアログ ID。 の形式は次のとおりです。  <br/> ダイアログ; 開始タグからタグへ  <br/> |
|**返信** <br/> |int  <br/> |セッション招待状への SIP 応答コード。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |SIP ヘッダーからキャプチャされた診断 ID。  <br/> |
|**レジストラー** <br/> |nvarchar(256)  <br/> |レジストラーの FQDN。  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |セッションのデータをキャプチャしたプールの FQDN。  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |登録されたユーザーによって使用されたエッジサーバーの FQDN。  <br/> |
|**IsInternal** <br/> |bit  <br/> |ユーザーが内部ネットワークからログオンしているかどうかを示します。  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> |登録時に UserService が利用可能であったかどうかを示します。  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> |登録がプライマリレジストラーであったかどうかを示します。  <br/> |
|**DeviceMacAddress** <br/> |bigint  <br/> |登録されているデバイスの MAC アドレス。  <br/> |
|**DeviceManufacturer** <br/> |nvarchar(256)  <br/> |登録されているデバイスの製造元。 詳細については、「 [Skype For Business Server 2015 の製造元の表](manufacturers.md)」を参照してください。 <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar(256)  <br/> |登録されているデバイスのハードウェアバージョン。 詳細については、「 [Skype For Business Server 2015 のハードウェアバージョン](hardwareversions.md)」の表を参照してください。 <br/> |
   

