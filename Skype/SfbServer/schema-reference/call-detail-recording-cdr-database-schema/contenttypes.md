---
title: ビジネス サーバー 2015 の Skype でのコンテンツ タイプのテーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: コンテンツ タイプのテーブルは、ピア ツー ピア セッションや会議セッションの両方で使用するコンテンツ タイプのリストを格納するサポート テーブルです。 テーブル内の各レコードは、1 つのコンテンツ タイプを表します。
ms.openlocfilehash: 77bbe375a5870d11c7e4a17a0f32392fe14975a0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894988"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype でのコンテンツ タイプのテーブル
 
コンテンツ タイプのテーブルは、ピア ツー ピア セッションや会議セッションの両方で使用するコンテンツ タイプのリストを格納するサポート テーブルです。 テーブル内の各レコードは、1 つのコンテンツ タイプを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |int  <br/> |Primary  <br/> |コンテンツの種類を識別する一意の番号です。  <br/> |
|**コンテンツ タイプ** <br/> |nvarchar(256)  <br/> ||コンテンツ タイプの名前です。  <br/> |
   

