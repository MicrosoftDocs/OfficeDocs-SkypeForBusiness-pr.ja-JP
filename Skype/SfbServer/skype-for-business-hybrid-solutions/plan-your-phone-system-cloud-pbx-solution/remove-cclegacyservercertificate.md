---
title: 削除 CcLegacyServerCertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: Remove-CcLegacyServerCertificate コマンドレットは、Renew-CcCACertificate または Renew CcServerCertificate コマンドレットの実行後に、中央管理ストア、仲介サーバーおよびエッジ サーバー上にあるレガシー サーバーの証明書を削除します。
ms.openlocfilehash: f23a753df1a5c9f81b81bc0f1d7d33c01020b489
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="remove-cclegacyservercertificate"></a><span data-ttu-id="95b43-103">削除 CcLegacyServerCertificate</span><span class="sxs-lookup"><span data-stu-id="95b43-103">Remove-CcLegacyServerCertificate</span></span>
 
<span data-ttu-id="95b43-104">Remove-CcLegacyServerCertificate コマンドレットは、Renew-CcCACertificate または Renew CcServerCertificate コマンドレットの実行後に、中央管理ストア、仲介サーバーおよびエッジ サーバー上にあるレガシー サーバーの証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="95b43-104">The Remove-CcLegacyServerCertificate cmdlet removes legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.</span></span>
  
```
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a><span data-ttu-id="95b43-105">例</span><span class="sxs-lookup"><span data-stu-id="95b43-105">Examples</span></span>
<span data-ttu-id="95b43-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="95b43-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="95b43-107">例 1</span><span class="sxs-lookup"><span data-stu-id="95b43-107">Example 1</span></span>

<span data-ttu-id="95b43-108">次の例では、中央管理ストア、仲介サーバーおよびエッジ サーバーに対して発行された証明書を更新した後にそれらのレガシー証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="95b43-108">The following example removes legacy certificates issued for the Central Management Store, Mediation Server, and Edge Server after you have renewed the certificates:</span></span>
  
```
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="95b43-109">例 2</span><span class="sxs-lookup"><span data-stu-id="95b43-109">Example 2</span></span>

<span data-ttu-id="95b43-110">次の例では、仲介サーバーおよびエッジ サーバーに対して発行された証明書を更新した後にそれらの証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="95b43-110">The next example removes certificates issued for Mediation Server and Edge Server after you have renewed the certificates:</span></span> 
  
```
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 

```

## <a name="parameters"></a><span data-ttu-id="95b43-111">パラメーター</span><span class="sxs-lookup"><span data-stu-id="95b43-111">Parameters</span></span>
<span data-ttu-id="95b43-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="95b43-112"></span></span>

|<span data-ttu-id="95b43-113">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="95b43-113">**Parameter**</span></span>|<span data-ttu-id="95b43-114">**必須**</span><span class="sxs-lookup"><span data-stu-id="95b43-114">**Required**</span></span>|<span data-ttu-id="95b43-115">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="95b43-115">**Type**</span></span>|<span data-ttu-id="95b43-116">**説明**</span><span class="sxs-lookup"><span data-stu-id="95b43-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="95b43-117">役割</span><span class="sxs-lookup"><span data-stu-id="95b43-117">Roles</span></span> <br/> |<span data-ttu-id="95b43-118">省略可能</span><span class="sxs-lookup"><span data-stu-id="95b43-118">Optional</span></span>  <br/> |<span data-ttu-id="95b43-119">System.Array</span><span class="sxs-lookup"><span data-stu-id="95b43-119">System.Array</span></span>  <br/> | <span data-ttu-id="95b43-120">Cloud Connector サーバーの役割のアレイ。</span><span class="sxs-lookup"><span data-stu-id="95b43-120">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="95b43-121">入力の種類</span><span class="sxs-lookup"><span data-stu-id="95b43-121">Input Types</span></span>
<span data-ttu-id="95b43-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="95b43-122"></span></span>

<span data-ttu-id="95b43-p101">なし。Remove-CcLegacyServerCertificate コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="95b43-p101">None. The Remove-CcLegacyServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="95b43-125">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="95b43-125">Return Types</span></span>
<span data-ttu-id="95b43-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="95b43-126"></span></span>

<span data-ttu-id="95b43-127">なし</span><span class="sxs-lookup"><span data-stu-id="95b43-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="95b43-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="95b43-128">See also</span></span>
<span data-ttu-id="95b43-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="95b43-129"></span></span>

[<span data-ttu-id="95b43-130">更新 CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="95b43-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="95b43-131">リセット CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="95b43-131">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="95b43-132">更新 CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="95b43-132">Renew-CcCACertificate</span></span>](renew-cccacertificate.md)
  
[<span data-ttu-id="95b43-133">更新 CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="95b43-133">Update-CcCACertificate</span></span>](update-cccacertificate.md)
  

