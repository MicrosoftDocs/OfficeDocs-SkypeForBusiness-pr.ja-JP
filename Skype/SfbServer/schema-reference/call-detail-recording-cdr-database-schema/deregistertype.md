---
title: ビジネス サーバー 2015 の Skype での DeRegisterType テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType テーブルは、可能性のあるユーザーの一覧を格納する静的なテーブルが 'クライアントの開始'、'登録の期限が切れて' 'クライアントが応答を停止して' などの種類を登録解除
ms.openlocfilehash: 958de5dd537f391ca75936ad86a84cb6fed0778d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901174"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype での DeRegisterType テーブル
 
DeRegisterType テーブルは、可能性のあるユーザーの一覧を格納する静的なテーブルが 'クライアントの開始'、'登録の期限が切れて' 'クライアントが応答を停止して' などの種類を登録解除
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || 使用可能な値: <br/>  0 - 不明 <br/>  1--クライアント開始の登録解除します。 <br/>  2-登録の有効期限が切れてください。 <br/>  3-クライアントがクラッシュしました。 <br/>  4--ユーザー属性の変更 <br/>  5-優先レジストラーの変更 <br/>  サバイバル モードでの 6 - レガシ クライアント <br/> |
   

