---
title: 統合ログの取得
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: '概要: 通話品質ダッシュボードのデータ API の一部である、統合ログの取得操作について説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 9caa909e80a0bab5257af16fe77e9d154947a56e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816816"
---
# <a name="get-integration-log"></a><span data-ttu-id="8b29f-104">統合ログの取得</span><span class="sxs-lookup"><span data-stu-id="8b29f-104">Get Integration Log</span></span>
 
<span data-ttu-id="8b29f-105">**概要:** 通話品質ダッシュボードのデータ API の一部である、統合ログの取得操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="8b29f-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="8b29f-106">通話品質ダッシュボードは、Skype for Business Server のツールです。</span><span class="sxs-lookup"><span data-stu-id="8b29f-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="8b29f-107">"統合ログの取得" 操作は、通話品質ダッシュボードのデータ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="8b29f-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="8b29f-108">統合ログの取得</span><span class="sxs-lookup"><span data-stu-id="8b29f-108">Get Integration Log</span></span>

<span data-ttu-id="8b29f-109">統合ログの取得操作 QoE キューブ処理のアクティビティを説明するログエントリの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="8b29f-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="8b29f-110">この操作は、セキュリティ上の理由で既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="8b29f-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="8b29f-111">無効にすると、空の文字列が返されます。</span><span class="sxs-lookup"><span data-stu-id="8b29f-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="8b29f-112">この操作を有効にするには、管理者が Data API のホスト web アプリケーション用に web.config を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b29f-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="8b29f-113">メソッド</span><span class="sxs-lookup"><span data-stu-id="8b29f-113">Method</span></span>|<span data-ttu-id="8b29f-114">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="8b29f-114">**Request URI**</span></span>|<span data-ttu-id="8b29f-115">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="8b29f-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8b29f-116">取得</span><span class="sxs-lookup"><span data-stu-id="8b29f-116">GET</span></span>  <br/> |<span data-ttu-id="8b29f-117">https://\<ポータル\>の/QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="8b29f-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="8b29f-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="8b29f-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="8b29f-119">**URI パラメーター** -なし。</span><span class="sxs-lookup"><span data-stu-id="8b29f-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="8b29f-120">**ヘッダーを要求**する-追加のヘッダーは不要です。</span><span class="sxs-lookup"><span data-stu-id="8b29f-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="8b29f-121">**要求本文**-なし。</span><span class="sxs-lookup"><span data-stu-id="8b29f-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="8b29f-122">**応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8b29f-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="8b29f-123">**状態コード**-正常に動作している操作は、状態コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="8b29f-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="8b29f-124">**応答ヘッダー** -ヘッダーは追加されません。</span><span class="sxs-lookup"><span data-stu-id="8b29f-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="8b29f-125">**応答本文**-以下に、ログエントリのサンプル構造を示します。</span><span class="sxs-lookup"><span data-stu-id="8b29f-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


