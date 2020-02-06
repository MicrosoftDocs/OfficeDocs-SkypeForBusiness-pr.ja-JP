---
title: Update-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: 'Update-CcCACertificate コマンドレットは、Skype for Business Cloud Connector エディションの有効期限が近づいている、またはすでに有効期限が切れているルート CA 証明書を更新します。 '
ms.openlocfilehash: 9a99e80e166b7c8624867594fa02243d9d70537e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824121"
---
# <a name="update-cccacertificate"></a><span data-ttu-id="bdfd6-103">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="bdfd6-103">Update-CcCACertificate</span></span>
 
<span data-ttu-id="bdfd6-104">Update-CcCACertificate コマンドレットは、Skype for Business Cloud Connector エディションの有効期限が近づいている、またはすでに有効期限が切れているルート CA 証明書を更新します。 </span><span class="sxs-lookup"><span data-stu-id="bdfd6-104">The Update-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> 
  
```powershell
Update-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="bdfd6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bdfd6-105">Parameters</span></span>

<span data-ttu-id="bdfd6-106">なし</span><span class="sxs-lookup"><span data-stu-id="bdfd6-106">None.</span></span>
  
## <a name="examples"></a><span data-ttu-id="bdfd6-107">例</span><span class="sxs-lookup"><span data-stu-id="bdfd6-107">Examples</span></span>
<span data-ttu-id="bdfd6-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bdfd6-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="bdfd6-109">例 1</span><span class="sxs-lookup"><span data-stu-id="bdfd6-109">Example 1</span></span>

<span data-ttu-id="bdfd6-110">次の例では、ルート CA 証明書を更新します。</span><span class="sxs-lookup"><span data-stu-id="bdfd6-110">The following example renews the root CA certificate:</span></span> 
  
```powershell
Update-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="bdfd6-111">解説</span><span class="sxs-lookup"><span data-stu-id="bdfd6-111">Detailed Description</span></span>
<span data-ttu-id="bdfd6-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="bdfd6-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="bdfd6-113">Cloud Connector のルート CA 証明書は証明機関サービスをインストールした日から 5 年間有効です。</span><span class="sxs-lookup"><span data-stu-id="bdfd6-113">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="bdfd6-p101">ルート証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合は、Update-CcCACertificate コマンドレットを実行して証明書を更新します。 ルート証明書を更新すると、AD サーバー、中央管理ストア、エッジ サーバーに対して新しい証明書が自動的に発行されます。</span><span class="sxs-lookup"><span data-stu-id="bdfd6-p101">If the root certificate is near expiration or already expired, run the Update-CcCACertificate cmdlet to renew the certificate. After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="bdfd6-116">同一の PSTN サイトに複数のアプライアンスが存在する場合は、その PSTN サイトのすべてのアプライアンスで Update-CcCACertificate コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="bdfd6-116">If there are multiple appliances in the same PSTN site, run the Update-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="bdfd6-117">最後に、Export-CcRootCertificate コマンドレットを実行して、最初のアプライアンスのローカル ファイルにルート証明書をエクスポートし、エクスポートした証明書を PSTN ゲートウェイにコピーしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="bdfd6-117">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
<span data-ttu-id="bdfd6-118">Cloud Connector 2.0 以降のリリースでは、このコマンドによって Renew-CcCACertificate コマンドレットが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="bdfd6-118">This command replaces the Renew-CcCACertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="bdfd6-119">入力の種類</span><span class="sxs-lookup"><span data-stu-id="bdfd6-119">Input Types</span></span>
<span data-ttu-id="bdfd6-120"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bdfd6-120"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="bdfd6-p102">なし。 Update-CcCACertificate コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="bdfd6-p102">None. The Update-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="bdfd6-123">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="bdfd6-123">Return Types</span></span>
<span data-ttu-id="bdfd6-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bdfd6-124"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="bdfd6-125">なし。</span><span class="sxs-lookup"><span data-stu-id="bdfd6-125">None.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="bdfd6-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="bdfd6-126">See also</span></span>
<span data-ttu-id="bdfd6-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bdfd6-127"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="bdfd6-128">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="bdfd6-128">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="bdfd6-129">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="bdfd6-129">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="bdfd6-130">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="bdfd6-130">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

