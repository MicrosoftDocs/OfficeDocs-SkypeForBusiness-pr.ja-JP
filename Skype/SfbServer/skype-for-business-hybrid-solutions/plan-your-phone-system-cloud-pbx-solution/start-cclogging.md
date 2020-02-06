---
title: Start-CcLogging
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
ms.assetid: 01b62253-2aaf-43ed-9d63-804e31edc522
description: Start-CcLogging コマンドレットは、Skype for Business Cloud Connector エディションのアプライアンスで、着信および発信の通話ログを生成します。
ms.openlocfilehash: bf84b55484e7f1d4f557730408676e337063a040
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824171"
---
# <a name="start-cclogging"></a><span data-ttu-id="6fb6e-103">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="6fb6e-103">Start-CcLogging</span></span>
 
<span data-ttu-id="6fb6e-104">Start-CcLogging コマンドレットは、Skype for Business Cloud Connector エディションのアプライアンスで、着信および発信の通話ログを生成します。</span><span class="sxs-lookup"><span data-stu-id="6fb6e-104">The Start-CcLogging cmdlet generates the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span> 
  
```powershell
Start-CcLogging
```

## <a name="parameters"></a><span data-ttu-id="6fb6e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6fb6e-105">Parameters</span></span>

<span data-ttu-id="6fb6e-106">なし</span><span class="sxs-lookup"><span data-stu-id="6fb6e-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="6fb6e-107">例</span><span class="sxs-lookup"><span data-stu-id="6fb6e-107">Examples</span></span>
<span data-ttu-id="6fb6e-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6fb6e-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="6fb6e-109">例 1</span><span class="sxs-lookup"><span data-stu-id="6fb6e-109">Example 1</span></span>

<span data-ttu-id="6fb6e-110">次の例では、着信および発信の通話ログを生成します。</span><span class="sxs-lookup"><span data-stu-id="6fb6e-110">The following example generates the incoming and outgoing call log:</span></span>
  
```powershell
Start-CcLogging
```

## <a name="detailed-description"></a><span data-ttu-id="6fb6e-111">解説</span><span class="sxs-lookup"><span data-stu-id="6fb6e-111">Detailed Description</span></span>
<span data-ttu-id="6fb6e-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="6fb6e-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="6fb6e-113">スタート-CcLogging コマンドレットを使用すると、管理者は、クラウドコネクタアプライアンスでの着信通話と発信通話の記録を開始することができます。</span><span class="sxs-lookup"><span data-stu-id="6fb6e-113">The Start-CcLogging cmdlet provides a way for administrators to begin logging incoming and outgoing calls on a Cloud Connector appliance.</span></span> <span data-ttu-id="6fb6e-114">既定では、ログは 4 時間後に自動的に停止します。</span><span class="sxs-lookup"><span data-stu-id="6fb6e-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="6fb6e-115">入力の種類</span><span class="sxs-lookup"><span data-stu-id="6fb6e-115">Input Types</span></span>
<span data-ttu-id="6fb6e-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6fb6e-116"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="6fb6e-p102">なし。Start-CcLogging コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="6fb6e-p102">None. The Start-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="6fb6e-119">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="6fb6e-119">Return Types</span></span>
<span data-ttu-id="6fb6e-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6fb6e-120"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="6fb6e-121">なし</span><span class="sxs-lookup"><span data-stu-id="6fb6e-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6fb6e-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fb6e-122">See also</span></span>
<span data-ttu-id="6fb6e-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6fb6e-123"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="6fb6e-124">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="6fb6e-124">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="6fb6e-125">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="6fb6e-125">Stop-CcLogging</span></span>](stop-cclogging.md)
  

