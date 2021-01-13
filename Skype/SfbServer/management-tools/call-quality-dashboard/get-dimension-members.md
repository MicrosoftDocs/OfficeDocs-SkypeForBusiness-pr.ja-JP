---
title: ディメンションのメンバーの取得
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: '概要: ディメンション メンバーの取得操作について学習します。 ディメンション メンバーの取得操作は、通話品質ダッシュボードのデータ API の一部です。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: ffec3b02a3c876a003adb679a28b0e8f2edb91c2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832637"
---
# <a name="get-dimension-members"></a><span data-ttu-id="41197-105">ディメンションのメンバーの取得</span><span class="sxs-lookup"><span data-stu-id="41197-105">Get Dimension Members</span></span>
 
<span data-ttu-id="41197-106">**概要:** ディメンション メンバーの取得操作について学習します。</span><span class="sxs-lookup"><span data-stu-id="41197-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="41197-107">ディメンション メンバーの取得操作は、通話品質ダッシュボードのデータ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="41197-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="41197-108">通話品質ダッシュボードは、Skype for Business Server 用のツールです。</span><span class="sxs-lookup"><span data-stu-id="41197-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="41197-109">ディメンション メンバーの取得操作は、通話品質ダッシュボードのデータ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="41197-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="41197-110">ディメンションのメンバーの取得</span><span class="sxs-lookup"><span data-stu-id="41197-110">Get Dimension Members</span></span>

<span data-ttu-id="41197-111">ディメンション メンバーの取得操作は、特定のディメンションのメンバーの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="41197-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="41197-112">また、メンバー リストをフィルター処理してサブセットを取得し、電信送金コストを削減する機能も提供します。</span><span class="sxs-lookup"><span data-stu-id="41197-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="41197-113">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="41197-113">**Method**</span></span>|<span data-ttu-id="41197-114">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="41197-114">**Request URI**</span></span>|<span data-ttu-id="41197-115">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="41197-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="41197-116">POST</span><span class="sxs-lookup"><span data-stu-id="41197-116">POST</span></span>  <br/> |<span data-ttu-id="41197-117">https:// \<portal\> /QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="41197-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="41197-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="41197-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="41197-119">**URI パラメーター** - なし。</span><span class="sxs-lookup"><span data-stu-id="41197-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="41197-120">**要求ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="41197-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="41197-121">**要求本文** - メンバーが必要なディメンションの名前が含まれる。</span><span class="sxs-lookup"><span data-stu-id="41197-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="41197-122">また、返されるメンバーの数も上限です。また、返されるメンバーを制限するフィルターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="41197-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
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

 <span data-ttu-id="41197-123">**応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="41197-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="41197-124">**状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。</span><span class="sxs-lookup"><span data-stu-id="41197-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="41197-125">**応答ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="41197-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="41197-126">**応答本文** - "[StartDate]" の要求に対する応答として JSON のサンプル応答ペイロードを次に示します。[Month]" ディメンション。</span><span class="sxs-lookup"><span data-stu-id="41197-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="41197-127">リストには、一覧の一部しか表示されません。</span><span class="sxs-lookup"><span data-stu-id="41197-127">The list is only showing a small portion of the list.</span></span> 
  
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
