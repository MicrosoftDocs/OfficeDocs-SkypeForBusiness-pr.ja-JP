---
title: Skype for Business Server 2015 の ContentTypes テーブル
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
ms.openlocfilehash: 461631c8fc824a23f0e4b22b65a3cbc8cf6a2c73
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816087"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9a0a4-104">Skype for Business Server 2015 の ContentTypes テーブル</span><span class="sxs-lookup"><span data-stu-id="9a0a4-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9a0a4-105">ContentTypes テーブルは、ピアツーピア セッションと会議セッションの両方で使用されるコンテンツ タイプのリストを格納するサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="9a0a4-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="9a0a4-106">テーブル内の各レコードは、1 つのコンテンツ タイプを表します。</span><span class="sxs-lookup"><span data-stu-id="9a0a4-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="9a0a4-107">**列**</span><span class="sxs-lookup"><span data-stu-id="9a0a4-107">**Column**</span></span>|<span data-ttu-id="9a0a4-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9a0a4-108">**Data Type**</span></span>|<span data-ttu-id="9a0a4-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="9a0a4-109">**Key/Index**</span></span>|<span data-ttu-id="9a0a4-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="9a0a4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9a0a4-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="9a0a4-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="9a0a4-112">int</span><span class="sxs-lookup"><span data-stu-id="9a0a4-112">int</span></span>  <br/> |<span data-ttu-id="9a0a4-113">Primary</span><span class="sxs-lookup"><span data-stu-id="9a0a4-113">Primary</span></span>  <br/> |<span data-ttu-id="9a0a4-114">コンテンツ タイプを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="9a0a4-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="9a0a4-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="9a0a4-115">**ContentType**</span></span> <br/> |<span data-ttu-id="9a0a4-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9a0a4-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="9a0a4-117">コンテンツ タイプ名。</span><span class="sxs-lookup"><span data-stu-id="9a0a4-117">Content type name.</span></span>  <br/> |
   

