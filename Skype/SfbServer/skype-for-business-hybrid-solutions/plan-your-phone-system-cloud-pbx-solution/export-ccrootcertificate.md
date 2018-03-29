---
title: エクスポート CcRootCertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: Export-CcRootCertificate コマンドレットはルート CA 証明書を Skype for Business Cloud Connector エディションのホスト サーバー上のローカル ファイルにエクスポートします。
ms.openlocfilehash: 9af3701fd89cf881b4f966c2b00500ad4e55bc9b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="export-ccrootcertificate"></a><span data-ttu-id="23783-103">エクスポート CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="23783-103">Export-CcRootCertificate</span></span>
 
<span data-ttu-id="23783-104">Export-CcRootCertificate コマンドレットはルート CA 証明書を Skype for Business Cloud Connector エディションのホスト サーバー上のローカル ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="23783-104">The Export-CcRootCertificate cmdlet exports the root CA certificate to a local file on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
```
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="23783-105">例</span><span class="sxs-lookup"><span data-stu-id="23783-105">Examples</span></span>
<span data-ttu-id="23783-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="23783-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="23783-107">例 1</span><span class="sxs-lookup"><span data-stu-id="23783-107">Example 1</span></span>

<span data-ttu-id="23783-108">次の例では、Path パラメータをファイル パスではなくディレクトリ パスで設定します。</span><span class="sxs-lookup"><span data-stu-id="23783-108">The following example sets the Path parameter as a directory path—not a file path.</span></span> <span data-ttu-id="23783-109">これによって、ファイル c:\test\CCERootCertificates.p7b が生成されます。</span><span class="sxs-lookup"><span data-stu-id="23783-109">It generates the file c:\test\CCERootCertificates.p7b.</span></span>
  
```
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a><span data-ttu-id="23783-110">解説</span><span class="sxs-lookup"><span data-stu-id="23783-110">Detailed Description</span></span>
<span data-ttu-id="23783-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="23783-111"></span></span>

<span data-ttu-id="23783-112">Export-CcRootCertificate コマンドレットを使用すると、ルートおよび中間証明書をファイル パスに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="23783-112">The Export-CcRootCertificate cmdlet allows you to save the root and intermediate certificates to a file path.</span></span> <span data-ttu-id="23783-113">これは、障害復旧シナリオの場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="23783-113">This can be useful in case of a disaster recovery scenario.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="23783-114">パラメーター</span><span class="sxs-lookup"><span data-stu-id="23783-114">Parameters</span></span>
<span data-ttu-id="23783-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="23783-115"></span></span>

|<span data-ttu-id="23783-116">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="23783-116">**Parameter**</span></span>|<span data-ttu-id="23783-117">**必須**</span><span class="sxs-lookup"><span data-stu-id="23783-117">**Required**</span></span>|<span data-ttu-id="23783-118">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="23783-118">**Type**</span></span>|<span data-ttu-id="23783-119">**説明**</span><span class="sxs-lookup"><span data-stu-id="23783-119">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="23783-120"> Path</span><span class="sxs-lookup"><span data-stu-id="23783-120">Path</span></span>  <br/> |<span data-ttu-id="23783-121">必須</span><span class="sxs-lookup"><span data-stu-id="23783-121">Required</span></span>  <br/> |<span data-ttu-id="23783-122">System.String</span><span class="sxs-lookup"><span data-stu-id="23783-122">System.String</span></span>  <br/> |<span data-ttu-id="23783-123">証明書が保存されるファイル パス。</span><span class="sxs-lookup"><span data-stu-id="23783-123">File path where the certificate will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="23783-124">入力の種類</span><span class="sxs-lookup"><span data-stu-id="23783-124">Input Types</span></span>
<span data-ttu-id="23783-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="23783-125"></span></span>

<span data-ttu-id="23783-126">なし。</span><span class="sxs-lookup"><span data-stu-id="23783-126">None.</span></span> <span data-ttu-id="23783-127">Export-CcRootCertificate コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="23783-127">The Export-CcRootCertificate cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="23783-128">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="23783-128">Return Types</span></span>
<span data-ttu-id="23783-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="23783-129"></span></span>

<span data-ttu-id="23783-130">なし</span><span class="sxs-lookup"><span data-stu-id="23783-130">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="23783-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="23783-131">See also</span></span>
<span data-ttu-id="23783-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="23783-132"></span></span>

<span data-ttu-id="23783-133">なし</span><span class="sxs-lookup"><span data-stu-id="23783-133">None</span></span>
  

