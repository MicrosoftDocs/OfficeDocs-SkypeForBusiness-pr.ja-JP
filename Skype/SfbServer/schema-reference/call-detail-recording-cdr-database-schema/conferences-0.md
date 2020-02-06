---
title: 会議ビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: 会議ビューには、会議に関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 9f9448769256bfb05e6552a41c2521defa65ded0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815365"
---
# <a name="conferences-view"></a>会議ビュー
 
会議ビューには、会議に関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**セッション Id** <br/> |datetime  <br/> |セッション要求の時刻。 セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> |会議の URI。  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |会議 URI の種類。 詳細については、 [UriTypes の表](uritypes.md)を参照してください。 <br/> |
|**ConfInstance** <br/> |長さ  <br/> |定期的な会議に使用されます。 定期的な会議の各インスタンスには、同じ ConferenceUri がありますが、ConfInstance は異なります。  <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> |会議の開始時刻。  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> |会議の終了時刻。  <br/> |
|**オーガナイザーの Uri** <br/> |nvarchar (450)  <br/> |会議を開催したユーザーの URI。  <br/> |
|**オーガナイザーの種類** <br/> |nvarchar(256)  <br/> |会議を開催したユーザーの URI の種類です。 詳細については、 [UriTypes の表](uritypes.md)を参照してください。 <br/> |
|**組織のテナント** <br/> |nvarchar(256)  <br/> |会議を開催したユーザーのテナント。 詳細については、「テナント」の[表](tenants.md)を参照してください。 <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |会議をホストしているプールの完全修飾ドメイン名。  <br/> |
|**フラッグ** <br/> |smallint  <br/> |会議の属性が含まれているビットマスク。 値の例は次のとおりです。  <br/> 0X01-代理トランザクション  <br/> |
   

