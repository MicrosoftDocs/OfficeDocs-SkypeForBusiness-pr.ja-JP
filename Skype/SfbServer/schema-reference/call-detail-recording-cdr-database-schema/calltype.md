---
title: ビジネス サーバー 2015 の Skype の CallType テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType の表は、可能な呼び出しの種類の一覧を格納する静的なテーブルです。
ms.openlocfilehash: 29e5ed85de5917092ad00cd0e1aa60fec1a31b22
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213362"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype の CallType テーブル
 
CallType の表は、可能な呼び出しの種類の一覧を格納する静的なテーブルです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || 使用可能な値: <br/>  0 - 不明 <br/>  1-インスタント メッセージング <br/>  2 - アプリケーションの共有 <br/>  3-オーディオ <br/>  4-オーディオとビデオ <br/>  5-ファイル転送 <br/> |
   

