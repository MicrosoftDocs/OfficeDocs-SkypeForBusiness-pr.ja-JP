---
title: 更新 CcServerCertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: Renew-CcServerCertificate コマンドレットは、Skype for Business Cloud Connector エディションの証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合にそれを更新します。 Cloud Connector  2.0 以降のリリースにおいて、このコマンドは Update-CcServerCertificate に変更されました。
ms.openlocfilehash: 3d895a24c4cc8b400aa48ce394324435cfbb3979
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="renew-ccservercertificate"></a><span data-ttu-id="3da58-104">更新 CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="3da58-104">Renew-CcServerCertificate</span></span>
 
<span data-ttu-id="3da58-105">Renew-CcServerCertificate コマンドレットは、Skype for Business Cloud Connector エディションの証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合にそれを更新します。</span><span class="sxs-lookup"><span data-stu-id="3da58-105">The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> <span data-ttu-id="3da58-106">Cloud Connector  2.0 以降のリリースにおいて、このコマンドは Update-CcServerCertificate に変更されました。</span><span class="sxs-lookup"><span data-stu-id="3da58-106">This command was changed to Update-CcServerCertificate in Cloud Connector 2.0 and later releases.</span></span> 
  
```
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="3da58-107">例</span><span class="sxs-lookup"><span data-stu-id="3da58-107">Examples</span></span>
<span data-ttu-id="3da58-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3da58-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="3da58-109">例 1</span><span class="sxs-lookup"><span data-stu-id="3da58-109">Example 1</span></span>

<span data-ttu-id="3da58-110">次の例では、中央管理サーバー、仲介サーバーおよびエッジ サーバーの証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合にそれらを更新します。</span><span class="sxs-lookup"><span data-stu-id="3da58-110">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```
Renew-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="3da58-111">例 2</span><span class="sxs-lookup"><span data-stu-id="3da58-111">Example 2</span></span>

<span data-ttu-id="3da58-112">次の例では、仲介サーバーとエッジ サーバーの証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合にそれらを更新します。</span><span class="sxs-lookup"><span data-stu-id="3da58-112">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="3da58-113">解説</span><span class="sxs-lookup"><span data-stu-id="3da58-113">Detailed Description</span></span>
<span data-ttu-id="3da58-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3da58-114"></span></span>

<span data-ttu-id="3da58-115">中央管理ストア、仲介サーバー、およびエッジ サーバーに内部証明書が発行されたクラウドのコネクタは、証明機関サービスから発行され、後の 2 年間有効です。</span><span class="sxs-lookup"><span data-stu-id="3da58-115">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="3da58-116">証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合は、Renew-CcServerCertificate コマンドレットを実行して、証明書を更新します。</span><span class="sxs-lookup"><span data-stu-id="3da58-116">If certificates are near expiration or already expired, run the Renew-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="3da58-117">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3da58-117">Parameters</span></span>
<span data-ttu-id="3da58-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3da58-118"></span></span>

|<span data-ttu-id="3da58-119">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="3da58-119">**Parameter**</span></span>|<span data-ttu-id="3da58-120">**必須**</span><span class="sxs-lookup"><span data-stu-id="3da58-120">**Required**</span></span>|<span data-ttu-id="3da58-121">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="3da58-121">**Type**</span></span>|<span data-ttu-id="3da58-122">**説明**</span><span class="sxs-lookup"><span data-stu-id="3da58-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3da58-123">役割</span><span class="sxs-lookup"><span data-stu-id="3da58-123">Roles</span></span>  <br/> |<span data-ttu-id="3da58-124">省略可能</span><span class="sxs-lookup"><span data-stu-id="3da58-124">Optional</span></span>  <br/> |<span data-ttu-id="3da58-125">System.Array</span><span class="sxs-lookup"><span data-stu-id="3da58-125">System.Array</span></span>  <br/> | <span data-ttu-id="3da58-126">Cloud Connector サーバーの役割のアレイ。</span><span class="sxs-lookup"><span data-stu-id="3da58-126">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="3da58-127">入力の種類</span><span class="sxs-lookup"><span data-stu-id="3da58-127">Input Types</span></span>
<span data-ttu-id="3da58-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3da58-128"></span></span>

<span data-ttu-id="3da58-p104">なし。Renew-CcServerCertificate コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="3da58-p104">None. The Renew-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="3da58-131">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="3da58-131">Return Types</span></span>
<span data-ttu-id="3da58-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3da58-132"></span></span>

<span data-ttu-id="3da58-133">なし</span><span class="sxs-lookup"><span data-stu-id="3da58-133">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3da58-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="3da58-134">See also</span></span>
<span data-ttu-id="3da58-135"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3da58-135"></span></span>

[<span data-ttu-id="3da58-136">リセット CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="3da58-136">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="3da58-137">更新 CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="3da58-137">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="3da58-138">エクスポート CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="3da58-138">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

