---
title: ディメンションのメンバーの取得
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: '概要: は、ディメンション メンバーを取得する操作について説明します。 ディメンション メンバーの取得操作は、品質のダッシュ ボードを呼び出すためのデータ API の一部です。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: 482fe92a95c6754695e983ed9ff0ec69ed7a442b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926094"
---
# <a name="get-dimension-members"></a><span data-ttu-id="96233-105">ディメンションのメンバーの取得</span><span class="sxs-lookup"><span data-stu-id="96233-105">Get Dimension Members</span></span>
 
<span data-ttu-id="96233-106">**の概要:** ディメンション メンバーを取得する操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="96233-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="96233-107">ディメンション メンバーの取得操作は、品質のダッシュ ボードを呼び出すためのデータ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="96233-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="96233-108">通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。</span><span class="sxs-lookup"><span data-stu-id="96233-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="96233-109">ディメンション メンバーの取得操作は、品質のダッシュ ボードを呼び出すためのデータ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="96233-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="96233-110">ディメンションのメンバーの取得</span><span class="sxs-lookup"><span data-stu-id="96233-110">Get Dimension Members</span></span>

<span data-ttu-id="96233-111">ディメンション メンバーの取得操作は、特定のディメンションのメンバーの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="96233-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="96233-112">また、メンバーの一覧をフィルター処理し、ワイヤ転送コストを削減するのには、サブセットを取得する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="96233-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="96233-113">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="96233-113">**Method**</span></span>|<span data-ttu-id="96233-114">**URI を要求します。**</span><span class="sxs-lookup"><span data-stu-id="96233-114">**Request URI**</span></span>|<span data-ttu-id="96233-115">**HTTP のバージョン**</span><span class="sxs-lookup"><span data-stu-id="96233-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="96233-116">投稿</span><span class="sxs-lookup"><span data-stu-id="96233-116">POST</span></span>  <br/> |<span data-ttu-id="96233-117">https://\<ポータル\>/QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="96233-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="96233-118">HTTP 1.1/</span><span class="sxs-lookup"><span data-stu-id="96233-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="96233-119">**URI パラメーター**を [なし] です。</span><span class="sxs-lookup"><span data-stu-id="96233-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="96233-120">**要求ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="96233-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="96233-121">**要求の本文**にするメンバーのディメンションの名前が含まれています。</span><span class="sxs-lookup"><span data-stu-id="96233-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="96233-122">メンバーの最大数が返されるの横にあるを指定することもいくつか返されるメンバーを制限するフィルタ リングします。</span><span class="sxs-lookup"><span data-stu-id="96233-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
```
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 <span data-ttu-id="96233-123">**応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="96233-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="96233-124">**ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="96233-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="96233-125">**応答ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="96233-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="96233-126">以下は、JSON 内の「[開始日] 要求へ応答サンプル応答内容を**応答本文**:。[月]"分析コード。</span><span class="sxs-lookup"><span data-stu-id="96233-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="96233-127">一覧を表示しているリストの一部です。</span><span class="sxs-lookup"><span data-stu-id="96233-127">The list is only showing a small portion of the list.</span></span> 
  
```
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
