---
title: SIPResponseMetaData テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable には、SIP 応答コードの一覧と、各コードの分類と定義が含まれています。 これらのコードは、SIP デバイスと SIP コミュニケーションセッションに影響を与えるイベントに対応して生成されます。たとえば、応答コード403は、SIP デバイスが要求を行ったときに、サーバーがその要求を受け入れることを拒否したときに生成されます。
ms.openlocfilehash: eecd8397315b93ebce9e5fad973f1274a6eb763a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295791"
---
# <a name="sipresponsemetadata-table"></a>SIPResponseMetaData テーブル
 
SIPResponseMetaDataTable には、SIP 応答コードの一覧と、各コードの分類と定義が含まれています。 これらのコードは、SIP デバイスと SIP コミュニケーションセッションに影響を与えるイベントに対応して生成されます。たとえば、応答コード403は、SIP デバイスが要求を行ったときに、サーバーがその要求を受け入れることを拒否したときに生成されます。
  
この表は、Skype for Business Server 2015 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**返信** <br/> |int  <br/> |Primary  <br/> |SIP 応答コードを表す数値。  <br/> |
|**クラス** <br/> |int  <br/> || 応答コードの一般的な分類。 分類には以下が含まれます。 <br/>  1-情報の返信 <br/>  2-成功応答 <br/>  3-リダイレクション応答 <br/>  4-クライアントの失敗応答 <br/>  5--サーバー障害への応答 <br/>  6-グローバルなエラー応答 <br/> |
|**説明** <br/> |nvarchar(256)  <br/> ||SIP 応答コードの説明。 たとえば、応答コード181には次の説明があります。  <br/> 通話が転送されています  <br/> |
   

