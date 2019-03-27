---
title: Update-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: 'Update-CcServerCertificate コマンドレットは、Skype for Business Cloud Connector エディションの証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合にそれを更新します。 '
ms.openlocfilehash: 92f914db04d3a3621624efd5b6a72e249b3eb19e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899660"
---
# <a name="update-ccservercertificate"></a><span data-ttu-id="e99ce-103">Update-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="e99ce-103">Update-CcServerCertificate</span></span>
 
<span data-ttu-id="e99ce-104">Update-CcServerCertificate コマンドレットは、Skype for Business Cloud Connector エディションの証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合にそれを更新します。 </span><span class="sxs-lookup"><span data-stu-id="e99ce-104">The Update-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> 
  
```
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="e99ce-105">例</span><span class="sxs-lookup"><span data-stu-id="e99ce-105">Examples</span></span>
<span data-ttu-id="e99ce-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e99ce-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="e99ce-107">例 1</span><span class="sxs-lookup"><span data-stu-id="e99ce-107">Example 1</span></span>

<span data-ttu-id="e99ce-108">次の例では、中央管理サーバー、仲介サーバーおよびエッジ サーバーの証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合にそれらを更新します。</span><span class="sxs-lookup"><span data-stu-id="e99ce-108">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```
Update-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="e99ce-109">例 2</span><span class="sxs-lookup"><span data-stu-id="e99ce-109">Example 2</span></span>

<span data-ttu-id="e99ce-110">次の例では、仲介サーバーとエッジ サーバーの証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合にそれらを更新します。</span><span class="sxs-lookup"><span data-stu-id="e99ce-110">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="e99ce-111">解説</span><span class="sxs-lookup"><span data-stu-id="e99ce-111">Detailed Description</span></span>
<span data-ttu-id="e99ce-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e99ce-112"></span></span>

<span data-ttu-id="e99ce-113">中央管理ストア、仲介サーバー、およびエッジ サーバーに内部証明書が発行されたクラウドのコネクタは、証明機関サービスから発行され、後の 2 年間有効です。</span><span class="sxs-lookup"><span data-stu-id="e99ce-113">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="e99ce-114">証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合は、Update-CcServerCertificate コマンドレットを実行して、証明書を更新します。</span><span class="sxs-lookup"><span data-stu-id="e99ce-114">If certificates are near expiration or already expired, run the Update-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
<span data-ttu-id="e99ce-115">Cloud Connector 2.0 以降のリリースでは、このコマンドによって Renew-CcServerCertificate コマンドレットが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="e99ce-115">This command replaces the Renew-CcServerCertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="e99ce-116">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e99ce-116">Parameters</span></span>
<span data-ttu-id="e99ce-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e99ce-117"></span></span>

|<span data-ttu-id="e99ce-118">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="e99ce-118">**Parameter**</span></span>|<span data-ttu-id="e99ce-119">**必須**</span><span class="sxs-lookup"><span data-stu-id="e99ce-119">**Required**</span></span>|<span data-ttu-id="e99ce-120">**型**</span><span class="sxs-lookup"><span data-stu-id="e99ce-120">**Type**</span></span>|<span data-ttu-id="e99ce-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="e99ce-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e99ce-122">役割</span><span class="sxs-lookup"><span data-stu-id="e99ce-122">Roles</span></span>  <br/> |<span data-ttu-id="e99ce-123">省略可能</span><span class="sxs-lookup"><span data-stu-id="e99ce-123">Optional</span></span>  <br/> |<span data-ttu-id="e99ce-124">System.Array</span><span class="sxs-lookup"><span data-stu-id="e99ce-124">System.Array</span></span>  <br/> | <span data-ttu-id="e99ce-125">Cloud Connector サーバーの役割のアレイ。</span><span class="sxs-lookup"><span data-stu-id="e99ce-125">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="e99ce-126">入力の種類</span><span class="sxs-lookup"><span data-stu-id="e99ce-126">Input Types</span></span>
<span data-ttu-id="e99ce-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e99ce-127"></span></span>

<span data-ttu-id="e99ce-p102">なし。 Update-CcServerCertificate コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="e99ce-p102">None. The Update-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="e99ce-130">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="e99ce-130">Return Types</span></span>
<span data-ttu-id="e99ce-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e99ce-131"></span></span>

<span data-ttu-id="e99ce-132">なし</span><span class="sxs-lookup"><span data-stu-id="e99ce-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e99ce-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="e99ce-133">See also</span></span>
<span data-ttu-id="e99ce-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e99ce-134"></span></span>

[<span data-ttu-id="e99ce-135">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="e99ce-135">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="e99ce-136">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="e99ce-136">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="e99ce-137">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="e99ce-137">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

