---
title: ユーザー設定の取得
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
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: '概要: User Settings Service の一部であるユーザー設定の取得操作について学習します。 ユーザー設定サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: e2ebf39ba5a7de5d36a8b1ea0441808b6e71f97b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832477"
---
# <a name="get-user-settings"></a><span data-ttu-id="504b6-105">ユーザー設定の取得</span><span class="sxs-lookup"><span data-stu-id="504b6-105">Get User Settings</span></span>
 
<span data-ttu-id="504b6-106">**概要:** User Settings Service の一部であるユーザー設定の取得操作について学習します。</span><span class="sxs-lookup"><span data-stu-id="504b6-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="504b6-107">ユーザー設定サービスは、通話品質ダッシュボードのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="504b6-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="504b6-108">通話品質ダッシュボードは、Skype for Business Server 用のツールです。</span><span class="sxs-lookup"><span data-stu-id="504b6-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="504b6-109">ユーザー設定の取得操作は、通話品質ダッシュボードのリポジトリ API のユーザー設定サービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="504b6-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="504b6-110">ユーザー設定の取得</span><span class="sxs-lookup"><span data-stu-id="504b6-110">Get User Settings</span></span>

<span data-ttu-id="504b6-111">ユーザー設定を取得すると、指定したユーザーの設定の一覧が返されます。</span><span class="sxs-lookup"><span data-stu-id="504b6-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="504b6-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="504b6-112">**Method**</span></span>|<span data-ttu-id="504b6-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="504b6-113">**Request URI**</span></span>|<span data-ttu-id="504b6-114">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="504b6-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="504b6-115">GET</span><span class="sxs-lookup"><span data-stu-id="504b6-115">GET</span></span>  <br/> |<span data-ttu-id="504b6-116">https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting</span><span class="sxs-lookup"><span data-stu-id="504b6-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="504b6-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="504b6-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="504b6-118">**URI パラメーター**</span><span class="sxs-lookup"><span data-stu-id="504b6-118">**URI Parameters**</span></span>
  
- <span data-ttu-id="504b6-119">*effective*  - 省略可能。</span><span class="sxs-lookup"><span data-stu-id="504b6-119">*effective*  - Optional.</span></span> <span data-ttu-id="504b6-120">このパラメーターは、特別なユーザー ID の既定値が使用されている場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="504b6-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="504b6-121">それ以外の場合は無視されます。</span><span class="sxs-lookup"><span data-stu-id="504b6-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="504b6-122">`True` は有効なユーザー設定を返 `false` し、ユーザー設定 (既定) を返します。</span><span class="sxs-lookup"><span data-stu-id="504b6-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
  <span data-ttu-id="504b6-123">**要求ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="504b6-123">**Request Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="504b6-124">**要求本文** - なし。</span><span class="sxs-lookup"><span data-stu-id="504b6-124">**Request Body** - None.</span></span>
  
  <span data-ttu-id="504b6-125">**応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="504b6-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
  <span data-ttu-id="504b6-126">**状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。</span><span class="sxs-lookup"><span data-stu-id="504b6-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
  <span data-ttu-id="504b6-127">**応答ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="504b6-127">**Response Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="504b6-128">**応答本文** - JSON の応答ペイロードのサンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="504b6-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
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
