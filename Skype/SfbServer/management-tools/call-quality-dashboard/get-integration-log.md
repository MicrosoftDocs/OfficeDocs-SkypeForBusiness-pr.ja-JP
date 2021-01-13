---
title: 統合ログの取得
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
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: '概要: 通話品質ダッシュボードのデータ API の一部である統合ログの取得操作について説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: 69827fa9f3fd3f56843a41867b029a071799ba66
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832597"
---
# <a name="get-integration-log"></a><span data-ttu-id="24640-104">統合ログの取得</span><span class="sxs-lookup"><span data-stu-id="24640-104">Get Integration Log</span></span>
 
<span data-ttu-id="24640-105">**概要:** 通話品質ダッシュボードのデータ API の一部である統合ログの取得操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="24640-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="24640-106">通話品質ダッシュボードは、Skype for Business Server 用のツールです。</span><span class="sxs-lookup"><span data-stu-id="24640-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="24640-107">統合ログの取得操作は、通話品質ダッシュボードのデータ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="24640-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="24640-108">統合ログの取得</span><span class="sxs-lookup"><span data-stu-id="24640-108">Get Integration Log</span></span>

<span data-ttu-id="24640-109">統合ログの取得操作は、QoE キューブ処理のアクティビティを記述するログ エントリのリストを返します。</span><span class="sxs-lookup"><span data-stu-id="24640-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="24640-110">セキュリティ上の理由により、この操作は既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="24640-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="24640-111">無効にすると、空の文字列が返されます。</span><span class="sxs-lookup"><span data-stu-id="24640-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="24640-112">この操作を有効にするには、管理者は、データ API のweb.config Web アプリケーションのアプリケーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24640-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="24640-113">メソッド</span><span class="sxs-lookup"><span data-stu-id="24640-113">Method</span></span>|<span data-ttu-id="24640-114">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="24640-114">**Request URI**</span></span>|<span data-ttu-id="24640-115">**HTTP バージョン**</span><span class="sxs-lookup"><span data-stu-id="24640-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="24640-116">GET</span><span class="sxs-lookup"><span data-stu-id="24640-116">GET</span></span>  <br/> |<span data-ttu-id="24640-117">https:// \<portal\> /QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="24640-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="24640-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="24640-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="24640-119">**URI パラメーター** - なし。</span><span class="sxs-lookup"><span data-stu-id="24640-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="24640-120">**要求ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="24640-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="24640-121">**要求本文** - なし。</span><span class="sxs-lookup"><span data-stu-id="24640-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="24640-122">**応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="24640-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="24640-123">**状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。</span><span class="sxs-lookup"><span data-stu-id="24640-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="24640-124">**応答ヘッダー** - 追加のヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="24640-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="24640-125">**応答本文** - ログ エントリのサンプル構造を次に示します。</span><span class="sxs-lookup"><span data-stu-id="24640-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


