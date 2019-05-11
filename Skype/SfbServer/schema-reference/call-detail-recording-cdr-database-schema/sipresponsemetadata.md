---
title: SIPResponseMetaData テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable には、SIP 応答コードの分類とそのコードのそれぞれの定義の一覧が含まれています。 これらのコードは SIP デバイスに影響するイベントへの応答として生成され、SIP 通信セッションです。などの SIP デバイスが、要求を行ったが、その要求を尊重する、サーバーが拒否した場合に、403 応答コードが生成されます。
ms.openlocfilehash: edd1f4e60376b367f701864ff15d334c4d971e47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930288"
---
# <a name="sipresponsemetadata-table"></a>SIPResponseMetaData テーブル
 
SIPResponseMetaDataTable には、SIP 応答コードの分類とそのコードのそれぞれの定義の一覧が含まれています。 これらのコードは SIP デバイスに影響するイベントへの応答として生成され、SIP 通信セッションです。などの SIP デバイスが、要求を行ったが、その要求を尊重する、サーバーが拒否した場合に、403 応答コードが生成されます。
  
次の表は、ビジネス サーバー 2015 の Skype で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |Primary  <br/> |SIP 応答コードを表す数値を指定します。  <br/> |
|**クラス** <br/> |int  <br/> || 応答コードの一般的な分類です。 分類は次のとおりです。 <br/>  1-情報の応答 <br/>  2-正常に応答 <br/>  3-リダイレクト応答 <br/>  4-クライアントのエラーへの応答 <br/>  5 - サーバー エラー応答 <br/>  6-グローバル エラーの応答 <br/> |
|**説明** <br/> |nvarchar(256)  <br/> ||SIP 応答コードの説明です。 たとえば、181 の応答コードには、次の説明があります。  <br/> 呼び出しが転送されます。  <br/> |
   

