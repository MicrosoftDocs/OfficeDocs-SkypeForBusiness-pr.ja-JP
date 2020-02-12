---
title: ディメンションのメンバーの取得
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: '概要: ディメンションメンバーの取得操作について説明します。 ディメンションメンバーの取得操作は、通話品質ダッシュボードのデータ API の一部です。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 40e5ac8b95c24c3a8cb759da99f7d7aeaa391576
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888816"
---
# <a name="get-dimension-members"></a><span data-ttu-id="362ca-105">ディメンションのメンバーの取得</span><span class="sxs-lookup"><span data-stu-id="362ca-105">Get Dimension Members</span></span>
 
<span data-ttu-id="362ca-106">**概要:** ディメンションメンバーの取得操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="362ca-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="362ca-107">ディメンションメンバーの取得操作は、通話品質ダッシュボードのデータ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="362ca-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="362ca-108">通話品質ダッシュボードは、Skype for Business Server のツールです。</span><span class="sxs-lookup"><span data-stu-id="362ca-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="362ca-109">ディメンションメンバーの取得操作は、通話品質ダッシュボードのデータ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="362ca-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="362ca-110">ディメンションのメンバーの取得</span><span class="sxs-lookup"><span data-stu-id="362ca-110">Get Dimension Members</span></span>

<span data-ttu-id="362ca-111">ディメンションメンバーの取得操作特定のディメンションのメンバーの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="362ca-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="362ca-112">また、メンバーリストをフィルター処理して、送金料金を削減することができます。</span><span class="sxs-lookup"><span data-stu-id="362ca-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="362ca-113">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="362ca-113">**Method**</span></span>|<span data-ttu-id="362ca-114">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="362ca-114">**Request URI**</span></span>|<span data-ttu-id="362ca-115">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="362ca-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="362ca-116">投稿</span><span class="sxs-lookup"><span data-stu-id="362ca-116">POST</span></span>  <br/> |<span data-ttu-id="362ca-117">https://\<ポータル\>の/QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="362ca-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="362ca-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="362ca-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="362ca-119">**URI パラメーター** -なし。</span><span class="sxs-lookup"><span data-stu-id="362ca-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="362ca-120">**ヘッダーを要求**する-追加のヘッダーは不要です。</span><span class="sxs-lookup"><span data-stu-id="362ca-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="362ca-121">**要求本文**-メンバーが必要とするディメンションの名前が含まれます。</span><span class="sxs-lookup"><span data-stu-id="362ca-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="362ca-122">返されるメンバーの最大数として、その横にあるフィルターを指定して、返されるメンバーを制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="362ca-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
```json
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 <span data-ttu-id="362ca-123">**応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="362ca-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="362ca-124">**状態コード**-正常に動作している操作は、状態コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="362ca-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="362ca-125">**応答ヘッダー** -ヘッダーは追加されません。</span><span class="sxs-lookup"><span data-stu-id="362ca-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="362ca-126">**応答本文**-以下は、"[開始日] の要求に応じて、JSON のサンプル応答のペイロードを示しています。[Month] "ディメンション。</span><span class="sxs-lookup"><span data-stu-id="362ca-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="362ca-127">リストは、リストのごく一部のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="362ca-127">The list is only showing a small portion of the list.</span></span> 
  
```json
{
"MembersCount": 493,
"Members": [["[1990-01-01T00:00:00]",
"January 1990"],
["[1990-02-01T00:00:00]",
"February 1990"],
["[1990-03-01T00:00:00]",
"March 1990"],
 
    ...
    
["[2030-10-01T00:00:00]",
"October 2030"],
["[2030-11-01T00:00:00]",
"November 2030"],
["[2030-12-01T00:00:00]",
"December 2030"],
["[2031-01-01T00:00:00]",
"January 2031"]]
}
```
