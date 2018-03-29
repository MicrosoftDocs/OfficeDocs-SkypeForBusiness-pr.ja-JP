---
title: 開始 CcLogging
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 01b62253-2aaf-43ed-9d63-804e31edc522
description: Start-CcLogging コマンドレットは、Skype for Business Cloud Connector エディションのアプライアンスで、着信および発信の通話ログを生成します。
ms.openlocfilehash: 26056f06ed8d7d3982729e9caab69a01eca189d6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="start-cclogging"></a><span data-ttu-id="1e065-103">開始 CcLogging</span><span class="sxs-lookup"><span data-stu-id="1e065-103">Start-CcLogging</span></span>
 
<span data-ttu-id="1e065-104">Start-CcLogging コマンドレットは、Skype for Business Cloud Connector エディションのアプライアンスで、着信および発信の通話ログを生成します。</span><span class="sxs-lookup"><span data-stu-id="1e065-104">The Start-CcLogging cmdlet generates the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span> 
  
```
Start-CcLogging
```

## <a name="parameters"></a><span data-ttu-id="1e065-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e065-105">Parameters</span></span>

<span data-ttu-id="1e065-106">なし</span><span class="sxs-lookup"><span data-stu-id="1e065-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="1e065-107">例</span><span class="sxs-lookup"><span data-stu-id="1e065-107">Examples</span></span>
<span data-ttu-id="1e065-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1e065-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="1e065-109">例 1</span><span class="sxs-lookup"><span data-stu-id="1e065-109">Example 1</span></span>

<span data-ttu-id="1e065-110">次の例では、着信および発信の通話ログを生成します。</span><span class="sxs-lookup"><span data-stu-id="1e065-110">The following example generates the incoming and outgoing call log:</span></span>
  
```
Start-CcLogging
```

## <a name="detailed-description"></a><span data-ttu-id="1e065-111">解説</span><span class="sxs-lookup"><span data-stu-id="1e065-111">Detailed Description</span></span>
<span data-ttu-id="1e065-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1e065-112"></span></span>

<span data-ttu-id="1e065-113">開始 CcLogging コマンドレットでは、管理者クラウド コネクタ アプライアンス上の着信および発信呼び出しのログを記録するための手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="1e065-113">The Start-CcLogging cmdlet provides a way for administrators to begin logging incoming and outgoing calls on a Cloud Connector appliance.</span></span> <span data-ttu-id="1e065-114">既定では、ログは 4 時間後に自動的に停止します。</span><span class="sxs-lookup"><span data-stu-id="1e065-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="1e065-115">入力の種類</span><span class="sxs-lookup"><span data-stu-id="1e065-115">Input Types</span></span>
<span data-ttu-id="1e065-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1e065-116"></span></span>

<span data-ttu-id="1e065-p102">なし。Start-CcLogging コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="1e065-p102">None. The Start-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="1e065-119">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="1e065-119">Return Types</span></span>
<span data-ttu-id="1e065-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1e065-120"></span></span>

<span data-ttu-id="1e065-121">なし</span><span class="sxs-lookup"><span data-stu-id="1e065-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1e065-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e065-122">See also</span></span>
<span data-ttu-id="1e065-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1e065-123"></span></span>

[<span data-ttu-id="1e065-124">検索 CcLog</span><span class="sxs-lookup"><span data-stu-id="1e065-124">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="1e065-125">Stop CcLogging</span><span class="sxs-lookup"><span data-stu-id="1e065-125">Stop-CcLogging</span></span>](stop-cclogging.md)
  

