---
title: Skype for Business Server 2015 の ContentTypes テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: ContentTypes テーブルは、ピアツーピアセッションと会議セッションの両方で使用されるコンテンツタイプのリストを格納するサポートテーブルです。 テーブル内の各レコードは、1つのコンテンツタイプを表します。
ms.openlocfilehash: b8422cbe95425ac79495c0506f4a94e70be3f9af
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296372"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の ContentTypes テーブル
 
ContentTypes テーブルは、ピアツーピアセッションと会議セッションの両方で使用されるコンテンツタイプのリストを格納するサポートテーブルです。 テーブル内の各レコードは、1つのコンテンツタイプを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |int  <br/> |Primary  <br/> |コンテンツの種類を識別する一意の番号。  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> ||コンテンツタイプの名前。  <br/> |
   

