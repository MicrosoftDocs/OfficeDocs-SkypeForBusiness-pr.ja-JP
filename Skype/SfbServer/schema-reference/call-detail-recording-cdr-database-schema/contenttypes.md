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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: ContentTypes テーブルは、ピアツーピアセッションと会議セッションの両方で使用されるコンテンツタイプのリストを格納するサポートテーブルです。 テーブル内の各レコードは、1つのコンテンツタイプを表します。
ms.openlocfilehash: 6dadf7de0107005cca751e27f0c0250bc8f9f03a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815305"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="25400-104">Skype for Business Server 2015 の ContentTypes テーブル</span><span class="sxs-lookup"><span data-stu-id="25400-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="25400-105">ContentTypes テーブルは、ピアツーピアセッションと会議セッションの両方で使用されるコンテンツタイプのリストを格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="25400-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="25400-106">テーブル内の各レコードは、1つのコンテンツタイプを表します。</span><span class="sxs-lookup"><span data-stu-id="25400-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="25400-107">**列**</span><span class="sxs-lookup"><span data-stu-id="25400-107">**Column**</span></span>|<span data-ttu-id="25400-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="25400-108">**Data Type**</span></span>|<span data-ttu-id="25400-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="25400-109">**Key/Index**</span></span>|<span data-ttu-id="25400-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="25400-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="25400-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="25400-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="25400-112">int</span><span class="sxs-lookup"><span data-stu-id="25400-112">int</span></span>  <br/> |<span data-ttu-id="25400-113">Primary</span><span class="sxs-lookup"><span data-stu-id="25400-113">Primary</span></span>  <br/> |<span data-ttu-id="25400-114">コンテンツの種類を識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="25400-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="25400-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="25400-115">**ContentType**</span></span> <br/> |<span data-ttu-id="25400-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="25400-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="25400-117">コンテンツタイプの名前。</span><span class="sxs-lookup"><span data-stu-id="25400-117">Content type name.</span></span>  <br/> |
   

