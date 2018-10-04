---
title: ユーザー設定を取得します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: '概要: は、ユーザー設定のサービスの一部では、ユーザー設定の取得操作について説明します。 ユーザー設定のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。 通話品質のダッシュ ボードは、ビジネス サーバー 2015 の Skype のツールです。'
ms.openlocfilehash: 41bc45f63366337000ad8c263ff8e6dbcb36a3b3
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375380"
---
# <a name="get-user-settings"></a><span data-ttu-id="5dbfa-105">ユーザー設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="5dbfa-105">Get User Settings</span></span>
 
<span data-ttu-id="5dbfa-106">**の概要:** ユーザー設定のサービスの一部では、ユーザー設定の取得操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="5dbfa-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="5dbfa-107">ユーザー設定のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="5dbfa-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="5dbfa-108">通話品質のダッシュ ボードは、ビジネス サーバー 2015 の Skype のツールです。</span><span class="sxs-lookup"><span data-stu-id="5dbfa-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5dbfa-109">ユーザー設定の取得操作は、ユーザーの設定でのサービス品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="5dbfa-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="5dbfa-110">ユーザー設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="5dbfa-110">Get User Settings</span></span>

<span data-ttu-id="5dbfa-111">ユーザー設定を取得、指定したユーザー設定の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="5dbfa-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="5dbfa-112">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="5dbfa-112">**Method**</span></span>|<span data-ttu-id="5dbfa-113">**URI を要求します。**</span><span class="sxs-lookup"><span data-stu-id="5dbfa-113">**Request URI**</span></span>|<span data-ttu-id="5dbfa-114">**HTTP のバージョン**</span><span class="sxs-lookup"><span data-stu-id="5dbfa-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5dbfa-115">取得</span><span class="sxs-lookup"><span data-stu-id="5dbfa-115">GET</span></span>  <br/> |<span data-ttu-id="5dbfa-116">https://\<ポータル\>/QoERepositoryService/リポジトリとユーザー/{ユーザー Id} の設定/</span><span class="sxs-lookup"><span data-stu-id="5dbfa-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="5dbfa-117">HTTP 1.1/</span><span class="sxs-lookup"><span data-stu-id="5dbfa-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="5dbfa-118">**URI パラメーター**</span><span class="sxs-lookup"><span data-stu-id="5dbfa-118">**URI Parameters**</span></span>
  
- <span data-ttu-id="5dbfa-119">*効果的な*- 省略可能です。</span><span class="sxs-lookup"><span data-stu-id="5dbfa-119">*effective*  - Optional.</span></span> <span data-ttu-id="5dbfa-120">このパラメーターでは、特別なユーザー ID の既定値を使用する場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="5dbfa-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="5dbfa-121">それ以外の場合、無視されます。</span><span class="sxs-lookup"><span data-stu-id="5dbfa-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="5dbfa-122">`True`効果的なユーザーの設定を取得および`false`ユーザーの設定 (既定値) だけを返します。</span><span class="sxs-lookup"><span data-stu-id="5dbfa-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
  <span data-ttu-id="5dbfa-123">**要求ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="5dbfa-123">**Request Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="5dbfa-124">**リクエストの本文**の [なし] です。</span><span class="sxs-lookup"><span data-stu-id="5dbfa-124">**Request Body** - None.</span></span>
  
  <span data-ttu-id="5dbfa-125">**応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5dbfa-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
  <span data-ttu-id="5dbfa-126">**ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="5dbfa-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
  <span data-ttu-id="5dbfa-127">**応答ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="5dbfa-127">**Response Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="5dbfa-128">**応答本体**の JSON のサンプル応答の内容を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5dbfa-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
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