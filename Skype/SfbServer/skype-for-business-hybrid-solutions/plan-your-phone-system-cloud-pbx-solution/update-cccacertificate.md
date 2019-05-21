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
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: 'Update-CcCACertificate コマンドレットは、Skype for Business Cloud Connector エディションの有効期限が近づいている、またはすでに有効期限が切れているルート CA 証明書を更新します。 '
ms.openlocfilehash: e32b910d07aa4f2370af72d0a04bb939b80b3034
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286846"
---
# <a name="update-cccacertificate"></a><span data-ttu-id="054c3-103">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="054c3-103">Update-CcCACertificate</span></span>
 
<span data-ttu-id="054c3-104">Update-CcCACertificate コマンドレットは、Skype for Business Cloud Connector エディションの有効期限が近づいている、またはすでに有効期限が切れているルート CA 証明書を更新します。 </span><span class="sxs-lookup"><span data-stu-id="054c3-104">The Update-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> 
  
```
Update-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="054c3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="054c3-105">Parameters</span></span>

<span data-ttu-id="054c3-106">なし</span><span class="sxs-lookup"><span data-stu-id="054c3-106">None.</span></span>
  
## <a name="examples"></a><span data-ttu-id="054c3-107">例</span><span class="sxs-lookup"><span data-stu-id="054c3-107">Examples</span></span>
<span data-ttu-id="054c3-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="054c3-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="054c3-109">例 1</span><span class="sxs-lookup"><span data-stu-id="054c3-109">Example 1</span></span>

<span data-ttu-id="054c3-110">次の例では、ルート CA 証明書を更新します。</span><span class="sxs-lookup"><span data-stu-id="054c3-110">The following example renews the root CA certificate:</span></span> 
  
```
Update-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="054c3-111">解説</span><span class="sxs-lookup"><span data-stu-id="054c3-111">Detailed Description</span></span>
<span data-ttu-id="054c3-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="054c3-112"></span></span>

<span data-ttu-id="054c3-113">Cloud Connector のルート CA 証明書は証明機関サービスをインストールした日から 5 年間有効です。</span><span class="sxs-lookup"><span data-stu-id="054c3-113">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="054c3-p101">ルート証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合は、Update-CcCACertificate コマンドレットを実行して証明書を更新します。 ルート証明書を更新すると、AD サーバー、中央管理ストア、エッジ サーバーに対して新しい証明書が自動的に発行されます。</span><span class="sxs-lookup"><span data-stu-id="054c3-p101">If the root certificate is near expiration or already expired, run the Update-CcCACertificate cmdlet to renew the certificate. After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="054c3-116">同一の PSTN サイトに複数のアプライアンスが存在する場合は、その PSTN サイトのすべてのアプライアンスで Update-CcCACertificate コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="054c3-116">If there are multiple appliances in the same PSTN site, run the Update-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="054c3-117">最後に、Export-CcRootCertificate コマンドレットを実行して、最初のアプライアンスのローカル ファイルにルート証明書をエクスポートし、エクスポートした証明書を PSTN ゲートウェイにコピーしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="054c3-117">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
<span data-ttu-id="054c3-118">Cloud Connector 2.0 以降のリリースでは、このコマンドによって Renew-CcCACertificate コマンドレットが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="054c3-118">This command replaces the Renew-CcCACertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="054c3-119">入力の種類</span><span class="sxs-lookup"><span data-stu-id="054c3-119">Input Types</span></span>
<span data-ttu-id="054c3-120"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="054c3-120"></span></span>

<span data-ttu-id="054c3-p102">なし。 Update-CcCACertificate コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="054c3-p102">None. The Update-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="054c3-123">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="054c3-123">Return Types</span></span>
<span data-ttu-id="054c3-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="054c3-124"></span></span>

<span data-ttu-id="054c3-125">なし。</span><span class="sxs-lookup"><span data-stu-id="054c3-125">None.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="054c3-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="054c3-126">See also</span></span>
<span data-ttu-id="054c3-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="054c3-127"></span></span>

[<span data-ttu-id="054c3-128">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="054c3-128">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="054c3-129">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="054c3-129">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="054c3-130">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="054c3-130">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

