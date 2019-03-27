---
title: Publish-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: Publish-CcAppliance コマンドレットは高可用性の情報をオンラインのテナント構成から取得して、ホスト サーバー上の Skype for Business Cloud Connector エディションのアプライアンスに公開します。
ms.openlocfilehash: 119b5e816555eedf221d9db06be15e6a778936d4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879806"
---
# <a name="publish-ccappliance"></a><span data-ttu-id="e3aaf-103">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="e3aaf-103">Publish-CcAppliance</span></span>
 
<span data-ttu-id="e3aaf-104">Publish-CcAppliance コマンドレットは高可用性の情報をオンラインのテナント構成から取得して、ホスト サーバー上の Skype for Business Cloud Connector エディションのアプライアンスに公開します。</span><span class="sxs-lookup"><span data-stu-id="e3aaf-104">The Publish-CcAppliance cmdlet gets high availability information from the online tenant configuration and publishes it to the Skype for Business Cloud Connector Edition appliance on the host server.</span></span> 
  
```
Publish-CcAppliance
```

## <a name="parameters"></a><span data-ttu-id="e3aaf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e3aaf-105">Parameters</span></span>

<span data-ttu-id="e3aaf-106">なし</span><span class="sxs-lookup"><span data-stu-id="e3aaf-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="e3aaf-107">例</span><span class="sxs-lookup"><span data-stu-id="e3aaf-107">Examples</span></span>
<span data-ttu-id="e3aaf-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e3aaf-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="e3aaf-109">例 1</span><span class="sxs-lookup"><span data-stu-id="e3aaf-109">Example 1</span></span>

<span data-ttu-id="e3aaf-110">次の例では、オンラインのテナント構成の高可用性の情報を取得し、クラウド コネクタ アプライアンス ホスト サーバー上に公開します。</span><span class="sxs-lookup"><span data-stu-id="e3aaf-110">The following example gets high availability information from the online tenant configuration and publishes it to the Cloud Connector appliance on the host server:</span></span>
  
```
Publish-CcAppliance
```

## <a name="detailed-description"></a><span data-ttu-id="e3aaf-111">解説</span><span class="sxs-lookup"><span data-stu-id="e3aaf-111">Detailed Description</span></span>
<span data-ttu-id="e3aaf-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e3aaf-112"></span></span>

<span data-ttu-id="e3aaf-p101">高可用性の情報には、PSTN サイトの仲介サーバーの FQDN と IP アドレスが含まれます。新しい DNS A レコードが、仲介サーバーの IP アドレスの AD サーバーに追加されます。新しいトポロジ項目が、仲介サーバーの FQDN と IP アドレスの中央管理ストアに更新されます。</span><span class="sxs-lookup"><span data-stu-id="e3aaf-p101">High availability information contains the Mediation Server FQDNs and IP addresses of the PSTN site. New DNS A records are added to the AD Server for Mediation Server IP addresses. New topology items are updated to the Central Management Store for the Mediation Server FQDNs and IP addresses.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="e3aaf-116">入力の種類</span><span class="sxs-lookup"><span data-stu-id="e3aaf-116">Input Types</span></span>
<span data-ttu-id="e3aaf-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e3aaf-117"></span></span>

<span data-ttu-id="e3aaf-118">なし。</span><span class="sxs-lookup"><span data-stu-id="e3aaf-118">None.</span></span> <span data-ttu-id="e3aaf-119">Publish-CcAppliance コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="e3aaf-119">The Publish-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="e3aaf-120">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="e3aaf-120">Return Types</span></span>
<span data-ttu-id="e3aaf-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e3aaf-121"></span></span>

<span data-ttu-id="e3aaf-122">なし</span><span class="sxs-lookup"><span data-stu-id="e3aaf-122">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e3aaf-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3aaf-123">See also</span></span>
<span data-ttu-id="e3aaf-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e3aaf-124"></span></span>

[<span data-ttu-id="e3aaf-125">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="e3aaf-125">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="e3aaf-126">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="e3aaf-126">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="e3aaf-127">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="e3aaf-127">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="e3aaf-128">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="e3aaf-128">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

