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
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: '概要: ユーザーサービスの一部であるユーザーの取得操作について説明します。 ユーザーサービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 6cf2248035c780c2efce6b1f4539a39cd2a5829a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992614"
---
# <a name="get-users"></a><span data-ttu-id="feeb7-105">ユーザーの取得</span><span class="sxs-lookup"><span data-stu-id="feeb7-105">Get Users</span></span>
 
<span data-ttu-id="feeb7-106">**概要:** ユーザーサービスの一部であるユーザーの取得操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="feeb7-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="feeb7-107">ユーザーサービスは、通話品質ダッシュボードのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="feeb7-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="feeb7-108">通話品質ダッシュボードは、Skype for Business Server のツールです。</span><span class="sxs-lookup"><span data-stu-id="feeb7-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="feeb7-109">ユーザーの取得操作は、ユーザーサービスの一部であり、通話品質ダッシュボードのリポジトリ API に含まれています。</span><span class="sxs-lookup"><span data-stu-id="feeb7-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="feeb7-110">ユーザーの取得</span><span class="sxs-lookup"><span data-stu-id="feeb7-110">Get Users</span></span>

<span data-ttu-id="feeb7-111">ユーザー Get は、リポジトリ内のユーザーのリストを返します。</span><span class="sxs-lookup"><span data-stu-id="feeb7-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="feeb7-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="feeb7-112">**Method**</span></span>|<span data-ttu-id="feeb7-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="feeb7-113">**Request URI**</span></span>|<span data-ttu-id="feeb7-114">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="feeb7-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="feeb7-115">取得</span><span class="sxs-lookup"><span data-stu-id="feeb7-115">GET</span></span>  <br/> |<span data-ttu-id="feeb7-116">https://\<ポータル\>の/QoERepositoryService/repository/user</span><span class="sxs-lookup"><span data-stu-id="feeb7-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="feeb7-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="feeb7-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="feeb7-118">**URI パラメーター** -なし。</span><span class="sxs-lookup"><span data-stu-id="feeb7-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="feeb7-119">**ヘッダーを要求**する-追加のヘッダーは不要です。</span><span class="sxs-lookup"><span data-stu-id="feeb7-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="feeb7-120">**要求本文**-なし。</span><span class="sxs-lookup"><span data-stu-id="feeb7-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="feeb7-121">**応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="feeb7-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="feeb7-122">**状態コード**-正常に動作している操作は、状態コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="feeb7-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="feeb7-123">**応答ヘッダー** -ヘッダーは追加されません。</span><span class="sxs-lookup"><span data-stu-id="feeb7-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="feeb7-124">**応答本文**-以下は JSON のサンプル応答ペイロードです。</span><span class="sxs-lookup"><span data-stu-id="feeb7-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="feeb7-125">ユーザーオブジェクトの配列が返されます。</span><span class="sxs-lookup"><span data-stu-id="feeb7-125">An array of User objects is returned.</span></span> <span data-ttu-id="feeb7-126">ユーザーオブジェクトの詳細については、「ユーザーの取得」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="feeb7-126">For details about the User object, see Get User.</span></span> 
  
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


