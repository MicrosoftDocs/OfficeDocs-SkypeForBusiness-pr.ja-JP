---
title: Stop CcLogging
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Stop CcLogging コマンドレットでは、ビジネス クラウド コネクタ ・ エディションのアプライアンス用の Skype の着信および発信呼び出しのログの生成を停止します。
ms.openlocfilehash: abecc5acc6a454b2965fbf79caadb23f2256e4cd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="stop-cclogging"></a><span data-ttu-id="b9182-103">Stop CcLogging</span><span class="sxs-lookup"><span data-stu-id="b9182-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="b9182-104">Stop CcLogging コマンドレットでは、ビジネス クラウド コネクタ ・ エディションのアプライアンス用の Skype の着信および発信呼び出しのログの生成を停止します。</span><span class="sxs-lookup"><span data-stu-id="b9182-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="b9182-105">例</span><span class="sxs-lookup"><span data-stu-id="b9182-105">Examples</span></span>
<span data-ttu-id="b9182-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b9182-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="b9182-107">例 1</span><span class="sxs-lookup"><span data-stu-id="b9182-107">Example 1</span></span>

<span data-ttu-id="b9182-108">次の例では、着信および発信の通話ログの生成を停止します。</span><span class="sxs-lookup"><span data-stu-id="b9182-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="b9182-109">例 2</span><span class="sxs-lookup"><span data-stu-id="b9182-109">Example 2</span></span>

<span data-ttu-id="b9182-110">次の例では、着信および発信の通話ログの生成を停止して、キャッシュ ファイルをクリーン　アップします。</span><span class="sxs-lookup"><span data-stu-id="b9182-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="b9182-111">解説</span><span class="sxs-lookup"><span data-stu-id="b9182-111">Detailed Description</span></span>
<span data-ttu-id="b9182-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b9182-112"></span></span>

<span data-ttu-id="b9182-p101">Stop-CcLogging コマンドレットは、アプライアンスでの着信および発信の通話のログを停止します。既定では、ログは 4 時間後に自動的に停止します。</span><span class="sxs-lookup"><span data-stu-id="b9182-p101">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance. By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="b9182-115">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b9182-115">Parameters</span></span>
<span data-ttu-id="b9182-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b9182-116"></span></span>

|<span data-ttu-id="b9182-117">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="b9182-117">**Parameter**</span></span>|<span data-ttu-id="b9182-118">**必須**</span><span class="sxs-lookup"><span data-stu-id="b9182-118">**Required**</span></span>|<span data-ttu-id="b9182-119">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="b9182-119">**Type**</span></span>|<span data-ttu-id="b9182-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="b9182-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="b9182-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="b9182-121">RemoveCache</span></span> <br/> | <span data-ttu-id="b9182-122">省略可能</span><span class="sxs-lookup"><span data-stu-id="b9182-122">Optional</span></span> <br/> | <span data-ttu-id="b9182-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="b9182-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="b9182-124">ログのキャッシュ ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="b9182-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="b9182-125">入力の種類</span><span class="sxs-lookup"><span data-stu-id="b9182-125">Input Types</span></span>
<span data-ttu-id="b9182-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b9182-126"></span></span>

<span data-ttu-id="b9182-p102">なし。Stop-CcLogging コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="b9182-p102">None. The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b9182-129">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="b9182-129">Return Types</span></span>
<span data-ttu-id="b9182-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b9182-130"></span></span>

<span data-ttu-id="b9182-131">なし</span><span class="sxs-lookup"><span data-stu-id="b9182-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b9182-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9182-132">See also</span></span>
<span data-ttu-id="b9182-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b9182-133"></span></span>

[<span data-ttu-id="b9182-134">検索 CcLog</span><span class="sxs-lookup"><span data-stu-id="b9182-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="b9182-135">開始 CcLogging</span><span class="sxs-lookup"><span data-stu-id="b9182-135">Start-CcLogging</span></span>](start-cclogging.md)
  

