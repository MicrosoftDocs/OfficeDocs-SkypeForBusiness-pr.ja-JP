---
title: 2015 年Skype for Business Server会議の表
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: この表の各レコードには、1 つの会議に関する通話の詳細が含まれている。
ms.openlocfilehash: cbcda30c47b4bbeac012f80d64f297a9a1259f2c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60838449"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>2015 年Skype for Business Server会議の表
 
この表の各レコードには、1 つの会議に関する通話の詳細が含まれている。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |Primary  <br/> |会議要求が CDR エージェントによってキャプチャされた時間。 会議インスタンスを一意に識別する主キーとしてのみ使用されます。  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |セッションを識別するための ID 番号。 **SessionIdTime と組み合わせて使用して**、会議インスタンスを一意に識別します。 * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |外部  <br/> |会議 URI。 詳細については[、2015 Skype for Business Serverの ConferenceUris](conferenceuris.md)テーブルを参照してください。 <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> | <br/> |定期的な会議に役立ちます。定期的な会議の各インスタンスは同じ **ConferenceUri** を持っていますが **、ConfInstance は異なります**。 <br/> |
|**ConferenceStartTime** <br/> |日付型  <br/> | <br/> |会議の開始時刻。  <br/> |
|**ConferenceEndTime** <br/> |日付型  <br/> | <br/> |会議の開始時刻。  <br/> |
|**PoolId** <br/> |int  <br/> |外部  <br/> |会議がキャプチャされたプールを識別する ID 番号。 詳細については [、「Pools」の表](pools.md) を参照してください。 <br/> |
|**OrganizerId** <br/> |Int  <br/> |外部  <br/> |この会議の開催者 URI を識別する ID 番号。 詳細については [、「Users」テーブル](users.md) を参照してください。 <br/> |
|**Flag** <br/> |smallint  <br/> || 会議属性を含むビット マスク。 使用可能な値は次のとおりです。 <br/>  0X01 <br/>  合成 <br/>  トランザクション <br/> |
|**処理** <br/> |ビット  <br/> ||監視サービスで使用される内部フィールド。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||監視サービスの内部用テーブル。  <br/> このフィールドは、2015 年Skype for Business Serverされました。  <br/> |
   
\* ほとんどのセッションでは、SessionIdSeq の値は 1 になります。 2 つのセッションがまったく同じ時刻に開始される場合、1 つの SessionIdSeq は 1、もう 1 つは 2 になります。
  

