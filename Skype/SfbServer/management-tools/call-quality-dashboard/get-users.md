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
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: '概要: は、ユーザー サービスの一部を取得するユーザーの操作について説明します。 ユーザー サービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: 24a01f7a149240c3f7bd6830cdfa7a9cb8123396
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217811"
---
# <a name="get-users"></a><span data-ttu-id="8e95e-105">ユーザーの取得</span><span class="sxs-lookup"><span data-stu-id="8e95e-105">Get Users</span></span>
 
<span data-ttu-id="8e95e-106">**の概要:** ユーザー サービスの一部を取得するユーザーの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="8e95e-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="8e95e-107">ユーザー サービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="8e95e-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="8e95e-108">通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。</span><span class="sxs-lookup"><span data-stu-id="8e95e-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="8e95e-109">ユーザーの取得操作は、リポジトリ api の呼び出し品質のダッシュ ボードのユーザー ・ サービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="8e95e-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="8e95e-110">ユーザーの取得</span><span class="sxs-lookup"><span data-stu-id="8e95e-110">Get Users</span></span>

<span data-ttu-id="8e95e-111">リポジトリ内のユーザーを返します。 ユーザーの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="8e95e-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="8e95e-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="8e95e-112">**Method**</span></span>|<span data-ttu-id="8e95e-113">**URI を要求します。**</span><span class="sxs-lookup"><span data-stu-id="8e95e-113">**Request URI**</span></span>|<span data-ttu-id="8e95e-114">**HTTP のバージョン**</span><span class="sxs-lookup"><span data-stu-id="8e95e-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8e95e-115">取得</span><span class="sxs-lookup"><span data-stu-id="8e95e-115">GET</span></span>  <br/> |<span data-ttu-id="8e95e-116">https://\<ポータル\>/QoERepositoryService/repository/user</span><span class="sxs-lookup"><span data-stu-id="8e95e-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="8e95e-117">HTTP 1.1/</span><span class="sxs-lookup"><span data-stu-id="8e95e-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="8e95e-118">**URI パラメーター**を [なし] です。</span><span class="sxs-lookup"><span data-stu-id="8e95e-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="8e95e-119">**要求ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="8e95e-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="8e95e-120">**リクエストの本文**の [なし] です。</span><span class="sxs-lookup"><span data-stu-id="8e95e-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="8e95e-121">**応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8e95e-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="8e95e-122">**ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="8e95e-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="8e95e-123">**応答ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="8e95e-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="8e95e-124">**応答本体**の JSON のサンプル応答の内容を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8e95e-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8e95e-125">ユーザー オブジェクトの配列が返されます。</span><span class="sxs-lookup"><span data-stu-id="8e95e-125">An array of User objects is returned.</span></span> <span data-ttu-id="8e95e-126">詳細については、ユーザー オブジェクトは、ユーザーの取得を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e95e-126">For details about the User object, see Get User.</span></span> 
  
```
[{
"userId": 0,
"loginName": "system",
"defaultItemId": 1652
},
{
"userId": 1,
"loginName": "SAMPLEDOMAIN\\testuser1",
"defaultItemId": 1652
},
{
"userId": 2,
"loginName": "SAMPLEDOMAIN\\testuser2",
"defaultItemId": 1774
}]
```


