---
title: Registration テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: 各レコードは、ユーザー登録の 1 つのイベントを表します。
ms.openlocfilehash: 1a487a01b0f8b3f6a087099daa32da99b7007445
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930603"
---
# <a name="registration-table"></a>Registration テーブル
 
各レコードは、ユーザー登録の 1 つのイベントを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |プライマリ サーバーで、外部  <br/> |セッションの要求の時間です。 セッションを一意に識別するのには**SessionIdSeq**と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |プライマリ サーバーで、外部  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するのには**SessionIdTime**と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**ユーザー Id** <br/> |int  <br/> |外部  <br/> |ユーザー id。 詳細については[「ユーザー」テーブル](users.md)を参照してください。 <br/> |
|**EndpointId** <br/> |一意識別子  <br/> ||登録エンドポイントを識別する GUID です。 同じエンドポイント ID を同じユーザーの同じコンピューターからの登録イベントが通常必要 別のエンドポイント ID が別のマシンです。  <br/> |
|**EndpointEra** <br/> |一意識別子  <br/> ||ID が同じユーザーと同じエンドポイントに関連する登録を区別するために使用します。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ClientVersionId** <br/> |int  <br/> |外部  <br/> |現在のユーザーのクライアントのバージョンです。 詳細については、 [Skype のビジネス サーバー 2015 で ClientVersions テーブル](clientversions.md)を参照してください。 <br/> |
|**RegistrarId** <br/> |int  <br/> |外部  <br/> |登録に使用するレジストラー サーバーの ID です。 詳細については[サーバーのテーブル](servers.md)を参照してください。 <br/> |
|**PoolId** <br/> |int  <br/> |外部  <br/> |セッションのキャプチャに使用されたプールの ID です。 詳細については、[プール ・ テーブル](pools.md)を参照してください。 <br/> |
|**EdgeServerId** <br/> |int  <br/> |外部  <br/> |エッジ サーバーの登録を通過します。 詳細については、 [Skype のビジネス サーバー 2015 で EdgeServers テーブル](edgeservers.md)を参照してください。 <br/> |
|**IsInternal** <br/> |ビット  <br/> ||ユーザーがログオンするか内部からか。  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||かどうか、UserService があるか。  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||かプライマリ レジストラーに登録するかどうか。  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||ユーザーがリカバリ性に優れたブランチ アプライアンスに登録されているかどうかを示します。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RegisterTime** <br/> |datetime  <br/> ||登録時刻です。  <br/> |
|**DeRegisterTime** <br/> |datetime  <br/> ||除外登録時刻です。  <br/> |
|**ResponseCode** <br/> |int  <br/> ||登録要求の応答コード。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||Register 要求の ID を診断します。 その診断情報の種類を示します。  <br/> |
|**DeviceId** <br/> |int  <br/> |外部  <br/> |登録要求を取得しているデバイスです。 [ビジネス サーバー 2015 の Skype でデバイス ・ テーブル](devices.md)の詳細についてを参照してください。 <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |外部  <br/> |De-register、'ユーザーが開始'、'登録の期限が切れて'、'クライアントの失敗' などの理由です。 詳細については、 [Skype のビジネス サーバー 2015 で DeRegisterType テーブル](deregistertype.md)を参照してください。 <br/> |
|**IPAddress** <br/> |nvarchar(256)  <br/> ||エンドポイントに登録されているユーザーの IP アドレスです。 IPv4 アドレスまたは IPv6 アドレスを指定できます。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LastModifiedTime** <br/> |日付時刻  <br/> ||監視サービスによって内部で使用します。  <br/> このフィールドは、ビジネス サーバー 2015 の Skype で導入されました。  <br/> |
   

