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
ms.openlocfilehash: 47f2bbefa6510ae49e2e4a3ddc321e288dee266e
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003267"
---
# <a name="renew-ccservercertificate"></a><span data-ttu-id="0993c-104">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="0993c-104">Renew-CcServerCertificate</span></span>
 
<span data-ttu-id="0993c-p102">Renew-CcServerCertificate コマンドレットは、Skype for Business Cloud Connector エディションの証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合にそれを更新します。 Cloud Connector  2.0 以降のリリースにおいて、このコマンドは Update-CcServerCertificate に変更されました。 </span><span class="sxs-lookup"><span data-stu-id="0993c-p102">The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired. This command was changed to Update-CcServerCertificate in Cloud Connector 2.0 and later releases.</span></span> 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="0993c-107">例</span><span class="sxs-lookup"><span data-stu-id="0993c-107">Examples</span></span>
<span data-ttu-id="0993c-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0993c-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="0993c-109">例 1</span><span class="sxs-lookup"><span data-stu-id="0993c-109">Example 1</span></span>

<span data-ttu-id="0993c-110">次の例では、中央管理サーバー、仲介サーバーおよびエッジ サーバーの証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合にそれらを更新します。</span><span class="sxs-lookup"><span data-stu-id="0993c-110">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="0993c-111">例 2</span><span class="sxs-lookup"><span data-stu-id="0993c-111">Example 2</span></span>

<span data-ttu-id="0993c-112">次の例では、仲介サーバーとエッジ サーバーの証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合にそれらを更新します。</span><span class="sxs-lookup"><span data-stu-id="0993c-112">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="0993c-113">解説</span><span class="sxs-lookup"><span data-stu-id="0993c-113">Detailed Description</span></span>
<span data-ttu-id="0993c-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0993c-114"></span></span>

<span data-ttu-id="0993c-115">クラウドコネクタ中央管理ストア、仲介サーバー、エッジサーバーに発行された内部証明書は、証明機関サービスから発行されてから2年間有効です。</span><span class="sxs-lookup"><span data-stu-id="0993c-115">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="0993c-116">証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合は、Renew-CcServerCertificate コマンドレットを実行して、証明書を更新します。</span><span class="sxs-lookup"><span data-stu-id="0993c-116">If certificates are near expiration or already expired, run the Renew-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="0993c-117">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0993c-117">Parameters</span></span>
<span data-ttu-id="0993c-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0993c-118"></span></span>

|<span data-ttu-id="0993c-119">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="0993c-119">**Parameter**</span></span>|<span data-ttu-id="0993c-120">**必須**</span><span class="sxs-lookup"><span data-stu-id="0993c-120">**Required**</span></span>|<span data-ttu-id="0993c-121">**種類**</span><span class="sxs-lookup"><span data-stu-id="0993c-121">**Type**</span></span>|<span data-ttu-id="0993c-122">**説明**</span><span class="sxs-lookup"><span data-stu-id="0993c-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0993c-123">役割</span><span class="sxs-lookup"><span data-stu-id="0993c-123">Roles</span></span>  <br/> |<span data-ttu-id="0993c-124">省略可能</span><span class="sxs-lookup"><span data-stu-id="0993c-124">Optional</span></span>  <br/> |<span data-ttu-id="0993c-125">System.Array</span><span class="sxs-lookup"><span data-stu-id="0993c-125">System.Array</span></span>  <br/> | <span data-ttu-id="0993c-126">Cloud Connector サーバーの役割のアレイ。</span><span class="sxs-lookup"><span data-stu-id="0993c-126">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="0993c-127">入力の種類</span><span class="sxs-lookup"><span data-stu-id="0993c-127">Input Types</span></span>
<span data-ttu-id="0993c-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0993c-128"></span></span>

<span data-ttu-id="0993c-p104">なし。Renew-CcServerCertificate コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="0993c-p104">None. The Renew-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0993c-131">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="0993c-131">Return Types</span></span>
<span data-ttu-id="0993c-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0993c-132"></span></span>

<span data-ttu-id="0993c-133">なし</span><span class="sxs-lookup"><span data-stu-id="0993c-133">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0993c-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="0993c-134">See also</span></span>
<span data-ttu-id="0993c-135"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0993c-135"></span></span>

[<span data-ttu-id="0993c-136">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="0993c-136">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="0993c-137">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="0993c-137">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="0993c-138">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="0993c-138">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

