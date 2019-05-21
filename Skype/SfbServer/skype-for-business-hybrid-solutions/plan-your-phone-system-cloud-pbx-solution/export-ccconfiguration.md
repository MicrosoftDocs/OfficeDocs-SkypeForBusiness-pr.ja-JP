---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Skype for Business Cloud Connector エディションの構成を、Skype for Business Cloud Connector エディションのホスト サーバー上のローカル ファイルにエクスポートします。
ms.openlocfilehash: 7548b2fba602364d98c7540607660ccc57710654
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287420"
---
# <a name="export-ccconfiguration"></a><span data-ttu-id="b4451-103">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="b4451-103">Export-CcConfiguration</span></span>
 
<span data-ttu-id="b4451-104">Skype for Business Cloud Connector エディションの構成を、Skype for Business Cloud Connector エディションのホスト サーバー上のローカル ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="b4451-104">Exports the Skype for Business Cloud Connector Edition configuration to a local file on the Skype for Business Cloud Connector Edition host server.</span></span>
  
```
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="b4451-105">例</span><span class="sxs-lookup"><span data-stu-id="b4451-105">Examples</span></span>
<span data-ttu-id="b4451-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b4451-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="b4451-107">例 1</span><span class="sxs-lookup"><span data-stu-id="b4451-107">Example 1</span></span>

<span data-ttu-id="b4451-108">次の例では、Path パラメータをフル ファイル パスで設定して、そのファイルに構成をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="b4451-108">The following example sets the Path parameter as a full file path and exports configurations to that file.</span></span>
  
```
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a><span data-ttu-id="b4451-109">解説</span><span class="sxs-lookup"><span data-stu-id="b4451-109">Detailed Description</span></span>
<span data-ttu-id="b4451-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b4451-110"></span></span>

<span data-ttu-id="b4451-p101">Export-CcConfiguration コマンドレットを使用すると、Cloud Connector 構成を選択したパスのファイルに保存できます。 このコマンドは Cloud Connector Edition バージョン 2.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b4451-p101">The Export-CcConfiguration cmdlet allows you to save the Cloud Connector configuration to a file in a selected path. This command was introduced in Cloud Connector Edition version 2.0.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="b4451-113">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b4451-113">Parameters</span></span>
<span data-ttu-id="b4451-114"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b4451-114"></span></span>

|<span data-ttu-id="b4451-115">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="b4451-115">**Parameter**</span></span>|<span data-ttu-id="b4451-116">**必須**</span><span class="sxs-lookup"><span data-stu-id="b4451-116">**Required**</span></span>|<span data-ttu-id="b4451-117">**型**</span><span class="sxs-lookup"><span data-stu-id="b4451-117">**Type**</span></span>|<span data-ttu-id="b4451-118">**説明**</span><span class="sxs-lookup"><span data-stu-id="b4451-118">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b4451-119">Path</span><span class="sxs-lookup"><span data-stu-id="b4451-119">Path</span></span>  <br/> |<span data-ttu-id="b4451-120">必須</span><span class="sxs-lookup"><span data-stu-id="b4451-120">Required</span></span>  <br/> |<span data-ttu-id="b4451-121">System.String</span><span class="sxs-lookup"><span data-stu-id="b4451-121">System.String</span></span>  <br/> |<span data-ttu-id="b4451-122">Cloud Connector 構成が保存されるフル ファイル パス。</span><span class="sxs-lookup"><span data-stu-id="b4451-122">Full file path where the Cloud Connector configurations will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="b4451-123">入力の種類</span><span class="sxs-lookup"><span data-stu-id="b4451-123">Input Types</span></span>
<span data-ttu-id="b4451-124"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b4451-124"></span></span>

<span data-ttu-id="b4451-p102">なし。 Export-CcConfiguration コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="b4451-p102">None. The Export-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b4451-127">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="b4451-127">Return Types</span></span>
<span data-ttu-id="b4451-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b4451-128"></span></span>

<span data-ttu-id="b4451-129">なし。</span><span class="sxs-lookup"><span data-stu-id="b4451-129">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b4451-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4451-130">See also</span></span>
<span data-ttu-id="b4451-131"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b4451-131"></span></span>

<span data-ttu-id="b4451-132">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="b4451-132">Import-CcConfiguration</span></span>
  

