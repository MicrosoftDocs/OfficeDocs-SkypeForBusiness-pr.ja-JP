---
title: Skype for Business Server 2015 の CallType テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType テーブルは、可能な呼び出しの種類の一覧を格納する静的テーブルです。
ms.openlocfilehash: 992e5682aedf7a0b9063960992197970146c8cfc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296561"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の CallType テーブル
 
CallType テーブルは、可能な呼び出しの種類の一覧を格納する静的テーブルです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**発信者の Typeid** <br/> |int  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || 許可される値: <br/>  0--不明 <br/>  1-インスタントメッセージ (im) <br/>  2--アプリケーション共有 <br/>  3--オーディオ <br/>  4-オーディオとビデオ <br/>  5-ファイル送信 <br/> |
   

