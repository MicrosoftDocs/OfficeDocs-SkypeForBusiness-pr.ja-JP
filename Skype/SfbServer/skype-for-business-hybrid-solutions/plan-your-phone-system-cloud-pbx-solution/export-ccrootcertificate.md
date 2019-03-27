---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: 'Export-CcRootCertificate コマンドレットはルート CA 証明書を Skype for Business Cloud Connector エディションのホスト サーバー上のローカル ファイルにエクスポートします。 '
ms.openlocfilehash: c2647baa9ab6762feb8f550e0d726b18ab5d3090
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889225"
---
# <a name="export-ccrootcertificate"></a><span data-ttu-id="b3c87-103">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="b3c87-103">Export-CcRootCertificate</span></span>
 
<span data-ttu-id="b3c87-104">Export-CcRootCertificate コマンドレットはルート CA 証明書を Skype for Business Cloud Connector エディションのホスト サーバー上のローカル ファイルにエクスポートします。 </span><span class="sxs-lookup"><span data-stu-id="b3c87-104">The Export-CcRootCertificate cmdlet exports the root CA certificate to a local file on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
```
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="b3c87-105">例</span><span class="sxs-lookup"><span data-stu-id="b3c87-105">Examples</span></span>
<span data-ttu-id="b3c87-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b3c87-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="b3c87-107">例 1</span><span class="sxs-lookup"><span data-stu-id="b3c87-107">Example 1</span></span>

<span data-ttu-id="b3c87-p101">次の例では、Path パラメータをファイル パスではなくディレクトリ パスで設定します。 これによって、ファイル c:\test\CCERootCertificates.p7b が生成されます。</span><span class="sxs-lookup"><span data-stu-id="b3c87-p101">The following example sets the Path parameter as a directory path—not a file path. It generates the file c:\test\CCERootCertificates.p7b.</span></span>
  
```
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a><span data-ttu-id="b3c87-110">解説</span><span class="sxs-lookup"><span data-stu-id="b3c87-110">Detailed Description</span></span>
<span data-ttu-id="b3c87-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b3c87-111"></span></span>

<span data-ttu-id="b3c87-p102">Export-CcRootCertificate コマンドレットを使用すると、ルートおよび中間証明書をファイル パスに保存することができます。 これは、障害復旧シナリオの場合に役立ちます。 </span><span class="sxs-lookup"><span data-stu-id="b3c87-p102">The Export-CcRootCertificate cmdlet allows you to save the root and intermediate certificates to a file path. This can be useful in case of a disaster recovery scenario.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="b3c87-114">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b3c87-114">Parameters</span></span>
<span data-ttu-id="b3c87-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b3c87-115"></span></span>

|<span data-ttu-id="b3c87-116">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="b3c87-116">**Parameter**</span></span>|<span data-ttu-id="b3c87-117">**必須**</span><span class="sxs-lookup"><span data-stu-id="b3c87-117">**Required**</span></span>|<span data-ttu-id="b3c87-118">**型**</span><span class="sxs-lookup"><span data-stu-id="b3c87-118">**Type**</span></span>|<span data-ttu-id="b3c87-119">**説明**</span><span class="sxs-lookup"><span data-stu-id="b3c87-119">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b3c87-120">Path</span><span class="sxs-lookup"><span data-stu-id="b3c87-120">Path</span></span>  <br/> |<span data-ttu-id="b3c87-121">必須</span><span class="sxs-lookup"><span data-stu-id="b3c87-121">Required</span></span>  <br/> |<span data-ttu-id="b3c87-122">System.String</span><span class="sxs-lookup"><span data-stu-id="b3c87-122">System.String</span></span>  <br/> |<span data-ttu-id="b3c87-123">証明書が保存されるファイル パス。 </span><span class="sxs-lookup"><span data-stu-id="b3c87-123">File path where the certificate will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="b3c87-124">入力の種類</span><span class="sxs-lookup"><span data-stu-id="b3c87-124">Input Types</span></span>
<span data-ttu-id="b3c87-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b3c87-125"></span></span>

<span data-ttu-id="b3c87-p103">なし。 Export-CcRootCertificate コマンドレットはパイプライン入力を受け入れません。 </span><span class="sxs-lookup"><span data-stu-id="b3c87-p103">None. The Export-CcRootCertificate cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="b3c87-128">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="b3c87-128">Return Types</span></span>
<span data-ttu-id="b3c87-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b3c87-129"></span></span>

<span data-ttu-id="b3c87-130">なし</span><span class="sxs-lookup"><span data-stu-id="b3c87-130">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b3c87-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3c87-131">See also</span></span>
<span data-ttu-id="b3c87-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b3c87-132"></span></span>

<span data-ttu-id="b3c87-133">なし</span><span class="sxs-lookup"><span data-stu-id="b3c87-133">None</span></span>
  

