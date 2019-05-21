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
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="2cfc7-104">Skype for Business Server 2015 の ContentTypes テーブル</span><span class="sxs-lookup"><span data-stu-id="2cfc7-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2cfc7-105">ContentTypes テーブルは、ピアツーピアセッションと会議セッションの両方で使用されるコンテンツタイプのリストを格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="2cfc7-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="2cfc7-106">テーブル内の各レコードは、1つのコンテンツタイプを表します。</span><span class="sxs-lookup"><span data-stu-id="2cfc7-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="2cfc7-107">**列**</span><span class="sxs-lookup"><span data-stu-id="2cfc7-107">**Column**</span></span>|<span data-ttu-id="2cfc7-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="2cfc7-108">**Data Type**</span></span>|<span data-ttu-id="2cfc7-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="2cfc7-109">**Key/Index**</span></span>|<span data-ttu-id="2cfc7-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="2cfc7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2cfc7-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="2cfc7-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="2cfc7-112">int</span><span class="sxs-lookup"><span data-stu-id="2cfc7-112">int</span></span>  <br/> |<span data-ttu-id="2cfc7-113">Primary</span><span class="sxs-lookup"><span data-stu-id="2cfc7-113">Primary</span></span>  <br/> |<span data-ttu-id="2cfc7-114">コンテンツの種類を識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="2cfc7-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="2cfc7-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="2cfc7-115">**ContentType**</span></span> <br/> |<span data-ttu-id="2cfc7-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2cfc7-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="2cfc7-117">コンテンツタイプの名前。</span><span class="sxs-lookup"><span data-stu-id="2cfc7-117">Content type name.</span></span>  <br/> |
   

