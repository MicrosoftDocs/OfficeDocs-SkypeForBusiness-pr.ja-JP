---
title: SIPResponseMetaData テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable には、SIP 応答コードと、各コードの分類と定義の一覧が含まれます。これらのコードは SIP デバイスおよび SIP 通信セッションに影響を与えるイベントへの応答して生成されます。たとえば、応答コード 403 は、SIP デバイスが要求を行い、サーバーがその要求の実行を拒否したときに生成されます。
ms.openlocfilehash: 6e4c891aefb41b88fdaae1e9d80a25f878042d14e06c94fe510414f6a24ac1a0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284497"
---
# <a name="sipresponsemetadata-table"></a>SIPResponseMetaData テーブル
 
SIPResponseMetaDataTable には、SIP 応答コードと、各コードの分類と定義の一覧が含まれます。これらのコードは SIP デバイスおよび SIP 通信セッションに影響を与えるイベントへの応答して生成されます。たとえば、応答コード 403 は、SIP デバイスが要求を行い、サーバーがその要求の実行を拒否したときに生成されます。
  
この表は、2015 年Skype for Business Serverされました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |整数  <br/> |Primary  <br/> |SIP 応答コードを表す数値。  <br/> |
|**クラス** <br/> |整数  <br/> || 応答コードの一般的な分類。以下の分類があります。 <br/>  1 - 情報応答 <br/>  2 - 成功した応答 <br/>  3 - リダイレクト応答 <br/>  4 - クライアント障害の応答 <br/>  5 -- サーバー障害の応答 <br/>  6 - グローバルエラー応答 <br/> |
|**Description** <br/> |nvarchar(256)  <br/> ||SIP 応答コードの説明。たとえば、コード 181 には以下の説明があります。  <br/> Call Is Being Forwarded (呼び出しを転送中)  <br/> |
   

