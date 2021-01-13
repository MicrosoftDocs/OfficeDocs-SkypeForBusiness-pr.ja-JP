---
title: Skype for Business Server 2015 の電話会議テーブル
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
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: この表の各レコードには、1 つの電話会議に関する通話の詳細が含まれている。
ms.openlocfilehash: 85da16807d6f314fb4f9239601c77a7aed2842ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813217"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の電話会議テーブル
 
この表の各レコードには、1 つの電話会議に関する通話の詳細が含まれている。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |Primary  <br/> |CDR エージェントが電話会議出席依頼をキャプチャした時刻。 会議インスタンスを一意に識別するための主キーとしてのみ使用されます。  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |セッションを識別するための ID 番号。 **SessionIdTime と組み合わせて使用し**、会議インスタンスを一意に識別します。 * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |外部  <br/> |会議 URI。 詳細については [、Skype for Business Server 2015 の ConferenceUris テーブル](conferenceuris.md) を参照してください。 <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> | <br/> |定期的な電話会議に役立ちます。定期的な電話会議の各インスタンスは同じ **ConferenceUri** を持っていますが **、ConfInstance は異なります**。 <br/> |
|**ConferenceStartTime** <br/> |日付型  <br/> | <br/> |電話会議の開始時刻。  <br/> |
|**ConferenceEndTime** <br/> |日付型  <br/> | <br/> |電話会議の開始時刻。  <br/> |
|**PoolId** <br/> |int  <br/> |外部  <br/> |会議がキャプチャされたプールを識別する ID 番号。 詳細については [、Pools の表](pools.md) を参照してください。 <br/> |
|**OrganizerId** <br/> |Int  <br/> |外部  <br/> |この会議の開催者 URI を識別する ID 番号。 詳細については [、Users の表](users.md) を参照してください。 <br/> |
|**Flag** <br/> |smallint  <br/> || 電話会議の属性を含むビット マスク。 使用可能な値は次のいずれかです。 <br/>  0X01 <br/>  代理 <br/>  トランザクション <br/> |
|**処理** <br/> |bit  <br/> ||監視サービスによって使用される内部フィールド。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||監視サービスの内部用テーブル。  <br/> このフィールドは、Skype for Business Server 2015 で導入されました。  <br/> |
   
\* ほとんどのセッションでは、SessionIdSeq の値は 1 になります。 2 つのセッションがまったく同時に開始する場合、1 つの SessionIdSeq は 1、もう 1 つのセッションは 2 になります。
  

