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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213250"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="07821-104">ビジネス サーバー 2015 の Skype でのコンテンツ タイプのテーブル</span><span class="sxs-lookup"><span data-stu-id="07821-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="07821-105">コンテンツ タイプのテーブルは、ピア ツー ピア セッションや会議セッションの両方で使用するコンテンツ タイプのリストを格納するサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="07821-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="07821-106">テーブル内の各レコードは、1 つのコンテンツ タイプを表します。</span><span class="sxs-lookup"><span data-stu-id="07821-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="07821-107">**列**</span><span class="sxs-lookup"><span data-stu-id="07821-107">**Column**</span></span>|<span data-ttu-id="07821-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="07821-108">**Data Type**</span></span>|<span data-ttu-id="07821-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="07821-109">**Key/Index**</span></span>|<span data-ttu-id="07821-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="07821-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="07821-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="07821-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="07821-112">int</span><span class="sxs-lookup"><span data-stu-id="07821-112">int</span></span>  <br/> |<span data-ttu-id="07821-113">Primary</span><span class="sxs-lookup"><span data-stu-id="07821-113">Primary</span></span>  <br/> |<span data-ttu-id="07821-114">コンテンツの種類を識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="07821-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="07821-115">**コンテンツ タイプ**</span><span class="sxs-lookup"><span data-stu-id="07821-115">**ContentType**</span></span> <br/> |<span data-ttu-id="07821-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="07821-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="07821-117">コンテンツ タイプの名前です。</span><span class="sxs-lookup"><span data-stu-id="07821-117">Content type name.</span></span>  <br/> |
   

