---
title: Renew-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: 'Renew-CcServerCertificate コマンドレットは、Skype for Business Cloud Connector エディションの証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合にそれを更新します。 Cloud Connector  2.0 以降のリリースにおいて、このコマンドは Update-CcServerCertificate に変更されました。 '
ms.openlocfilehash: 611eeb648c88411afa5d74cc7564703a5e37e9bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287063"
---
# <a name="renew-ccservercertificate"></a><span data-ttu-id="f8e17-104">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="f8e17-104">Renew-CcServerCertificate</span></span>
 
<span data-ttu-id="f8e17-p102">Renew-CcServerCertificate コマンドレットは、Skype for Business Cloud Connector エディションの証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合にそれを更新します。 Cloud Connector  2.0 以降のリリースにおいて、このコマンドは Update-CcServerCertificate に変更されました。 </span><span class="sxs-lookup"><span data-stu-id="f8e17-p102">The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired. This command was changed to Update-CcServerCertificate in Cloud Connector 2.0 and later releases.</span></span> 
  
```
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="f8e17-107">例</span><span class="sxs-lookup"><span data-stu-id="f8e17-107">Examples</span></span>
<span data-ttu-id="f8e17-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f8e17-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="f8e17-109">例 1</span><span class="sxs-lookup"><span data-stu-id="f8e17-109">Example 1</span></span>

<span data-ttu-id="f8e17-110">次の例では、中央管理サーバー、仲介サーバーおよびエッジ サーバーの証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合にそれらを更新します。</span><span class="sxs-lookup"><span data-stu-id="f8e17-110">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```
Renew-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="f8e17-111">例 2</span><span class="sxs-lookup"><span data-stu-id="f8e17-111">Example 2</span></span>

<span data-ttu-id="f8e17-112">次の例では、仲介サーバーとエッジ サーバーの証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合にそれらを更新します。</span><span class="sxs-lookup"><span data-stu-id="f8e17-112">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="f8e17-113">解説</span><span class="sxs-lookup"><span data-stu-id="f8e17-113">Detailed Description</span></span>
<span data-ttu-id="f8e17-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f8e17-114"></span></span>

<span data-ttu-id="f8e17-115">クラウドコネクタ中央管理ストア、仲介サーバー、エッジサーバーに発行された内部証明書は、証明機関サービスから発行されてから2年間有効です。</span><span class="sxs-lookup"><span data-stu-id="f8e17-115">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="f8e17-116">証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合は、Renew-CcServerCertificate コマンドレットを実行して、証明書を更新します。</span><span class="sxs-lookup"><span data-stu-id="f8e17-116">If certificates are near expiration or already expired, run the Renew-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="f8e17-117">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f8e17-117">Parameters</span></span>
<span data-ttu-id="f8e17-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f8e17-118"></span></span>

|<span data-ttu-id="f8e17-119">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="f8e17-119">**Parameter**</span></span>|<span data-ttu-id="f8e17-120">**必須**</span><span class="sxs-lookup"><span data-stu-id="f8e17-120">**Required**</span></span>|<span data-ttu-id="f8e17-121">**型**</span><span class="sxs-lookup"><span data-stu-id="f8e17-121">**Type**</span></span>|<span data-ttu-id="f8e17-122">**説明**</span><span class="sxs-lookup"><span data-stu-id="f8e17-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f8e17-123">役割</span><span class="sxs-lookup"><span data-stu-id="f8e17-123">Roles</span></span>  <br/> |<span data-ttu-id="f8e17-124">省略可能</span><span class="sxs-lookup"><span data-stu-id="f8e17-124">Optional</span></span>  <br/> |<span data-ttu-id="f8e17-125">System.Array</span><span class="sxs-lookup"><span data-stu-id="f8e17-125">System.Array</span></span>  <br/> | <span data-ttu-id="f8e17-126">Cloud Connector サーバーの役割のアレイ。</span><span class="sxs-lookup"><span data-stu-id="f8e17-126">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="f8e17-127">入力の種類</span><span class="sxs-lookup"><span data-stu-id="f8e17-127">Input Types</span></span>
<span data-ttu-id="f8e17-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f8e17-128"></span></span>

<span data-ttu-id="f8e17-p104">なし。Renew-CcServerCertificate コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="f8e17-p104">None. The Renew-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f8e17-131">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="f8e17-131">Return Types</span></span>
<span data-ttu-id="f8e17-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f8e17-132"></span></span>

<span data-ttu-id="f8e17-133">なし</span><span class="sxs-lookup"><span data-stu-id="f8e17-133">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f8e17-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8e17-134">See also</span></span>
<span data-ttu-id="f8e17-135"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f8e17-135"></span></span>

[<span data-ttu-id="f8e17-136">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="f8e17-136">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="f8e17-137">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="f8e17-137">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="f8e17-138">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="f8e17-138">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

