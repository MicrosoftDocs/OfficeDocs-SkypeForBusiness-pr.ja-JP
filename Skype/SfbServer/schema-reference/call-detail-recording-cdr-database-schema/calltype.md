---
title: ビジネス サーバー 2015 の Skype の CallType テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType の表は、可能な呼び出しの種類の一覧を格納する静的なテーブルです。
ms.openlocfilehash: a75ae3e22d435241e6bf2eb81b8268a7f1bb5a40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924795"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype の CallType テーブル
 
CallType の表は、可能な呼び出しの種類の一覧を格納する静的なテーブルです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || 使用可能な値: <br/>  0 - 不明 <br/>  1-インスタント メッセージング <br/>  2 - アプリケーションの共有 <br/>  3-オーディオ <br/>  4-オーディオとビデオ <br/>  5-ファイル転送 <br/> |
   

