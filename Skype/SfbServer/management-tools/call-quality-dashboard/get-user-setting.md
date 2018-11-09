---
title: ユーザー設定を取得します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: '概要: は、ユーザー設定のサービスの一部では、ユーザー設定の取得操作について説明します。 ユーザー設定のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: 286939271bdc99790f125beabb68735dd4c5f758
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035646"
---
# <a name="get-user-setting"></a><span data-ttu-id="bb347-105">ユーザー設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="bb347-105">Get User Setting</span></span>
 
<span data-ttu-id="bb347-106">**の概要:** ユーザー設定のサービスの一部では、ユーザー設定の取得操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="bb347-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="bb347-107">ユーザー設定のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="bb347-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="bb347-108">通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。</span><span class="sxs-lookup"><span data-stu-id="bb347-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="bb347-109">ユーザー設定の取得操作は、ユーザーの設定でのサービス品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="bb347-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="bb347-110">ユーザー設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="bb347-110">Get User Setting</span></span>

<span data-ttu-id="bb347-111">ユーザーの設定を返します。 1 つのユーザー設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="bb347-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="bb347-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="bb347-112">**Method**</span></span>|<span data-ttu-id="bb347-113">**URI を要求します。**</span><span class="sxs-lookup"><span data-stu-id="bb347-113">**Request URI**</span></span>|<span data-ttu-id="bb347-114">**HTTP のバージョン**</span><span class="sxs-lookup"><span data-stu-id="bb347-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bb347-115">取得</span><span class="sxs-lookup"><span data-stu-id="bb347-115">GET</span></span>  <br/> |<span data-ttu-id="bb347-116">https://\<ポータル\>/QoERepositoryService/リポジトリとユーザー/{ユーザー Id}/setting/{キー}</span><span class="sxs-lookup"><span data-stu-id="bb347-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="bb347-117">HTTP 1.1/</span><span class="sxs-lookup"><span data-stu-id="bb347-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="bb347-118">**URI パラメーター**を [なし] です。</span><span class="sxs-lookup"><span data-stu-id="bb347-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="bb347-119">**要求ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="bb347-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="bb347-120">**リクエストの本文**の [なし] です。</span><span class="sxs-lookup"><span data-stu-id="bb347-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="bb347-121">**応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bb347-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="bb347-122">**ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="bb347-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="bb347-123">**応答ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="bb347-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="bb347-124">**応答本体**の JSON のサンプル応答の内容を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bb347-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="bb347-125">*ユーザー Id*がユーザーの ID。</span><span class="sxs-lookup"><span data-stu-id="bb347-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="bb347-126">*キー*の設定のキーです。</span><span class="sxs-lookup"><span data-stu-id="bb347-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="bb347-127">*値*の設定の値です。</span><span class="sxs-lookup"><span data-stu-id="bb347-127">*value*  - Value of the setting.</span></span>
  

