---
title: セット CcExternalCertificateFilePath
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: Set-CcExternalCertificateFilePath コマンドレットは仲介サーバーまたはエッジ サーバーの証明書が保管されているパスを指定します。
ms.openlocfilehash: 89216fb2b56130dd76b711a483c6279ac1073392
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="set-ccexternalcertificatefilepath"></a><span data-ttu-id="faa24-103">セット CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="faa24-103">Set-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="faa24-104">Set-CcExternalCertificateFilePath コマンドレットは仲介サーバーまたはエッジ サーバーの証明書が保管されているパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="faa24-104">The Set-CcExternalCertificateFilePath cmdlet specifies the path where the certificate for the Mediation Server or Edge Server is stored.</span></span>
  
<span data-ttu-id="faa24-p101">この証明書は、展開時や Skype for Business Cloud Connector エディションの新しいアプライアンスを追加するときに必要になります。コマンドにより、展開後に仲介サーバーの新しい証明書をインポートすることも可能になります。</span><span class="sxs-lookup"><span data-stu-id="faa24-p101">This certificate is required during deployment or when adding new appliances of Skype for Business Cloud Connector Edition. The command also allows importing a new certificate for the Mediation Server after the deployment.</span></span>
  
<span data-ttu-id="faa24-107">このコマンドレットは Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="faa24-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="faa24-108">例</span><span class="sxs-lookup"><span data-stu-id="faa24-108">Examples</span></span>
<span data-ttu-id="faa24-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="faa24-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="faa24-110">例 1</span><span class="sxs-lookup"><span data-stu-id="faa24-110">Example 1</span></span>

<span data-ttu-id="faa24-111">次の例は、エッジ サーバーの証明書のパスを設定します。</span><span class="sxs-lookup"><span data-stu-id="faa24-111">The following example sets the path of the certificate for the Edge Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a><span data-ttu-id="faa24-112">例 2</span><span class="sxs-lookup"><span data-stu-id="faa24-112">Example 2</span></span>

<span data-ttu-id="faa24-113">次の例は、仲介サーバーの証明書のパスを設定します。</span><span class="sxs-lookup"><span data-stu-id="faa24-113">The next example sets the path of the certificate for the Mediation Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a><span data-ttu-id="faa24-114">例 3</span><span class="sxs-lookup"><span data-stu-id="faa24-114">Example 3</span></span>

<span data-ttu-id="faa24-115">次の例は、仲介サーバーの証明書を更新します。</span><span class="sxs-lookup"><span data-stu-id="faa24-115">The next example updates the certificate for the Mediation Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a><span data-ttu-id="faa24-116">解説</span><span class="sxs-lookup"><span data-stu-id="faa24-116">Detailed Description</span></span>
<span data-ttu-id="faa24-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="faa24-117"></span></span>

<span data-ttu-id="faa24-118">展開時またはトポロジを変更しているときに、エッジ サーバーの証明書のパスを指定する必要があります。必要に応じて、仲介サーバーの証明書のパスも任意で指定します。</span><span class="sxs-lookup"><span data-stu-id="faa24-118">During the deployment, or while modifying the topology, you need to specify the path for the Edge Server certificate, and optionally for the Mediation Server certificate.</span></span> 
  
<span data-ttu-id="faa24-119">仲介サーバーの証明書は、TLS がゲートウェイと仲介サーバーの間で使用される場合に必要となります。</span><span class="sxs-lookup"><span data-stu-id="faa24-119">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="faa24-120">クラウド コネクタのアプライアンスを導入し、TLS を展開する仲介サーバー上に配置される証明書へのパスのみ指定できます。</span><span class="sxs-lookup"><span data-stu-id="faa24-120">When you deploy a Cloud Connector appliance and want to deploy TLS, you can only specify the path to the certificate that will be deployed on the Mediation Server.</span></span> <span data-ttu-id="faa24-121">ただし、既に展開済みのアプライアンス上の仲介証明書を更新する場合は、パスと -Import パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="faa24-121">However, if you want to update the Mediation certificate on an already deployed appliance, you need to specify the path and the -Import parameter.</span></span> <span data-ttu-id="faa24-122">パスを表示するには、Get-CCExternalCertificateFilePath コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="faa24-122">To see the path, use the Get-CCExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="faa24-123">パラメーター</span><span class="sxs-lookup"><span data-stu-id="faa24-123">Parameters</span></span>
<span data-ttu-id="faa24-124"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="faa24-124"></span></span>

|<span data-ttu-id="faa24-125">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="faa24-125">**Parameter**</span></span>|<span data-ttu-id="faa24-126">**必須**</span><span class="sxs-lookup"><span data-stu-id="faa24-126">**Required**</span></span>|<span data-ttu-id="faa24-127">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="faa24-127">**Type**</span></span>|<span data-ttu-id="faa24-128">**説明**</span><span class="sxs-lookup"><span data-stu-id="faa24-128">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="faa24-129">Target</span><span class="sxs-lookup"><span data-stu-id="faa24-129">Target</span></span> <br/> | <span data-ttu-id="faa24-130">必須</span><span class="sxs-lookup"><span data-stu-id="faa24-130">Required</span></span> <br/> |<span data-ttu-id="faa24-131">System.String</span><span class="sxs-lookup"><span data-stu-id="faa24-131">System.String</span></span>  <br/> |<span data-ttu-id="faa24-p103">必要なファイル パスの種類。種類:</span><span class="sxs-lookup"><span data-stu-id="faa24-p103">Type of file path requested. Types include:</span></span>  <br/> <span data-ttu-id="faa24-134">EdgeServer (既定)</span><span class="sxs-lookup"><span data-stu-id="faa24-134">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="faa24-135">MediationServer</span><span class="sxs-lookup"><span data-stu-id="faa24-135">MediationServer</span></span>  <br/> |
|<span data-ttu-id="faa24-136">Import</span><span class="sxs-lookup"><span data-stu-id="faa24-136">Import</span></span>  <br/> |<span data-ttu-id="faa24-137">省略可能</span><span class="sxs-lookup"><span data-stu-id="faa24-137">Optional</span></span>  <br/> |<span data-ttu-id="faa24-138">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="faa24-138">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="faa24-p104">証明書が仲介サーバーにインポートされる必要があることを示します。初めてアプライアンスを展開する場合は、このパラメーターは必要ありません。このパラメーターは、既に展開済みのバージョン上で、既存の証明書を変更する場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="faa24-p104">Indicates that the certificate must be imported to the Mediation Server. This parameter is not needed if you deploy an appliance for first time. The parameter is required if you want to change the existing certificate on an already deployed version.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="faa24-142">入力の種類</span><span class="sxs-lookup"><span data-stu-id="faa24-142">Input Types</span></span>
<span data-ttu-id="faa24-143"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="faa24-143"></span></span>

<span data-ttu-id="faa24-144">Set-CcExternalCertificateFilePath コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="faa24-144">The Set-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="faa24-145">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="faa24-145">Return Types</span></span>
<span data-ttu-id="faa24-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="faa24-146"></span></span>

<span data-ttu-id="faa24-147">なし</span><span class="sxs-lookup"><span data-stu-id="faa24-147">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="faa24-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="faa24-148">See also</span></span>
<span data-ttu-id="faa24-149"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="faa24-149"></span></span>

[<span data-ttu-id="faa24-150">Get CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="faa24-150">Get-CcExternalCertificateFilePath</span></span>](get-ccexternalcertificatefilepath.md)
  

