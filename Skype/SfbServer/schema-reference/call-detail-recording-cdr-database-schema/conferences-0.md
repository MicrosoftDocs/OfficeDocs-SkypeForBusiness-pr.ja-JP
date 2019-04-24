---
title: 会議を表示します。
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: 会議のビューでは、会議に関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 42bdbed9cceb8d50e2de8ddbe29ba406e4a0a2f5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213271"
---
# <a name="conferences-view"></a>会議を表示します。
 
会議のビューでは、会議に関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |セッションの要求の時間です。 セッションを一意に識別するのには SessionIdSeq と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するのには SessionIdTime と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |会議の URI。  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |会議 URI の種類です。 詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。 <br/> |
|**ConfInstance** <br/> |一意識別子  <br/> |定期的な会議のために使用します。 定期的な会議の各インスタンスは、さまざまな ConfInstance が、同じ ConferenceUri を持っています。  <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> |会議の開始時刻。  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> |会議の時間を終了します。  <br/> |
|**OrganizerUri** <br/> |nvarchar(450)  <br/> |会議を開催したユーザーの URI。  <br/> |
|**OrganizerType** <br/> |nvarchar(256)  <br/> |会議を開催したユーザーの URI の種類です。 詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。 <br/> |
|**OrganizerTenant** <br/> |nvarchar(256)  <br/> |会議を開催したユーザーのテナントです。 詳細については[テナントのテーブル](tenants.md)を参照してください。 <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |会議をホストするプールの完全修飾ドメイン名です。  <br/> |
|**フラグ** <br/> |smallint  <br/> |会議属性を含むビット マスクです。 値の例は次のとおりです。  <br/> 0X01 - 代理トランザクション  <br/> |
   

