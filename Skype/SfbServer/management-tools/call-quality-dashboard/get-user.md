---
title: ユーザーの取得
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
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: '概要: ユーザー サービスの一部であるユーザーの取得操作について学習します。 ユーザー サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: dd2bb5e46ddbe3e65faf441a11e39cbc5429e473
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832417"
---
# <a name="get-user"></a><span data-ttu-id="64151-105">ユーザーの取得</span><span class="sxs-lookup"><span data-stu-id="64151-105">Get User</span></span>
 
<span data-ttu-id="64151-106">**概要:** ユーザー サービスの一部であるユーザーの取得操作について学習します。</span><span class="sxs-lookup"><span data-stu-id="64151-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="64151-107">ユーザー サービスは、通話品質ダッシュボードのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="64151-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="64151-108">通話品質ダッシュボードは、Skype for Business Server 用のツールです。</span><span class="sxs-lookup"><span data-stu-id="64151-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="64151-109">ユーザーの取得操作は、通話品質ダッシュボードのリポジトリ API のユーザー サービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="64151-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="64151-110">ユーザーの取得</span><span class="sxs-lookup"><span data-stu-id="64151-110">Get User</span></span>

<span data-ttu-id="64151-111">Get User はリポジトリからユーザー レコードを返します。</span><span class="sxs-lookup"><span data-stu-id="64151-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="64151-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="64151-112">**Method**</span></span>|<span data-ttu-id="64151-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="64151-113">**Request URI**</span></span>|<span data-ttu-id="64151-114">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="64151-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="64151-115">GET</span><span class="sxs-lookup"><span data-stu-id="64151-115">GET</span></span>  <br/> |<span data-ttu-id="64151-116">https:// \<portal\> /QoERepositoryService/repository/user/{userId}</span><span class="sxs-lookup"><span data-stu-id="64151-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="64151-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="64151-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="64151-118">**URI パラメーター** - なし。</span><span class="sxs-lookup"><span data-stu-id="64151-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="64151-119">**要求ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="64151-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="64151-120">**要求本文** - なし。</span><span class="sxs-lookup"><span data-stu-id="64151-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="64151-121">**応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="64151-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="64151-122">**状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。</span><span class="sxs-lookup"><span data-stu-id="64151-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="64151-123">指定されたユーザー ID が見つからない場合は、状態コード 404 (Not Found) が返されます。</span><span class="sxs-lookup"><span data-stu-id="64151-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="64151-124">**応答ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="64151-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="64151-125">**応答本文** - JSON の応答ペイロードのサンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="64151-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="64151-126">*userId*  - ユーザーの ID。</span><span class="sxs-lookup"><span data-stu-id="64151-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="64151-127">*loginName*  - 通常のユーザーの外部ユーザー ID。</span><span class="sxs-lookup"><span data-stu-id="64151-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="64151-128">Windows 認証を使用してユーザーを認証する場合、これはユーザーの FQDN である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="64151-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="64151-129">*defaultItemId*  - このユーザーの既定のアイテムの ID。</span><span class="sxs-lookup"><span data-stu-id="64151-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="64151-130">既定のアイテムは、ユーザーに関連付けられている最も上位のアイテムです。</span><span class="sxs-lookup"><span data-stu-id="64151-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="64151-131">このユーザーが所有する他のすべてのアイテムは、既定のアイテムから移動できます。</span><span class="sxs-lookup"><span data-stu-id="64151-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="64151-132">既定の  `defaultItemId` アイテムの詳細を取得するアイテムの取得操作の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="64151-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

