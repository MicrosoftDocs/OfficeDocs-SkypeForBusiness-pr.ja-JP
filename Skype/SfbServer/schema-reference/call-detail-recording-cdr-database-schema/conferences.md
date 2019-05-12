---
title: ビジネス サーバー 2015 の Skype での会議テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: このテーブルの各レコードには、呼び出しの詳細については、1 つの会議が含まれています。
ms.openlocfilehash: 3d8382316d17dfc13cd0d9cd2e98e79b3461951c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901367"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype での会議テーブル
 
このテーブルの各レコードには、呼び出しの詳細については、1 つの会議が含まれています。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |会議の依頼は、CDR エージェントによってキャプチャされた時間です。 会議のインスタンスを一意に識別する主キーとしてのみ使用されます。  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |セッションを識別する ID 番号。 会議のインスタンスを一意に識別するのには**SessionIdTime**と組み合わせてを使用します。 * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |外部  <br/> |会議 URI です。 詳細については、 [Skype のビジネス サーバー 2015 で ConferenceUris テーブル](conferenceuris.md)を参照してください。 <br/> |
|**ConfInstance** <br/> |一意識別子  <br/> | <br/> |定期的な会議の場合に便利です。定期的な会議の各インスタンスは、同じ**ConferenceUri**が別の**ConfInstance**。 <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> | <br/> |会議の開始時刻。  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> | <br/> |会議の開始時刻。  <br/> |
|**PoolId** <br/> |int  <br/> |外部  <br/> |会議のキャプチャに使用されたプールを識別する ID 番号。 詳細については、[プール ・ テーブル](pools.md)を参照してください。 <br/> |
|**OrganizerId** <br/> |Int  <br/> |外部  <br/> |URI はこの会議の開催者を識別する ID 番号。 詳細については[「ユーザー」テーブル](users.md)を参照してください。 <br/> |
|**フラグ** <br/> |smallint  <br/> || 会議属性を含むビット マスクです。 値の例は次のとおりです。 <br/>  0X01 <br/>  合成 <br/>  トランザクション <br/> |
|**処理** <br/> |bit  <br/> ||監視サービスによって使用される内部のフィールドです。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LastModifiedTime** <br/> |日付時刻  <br/> ||監視サービスによって内部で使用します。  <br/> このフィールドは、ビジネス サーバー 2015 の Skype で導入されました。  <br/> |
   
\*ほとんどのセッションでは、SessionIdSeq は 1 の値があります。 1、1 つの同時に、正確であり、SessionIdSeq、2 つのセッションが開始し、他の 2 とするための。
  

