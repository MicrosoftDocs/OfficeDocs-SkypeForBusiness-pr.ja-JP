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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Stop-CcLogging コマンドレットは、Skype for Business Cloud Connector エディションのアプライアンスで、着信および発信の通話ログの生成を停止します。
ms.openlocfilehash: 8a012e9b1a94c3698cc61da4326eb0ccbb27bca2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824161"
---
# <a name="stop-cclogging"></a><span data-ttu-id="81b95-103">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="81b95-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="81b95-104">Stop-CcLogging コマンドレットは、Skype for Business Cloud Connector エディションのアプライアンスで、着信および発信の通話ログの生成を停止します。</span><span class="sxs-lookup"><span data-stu-id="81b95-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="81b95-105">例</span><span class="sxs-lookup"><span data-stu-id="81b95-105">Examples</span></span>
<span data-ttu-id="81b95-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="81b95-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="81b95-107">例 1</span><span class="sxs-lookup"><span data-stu-id="81b95-107">Example 1</span></span>

<span data-ttu-id="81b95-108">次の例では、着信および発信の通話ログの生成を停止します。</span><span class="sxs-lookup"><span data-stu-id="81b95-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="81b95-109">例 2</span><span class="sxs-lookup"><span data-stu-id="81b95-109">Example 2</span></span>

<span data-ttu-id="81b95-110">次の例では、着信および発信の通話ログの生成を停止して、キャッシュ ファイルをクリーン　アップします。</span><span class="sxs-lookup"><span data-stu-id="81b95-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="81b95-111">解説</span><span class="sxs-lookup"><span data-stu-id="81b95-111">Detailed Description</span></span>
<span data-ttu-id="81b95-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="81b95-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="81b95-113">Stop-CcLogging コマンドレットは、アプライアンスでの着信および発信の通話のログを停止します。</span><span class="sxs-lookup"><span data-stu-id="81b95-113">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance.</span></span> <span data-ttu-id="81b95-114">既定では、ログは 4 時間後に自動的に停止します。</span><span class="sxs-lookup"><span data-stu-id="81b95-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="81b95-115">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81b95-115">Parameters</span></span>
<span data-ttu-id="81b95-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="81b95-116"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="81b95-117">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="81b95-117">**Parameter**</span></span>|<span data-ttu-id="81b95-118">**必須**</span><span class="sxs-lookup"><span data-stu-id="81b95-118">**Required**</span></span>|<span data-ttu-id="81b95-119">**種類**</span><span class="sxs-lookup"><span data-stu-id="81b95-119">**Type**</span></span>|<span data-ttu-id="81b95-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="81b95-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="81b95-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="81b95-121">RemoveCache</span></span> <br/> | <span data-ttu-id="81b95-122">省略可能</span><span class="sxs-lookup"><span data-stu-id="81b95-122">Optional</span></span> <br/> | <span data-ttu-id="81b95-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="81b95-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="81b95-124">ログのキャッシュ ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="81b95-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="81b95-125">入力の種類</span><span class="sxs-lookup"><span data-stu-id="81b95-125">Input Types</span></span>
<span data-ttu-id="81b95-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="81b95-126"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="81b95-p102">なし。Stop-CcLogging コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="81b95-p102">None. The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="81b95-129">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="81b95-129">Return Types</span></span>
<span data-ttu-id="81b95-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="81b95-130"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="81b95-131">なし</span><span class="sxs-lookup"><span data-stu-id="81b95-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="81b95-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="81b95-132">See also</span></span>
<span data-ttu-id="81b95-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="81b95-133"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="81b95-134">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="81b95-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="81b95-135">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="81b95-135">Start-CcLogging</span></span>](start-cclogging.md)
  

