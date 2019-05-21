---
title: Stop-CcLogging
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Stop-CcLogging コマンドレットは、Skype for Business Cloud Connector エディションのアプライアンスで、着信および発信の通話ログの生成を停止します。
ms.openlocfilehash: dcc62e8ec772912a8275f5321a6c91e28dde8c25
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286937"
---
# <a name="stop-cclogging"></a><span data-ttu-id="3b0e0-103">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="3b0e0-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="3b0e0-104">Stop-CcLogging コマンドレットは、Skype for Business Cloud Connector エディションのアプライアンスで、着信および発信の通話ログの生成を停止します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="3b0e0-105">例</span><span class="sxs-lookup"><span data-stu-id="3b0e0-105">Examples</span></span>
<span data-ttu-id="3b0e0-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3b0e0-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="3b0e0-107">例 1</span><span class="sxs-lookup"><span data-stu-id="3b0e0-107">Example 1</span></span>

<span data-ttu-id="3b0e0-108">次の例では、着信および発信の通話ログの生成を停止します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="3b0e0-109">例 2</span><span class="sxs-lookup"><span data-stu-id="3b0e0-109">Example 2</span></span>

<span data-ttu-id="3b0e0-110">次の例では、着信および発信の通話ログの生成を停止して、キャッシュ ファイルをクリーン　アップします。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="3b0e0-111">解説</span><span class="sxs-lookup"><span data-stu-id="3b0e0-111">Detailed Description</span></span>
<span data-ttu-id="3b0e0-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3b0e0-112"></span></span>

<span data-ttu-id="3b0e0-113">Stop-CcLogging コマンドレットは、アプライアンスでの着信および発信の通話のログを停止します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-113">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance.</span></span> <span data-ttu-id="3b0e0-114">既定では、ログは 4 時間後に自動的に停止します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="3b0e0-115">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3b0e0-115">Parameters</span></span>
<span data-ttu-id="3b0e0-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3b0e0-116"></span></span>

|<span data-ttu-id="3b0e0-117">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="3b0e0-117">**Parameter**</span></span>|<span data-ttu-id="3b0e0-118">**必須**</span><span class="sxs-lookup"><span data-stu-id="3b0e0-118">**Required**</span></span>|<span data-ttu-id="3b0e0-119">**型**</span><span class="sxs-lookup"><span data-stu-id="3b0e0-119">**Type**</span></span>|<span data-ttu-id="3b0e0-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="3b0e0-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="3b0e0-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="3b0e0-121">RemoveCache</span></span> <br/> | <span data-ttu-id="3b0e0-122">省略可能</span><span class="sxs-lookup"><span data-stu-id="3b0e0-122">Optional</span></span> <br/> | <span data-ttu-id="3b0e0-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="3b0e0-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="3b0e0-124">ログのキャッシュ ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="3b0e0-125">入力の種類</span><span class="sxs-lookup"><span data-stu-id="3b0e0-125">Input Types</span></span>
<span data-ttu-id="3b0e0-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3b0e0-126"></span></span>

<span data-ttu-id="3b0e0-p102">なし。Stop-CcLogging コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-p102">None. The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="3b0e0-129">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="3b0e0-129">Return Types</span></span>
<span data-ttu-id="3b0e0-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3b0e0-130"></span></span>

<span data-ttu-id="3b0e0-131">なし</span><span class="sxs-lookup"><span data-stu-id="3b0e0-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3b0e0-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b0e0-132">See also</span></span>
<span data-ttu-id="3b0e0-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3b0e0-133"></span></span>

[<span data-ttu-id="3b0e0-134">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="3b0e0-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="3b0e0-135">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="3b0e0-135">Start-CcLogging</span></span>](start-cclogging.md)
  

