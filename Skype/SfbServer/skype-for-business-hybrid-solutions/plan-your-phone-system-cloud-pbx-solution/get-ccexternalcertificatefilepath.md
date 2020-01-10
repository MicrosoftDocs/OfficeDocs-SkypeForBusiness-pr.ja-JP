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
ms.openlocfilehash: 7a471b0e4258728bfaa50558aab54955346b457c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003377"
---
# <a name="get-ccexternalcertificatefilepath"></a><span data-ttu-id="5b776-104">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="5b776-104">Get-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="5b776-p102">Get-CcExternalCertificateFilePath コマンドレットは、Skype for Business Cloud Connector エディションの展開用に外部証明書ファイルのパスを返します。この証明書はユーザーが準備します。</span><span class="sxs-lookup"><span data-stu-id="5b776-p102">The Get-CcExternalCertificateFilePath cmdlet returns the external certificate file path for the Skype for Business Cloud Connector Edition deployment. The user prepares this certificate.</span></span>
  
<span data-ttu-id="5b776-107">このコマンドレットは、Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="5b776-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a><span data-ttu-id="5b776-108">例</span><span class="sxs-lookup"><span data-stu-id="5b776-108">Examples</span></span>
<span data-ttu-id="5b776-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5b776-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="5b776-110">例 1</span><span class="sxs-lookup"><span data-stu-id="5b776-110">Example 1</span></span>

<span data-ttu-id="5b776-111">次の例では、エッジ サーバーの証明書のパスを示します。</span><span class="sxs-lookup"><span data-stu-id="5b776-111">The following example shows the path of the certificate for the Edge Server:</span></span>
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a><span data-ttu-id="5b776-112">例 2</span><span class="sxs-lookup"><span data-stu-id="5b776-112">Example 2</span></span>

<span data-ttu-id="5b776-113">次の例では、仲介サーバーの証明書セットを示します。</span><span class="sxs-lookup"><span data-stu-id="5b776-113">The following example shows the certificate set for the Mediation Server:</span></span>
  
```powershell
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a><span data-ttu-id="5b776-114">解説</span><span class="sxs-lookup"><span data-stu-id="5b776-114">Detailed Description</span></span>
<span data-ttu-id="5b776-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5b776-115"></span></span>

<span data-ttu-id="5b776-p103">展開中またはトポロジの変更時には、エッジ サーバーの証明書および仲介サーバーの証明書 (省略可能) のパスを指定する必要があります。仲介サーバーの証明書は、ゲートウェイと仲介サーバーの間に TLS を使用する場合に必要です。パスを変更するには、Set-CcExternalCertificateFilePath コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5b776-p103">During deployment or when modifying the topology, you need to specify the path for the Edge Server certificate, and, optionally, for the Mediation Server. The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server. To change the path, use the Set-CcExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="5b776-119">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5b776-119">Parameters</span></span>
<span data-ttu-id="5b776-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5b776-120"></span></span>

|<span data-ttu-id="5b776-121">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="5b776-121">**Parameter**</span></span>|<span data-ttu-id="5b776-122">**必須**</span><span class="sxs-lookup"><span data-stu-id="5b776-122">**Required**</span></span>|<span data-ttu-id="5b776-123">**種類**</span><span class="sxs-lookup"><span data-stu-id="5b776-123">**Type**</span></span>|<span data-ttu-id="5b776-124">**説明**</span><span class="sxs-lookup"><span data-stu-id="5b776-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5b776-125">Target</span><span class="sxs-lookup"><span data-stu-id="5b776-125">Target</span></span>  <br/> |<span data-ttu-id="5b776-126">省略可能</span><span class="sxs-lookup"><span data-stu-id="5b776-126">Optional</span></span>  <br/> | <span data-ttu-id="5b776-127">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="5b776-127">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="5b776-p104">必要なファイル パスの種類。種類:</span><span class="sxs-lookup"><span data-stu-id="5b776-p104">Type of file path requested. Types include:</span></span>  <br/> <span data-ttu-id="5b776-130">EdgeServer (既定)</span><span class="sxs-lookup"><span data-stu-id="5b776-130">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="5b776-131">MediationServer</span><span class="sxs-lookup"><span data-stu-id="5b776-131">MediationServer</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="5b776-132">入力の種類</span><span class="sxs-lookup"><span data-stu-id="5b776-132">Input Types</span></span>
<span data-ttu-id="5b776-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5b776-133"></span></span>

<span data-ttu-id="5b776-134">Get-CcExternalCertificateFilePath コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="5b776-134">The Get-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5b776-135">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="5b776-135">Return Types</span></span>
<span data-ttu-id="5b776-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5b776-136"></span></span>

<span data-ttu-id="5b776-137">このコマンドはファイル パスを返します。</span><span class="sxs-lookup"><span data-stu-id="5b776-137">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5b776-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b776-138">See also</span></span>
<span data-ttu-id="5b776-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5b776-139"></span></span>

[<span data-ttu-id="5b776-140">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="5b776-140">Set-CcExternalCertificateFilePath</span></span>](set-ccexternalcertificatefilepath.md)
  

