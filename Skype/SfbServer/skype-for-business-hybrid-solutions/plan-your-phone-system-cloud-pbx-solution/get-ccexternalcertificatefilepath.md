---
title: Get-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: Get-CcExternalCertificateFilePath コマンドレットは、Skype for Business Cloud Connector エディションの展開用に外部証明書ファイルのパスを返します。 この証明書はユーザーが準備します。
ms.openlocfilehash: ed725814380741aade73166d01025650dfa78538
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287322"
---
# <a name="get-ccexternalcertificatefilepath"></a><span data-ttu-id="de25d-104">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="de25d-104">Get-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="de25d-p102">Get-CcExternalCertificateFilePath コマンドレットは、Skype for Business Cloud Connector エディションの展開用に外部証明書ファイルのパスを返します。この証明書はユーザーが準備します。</span><span class="sxs-lookup"><span data-stu-id="de25d-p102">The Get-CcExternalCertificateFilePath cmdlet returns the external certificate file path for the Skype for Business Cloud Connector Edition deployment. The user prepares this certificate.</span></span>
  
<span data-ttu-id="de25d-107">このコマンドレットは、Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="de25d-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a><span data-ttu-id="de25d-108">例</span><span class="sxs-lookup"><span data-stu-id="de25d-108">Examples</span></span>
<span data-ttu-id="de25d-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="de25d-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="de25d-110">例 1</span><span class="sxs-lookup"><span data-stu-id="de25d-110">Example 1</span></span>

<span data-ttu-id="de25d-111">次の例では、エッジ サーバーの証明書のパスを示します。</span><span class="sxs-lookup"><span data-stu-id="de25d-111">The following example shows the path of the certificate for the Edge Server:</span></span>
  
```
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a><span data-ttu-id="de25d-112">例 2</span><span class="sxs-lookup"><span data-stu-id="de25d-112">Example 2</span></span>

<span data-ttu-id="de25d-113">次の例では、仲介サーバーの証明書セットを示します。</span><span class="sxs-lookup"><span data-stu-id="de25d-113">The following example shows the certificate set for the Mediation Server:</span></span>
  
```
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a><span data-ttu-id="de25d-114">解説</span><span class="sxs-lookup"><span data-stu-id="de25d-114">Detailed Description</span></span>
<span data-ttu-id="de25d-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="de25d-115"></span></span>

<span data-ttu-id="de25d-p103">展開中またはトポロジの変更時には、エッジ サーバーの証明書および仲介サーバーの証明書 (省略可能) のパスを指定する必要があります。仲介サーバーの証明書は、ゲートウェイと仲介サーバーの間に TLS を使用する場合に必要です。パスを変更するには、Set-CcExternalCertificateFilePath コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="de25d-p103">During deployment or when modifying the topology, you need to specify the path for the Edge Server certificate, and, optionally, for the Mediation Server. The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server. To change the path, use the Set-CcExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="de25d-119">パラメーター</span><span class="sxs-lookup"><span data-stu-id="de25d-119">Parameters</span></span>
<span data-ttu-id="de25d-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="de25d-120"></span></span>

|<span data-ttu-id="de25d-121">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="de25d-121">**Parameter**</span></span>|<span data-ttu-id="de25d-122">**必須**</span><span class="sxs-lookup"><span data-stu-id="de25d-122">**Required**</span></span>|<span data-ttu-id="de25d-123">**型**</span><span class="sxs-lookup"><span data-stu-id="de25d-123">**Type**</span></span>|<span data-ttu-id="de25d-124">**説明**</span><span class="sxs-lookup"><span data-stu-id="de25d-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="de25d-125">Target</span><span class="sxs-lookup"><span data-stu-id="de25d-125">Target</span></span>  <br/> |<span data-ttu-id="de25d-126">省略可能</span><span class="sxs-lookup"><span data-stu-id="de25d-126">Optional</span></span>  <br/> | <span data-ttu-id="de25d-127">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="de25d-127">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="de25d-p104">必要なファイル パスの種類。種類:</span><span class="sxs-lookup"><span data-stu-id="de25d-p104">Type of file path requested. Types include:</span></span>  <br/> <span data-ttu-id="de25d-130">EdgeServer (既定)</span><span class="sxs-lookup"><span data-stu-id="de25d-130">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="de25d-131">MediationServer</span><span class="sxs-lookup"><span data-stu-id="de25d-131">MediationServer</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="de25d-132">入力の種類</span><span class="sxs-lookup"><span data-stu-id="de25d-132">Input Types</span></span>
<span data-ttu-id="de25d-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="de25d-133"></span></span>

<span data-ttu-id="de25d-134">Get-CcExternalCertificateFilePath コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="de25d-134">The Get-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="de25d-135">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="de25d-135">Return Types</span></span>
<span data-ttu-id="de25d-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="de25d-136"></span></span>

<span data-ttu-id="de25d-137">このコマンドはファイル パスを返します。</span><span class="sxs-lookup"><span data-stu-id="de25d-137">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="de25d-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="de25d-138">See also</span></span>
<span data-ttu-id="de25d-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="de25d-139"></span></span>

[<span data-ttu-id="de25d-140">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="de25d-140">Set-CcExternalCertificateFilePath</span></span>](set-ccexternalcertificatefilepath.md)
  

