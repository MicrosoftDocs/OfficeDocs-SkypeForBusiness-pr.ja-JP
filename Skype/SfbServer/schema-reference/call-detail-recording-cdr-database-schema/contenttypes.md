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
ms.localizationpriority: medium
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: ContentTypes テーブルは、ピアツーピア セッションと会議セッションの両方で使用されるコンテンツ タイプのリストを格納するサポート テーブルです。 テーブル内の各レコードは、1 つのコンテンツ タイプを表します。
ms.openlocfilehash: 04c28a39d95ac9c2252f6c2f400649d3d74ef654
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627789"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>ContentTypes テーブル (2015 Skype for Business Server)
 
ContentTypes テーブルは、ピアツーピア セッションと会議セッションの両方で使用されるコンテンツ タイプのリストを格納するサポート テーブルです。 テーブル内の各レコードは、1 つのコンテンツ タイプを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |int  <br/> |Primary  <br/> |コンテンツ タイプを識別する一意の番号。  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> ||コンテンツ タイプ名。  <br/> |
   

