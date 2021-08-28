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
ms.localizationpriority: medium
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable には、SIP 応答コードと、各コードの分類と定義の一覧が含まれます。これらのコードは SIP デバイスおよび SIP 通信セッションに影響を与えるイベントへの応答して生成されます。たとえば、応答コード 403 は、SIP デバイスが要求を行い、サーバーがその要求の実行を拒否したときに生成されます。
ms.openlocfilehash: 9fb5921b2ff0c371dc8771ce8627bdae23f651dc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58630351"
---
# <a name="sipresponsemetadata-table"></a>SIPResponseMetaData テーブル
 
SIPResponseMetaDataTable には、SIP 応答コードと、各コードの分類と定義の一覧が含まれます。これらのコードは SIP デバイスおよび SIP 通信セッションに影響を与えるイベントへの応答して生成されます。たとえば、応答コード 403 は、SIP デバイスが要求を行い、サーバーがその要求の実行を拒否したときに生成されます。
  
この表は、2015 年Skype for Business Serverされました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |Primary  <br/> |SIP 応答コードを表す数値。  <br/> |
|**クラス** <br/> |int  <br/> || 応答コードの一般的な分類。以下の分類があります。 <br/>  1 - 情報応答 <br/>  2 - 成功した応答 <br/>  3 - リダイレクト応答 <br/>  4 - クライアント障害の応答 <br/>  5 -- サーバー障害の応答 <br/>  6 - グローバルエラー応答 <br/> |
|**説明** <br/> |nvarchar(256)  <br/> ||SIP 応答コードの説明。たとえば、コード 181 には以下の説明があります。  <br/> Call Is Being Forwarded (呼び出しを転送中)  <br/> |
   

