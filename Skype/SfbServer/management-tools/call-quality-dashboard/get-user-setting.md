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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: '概要: ユーザー設定サービスの一部である [ユーザー設定の取得] 操作について説明します。 ユーザー設定サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 168e61aaebb47cb087e77cbd18e3e6edfd987227
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992644"
---
# <a name="get-user-setting"></a><span data-ttu-id="35957-105">ユーザー設定の取得</span><span class="sxs-lookup"><span data-stu-id="35957-105">Get User Setting</span></span>
 
<span data-ttu-id="35957-106">**概要:** ユーザー設定サービスの一部である [ユーザー設定の取得] 操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="35957-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="35957-107">ユーザー設定サービスは、通話品質ダッシュボードのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="35957-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="35957-108">通話品質ダッシュボードは、Skype for Business Server のツールです。</span><span class="sxs-lookup"><span data-stu-id="35957-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="35957-109">"ユーザー設定の取得" 操作は、[リポジトリ API for Call Quality] ダッシュボードのユーザー設定サービスに含まれています。</span><span class="sxs-lookup"><span data-stu-id="35957-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="35957-110">ユーザー設定の取得</span><span class="sxs-lookup"><span data-stu-id="35957-110">Get User Setting</span></span>

<span data-ttu-id="35957-111">Get User Setting は、単一のユーザー設定を返します。</span><span class="sxs-lookup"><span data-stu-id="35957-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="35957-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="35957-112">**Method**</span></span>|<span data-ttu-id="35957-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="35957-113">**Request URI**</span></span>|<span data-ttu-id="35957-114">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="35957-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="35957-115">取得</span><span class="sxs-lookup"><span data-stu-id="35957-115">GET</span></span>  <br/> |<span data-ttu-id="35957-116">https://\<ポータル\>の/QoERepositoryService/repository/user/{userId}/setting/{key}</span><span class="sxs-lookup"><span data-stu-id="35957-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="35957-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="35957-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="35957-118">**URI パラメーター** -なし。</span><span class="sxs-lookup"><span data-stu-id="35957-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="35957-119">**ヘッダーを要求**する-追加のヘッダーは不要です。</span><span class="sxs-lookup"><span data-stu-id="35957-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="35957-120">**要求本文**-なし。</span><span class="sxs-lookup"><span data-stu-id="35957-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="35957-121">**応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="35957-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="35957-122">**状態コード**-正常に動作している操作は、状態コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="35957-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="35957-123">**応答ヘッダー** -ヘッダーは追加されません。</span><span class="sxs-lookup"><span data-stu-id="35957-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="35957-124">**応答本文**-以下は JSON のサンプル応答ペイロードです。</span><span class="sxs-lookup"><span data-stu-id="35957-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="35957-125">*userId* -ユーザーの id です。</span><span class="sxs-lookup"><span data-stu-id="35957-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="35957-126">設定*のキーキー* 。</span><span class="sxs-lookup"><span data-stu-id="35957-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="35957-127">*値*-設定の値。</span><span class="sxs-lookup"><span data-stu-id="35957-127">*value*  - Value of the setting.</span></span>
  

