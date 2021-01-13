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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: '概要: User Settings Service の一部であるユーザー設定の取得操作について学習します。 ユーザー設定サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: 82632f5de7ae215d6f34d9f0b39e500fb713a1be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832487"
---
# <a name="get-user-setting"></a><span data-ttu-id="10474-105">ユーザー設定の取得</span><span class="sxs-lookup"><span data-stu-id="10474-105">Get User Setting</span></span>
 
<span data-ttu-id="10474-106">**概要:** User Settings Service の一部であるユーザー設定の取得操作について学習します。</span><span class="sxs-lookup"><span data-stu-id="10474-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="10474-107">ユーザー設定サービスは、通話品質ダッシュボードのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="10474-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="10474-108">通話品質ダッシュボードは、Skype for Business Server 用のツールです。</span><span class="sxs-lookup"><span data-stu-id="10474-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="10474-109">ユーザー設定の取得操作は、通話品質ダッシュボードのリポジトリ API のユーザー設定サービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="10474-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="10474-110">ユーザー設定の取得</span><span class="sxs-lookup"><span data-stu-id="10474-110">Get User Setting</span></span>

<span data-ttu-id="10474-111">ユーザー設定を取得すると、1 つのユーザー設定が返されます。</span><span class="sxs-lookup"><span data-stu-id="10474-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="10474-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="10474-112">**Method**</span></span>|<span data-ttu-id="10474-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="10474-113">**Request URI**</span></span>|<span data-ttu-id="10474-114">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="10474-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="10474-115">GET</span><span class="sxs-lookup"><span data-stu-id="10474-115">GET</span></span>  <br/> |<span data-ttu-id="10474-116">https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting/{key}</span><span class="sxs-lookup"><span data-stu-id="10474-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="10474-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="10474-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="10474-118">**URI パラメーター** - なし。</span><span class="sxs-lookup"><span data-stu-id="10474-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="10474-119">**要求ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="10474-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="10474-120">**要求本文** - なし。</span><span class="sxs-lookup"><span data-stu-id="10474-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="10474-121">**応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="10474-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="10474-122">**状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。</span><span class="sxs-lookup"><span data-stu-id="10474-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="10474-123">**応答ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="10474-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="10474-124">**応答本文** - JSON の応答ペイロードのサンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="10474-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="10474-125">*userId*  - ユーザーの ID。</span><span class="sxs-lookup"><span data-stu-id="10474-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="10474-126">*key*  - 設定のキー。</span><span class="sxs-lookup"><span data-stu-id="10474-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="10474-127">*value*  - 設定の値。</span><span class="sxs-lookup"><span data-stu-id="10474-127">*value*  - Value of the setting.</span></span>
  

