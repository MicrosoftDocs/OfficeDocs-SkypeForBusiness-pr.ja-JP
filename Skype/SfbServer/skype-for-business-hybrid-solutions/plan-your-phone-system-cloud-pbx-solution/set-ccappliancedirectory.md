---
title: Set-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: Set-CcApplianceDirectory コマンドレットは、Skype for Business Cloud Connector エディションのホスト サーバーでの作業ディレクトリを設定します。すべての展開ファイルはこのディレクトリに保存されます。
ms.openlocfilehash: 16c9c858d770b7d4a74c9030ebdc760f5a9f25e9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888183"
---
# <a name="set-ccappliancedirectory"></a><span data-ttu-id="6ab89-104">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="6ab89-104">Set-CcApplianceDirectory</span></span>
 
<span data-ttu-id="6ab89-p102">Set-CcApplianceDirectory コマンドレットは、Skype for Business Cloud Connector エディションのホスト サーバーでの作業ディレクトリを設定します。すべての展開ファイルはこのディレクトリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="6ab89-p102">The Set-CcApplianceDirectory cmdlet sets the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span>
  
```
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="6ab89-107">例</span><span class="sxs-lookup"><span data-stu-id="6ab89-107">Examples</span></span>
<span data-ttu-id="6ab89-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6ab89-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="6ab89-109">例 1</span><span class="sxs-lookup"><span data-stu-id="6ab89-109">Example 1</span></span>

<span data-ttu-id="6ab89-110">次の例は、ホスト サーバーでの作業ディレクトリを c:\cloudconnector\applianceroot に設定します。</span><span class="sxs-lookup"><span data-stu-id="6ab89-110">The following example sets the working directory on the host server to c:\cloudconnector\applianceroot:</span></span>
  
```
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a><span data-ttu-id="6ab89-111">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6ab89-111">Parameters</span></span>
<span data-ttu-id="6ab89-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6ab89-112"></span></span>

|<span data-ttu-id="6ab89-113">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="6ab89-113">**Parameter**</span></span>|<span data-ttu-id="6ab89-114">**必須**</span><span class="sxs-lookup"><span data-stu-id="6ab89-114">**Required**</span></span>|<span data-ttu-id="6ab89-115">**型**</span><span class="sxs-lookup"><span data-stu-id="6ab89-115">**Type**</span></span>|<span data-ttu-id="6ab89-116">**説明**</span><span class="sxs-lookup"><span data-stu-id="6ab89-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="6ab89-117">Path</span><span class="sxs-lookup"><span data-stu-id="6ab89-117">Path</span></span> <br/> | <span data-ttu-id="6ab89-118">必須</span><span class="sxs-lookup"><span data-stu-id="6ab89-118">Required</span></span> <br/> |<span data-ttu-id="6ab89-119">System.String</span><span class="sxs-lookup"><span data-stu-id="6ab89-119">System.String</span></span>  <br/> | <span data-ttu-id="6ab89-120">すべての展開ファイルが格納されるパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="6ab89-120">Specifies the path where all deployment files are stored.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="6ab89-121">入力の種類</span><span class="sxs-lookup"><span data-stu-id="6ab89-121">Input Types</span></span>
<span data-ttu-id="6ab89-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6ab89-122"></span></span>

<span data-ttu-id="6ab89-p103">なし。Set-CcApplianceDirectory コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="6ab89-p103">None. The Set-CcApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="6ab89-125">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="6ab89-125">Return Types</span></span>
<span data-ttu-id="6ab89-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6ab89-126"></span></span>

<span data-ttu-id="6ab89-127">なし</span><span class="sxs-lookup"><span data-stu-id="6ab89-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6ab89-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ab89-128">See also</span></span>
<span data-ttu-id="6ab89-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6ab89-129"></span></span>

<span data-ttu-id="6ab89-130">なし</span><span class="sxs-lookup"><span data-stu-id="6ab89-130">None</span></span>
  

