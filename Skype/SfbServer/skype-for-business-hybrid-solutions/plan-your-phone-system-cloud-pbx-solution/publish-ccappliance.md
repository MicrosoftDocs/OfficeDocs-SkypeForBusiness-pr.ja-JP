---
title: Publish-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: Publish-CcAppliance コマンドレットは高可用性の情報をオンラインのテナント構成から取得して、ホスト サーバー上の Skype for Business Cloud Connector エディションのアプライアンスに公開します。
ms.openlocfilehash: da9135f669cb5b8cbe127295b20d82fd1632a3d3
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003087"
---
# <a name="publish-ccappliance"></a><span data-ttu-id="d6941-103">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d6941-103">Publish-CcAppliance</span></span>
 
<span data-ttu-id="d6941-104">Publish-CcAppliance コマンドレットは高可用性の情報をオンラインのテナント構成から取得して、ホスト サーバー上の Skype for Business Cloud Connector エディションのアプライアンスに公開します。</span><span class="sxs-lookup"><span data-stu-id="d6941-104">The Publish-CcAppliance cmdlet gets high availability information from the online tenant configuration and publishes it to the Skype for Business Cloud Connector Edition appliance on the host server.</span></span> 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a><span data-ttu-id="d6941-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d6941-105">Parameters</span></span>

<span data-ttu-id="d6941-106">なし</span><span class="sxs-lookup"><span data-stu-id="d6941-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="d6941-107">例</span><span class="sxs-lookup"><span data-stu-id="d6941-107">Examples</span></span>
<span data-ttu-id="d6941-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d6941-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="d6941-109">例 1</span><span class="sxs-lookup"><span data-stu-id="d6941-109">Example 1</span></span>

<span data-ttu-id="d6941-110">次の例では、オンラインテナント構成から高可用性情報を取得し、それをホストサーバー上のクラウドコネクタアプライアンスに公開しています。</span><span class="sxs-lookup"><span data-stu-id="d6941-110">The following example gets high availability information from the online tenant configuration and publishes it to the Cloud Connector appliance on the host server:</span></span>
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a><span data-ttu-id="d6941-111">解説</span><span class="sxs-lookup"><span data-stu-id="d6941-111">Detailed Description</span></span>
<span data-ttu-id="d6941-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d6941-112"></span></span>

<span data-ttu-id="d6941-p101">高可用性の情報には、PSTN サイトの仲介サーバーの FQDN と IP アドレスが含まれます。新しい DNS A レコードが、仲介サーバーの IP アドレスの AD サーバーに追加されます。新しいトポロジ項目が、仲介サーバーの FQDN と IP アドレスの中央管理ストアに更新されます。</span><span class="sxs-lookup"><span data-stu-id="d6941-p101">High availability information contains the Mediation Server FQDNs and IP addresses of the PSTN site. New DNS A records are added to the AD Server for Mediation Server IP addresses. New topology items are updated to the Central Management Store for the Mediation Server FQDNs and IP addresses.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="d6941-116">入力の種類</span><span class="sxs-lookup"><span data-stu-id="d6941-116">Input Types</span></span>
<span data-ttu-id="d6941-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d6941-117"></span></span>

<span data-ttu-id="d6941-118">なし。</span><span class="sxs-lookup"><span data-stu-id="d6941-118">None.</span></span> <span data-ttu-id="d6941-119">Publish-CcAppliance コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="d6941-119">The Publish-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="d6941-120">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="d6941-120">Return Types</span></span>
<span data-ttu-id="d6941-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d6941-121"></span></span>

<span data-ttu-id="d6941-122">なし</span><span class="sxs-lookup"><span data-stu-id="d6941-122">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d6941-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6941-123">See also</span></span>
<span data-ttu-id="d6941-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d6941-124"></span></span>

[<span data-ttu-id="d6941-125">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d6941-125">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="d6941-126">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d6941-126">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="d6941-127">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d6941-127">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="d6941-128">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d6941-128">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

