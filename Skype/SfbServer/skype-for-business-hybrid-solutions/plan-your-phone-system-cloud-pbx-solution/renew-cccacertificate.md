---
title: Renew-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: Renew-CcCACertificate コマンドレットは、有効期限が近づいている、またはすでに有効期限が切れている Skype for Business Cloud Connector エディションのルート CA 証明書を更新します。 このコマンドは、クラウドコネクタ2.0 以降のリリースで CcCACertificate に変更されました。
ms.openlocfilehash: e92709cd1da0ffccd2b356000dbd2345ba56a1d9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824273"
---
# <a name="renew-cccacertificate"></a><span data-ttu-id="db644-104">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="db644-104">Renew-CcCACertificate</span></span>
 
<span data-ttu-id="db644-105">Renew-CcCACertificate コマンドレットは、有効期限が近づいている、またはすでに有効期限が切れている Skype for Business Cloud Connector エディションのルート CA 証明書を更新します。</span><span class="sxs-lookup"><span data-stu-id="db644-105">The Renew-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> <span data-ttu-id="db644-106">このコマンドは、クラウドコネクタ2.0 以降のリリースで CcCACertificate に変更されました。</span><span class="sxs-lookup"><span data-stu-id="db644-106">This command was changed to Update-CcCACertificate in Cloud Connector 2.0 and later releases.</span></span>
  
```powershell
Renew-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="db644-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="db644-107">Parameters</span></span>

<span data-ttu-id="db644-108">なし</span><span class="sxs-lookup"><span data-stu-id="db644-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="db644-109">例</span><span class="sxs-lookup"><span data-stu-id="db644-109">Examples</span></span>
<span data-ttu-id="db644-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="db644-110"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="db644-111">例 1</span><span class="sxs-lookup"><span data-stu-id="db644-111">Example 1</span></span>

<span data-ttu-id="db644-112">次の例では、ルート CA 証明書を更新します。</span><span class="sxs-lookup"><span data-stu-id="db644-112">The following example renews the root CA certificate:</span></span> 
  
```powershell
Renew-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="db644-113">解説</span><span class="sxs-lookup"><span data-stu-id="db644-113">Detailed Description</span></span>
<span data-ttu-id="db644-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="db644-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="db644-115">Cloud Connector のルート CA 証明書は証明機関サービスをインストールした日から 5 年間有効です。</span><span class="sxs-lookup"><span data-stu-id="db644-115">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="db644-p103">ルート証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合は、Renew-CcCACertificate コマンドレットを実行して証明書を更新します。ルート証明書を更新すると、AD サーバー、中央管理ストア、エッジ サーバーに対して新しい証明書が自動的に発行されます。</span><span class="sxs-lookup"><span data-stu-id="db644-p103">If the root certificate is near expiration or already expired, run the Renew-CcCACertificate cmdlet to renew the certificate. After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="db644-118">同一の PSTN サイトに複数のアプライアンスが存在する場合は、その PSTN サイトのすべてのアプライアンスで Renew-CcCACertificate コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="db644-118">If there are multiple appliances in the same PSTN site, run the Renew-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="db644-119">最後に、Export-CcRootCertificate コマンドレットを実行して、最初のアプライアンスのローカル ファイルにルート証明書をエクスポートし、エクスポートした証明書を PSTN ゲートウェイにコピーしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="db644-119">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="db644-120">入力の種類</span><span class="sxs-lookup"><span data-stu-id="db644-120">Input Types</span></span>
<span data-ttu-id="db644-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="db644-121"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="db644-p104">なし。Renew-CcCACertificate コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="db644-p104">None. The Renew-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="db644-124">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="db644-124">Return Types</span></span>
<span data-ttu-id="db644-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="db644-125"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="db644-126">なし</span><span class="sxs-lookup"><span data-stu-id="db644-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="db644-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="db644-127">See also</span></span>
<span data-ttu-id="db644-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="db644-128"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="db644-129">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="db644-129">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="db644-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="db644-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="db644-131">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="db644-131">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

