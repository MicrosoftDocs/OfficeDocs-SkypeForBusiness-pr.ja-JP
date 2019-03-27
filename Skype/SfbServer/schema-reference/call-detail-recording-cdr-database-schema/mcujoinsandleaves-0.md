---
title: McuJoinsAndLeaves ビュー
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: McuJoinsAndLeaves ビューでは、ユーザーの結合に関する情報が格納され、1 つの会議サーバーの情報のままにします。 このビュー内の各レコードには、呼び出しの詳細については、ユーザーまたは結合と会議サーバーの 1 つの組み合わせが含まれています。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: db759e324689cfbad92389f30c8fd632c24ebd5e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892809"
---
# <a name="mcujoinsandleaves-view"></a>McuJoinsAndLeaves ビュー
 
McuJoinsAndLeaves ビューでは、ユーザーの結合に関する情報が格納され、1 つの会議サーバーの情報のままにします。 このビュー内の各レコードには、呼び出しの詳細については、ユーザーまたは結合と会議サーバーの 1 つの組み合わせが含まれています。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会議インスタンスの時間です。 会議のインスタンスを一意に識別するのには SessionIdSeq と組み合わせてを使用します。 [ビジネス サーバー 2015 の Skype での会議のテーブル](conferences.md)の詳細についてを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |会議のインスタンスを識別する ID 番号。 会議のインスタンスを一意に識別するのには SessionIdTime と組み合わせてを使用します。 [ビジネス サーバー 2015 の Skype での会議のテーブル](conferences.md)の詳細についてを参照してください。 <br/> |
|**McuUri** <br/> |nvarchar(256)  <br/> |ユーザーが接続されている会議サーバーの URI。  <br/> |
|**McuUriType** <br/> |nvarchar(256)  <br/> |ユーザーが接続されている会議サーバーの URI。 詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。 <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |会議サーバーの参加/脱退情報がキャプチャされ、ユーザーの URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |会議サーバーの参加/脱退情報がキャプチャされ、ユーザーの URI の種類。 詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。 <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |テナントのユーザーが会議サーバーの参加/脱退の情報をキャプチャしました。 詳細については[テナントのテーブル](tenants.md)を参照してください。 <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |会議サーバーの参加/脱退情報がキャプチャされ、ユーザーによって使用されるクライアントのバージョンです。  <br/> |
|**UserClientType** <br/> |int  <br/> |会議サーバーの参加/脱退情報がキャプチャされ、ユーザーによって使用されるクライアントです。 詳細については、 [UserAgentDef テーブル](useragentdef.md)を参照してください。 <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |会議サーバーの参加/脱退情報がキャプチャされ、ユーザーによって使用されるクライアントのカテゴリの名前。  <br/> |
|**McuUserInstance** <br/> |int  <br/> |同時に複数のデバイスにログオンしたユーザーのユーザーとデバイスの組み合わせを一意に識別します。  <br/> |
|**IsUserFromPstn** <br/> |bit  <br/> |かどうか、ユーザーが内部ユーザーを表すビット。  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |セッションの要求の時間です。 セッションを一意に識別するのには SessionIdSeq と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するのには SessionIdTime と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |SIP ダイアログのセッションの ID。 形式: ダイアログ; タグからタグにします。  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |ユーザーは、会議サーバーを参加している時間です。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |時間のユーザーの会議サーバーのままにします。  <br/> |
   

