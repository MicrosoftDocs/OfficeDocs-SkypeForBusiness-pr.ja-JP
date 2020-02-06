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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: 'Export-CcRootCertificate コマンドレットはルート CA 証明書を Skype for Business Cloud Connector エディションのホスト サーバー上のローカル ファイルにエクスポートします。 '
ms.openlocfilehash: 2b252eba4688deb790d85b0c3663b09a9e85e7b9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800917"
---
# <a name="export-ccrootcertificate"></a><span data-ttu-id="45a95-103">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="45a95-103">Export-CcRootCertificate</span></span>
 
<span data-ttu-id="45a95-104">Export-CcRootCertificate コマンドレットはルート CA 証明書を Skype for Business Cloud Connector エディションのホスト サーバー上のローカル ファイルにエクスポートします。 </span><span class="sxs-lookup"><span data-stu-id="45a95-104">The Export-CcRootCertificate cmdlet exports the root CA certificate to a local file on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
```powershell
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="45a95-105">例</span><span class="sxs-lookup"><span data-stu-id="45a95-105">Examples</span></span>
<span data-ttu-id="45a95-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="45a95-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="45a95-107">例 1</span><span class="sxs-lookup"><span data-stu-id="45a95-107">Example 1</span></span>

<span data-ttu-id="45a95-p101">次の例では、Path パラメータをファイル パスではなくディレクトリ パスで設定します。 これによって、ファイル c:\test\CCERootCertificates.p7b が生成されます。</span><span class="sxs-lookup"><span data-stu-id="45a95-p101">The following example sets the Path parameter as a directory path—not a file path. It generates the file c:\test\CCERootCertificates.p7b.</span></span>
  
```powershell
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a><span data-ttu-id="45a95-110">解説</span><span class="sxs-lookup"><span data-stu-id="45a95-110">Detailed Description</span></span>
<span data-ttu-id="45a95-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="45a95-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="45a95-p102">Export-CcRootCertificate コマンドレットを使用すると、ルートおよび中間証明書をファイル パスに保存することができます。 これは、障害復旧シナリオの場合に役立ちます。 </span><span class="sxs-lookup"><span data-stu-id="45a95-p102">The Export-CcRootCertificate cmdlet allows you to save the root and intermediate certificates to a file path. This can be useful in case of a disaster recovery scenario.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="45a95-114">パラメーター</span><span class="sxs-lookup"><span data-stu-id="45a95-114">Parameters</span></span>
<span data-ttu-id="45a95-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="45a95-115"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="45a95-116">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="45a95-116">**Parameter**</span></span>|<span data-ttu-id="45a95-117">**必須**</span><span class="sxs-lookup"><span data-stu-id="45a95-117">**Required**</span></span>|<span data-ttu-id="45a95-118">**種類**</span><span class="sxs-lookup"><span data-stu-id="45a95-118">**Type**</span></span>|<span data-ttu-id="45a95-119">**説明**</span><span class="sxs-lookup"><span data-stu-id="45a95-119">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="45a95-120">Path</span><span class="sxs-lookup"><span data-stu-id="45a95-120">Path</span></span>  <br/> |<span data-ttu-id="45a95-121">必須</span><span class="sxs-lookup"><span data-stu-id="45a95-121">Required</span></span>  <br/> |<span data-ttu-id="45a95-122">System.String</span><span class="sxs-lookup"><span data-stu-id="45a95-122">System.String</span></span>  <br/> |<span data-ttu-id="45a95-123">証明書が保存されるファイル パス。 </span><span class="sxs-lookup"><span data-stu-id="45a95-123">File path where the certificate will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="45a95-124">入力の種類</span><span class="sxs-lookup"><span data-stu-id="45a95-124">Input Types</span></span>
<span data-ttu-id="45a95-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="45a95-125"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="45a95-p103">なし。 Export-CcRootCertificate コマンドレットはパイプライン入力を受け入れません。 </span><span class="sxs-lookup"><span data-stu-id="45a95-p103">None. The Export-CcRootCertificate cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="45a95-128">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="45a95-128">Return Types</span></span>
<span data-ttu-id="45a95-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="45a95-129"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="45a95-130">なし</span><span class="sxs-lookup"><span data-stu-id="45a95-130">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="45a95-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="45a95-131">See also</span></span>
<span data-ttu-id="45a95-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="45a95-132"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="45a95-133">なし</span><span class="sxs-lookup"><span data-stu-id="45a95-133">None</span></span>
  

