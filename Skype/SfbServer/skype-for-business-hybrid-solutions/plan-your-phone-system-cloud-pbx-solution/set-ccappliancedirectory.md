---
title: セット CcApplianceDirectory
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
ms.openlocfilehash: 67fda4f1ef7da0f9a7e61b1099c7edb3b96ad62c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="set-ccappliancedirectory"></a><span data-ttu-id="6e831-104">セット CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="6e831-104">Set-CcApplianceDirectory</span></span>
 
<span data-ttu-id="6e831-p102">Set-CcApplianceDirectory コマンドレットは、Skype for Business Cloud Connector エディションのホスト サーバーでの作業ディレクトリを設定します。すべての展開ファイルはこのディレクトリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="6e831-p102">The Set-CcApplianceDirectory cmdlet sets the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span>
  
```
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="6e831-107">例</span><span class="sxs-lookup"><span data-stu-id="6e831-107">Examples</span></span>
<span data-ttu-id="6e831-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6e831-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="6e831-109">例 1</span><span class="sxs-lookup"><span data-stu-id="6e831-109">Example 1</span></span>

<span data-ttu-id="6e831-110">次の例は、ホスト サーバーでの作業ディレクトリを c:\cloudconnector\applianceroot に設定します。</span><span class="sxs-lookup"><span data-stu-id="6e831-110">The following example sets the working directory on the host server to c:\cloudconnector\applianceroot:</span></span>
  
```
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a><span data-ttu-id="6e831-111">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6e831-111">Parameters</span></span>
<span data-ttu-id="6e831-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6e831-112"></span></span>

|<span data-ttu-id="6e831-113">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="6e831-113">**Parameter**</span></span>|<span data-ttu-id="6e831-114">**必須**</span><span class="sxs-lookup"><span data-stu-id="6e831-114">**Required**</span></span>|<span data-ttu-id="6e831-115">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="6e831-115">**Type**</span></span>|<span data-ttu-id="6e831-116">**説明**</span><span class="sxs-lookup"><span data-stu-id="6e831-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="6e831-117"> Path</span><span class="sxs-lookup"><span data-stu-id="6e831-117">Path</span></span> <br/> | <span data-ttu-id="6e831-118">必須</span><span class="sxs-lookup"><span data-stu-id="6e831-118">Required</span></span> <br/> |<span data-ttu-id="6e831-119">System.String</span><span class="sxs-lookup"><span data-stu-id="6e831-119">System.String</span></span>  <br/> | <span data-ttu-id="6e831-120">すべての展開ファイルが格納されるパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="6e831-120">Specifies the path where all deployment files are stored.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="6e831-121">入力の種類</span><span class="sxs-lookup"><span data-stu-id="6e831-121">Input Types</span></span>
<span data-ttu-id="6e831-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6e831-122"></span></span>

<span data-ttu-id="6e831-p103">なし。Set-CcApplianceDirectory コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="6e831-p103">None. The Set-CcApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="6e831-125">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="6e831-125">Return Types</span></span>
<span data-ttu-id="6e831-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6e831-126"></span></span>

<span data-ttu-id="6e831-127">なし</span><span class="sxs-lookup"><span data-stu-id="6e831-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6e831-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e831-128">See also</span></span>
<span data-ttu-id="6e831-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6e831-129"></span></span>

<span data-ttu-id="6e831-130">なし</span><span class="sxs-lookup"><span data-stu-id="6e831-130">None</span></span>
  

