---
title: Get-CcSiteLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: Get-CcSiteLogDirectory コマンドレットは、Skype for Business Cloud Connector エディションのサイト レベルのログが格納されている現在のディレクトリを示します。
ms.openlocfilehash: c4354920ac25d076e550c5eda3a641eef0c8b900
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886128"
---
# <a name="get-ccsitelogdirectory"></a><span data-ttu-id="31260-103">Get-CcSiteLogDirectory</span><span class="sxs-lookup"><span data-stu-id="31260-103">Get-CcSiteLogDirectory</span></span>
 
<span data-ttu-id="31260-104">Get-CcSiteLogDirectory コマンドレットは、Skype for Business Cloud Connector エディションのサイト レベルのログが格納されている現在のディレクトリを示します。</span><span class="sxs-lookup"><span data-stu-id="31260-104">The Get-CcSiteLogDirectory cmdlet shows the current directory where the site level logs for Skype for Business Cloud Connector Edition are stored.</span></span> 
  
<span data-ttu-id="31260-105">このコマンドレットは、Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="31260-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcSiteLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="31260-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="31260-106">Parameters</span></span>

<span data-ttu-id="31260-107">なし</span><span class="sxs-lookup"><span data-stu-id="31260-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="31260-108">例</span><span class="sxs-lookup"><span data-stu-id="31260-108">Examples</span></span>
<span data-ttu-id="31260-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="31260-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="31260-110">例 1</span><span class="sxs-lookup"><span data-stu-id="31260-110">Example 1</span></span>

<span data-ttu-id="31260-111">クラウド コネクタ サイトのログ ファイルが保存されている現在のフォルダーを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="31260-111">The following example shows the current folder where the log files for the Cloud Connector site are stored:</span></span>
  
```
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="31260-112">解説</span><span class="sxs-lookup"><span data-stu-id="31260-112">Detailed Description</span></span>
<span data-ttu-id="31260-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="31260-113"></span></span>

<span data-ttu-id="31260-114">既定のフォルダーは、C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs。</span><span class="sxs-lookup"><span data-stu-id="31260-114">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs.</span></span> <span data-ttu-id="31260-115">Set-CcSiteDirectory コマンドレットを実行することで、このフォルダーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="31260-115">You can change the folder by running the Set-CcSiteDirectory cmdlet.</span></span> <span data-ttu-id="31260-116">サイト ディレクトリを変更せずにログ フォルダーの場所のみを変更するコマンドレットはありません。</span><span class="sxs-lookup"><span data-stu-id="31260-116">There is no separate cmdlet that changes only the log folder location without changing the site directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="31260-117">入力の種類</span><span class="sxs-lookup"><span data-stu-id="31260-117">Input Types</span></span>
<span data-ttu-id="31260-118"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="31260-118"></span></span>

<span data-ttu-id="31260-p102">なし。Get-CcSiteLogDirectory コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="31260-p102">None. The Get-CcSiteLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="31260-121">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="31260-121">Return Types</span></span>
<span data-ttu-id="31260-122"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="31260-122"></span></span>

<span data-ttu-id="31260-123">このコマンドはファイル パスを返します。</span><span class="sxs-lookup"><span data-stu-id="31260-123">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="31260-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="31260-124">See also</span></span>
<span data-ttu-id="31260-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="31260-125"></span></span>

[<span data-ttu-id="31260-126">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="31260-126">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

