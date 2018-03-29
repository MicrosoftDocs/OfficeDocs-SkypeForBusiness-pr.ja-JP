---
title: SIPResponseMetaData テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable には、SIP 応答コードの分類とそのコードのそれぞれの定義の一覧が含まれています。 これらのコードは SIP デバイスに影響するイベントへの応答として生成され、SIP 通信セッションです。などの SIP デバイスが、要求を行ったが、その要求を尊重する、サーバーが拒否した場合に、403 応答コードが生成されます。
ms.openlocfilehash: a90a248837dd705746fe3b342874aad10480e8a6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="sipresponsemetadata-table"></a>SIPResponseMetaData テーブル
 
SIPResponseMetaDataTable には、SIP 応答コードの分類とそのコードのそれぞれの定義の一覧が含まれています。 これらのコードは SIP デバイスに影響するイベントへの応答として生成され、SIP 通信セッションです。などの SIP デバイスが、要求を行ったが、その要求を尊重する、サーバーが拒否した場合に、403 応答コードが生成されます。
  
次の表は、ビジネス サーバー 2015 の Skype で導入されました。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |Primary  <br/> |SIP 応答コードを表す数値を指定します。  <br/> |
|**クラス** <br/> |int  <br/> || 応答コードの一般的な分類です。 分類は次のとおりです。 <br/>  1-情報の応答 <br/>  2-正常に応答 <br/>  3-リダイレクト応答 <br/>  4-クライアントのエラーへの応答 <br/>  5 - サーバー エラー応答 <br/>  6-グローバル エラーの応答 <br/> |
|**説明** <br/> |nvarchar(256)  <br/> ||SIP 応答コードの説明です。 たとえば、181 の応答コードには、次の説明があります。  <br/> 呼び出しが転送されます。  <br/> |
   

