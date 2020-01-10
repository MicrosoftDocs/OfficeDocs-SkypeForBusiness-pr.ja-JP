---
title: Unregister-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: Unregister-CcAppliance コマンドレットは、オンラインのテナント構成内の PSTN サイトから、現在の Skype for Business Cloud Connector エディションのアプライアンスを登録解除します。
ms.openlocfilehash: 2bd8f3a3ef4ac2b29ab9e7d766836d7a3555c0f4
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003137"
---
# <a name="unregister-ccappliance"></a><span data-ttu-id="d9fec-103">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d9fec-103">Unregister-CcAppliance</span></span>
 
<span data-ttu-id="d9fec-104">Unregister-CcAppliance コマンドレットは、オンラインのテナント構成内の PSTN サイトから、現在の Skype for Business Cloud Connector エディションのアプライアンスを登録解除します。</span><span class="sxs-lookup"><span data-stu-id="d9fec-104">The Unregister-CcAppliance cmdlet unregisters the current Skype for Business Cloud Connector Edition appliance from a PSTN site in the online tenant configuration.</span></span>
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="d9fec-105">例</span><span class="sxs-lookup"><span data-stu-id="d9fec-105">Examples</span></span>
<span data-ttu-id="d9fec-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d9fec-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="d9fec-107">例 1</span><span class="sxs-lookup"><span data-stu-id="d9fec-107">Example 1</span></span>

<span data-ttu-id="d9fec-108">次の例では、オンラインのテナント構成から現在のアプライアンスの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="d9fec-108">The following example unregisters a current appliance from the online tenant configuration:</span></span>
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="d9fec-109">例 2</span><span class="sxs-lookup"><span data-stu-id="d9fec-109">Example 2</span></span>

<span data-ttu-id="d9fec-110">次の例では、オンラインのテナント構成に接続せずにローカルで登録解除するために、構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="d9fec-110">The next example checks the configuration for unregistering locally without connecting to the online tenant configuration:</span></span>
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="d9fec-111">例 3</span><span class="sxs-lookup"><span data-stu-id="d9fec-111">Example 3</span></span>

<span data-ttu-id="d9fec-112">次の例では、「Appliance1」という名前を持つ現在のアプライアンスを「Site1」という PSTN サイトで登録解除します。</span><span class="sxs-lookup"><span data-stu-id="d9fec-112">The next example unregisters the current appliance with the name "Appliance1" to PSTN site "Site1":</span></span>
  
```powershell
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="d9fec-113">解説</span><span class="sxs-lookup"><span data-stu-id="d9fec-113">Detailed Description</span></span>
<span data-ttu-id="d9fec-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d9fec-114"></span></span>

<span data-ttu-id="d9fec-p101">Register-CcAppliance コマンドレットと同様に、CloudConnector.ini ファイルでエッジ サーバーの外部 FQDN と組み合わされた SiteName は PSTN サイトの ID として考慮されます。同じく、CloudConnector.ini ファイルで仲介サーバーの FQDN と組み合わされた ApplianceName は、アプライアンス ID として考慮されます。</span><span class="sxs-lookup"><span data-stu-id="d9fec-p101">Similar to the Register-CcAppliance cmdlet, SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity. Likewise, ApplianceName combined with the Mediation Server FQDN in the CloudConnector.ini file is considered an appliance identity.</span></span>
  
<span data-ttu-id="d9fec-117">アプライアンスの登録が解除されたら、クラウドコネクタ管理サービスを再起動し、NetworkService アカウントとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="d9fec-117">After the appliance is unregistered, restart the Cloud Connector management service and log on as the NetworkService account.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="d9fec-118">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d9fec-118">Parameters</span></span>
<span data-ttu-id="d9fec-119"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d9fec-119"></span></span>

|<span data-ttu-id="d9fec-120">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="d9fec-120">**Parameter**</span></span>|<span data-ttu-id="d9fec-121">**必須**</span><span class="sxs-lookup"><span data-stu-id="d9fec-121">**Required**</span></span>|<span data-ttu-id="d9fec-122">**種類**</span><span class="sxs-lookup"><span data-stu-id="d9fec-122">**Type**</span></span>|<span data-ttu-id="d9fec-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="d9fec-123">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="d9fec-124">SiteName</span><span class="sxs-lookup"><span data-stu-id="d9fec-124">SiteName</span></span> <br/> |<span data-ttu-id="d9fec-125">省略可能</span><span class="sxs-lookup"><span data-stu-id="d9fec-125">Optional</span></span>  <br/> |<span data-ttu-id="d9fec-126">System.String</span><span class="sxs-lookup"><span data-stu-id="d9fec-126">System.String</span></span>  <br/> |<span data-ttu-id="d9fec-p102">アプライアンスが登録されている PSTN サイトの名前。既定値は CloudConnector.ini ファイル内の SiteName 値です。</span><span class="sxs-lookup"><span data-stu-id="d9fec-p102">PSTN site name where the appliance is registered. Default value is SiteName value in CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="d9fec-129">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="d9fec-129">ApplianceName</span></span>  <br/> |<span data-ttu-id="d9fec-130">省略可能</span><span class="sxs-lookup"><span data-stu-id="d9fec-130">Optional</span></span>  <br/> |<span data-ttu-id="d9fec-131">System.String</span><span class="sxs-lookup"><span data-stu-id="d9fec-131">System.String</span></span>  <br/> |<span data-ttu-id="d9fec-p103">現在のアプライアンスの名前。既定の値はホスト サーバーのコンピューター名です。</span><span class="sxs-lookup"><span data-stu-id="d9fec-p103">Name of the current appliance. Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="d9fec-134">Local</span><span class="sxs-lookup"><span data-stu-id="d9fec-134">Local</span></span>  <br/> |<span data-ttu-id="d9fec-135">省略可能</span><span class="sxs-lookup"><span data-stu-id="d9fec-135">Optional</span></span>  <br/> |<span data-ttu-id="d9fec-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="d9fec-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="d9fec-137">オンライン テナント構成に接続することなく、ローカルで登録するための構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="d9fec-137">Check configuration for registration locally without connecting to an online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="d9fec-138">入力の種類</span><span class="sxs-lookup"><span data-stu-id="d9fec-138">Input Types</span></span>
<span data-ttu-id="d9fec-139"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d9fec-139"></span></span>

<span data-ttu-id="d9fec-p104">なし。Unregister-CcAppliance コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="d9fec-p104">None. The Unregister-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="d9fec-142">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="d9fec-142">Return Types</span></span>
<span data-ttu-id="d9fec-143"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d9fec-143"></span></span>

<span data-ttu-id="d9fec-144">なし</span><span class="sxs-lookup"><span data-stu-id="d9fec-144">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d9fec-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9fec-145">See also</span></span>
<span data-ttu-id="d9fec-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d9fec-146"></span></span>

[<span data-ttu-id="d9fec-147">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d9fec-147">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="d9fec-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d9fec-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="d9fec-149">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d9fec-149">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="d9fec-150">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d9fec-150">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  

