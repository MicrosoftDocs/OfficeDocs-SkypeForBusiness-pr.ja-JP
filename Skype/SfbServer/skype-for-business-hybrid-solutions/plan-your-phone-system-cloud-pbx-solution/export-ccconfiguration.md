---
title: エクスポート CcConfiguration
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Skype for Business Cloud Connector エディションの構成を、Skype for Business Cloud Connector エディションのホスト サーバー上のローカル ファイルにエクスポートします。
ms.openlocfilehash: dfabf5f486190b13acd18f0ffcf67f9b7e37052c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="export-ccconfiguration"></a><span data-ttu-id="b96ab-103">エクスポート CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="b96ab-103">Export-CcConfiguration</span></span>
 
<span data-ttu-id="b96ab-104">Skype for Business Cloud Connector エディションの構成を、Skype for Business Cloud Connector エディションのホスト サーバー上のローカル ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="b96ab-104">Exports the Skype for Business Cloud Connector Edition configuration to a local file on the Skype for Business Cloud Connector Edition host server.</span></span>
  
```
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="b96ab-105">例</span><span class="sxs-lookup"><span data-stu-id="b96ab-105">Examples</span></span>
<span data-ttu-id="b96ab-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b96ab-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="b96ab-107">例 1</span><span class="sxs-lookup"><span data-stu-id="b96ab-107">Example 1</span></span>

<span data-ttu-id="b96ab-108">次の例では、Path パラメータをフル ファイル パスで設定して、そのファイルに構成をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="b96ab-108">The following example sets the Path parameter as a full file path and exports configurations to that file.</span></span>
  
```
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a><span data-ttu-id="b96ab-109">解説</span><span class="sxs-lookup"><span data-stu-id="b96ab-109">Detailed Description</span></span>
<span data-ttu-id="b96ab-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b96ab-110"></span></span>

<span data-ttu-id="b96ab-111">Export-CcConfiguration コマンドレットを使用すると、Cloud Connector 構成を選択したパスのファイルに保存できます。</span><span class="sxs-lookup"><span data-stu-id="b96ab-111">The Export-CcConfiguration cmdlet allows you to save the Cloud Connector configuration to a file in a selected path.</span></span> <span data-ttu-id="b96ab-112">このコマンドは Cloud Connector Edition バージョン 2.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b96ab-112">This command was introduced in Cloud Connector Edition version 2.0.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="b96ab-113">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b96ab-113">Parameters</span></span>
<span data-ttu-id="b96ab-114"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b96ab-114"></span></span>

|<span data-ttu-id="b96ab-115">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="b96ab-115">**Parameter**</span></span>|<span data-ttu-id="b96ab-116">**必須**</span><span class="sxs-lookup"><span data-stu-id="b96ab-116">**Required**</span></span>|<span data-ttu-id="b96ab-117">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="b96ab-117">**Type**</span></span>|<span data-ttu-id="b96ab-118">**説明**</span><span class="sxs-lookup"><span data-stu-id="b96ab-118">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b96ab-119"> Path</span><span class="sxs-lookup"><span data-stu-id="b96ab-119">Path</span></span>  <br/> |<span data-ttu-id="b96ab-120">必須</span><span class="sxs-lookup"><span data-stu-id="b96ab-120">Required</span></span>  <br/> |<span data-ttu-id="b96ab-121">System.String</span><span class="sxs-lookup"><span data-stu-id="b96ab-121">System.String</span></span>  <br/> |<span data-ttu-id="b96ab-122">Cloud Connector 構成が保存されるフル ファイル パス。</span><span class="sxs-lookup"><span data-stu-id="b96ab-122">Full file path where the Cloud Connector configurations will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="b96ab-123">入力の種類</span><span class="sxs-lookup"><span data-stu-id="b96ab-123">Input Types</span></span>
<span data-ttu-id="b96ab-124"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b96ab-124"></span></span>

<span data-ttu-id="b96ab-125">なし。</span><span class="sxs-lookup"><span data-stu-id="b96ab-125">None.</span></span> <span data-ttu-id="b96ab-126">Export-CcConfiguration コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="b96ab-126">The Export-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b96ab-127">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="b96ab-127">Return Types</span></span>
<span data-ttu-id="b96ab-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b96ab-128"></span></span>

<span data-ttu-id="b96ab-129">なし。</span><span class="sxs-lookup"><span data-stu-id="b96ab-129">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b96ab-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="b96ab-130">See also</span></span>
<span data-ttu-id="b96ab-131"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b96ab-131"></span></span>

<span data-ttu-id="b96ab-132">インポート-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="b96ab-132">Import-CcConfiguration</span></span>
  

