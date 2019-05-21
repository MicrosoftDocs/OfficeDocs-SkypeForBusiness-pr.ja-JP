---
title: Remove-CcLegacyServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: Remove-CcLegacyServerCertificate コマンドレットは、Renew-CcCACertificate または Renew CcServerCertificate コマンドレットの実行後に、中央管理ストア、仲介サーバーおよびエッジ サーバー上にあるレガシー サーバーの証明書を削除します。
ms.openlocfilehash: ab332f6f0c88de01f59342002f6387ab8a83a13b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287077"
---
# <a name="remove-cclegacyservercertificate"></a><span data-ttu-id="0a49d-103">Remove-CcLegacyServerCertificate</span><span class="sxs-lookup"><span data-stu-id="0a49d-103">Remove-CcLegacyServerCertificate</span></span>
 
<span data-ttu-id="0a49d-104">Remove-CcLegacyServerCertificate コマンドレットは、Renew-CcCACertificate または Renew CcServerCertificate コマンドレットの実行後に、中央管理ストア、仲介サーバーおよびエッジ サーバー上にあるレガシー サーバーの証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="0a49d-104">The Remove-CcLegacyServerCertificate cmdlet removes legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.</span></span>
  
```
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a><span data-ttu-id="0a49d-105">例</span><span class="sxs-lookup"><span data-stu-id="0a49d-105">Examples</span></span>
<span data-ttu-id="0a49d-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0a49d-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="0a49d-107">例 1</span><span class="sxs-lookup"><span data-stu-id="0a49d-107">Example 1</span></span>

<span data-ttu-id="0a49d-108">次の例では、中央管理ストア、仲介サーバーおよびエッジ サーバーに対して発行された証明書を更新した後にそれらのレガシー証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="0a49d-108">The following example removes legacy certificates issued for the Central Management Store, Mediation Server, and Edge Server after you have renewed the certificates:</span></span>
  
```
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="0a49d-109">例 2</span><span class="sxs-lookup"><span data-stu-id="0a49d-109">Example 2</span></span>

<span data-ttu-id="0a49d-110">次の例では、仲介サーバーおよびエッジ サーバーに対して発行された証明書を更新した後にそれらの証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="0a49d-110">The next example removes certificates issued for Mediation Server and Edge Server after you have renewed the certificates:</span></span> 
  
```
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a><span data-ttu-id="0a49d-111">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0a49d-111">Parameters</span></span>
<span data-ttu-id="0a49d-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0a49d-112"></span></span>

|<span data-ttu-id="0a49d-113">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="0a49d-113">**Parameter**</span></span>|<span data-ttu-id="0a49d-114">**必須**</span><span class="sxs-lookup"><span data-stu-id="0a49d-114">**Required**</span></span>|<span data-ttu-id="0a49d-115">**型**</span><span class="sxs-lookup"><span data-stu-id="0a49d-115">**Type**</span></span>|<span data-ttu-id="0a49d-116">**説明**</span><span class="sxs-lookup"><span data-stu-id="0a49d-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="0a49d-117">役割</span><span class="sxs-lookup"><span data-stu-id="0a49d-117">Roles</span></span> <br/> |<span data-ttu-id="0a49d-118">省略可能</span><span class="sxs-lookup"><span data-stu-id="0a49d-118">Optional</span></span>  <br/> |<span data-ttu-id="0a49d-119">System.Array</span><span class="sxs-lookup"><span data-stu-id="0a49d-119">System.Array</span></span>  <br/> | <span data-ttu-id="0a49d-120">Cloud Connector サーバーの役割のアレイ。</span><span class="sxs-lookup"><span data-stu-id="0a49d-120">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="0a49d-121">入力の種類</span><span class="sxs-lookup"><span data-stu-id="0a49d-121">Input Types</span></span>
<span data-ttu-id="0a49d-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0a49d-122"></span></span>

<span data-ttu-id="0a49d-p101">なし。Remove-CcLegacyServerCertificate コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="0a49d-p101">None. The Remove-CcLegacyServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0a49d-125">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="0a49d-125">Return Types</span></span>
<span data-ttu-id="0a49d-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0a49d-126"></span></span>

<span data-ttu-id="0a49d-127">なし</span><span class="sxs-lookup"><span data-stu-id="0a49d-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0a49d-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="0a49d-128">See also</span></span>
<span data-ttu-id="0a49d-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0a49d-129"></span></span>

[<span data-ttu-id="0a49d-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="0a49d-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="0a49d-131">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="0a49d-131">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="0a49d-132">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="0a49d-132">Renew-CcCACertificate</span></span>](renew-cccacertificate.md)
  
[<span data-ttu-id="0a49d-133">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="0a49d-133">Update-CcCACertificate</span></span>](update-cccacertificate.md)
  

