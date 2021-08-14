---
title: 2015 年の場所Skype for Business Server表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: それぞれのレコードは、E9-1-1 通話など、緊急通話における 1 つの場所の参照を表します。
ms.openlocfilehash: 887c9c7198272fa2087399c0ccf67e37ae890dc90a322eb17bcff16688808080
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343231"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a>2015 年の場所Skype for Business Server表
 
それぞれのレコードは、E9-1-1 通話など、緊急通話における 1 つの場所の参照を表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |主/プライマリ、外部  <br/> |セッション要求の時刻。 セッションを一意に識別するために **SessionIdSeq** と併用されます。 詳細については[、「ダイアログ」の表Skype for Business Server 2015](dialogs.md)を参照してください。 <br/> |
|**SessionIdSeq** <br/> |整数  <br/> |主/プライマリ、外部  <br/> |セッションを識別するための ID 番号。 セッションを一意に識別するために **SessionIdTime** と併用されます。 詳細については[、「ダイアログ」の表Skype for Business Server 2015](dialogs.md)を参照してください。 <br/> |
|**場所** <br/> |nvarchar(max)  <br/> ||緊急通話の場所。  <br/> |
   

