---
title: ユーザーの取得
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: '概要: は、ユーザー サービスの一部を取得するユーザーの操作について説明します。 ユーザー サービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: 2d3c5febe30af2ea4d41d94aec026c25e27f21b9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32235724"
---
# <a name="get-user"></a><span data-ttu-id="177e8-105">ユーザーの取得</span><span class="sxs-lookup"><span data-stu-id="177e8-105">Get User</span></span>
 
<span data-ttu-id="177e8-106">**の概要:** ユーザー サービスの一部を取得するユーザーの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="177e8-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="177e8-107">ユーザー サービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="177e8-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="177e8-108">通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。</span><span class="sxs-lookup"><span data-stu-id="177e8-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="177e8-109">ユーザーの取得操作は、リポジトリ api の呼び出し品質のダッシュ ボードのユーザー ・ サービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="177e8-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="177e8-110">ユーザーの取得</span><span class="sxs-lookup"><span data-stu-id="177e8-110">Get User</span></span>

<span data-ttu-id="177e8-111">リポジトリからユーザを返します。 ユーザー レコードを取得します。</span><span class="sxs-lookup"><span data-stu-id="177e8-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="177e8-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="177e8-112">**Method**</span></span>|<span data-ttu-id="177e8-113">**URI を要求します。**</span><span class="sxs-lookup"><span data-stu-id="177e8-113">**Request URI**</span></span>|<span data-ttu-id="177e8-114">**HTTP のバージョン**</span><span class="sxs-lookup"><span data-stu-id="177e8-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="177e8-115">取得</span><span class="sxs-lookup"><span data-stu-id="177e8-115">GET</span></span>  <br/> |<span data-ttu-id="177e8-116">https://\<ポータル\>/QoERepositoryService/リポジトリとユーザー/{ユーザー Id}</span><span class="sxs-lookup"><span data-stu-id="177e8-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="177e8-117">HTTP 1.1/</span><span class="sxs-lookup"><span data-stu-id="177e8-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="177e8-118">**URI パラメーター**を [なし] です。</span><span class="sxs-lookup"><span data-stu-id="177e8-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="177e8-119">**要求ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="177e8-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="177e8-120">**リクエストの本文**の [なし] です。</span><span class="sxs-lookup"><span data-stu-id="177e8-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="177e8-121">**応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="177e8-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="177e8-122">**ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="177e8-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="177e8-123">特定のユーザ ID が見つからない場合は、ステータス コード 404 (見つかりません) を返します。</span><span class="sxs-lookup"><span data-stu-id="177e8-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="177e8-124">**応答ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="177e8-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="177e8-125">**応答本体**の JSON のサンプル応答の内容を次に示します。</span><span class="sxs-lookup"><span data-stu-id="177e8-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="177e8-126">*ユーザー Id*がユーザーの ID。</span><span class="sxs-lookup"><span data-stu-id="177e8-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="177e8-127">*loginName* - 通常のユーザーの外部ユーザー id です。</span><span class="sxs-lookup"><span data-stu-id="177e8-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="177e8-128">ユーザーの認証に Windows 認証を使用する場合、この可能性がありますユーザーの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="177e8-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="177e8-129">*defaultItemId* - このユーザーの既定の項目の ID です。</span><span class="sxs-lookup"><span data-stu-id="177e8-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="177e8-130">既定の項目は、ユーザーに関連付けられている最上位のアイテムです。</span><span class="sxs-lookup"><span data-stu-id="177e8-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="177e8-131">このユーザーが所有する他のすべての項目は、既定アイテムから移動できます。</span><span class="sxs-lookup"><span data-stu-id="177e8-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="177e8-132">装置、`defaultItemId`の値を既定の項目の詳細を取得する項目の取得操作。</span><span class="sxs-lookup"><span data-stu-id="177e8-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

