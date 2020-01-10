---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: 'Export-CcRootCertificate コマンドレットはルート CA 証明書を Skype for Business Cloud Connector エディションのホスト サーバー上のローカル ファイルにエクスポートします。 '
ms.openlocfilehash: 90eadb257d91a05c05fabbfe1db84b8160ad4a7c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003417"
---
# <a name="export-ccrootcertificate"></a><span data-ttu-id="e240f-103">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="e240f-103">Export-CcRootCertificate</span></span>
 
<span data-ttu-id="e240f-104">Export-CcRootCertificate コマンドレットはルート CA 証明書を Skype for Business Cloud Connector エディションのホスト サーバー上のローカル ファイルにエクスポートします。 </span><span class="sxs-lookup"><span data-stu-id="e240f-104">The Export-CcRootCertificate cmdlet exports the root CA certificate to a local file on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
```powershell
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="e240f-105">例</span><span class="sxs-lookup"><span data-stu-id="e240f-105">Examples</span></span>
<span data-ttu-id="e240f-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e240f-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="e240f-107">例 1</span><span class="sxs-lookup"><span data-stu-id="e240f-107">Example 1</span></span>

<span data-ttu-id="e240f-p101">次の例では、Path パラメータをファイル パスではなくディレクトリ パスで設定します。 これによって、ファイル c:\test\CCERootCertificates.p7b が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e240f-p101">The following example sets the Path parameter as a directory path—not a file path. It generates the file c:\test\CCERootCertificates.p7b.</span></span>
  
```powershell
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a><span data-ttu-id="e240f-110">解説</span><span class="sxs-lookup"><span data-stu-id="e240f-110">Detailed Description</span></span>
<span data-ttu-id="e240f-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e240f-111"></span></span>

<span data-ttu-id="e240f-p102">Export-CcRootCertificate コマンドレットを使用すると、ルートおよび中間証明書をファイル パスに保存することができます。 これは、障害復旧シナリオの場合に役立ちます。 </span><span class="sxs-lookup"><span data-stu-id="e240f-p102">The Export-CcRootCertificate cmdlet allows you to save the root and intermediate certificates to a file path. This can be useful in case of a disaster recovery scenario.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="e240f-114">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e240f-114">Parameters</span></span>
<span data-ttu-id="e240f-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e240f-115"></span></span>

|<span data-ttu-id="e240f-116">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="e240f-116">**Parameter**</span></span>|<span data-ttu-id="e240f-117">**必須**</span><span class="sxs-lookup"><span data-stu-id="e240f-117">**Required**</span></span>|<span data-ttu-id="e240f-118">**種類**</span><span class="sxs-lookup"><span data-stu-id="e240f-118">**Type**</span></span>|<span data-ttu-id="e240f-119">**説明**</span><span class="sxs-lookup"><span data-stu-id="e240f-119">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e240f-120">Path</span><span class="sxs-lookup"><span data-stu-id="e240f-120">Path</span></span>  <br/> |<span data-ttu-id="e240f-121">必須</span><span class="sxs-lookup"><span data-stu-id="e240f-121">Required</span></span>  <br/> |<span data-ttu-id="e240f-122">System.String</span><span class="sxs-lookup"><span data-stu-id="e240f-122">System.String</span></span>  <br/> |<span data-ttu-id="e240f-123">証明書が保存されるファイル パス。 </span><span class="sxs-lookup"><span data-stu-id="e240f-123">File path where the certificate will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="e240f-124">入力の種類</span><span class="sxs-lookup"><span data-stu-id="e240f-124">Input Types</span></span>
<span data-ttu-id="e240f-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e240f-125"></span></span>

<span data-ttu-id="e240f-p103">なし。 Export-CcRootCertificate コマンドレットはパイプライン入力を受け入れません。 </span><span class="sxs-lookup"><span data-stu-id="e240f-p103">None. The Export-CcRootCertificate cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="e240f-128">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="e240f-128">Return Types</span></span>
<span data-ttu-id="e240f-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e240f-129"></span></span>

<span data-ttu-id="e240f-130">なし</span><span class="sxs-lookup"><span data-stu-id="e240f-130">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e240f-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="e240f-131">See also</span></span>
<span data-ttu-id="e240f-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e240f-132"></span></span>

<span data-ttu-id="e240f-133">なし</span><span class="sxs-lookup"><span data-stu-id="e240f-133">None</span></span>
  

