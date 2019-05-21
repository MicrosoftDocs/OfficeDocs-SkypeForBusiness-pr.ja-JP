---
title: Set-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: Set-CcExternalCertificateFilePath コマンドレットは仲介サーバーまたはエッジ サーバーの証明書が保管されているパスを指定します。
ms.openlocfilehash: bc22771c20277d9de99660551864d600f06b3acc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286986"
---
# <a name="set-ccexternalcertificatefilepath"></a><span data-ttu-id="0c655-103">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="0c655-103">Set-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="0c655-104">Set-CcExternalCertificateFilePath コマンドレットは仲介サーバーまたはエッジ サーバーの証明書が保管されているパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="0c655-104">The Set-CcExternalCertificateFilePath cmdlet specifies the path where the certificate for the Mediation Server or Edge Server is stored.</span></span>
  
<span data-ttu-id="0c655-p101">この証明書は、展開時や Skype for Business Cloud Connector エディションの新しいアプライアンスを追加するときに必要になります。コマンドにより、展開後に仲介サーバーの新しい証明書をインポートすることも可能になります。</span><span class="sxs-lookup"><span data-stu-id="0c655-p101">This certificate is required during deployment or when adding new appliances of Skype for Business Cloud Connector Edition. The command also allows importing a new certificate for the Mediation Server after the deployment.</span></span>
  
<span data-ttu-id="0c655-107">このコマンドレットは Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0c655-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="0c655-108">例</span><span class="sxs-lookup"><span data-stu-id="0c655-108">Examples</span></span>
<span data-ttu-id="0c655-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0c655-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="0c655-110">例 1</span><span class="sxs-lookup"><span data-stu-id="0c655-110">Example 1</span></span>

<span data-ttu-id="0c655-111">次の例は、エッジ サーバーの証明書のパスを設定します。</span><span class="sxs-lookup"><span data-stu-id="0c655-111">The following example sets the path of the certificate for the Edge Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a><span data-ttu-id="0c655-112">例 2</span><span class="sxs-lookup"><span data-stu-id="0c655-112">Example 2</span></span>

<span data-ttu-id="0c655-113">次の例は、仲介サーバーの証明書のパスを設定します。</span><span class="sxs-lookup"><span data-stu-id="0c655-113">The next example sets the path of the certificate for the Mediation Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a><span data-ttu-id="0c655-114">例 3</span><span class="sxs-lookup"><span data-stu-id="0c655-114">Example 3</span></span>

<span data-ttu-id="0c655-115">次の例は、仲介サーバーの証明書を更新します。</span><span class="sxs-lookup"><span data-stu-id="0c655-115">The next example updates the certificate for the Mediation Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a><span data-ttu-id="0c655-116">解説</span><span class="sxs-lookup"><span data-stu-id="0c655-116">Detailed Description</span></span>
<span data-ttu-id="0c655-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0c655-117"></span></span>

<span data-ttu-id="0c655-118">展開時またはトポロジを変更しているときに、エッジ サーバーの証明書のパスを指定する必要があります。必要に応じて、仲介サーバーの証明書のパスも任意で指定します。</span><span class="sxs-lookup"><span data-stu-id="0c655-118">During the deployment, or while modifying the topology, you need to specify the path for the Edge Server certificate, and optionally for the Mediation Server certificate.</span></span> 
  
<span data-ttu-id="0c655-119">仲介サーバーの証明書は、TLS がゲートウェイと仲介サーバーの間で使用される場合に必要となります。</span><span class="sxs-lookup"><span data-stu-id="0c655-119">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="0c655-120">クラウドコネクタのアプライアンスを展開して、TLS を展開する場合、仲介サーバーに展開される証明書へのパスのみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0c655-120">When you deploy a Cloud Connector appliance and want to deploy TLS, you can only specify the path to the certificate that will be deployed on the Mediation Server.</span></span> <span data-ttu-id="0c655-121">ただし、既に展開済みのアプライアンス上の仲介証明書を更新する場合は、パスと -Import パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c655-121">However, if you want to update the Mediation certificate on an already deployed appliance, you need to specify the path and the -Import parameter.</span></span> <span data-ttu-id="0c655-122">パスを表示するには、Get-CCExternalCertificateFilePath コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="0c655-122">To see the path, use the Get-CCExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="0c655-123">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0c655-123">Parameters</span></span>
<span data-ttu-id="0c655-124"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0c655-124"></span></span>

|<span data-ttu-id="0c655-125">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="0c655-125">**Parameter**</span></span>|<span data-ttu-id="0c655-126">**必須**</span><span class="sxs-lookup"><span data-stu-id="0c655-126">**Required**</span></span>|<span data-ttu-id="0c655-127">**型**</span><span class="sxs-lookup"><span data-stu-id="0c655-127">**Type**</span></span>|<span data-ttu-id="0c655-128">**説明**</span><span class="sxs-lookup"><span data-stu-id="0c655-128">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="0c655-129">Target</span><span class="sxs-lookup"><span data-stu-id="0c655-129">Target</span></span> <br/> | <span data-ttu-id="0c655-130">必須</span><span class="sxs-lookup"><span data-stu-id="0c655-130">Required</span></span> <br/> |<span data-ttu-id="0c655-131">System.String</span><span class="sxs-lookup"><span data-stu-id="0c655-131">System.String</span></span>  <br/> |<span data-ttu-id="0c655-p103">必要なファイル パスの種類。種類:</span><span class="sxs-lookup"><span data-stu-id="0c655-p103">Type of file path requested. Types include:</span></span>  <br/> <span data-ttu-id="0c655-134">EdgeServer (既定)</span><span class="sxs-lookup"><span data-stu-id="0c655-134">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="0c655-135">MediationServer</span><span class="sxs-lookup"><span data-stu-id="0c655-135">MediationServer</span></span>  <br/> |
|<span data-ttu-id="0c655-136">Import</span><span class="sxs-lookup"><span data-stu-id="0c655-136">Import</span></span>  <br/> |<span data-ttu-id="0c655-137">省略可能</span><span class="sxs-lookup"><span data-stu-id="0c655-137">Optional</span></span>  <br/> |<span data-ttu-id="0c655-138">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0c655-138">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="0c655-p104">証明書が仲介サーバーにインポートされる必要があることを示します。初めてアプライアンスを展開する場合は、このパラメーターは必要ありません。このパラメーターは、既に展開済みのバージョン上で、既存の証明書を変更する場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="0c655-p104">Indicates that the certificate must be imported to the Mediation Server. This parameter is not needed if you deploy an appliance for first time. The parameter is required if you want to change the existing certificate on an already deployed version.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="0c655-142">入力の種類</span><span class="sxs-lookup"><span data-stu-id="0c655-142">Input Types</span></span>
<span data-ttu-id="0c655-143"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0c655-143"></span></span>

<span data-ttu-id="0c655-144">Set-CcExternalCertificateFilePath コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="0c655-144">The Set-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0c655-145">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="0c655-145">Return Types</span></span>
<span data-ttu-id="0c655-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0c655-146"></span></span>

<span data-ttu-id="0c655-147">なし</span><span class="sxs-lookup"><span data-stu-id="0c655-147">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0c655-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c655-148">See also</span></span>
<span data-ttu-id="0c655-149"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0c655-149"></span></span>

[<span data-ttu-id="0c655-150">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="0c655-150">Get-CcExternalCertificateFilePath</span></span>](get-ccexternalcertificatefilepath.md)
  

