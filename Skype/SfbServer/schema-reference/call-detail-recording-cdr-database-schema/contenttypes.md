---
title: ContentTypes テーブル (2015 Skype for Business Server)
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
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: ContentTypes テーブルは、ピアツーピア セッションと会議セッションの両方で使用されるコンテンツ タイプのリストを格納するサポート テーブルです。 テーブル内の各レコードは、1 つのコンテンツ タイプを表します。
ms.openlocfilehash: 6f15fe8bc5f4da7e12fa3b36de6b613fc1783b3d21e5903e2840f3cd22f5e139
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336422"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>ContentTypes テーブル (2015 Skype for Business Server)
 
ContentTypes テーブルは、ピアツーピア セッションと会議セッションの両方で使用されるコンテンツ タイプのリストを格納するサポート テーブルです。 テーブル内の各レコードは、1 つのコンテンツ タイプを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |整数  <br/> |Primary  <br/> |コンテンツ タイプを識別する一意の番号。  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> ||コンテンツ タイプ名。  <br/> |
   

