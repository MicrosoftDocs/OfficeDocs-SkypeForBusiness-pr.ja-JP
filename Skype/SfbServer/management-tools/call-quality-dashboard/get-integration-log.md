---
title: 統合ログを取得します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: '概要: は、統合ログの取得の操作では、品質のダッシュ ボードを呼び出すためのデータ API の一部について説明します。 通話品質のダッシュ ボードは、ビジネス サーバー 2015 の Skype のツールです。'
ms.openlocfilehash: a71d01780222d673c8455176ac82fc51683b441e
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569073"
---
# <a name="get-integration-log"></a><span data-ttu-id="777e0-104">統合ログを取得します。</span><span class="sxs-lookup"><span data-stu-id="777e0-104">Get Integration Log</span></span>
 
<span data-ttu-id="777e0-105">**の概要:** 統合ログの取得の操作では、品質のダッシュ ボードを呼び出すためのデータ API の一部について説明します。</span><span class="sxs-lookup"><span data-stu-id="777e0-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="777e0-106">通話品質のダッシュ ボードは、ビジネス サーバー 2015 の Skype のツールです。</span><span class="sxs-lookup"><span data-stu-id="777e0-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="777e0-107">統合ログの取得操作は、品質のダッシュ ボードを呼び出すためのデータ API の一部</span><span class="sxs-lookup"><span data-stu-id="777e0-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="777e0-108">統合ログを取得します。</span><span class="sxs-lookup"><span data-stu-id="777e0-108">Get Integration Log</span></span>

<span data-ttu-id="777e0-109">操作が返されます QoE のキューブに含まれるアクティビティを説明するログ エントリの一覧を処理する統合ログを取得します。</span><span class="sxs-lookup"><span data-stu-id="777e0-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="777e0-110">この操作は既定ではセキュリティ上の理由で無効になります。</span><span class="sxs-lookup"><span data-stu-id="777e0-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="777e0-111">無効にすると、空の文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="777e0-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="777e0-112">この操作を有効にするには、管理者はデータ API のホストの web アプリケーションの web.config を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="777e0-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="777e0-113">メソッド</span><span class="sxs-lookup"><span data-stu-id="777e0-113">Method</span></span>|<span data-ttu-id="777e0-114">**URI を要求します。**</span><span class="sxs-lookup"><span data-stu-id="777e0-114">**Request URI**</span></span>|<span data-ttu-id="777e0-115">**HTTP のバージョン**</span><span class="sxs-lookup"><span data-stu-id="777e0-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="777e0-116">取得</span><span class="sxs-lookup"><span data-stu-id="777e0-116">GET</span></span>  <br/> |<span data-ttu-id="777e0-117">https://\<ポータル\>/QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="777e0-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="777e0-118">HTTP 1.1/</span><span class="sxs-lookup"><span data-stu-id="777e0-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="777e0-119">**URI パラメーター**を [なし] です。</span><span class="sxs-lookup"><span data-stu-id="777e0-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="777e0-120">**要求ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="777e0-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="777e0-121">**リクエストの本文**の [なし] です。</span><span class="sxs-lookup"><span data-stu-id="777e0-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="777e0-122">**応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="777e0-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="777e0-123">**ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。</span><span class="sxs-lookup"><span data-stu-id="777e0-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="777e0-124">**応答ヘッダー**の追加のヘッダーではありません。</span><span class="sxs-lookup"><span data-stu-id="777e0-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="777e0-125">**応答本体**のログ エントリの構造の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="777e0-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


