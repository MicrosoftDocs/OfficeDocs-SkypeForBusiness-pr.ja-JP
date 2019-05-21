---
title: Skype for Business Server 2015 の会議テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: この表の各レコードには、1人の会議に関する通話の詳細が含まれています。
ms.openlocfilehash: 41a2a25e80b073b568152422defeee1ca3e2ac19
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296449"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の会議テーブル
 
この表の各レコードには、1人の会議に関する通話の詳細が含まれています。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**セッション Id** <br/> |datetime  <br/> |Primary  <br/> |会議出席依頼が CDR エージェントによってキャプチャされた時刻。 会議インスタンスを一意に識別するために、主キーとしてのみ使用されます。  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |セッションを識別する ID 番号。 電話会議インスタンスを一意に識別するために**Sessionidtime**と組み合わせて使用されます。 * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |外部  <br/> |会議の URI。 詳細については、「 [Skype For Business Server 2015 の ConferenceUris テーブル](conferenceuris.md)」を参照してください。 <br/> |
|**ConfInstance** <br/> |長さ  <br/> | <br/> |定期的な会議に便利。定期的な会議の各インスタンスには、同じ**ConferenceUri**がありますが、別の**confinstance**があります。 <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> | <br/> |会議の開始時刻。  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> | <br/> |会議の開始時刻。  <br/> |
|**PoolId** <br/> |int  <br/> |外部  <br/> |会議がキャプチャされたプールを識別する ID 番号。 詳細については、「プール」の[表](pools.md)を参照してください。 <br/> |
|**オーガナイザー Erid** <br/> |Int  <br/> |外部  <br/> |この会議の開催者の URI を識別する ID 番号。 詳細については、「ユーザー」の[表](users.md)を参照してください。 <br/> |
|**フラッグ** <br/> |smallint  <br/> || 会議の属性が含まれているビットマスク。 値の例は次のとおりです。 <br/>  0X01 <br/>  Synthetic <br/>  トランザクション <br/> |
|**処理** <br/> |bit  <br/> ||監視サービスで使用される内部フィールド。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||監視サービスで内部的に使用されます。  <br/> このフィールドは、Skype for Business Server 2015 で導入されました。  <br/> |
   
\*ほとんどのセッションでは、SessionIdSeq の値は1になります。 2つのセッションがまったく同じ時刻に開始された場合、1つのセッションの SessionIdSeq は1になり、残りのセッションは2になります。
  

