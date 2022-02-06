---
title: 2015 年の場所Skype for Business Server表
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: それぞれのレコードは、E9-1-1 通話など、緊急通話における 1 つの場所の参照を表します。
---

# <a name="locations-table-in-skype-for-business-server-2015"></a>2015 年の場所Skype for Business Server表
 
それぞれのレコードは、E9-1-1 通話など、緊急通話における 1 つの場所の参照を表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |主/プライマリ、外部  <br/> |セッション要求の時刻。 セッションを一意に識別するために **SessionIdSeq** と併用されます。 詳細については[、2015 Skype for Business Serverの](dialogs.md) Dialogs テーブルを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主/プライマリ、外部  <br/> |セッションを識別するための ID 番号。 セッションを一意に識別するために **SessionIdTime** と併用されます。 詳細については[、2015 Skype for Business Serverの](dialogs.md) Dialogs テーブルを参照してください。 <br/> |
|**Location** <br/> |nvarchar(max)  <br/> ||緊急通話の場所。  <br/> |
   

