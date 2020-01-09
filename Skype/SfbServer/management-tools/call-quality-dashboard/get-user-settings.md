---
title: ユーザー設定の取得
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: '概要: ユーザー設定サービスの一部である [ユーザー設定の取得] 操作について説明します。 ユーザー設定サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 42934496b8b65132a67d4012d81d7b8997859726
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992634"
---
# <a name="get-user-settings"></a><span data-ttu-id="4f538-105">ユーザー設定の取得</span><span class="sxs-lookup"><span data-stu-id="4f538-105">Get User Settings</span></span>
 
<span data-ttu-id="4f538-106">**概要:** ユーザー設定サービスの一部である [ユーザー設定の取得] 操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f538-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="4f538-107">ユーザー設定サービスは、通話品質ダッシュボードのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="4f538-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="4f538-108">通話品質ダッシュボードは、Skype for Business Server のツールです。</span><span class="sxs-lookup"><span data-stu-id="4f538-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="4f538-109">[ユーザー設定の取得] 操作は、[リポジトリ API for Call Quality] ダッシュボードのユーザー設定サービスに含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f538-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="4f538-110">ユーザー設定の取得</span><span class="sxs-lookup"><span data-stu-id="4f538-110">Get User Settings</span></span>

<span data-ttu-id="4f538-111">ユーザー設定の取得指定したユーザーの設定のリストを返します。</span><span class="sxs-lookup"><span data-stu-id="4f538-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="4f538-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="4f538-112">**Method**</span></span>|<span data-ttu-id="4f538-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="4f538-113">**Request URI**</span></span>|<span data-ttu-id="4f538-114">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="4f538-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4f538-115">取得</span><span class="sxs-lookup"><span data-stu-id="4f538-115">GET</span></span>  <br/> |<span data-ttu-id="4f538-116">https://\<ポータル\>の/QoERepositoryService/repository/user/{userId}/setting</span><span class="sxs-lookup"><span data-stu-id="4f538-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="4f538-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="4f538-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="4f538-118">**URI パラメーター**</span><span class="sxs-lookup"><span data-stu-id="4f538-118">**URI Parameters**</span></span>
  
- <span data-ttu-id="4f538-119">*有効*-省略可能。</span><span class="sxs-lookup"><span data-stu-id="4f538-119">*effective*  - Optional.</span></span> <span data-ttu-id="4f538-120">このパラメーターは、特別なユーザー ID の既定値が使用されている場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="4f538-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="4f538-121">それ以外の場合は、無視されます。</span><span class="sxs-lookup"><span data-stu-id="4f538-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="4f538-122">`True`有効なユーザー設定を`false`返し、ユーザー設定 (既定値) のみを返します。</span><span class="sxs-lookup"><span data-stu-id="4f538-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
  <span data-ttu-id="4f538-123">**ヘッダーを要求**する-追加のヘッダーは不要です。</span><span class="sxs-lookup"><span data-stu-id="4f538-123">**Request Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="4f538-124">**要求本文**-なし。</span><span class="sxs-lookup"><span data-stu-id="4f538-124">**Request Body** - None.</span></span>
  
  <span data-ttu-id="4f538-125">**応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4f538-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
  <span data-ttu-id="4f538-126">**状態コード**-正常に動作している操作は、状態コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="4f538-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
  <span data-ttu-id="4f538-127">**応答ヘッダー** -ヘッダーは追加されません。</span><span class="sxs-lookup"><span data-stu-id="4f538-127">**Response Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="4f538-128">**応答本文**-以下は JSON のサンプル応答ペイロードです。</span><span class="sxs-lookup"><span data-stu-id="4f538-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
[{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
},
{
"userId": 6,
"key": "ShowTimeStamps",
"value": "true"
}]
```
