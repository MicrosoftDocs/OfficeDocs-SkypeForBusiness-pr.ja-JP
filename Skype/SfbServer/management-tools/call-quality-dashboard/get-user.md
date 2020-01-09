---
title: ユーザーの取得
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: '概要: ユーザーサービスの一部であるユーザーの取得操作について説明します。 ユーザーサービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 09dcbbaeaae98ed7b01f3d710cfda23aa5fa986f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992624"
---
# <a name="get-user"></a><span data-ttu-id="5368b-105">ユーザーの取得</span><span class="sxs-lookup"><span data-stu-id="5368b-105">Get User</span></span>
 
<span data-ttu-id="5368b-106">**概要:** ユーザーサービスの一部であるユーザーの取得操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="5368b-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="5368b-107">ユーザーサービスは、通話品質ダッシュボードのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="5368b-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="5368b-108">通話品質ダッシュボードは、Skype for Business Server のツールです。</span><span class="sxs-lookup"><span data-stu-id="5368b-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="5368b-109">ユーザーの取得操作は、ユーザーサービスの一部であり、通話品質ダッシュボードのリポジトリ API に含まれています。</span><span class="sxs-lookup"><span data-stu-id="5368b-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="5368b-110">ユーザーの取得</span><span class="sxs-lookup"><span data-stu-id="5368b-110">Get User</span></span>

<span data-ttu-id="5368b-111">ユーザー Get は、リポジトリからユーザーレコードを返します。</span><span class="sxs-lookup"><span data-stu-id="5368b-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="5368b-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="5368b-112">**Method**</span></span>|<span data-ttu-id="5368b-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="5368b-113">**Request URI**</span></span>|<span data-ttu-id="5368b-114">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="5368b-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5368b-115">取得</span><span class="sxs-lookup"><span data-stu-id="5368b-115">GET</span></span>  <br/> |<span data-ttu-id="5368b-116">https://\<ポータル\>の/QoERepositoryService/repository/user/{userId}</span><span class="sxs-lookup"><span data-stu-id="5368b-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="5368b-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="5368b-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="5368b-118">**URI パラメーター** -なし。</span><span class="sxs-lookup"><span data-stu-id="5368b-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="5368b-119">**ヘッダーを要求**する-追加のヘッダーは不要です。</span><span class="sxs-lookup"><span data-stu-id="5368b-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="5368b-120">**要求本文**-なし。</span><span class="sxs-lookup"><span data-stu-id="5368b-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="5368b-121">**応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5368b-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="5368b-122">**状態コード**-正常に動作している操作は、状態コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="5368b-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="5368b-123">指定したユーザー ID が見つからない場合は、状態コード 404 (見つかりません) が返されます。</span><span class="sxs-lookup"><span data-stu-id="5368b-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="5368b-124">**応答ヘッダー** -ヘッダーは追加されません。</span><span class="sxs-lookup"><span data-stu-id="5368b-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="5368b-125">**応答本文**-以下は JSON のサンプル応答ペイロードです。</span><span class="sxs-lookup"><span data-stu-id="5368b-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="5368b-126">*userId* -ユーザーの id です。</span><span class="sxs-lookup"><span data-stu-id="5368b-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="5368b-127">*ログイン*情報-通常ユーザーの外部ユーザー id。</span><span class="sxs-lookup"><span data-stu-id="5368b-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="5368b-128">ユーザーの認証に Windows 認証が使用されている場合は、ユーザーの FQDN である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5368b-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="5368b-129">*defaultItemId* -このユーザーの既定のアイテムの ID です。</span><span class="sxs-lookup"><span data-stu-id="5368b-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="5368b-130">既定のアイテムは、ユーザーに関連付けられている最上位のアイテムです。</span><span class="sxs-lookup"><span data-stu-id="5368b-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="5368b-131">このユーザーが所有する他のすべてのアイテムは、既定のアイテムから移動することができます。</span><span class="sxs-lookup"><span data-stu-id="5368b-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5368b-132">項目の`defaultItemId`操作を取得する値を指定して、既定の項目の詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="5368b-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

