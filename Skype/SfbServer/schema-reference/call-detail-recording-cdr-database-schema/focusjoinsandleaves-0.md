---
title: FocusJoinsAndLeaves ビュー
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: FocusJoinsAndLeaves ビューでは、結合に関する情報が格納され、1 つの会議の情報のままにします。 各会議は、レコードを結合し、会議を離れるたびにユーザーを作成して、このビューで表されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 4fa6a2ec043c5f9746a14d5214be9ad531159cd7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213677"
---
# <a name="focusjoinsandleaves-view"></a>FocusJoinsAndLeaves ビュー
 
FocusJoinsAndLeaves ビューでは、結合に関する情報が格納され、1 つの会議の情報のままにします。 各会議は、レコードを結合し、会議を離れるたびにユーザーを作成して、このビューで表されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会議インスタンスの時間です。 会議のインスタンスを一意に識別するのには SessionIdSeq と組み合わせてを使用します。 [ビジネス サーバー 2015 の Skype での会議のテーブル](conferences.md)の詳細についてを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |会議のインスタンスを識別する ID 番号。 会議のインスタンスを一意に識別するのには SessionIdTime と組み合わせてを使用します。 [ビジネス サーバー 2015 の Skype での会議のテーブル](conferences.md)の詳細についてを参照してください。 <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |会議の参加/脱退情報がキャプチャされ、ユーザーの URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |会議の参加/脱退情報がキャプチャされ、ユーザーの URI の種類です。 詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。 <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |テナントのユーザーが会議の参加/脱退の情報をキャプチャしました。 詳細については[テナントのテーブル](tenants.md)を参照してください。 <br/> |
|**UserEndpointId** <br/> |一意識別子  <br/> |会議の参加/脱退情報がキャプチャされ、ユーザーの一意の識別子です。  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |会議の参加/脱退情報がキャプチャされ、ユーザーによって使用されるクライアントのバージョンです。  <br/> |
|**UserClientType** <br/> |int  <br/> |会議の参加/脱退情報がキャプチャされ、ユーザーによって使用されるクライアントです。 詳細については、 [UserAgentDef テーブル](useragentdef.md)を参照してください。 <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |会議の参加/脱退情報がキャプチャされ、ユーザーによって使用されるクライアントのカテゴリの名前です。  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |bit  <br/> |かどうか、ユーザーが内部ユーザーを表すビット。  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |セッションの要求の時間です。 セッションを一意に識別するのには SessionIdSeq と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |同時複数のコンピューターまたはデバイスにユーザーがログオン、ユーザーとデバイスの組み合わせを一意に識別するのには UserInstance が使用されます。  <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |SIP ダイアログのセッションの ID。 形式: ダイアログ; タグからタグにします。  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |ユーザーが会議に参加している時間です。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |ユーザーが会議から退席する時間です。  <br/> |
|**UserRole** <br/> |nvarchar(256)  <br/> |など、発表者または出席者の会議内で、ユーザーのロールです。  <br/> |
   

