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
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: '概要: ユーザー サービスの一部であるユーザーの取得操作について学習します。 ユーザー サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: a830663fc97d8fda727d1ebb008d97407796cc7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832427"
---
# <a name="get-users"></a><span data-ttu-id="f75ce-105">ユーザーの取得</span><span class="sxs-lookup"><span data-stu-id="f75ce-105">Get Users</span></span>
 
<span data-ttu-id="f75ce-106">**概要:** ユーザー サービスの一部であるユーザーの取得操作について学習します。</span><span class="sxs-lookup"><span data-stu-id="f75ce-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="f75ce-107">ユーザー サービスは、通話品質ダッシュボードのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="f75ce-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="f75ce-108">通話品質ダッシュボードは、Skype for Business Server 用のツールです。</span><span class="sxs-lookup"><span data-stu-id="f75ce-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="f75ce-109">ユーザーの取得操作は、通話品質ダッシュボードのリポジトリ API のユーザー サービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="f75ce-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="f75ce-110">ユーザーの取得</span><span class="sxs-lookup"><span data-stu-id="f75ce-110">Get Users</span></span>

<span data-ttu-id="f75ce-111">Get Users returns a list of users in the repository.</span><span class="sxs-lookup"><span data-stu-id="f75ce-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="f75ce-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="f75ce-112">**Method**</span></span>|<span data-ttu-id="f75ce-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="f75ce-113">**Request URI**</span></span>|<span data-ttu-id="f75ce-114">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="f75ce-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f75ce-115">GET</span><span class="sxs-lookup"><span data-stu-id="f75ce-115">GET</span></span>  <br/> |<span data-ttu-id="f75ce-116">https:// \<portal\> /QoERepositoryService/repository/user</span><span class="sxs-lookup"><span data-stu-id="f75ce-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="f75ce-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="f75ce-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="f75ce-118">**URI パラメーター** - なし。</span><span class="sxs-lookup"><span data-stu-id="f75ce-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="f75ce-119">**要求ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="f75ce-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="f75ce-120">**要求本文** - なし。</span><span class="sxs-lookup"><span data-stu-id="f75ce-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="f75ce-121">**応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f75ce-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="f75ce-122">**状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。</span><span class="sxs-lookup"><span data-stu-id="f75ce-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="f75ce-123">**応答ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="f75ce-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="f75ce-124">**応答本文** - JSON の応答ペイロードのサンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f75ce-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f75ce-125">User オブジェクトの配列が返されます。</span><span class="sxs-lookup"><span data-stu-id="f75ce-125">An array of User objects is returned.</span></span> <span data-ttu-id="f75ce-126">User オブジェクトの詳細については、「ユーザーの取得」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f75ce-126">For details about the User object, see Get User.</span></span> 
  
```json
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


