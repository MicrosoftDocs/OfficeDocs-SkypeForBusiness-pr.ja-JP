---
title: 登録解除 CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: Unregister-CcAppliance コマンドレットは、オンラインのテナント構成内の PSTN サイトから、現在の Skype for Business Cloud Connector エディションのアプライアンスを登録解除します。
ms.openlocfilehash: 21bd0a7dffc6a395f829af68a61dfd7523d2c09a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="unregister-ccappliance"></a><span data-ttu-id="28db4-103">登録解除 CcAppliance</span><span class="sxs-lookup"><span data-stu-id="28db4-103">Unregister-CcAppliance</span></span>
 
<span data-ttu-id="28db4-104">Unregister-CcAppliance コマンドレットは、オンラインのテナント構成内の PSTN サイトから、現在の Skype for Business Cloud Connector エディションのアプライアンスを登録解除します。</span><span class="sxs-lookup"><span data-stu-id="28db4-104">The Unregister-CcAppliance cmdlet unregisters the current Skype for Business Cloud Connector Edition appliance from a PSTN site in the online tenant configuration.</span></span>
  
```
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="28db4-105">例</span><span class="sxs-lookup"><span data-stu-id="28db4-105">Examples</span></span>
<span data-ttu-id="28db4-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="28db4-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="28db4-107">例 1</span><span class="sxs-lookup"><span data-stu-id="28db4-107">Example 1</span></span>

<span data-ttu-id="28db4-108">次の例では、オンラインのテナント構成から現在のアプライアンスの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="28db4-108">The following example unregisters a current appliance from the online tenant configuration:</span></span>
  
```
Unregister-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="28db4-109">例 2</span><span class="sxs-lookup"><span data-stu-id="28db4-109">Example 2</span></span>

<span data-ttu-id="28db4-110">次の例では、オンラインのテナント構成に接続せずにローカルに登録を解除するための構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="28db4-110">The next example checks the configuration for unregistering locally without connecting to the online tenant configuration:</span></span>
  
```
Unregister-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="28db4-111">例 3</span><span class="sxs-lookup"><span data-stu-id="28db4-111">Example 3</span></span>

<span data-ttu-id="28db4-112">次の使用例は、PSTN のサイト"Site1"名"Appliance1"を持つ現在のアプライアンスを登録解除します。</span><span class="sxs-lookup"><span data-stu-id="28db4-112">The next example unregisters the current appliance with the name "Appliance1" to PSTN site "Site1":</span></span>
  
```
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="28db4-113">解説</span><span class="sxs-lookup"><span data-stu-id="28db4-113">Detailed Description</span></span>
<span data-ttu-id="28db4-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="28db4-114"></span></span>

<span data-ttu-id="28db4-p101">Register-CcAppliance コマンドレットと同様に、CloudConnector.ini ファイルでエッジ サーバーの外部 FQDN と組み合わされた SiteName は PSTN サイトの ID として考慮されます。同じく、CloudConnector.ini ファイルで仲介サーバーの FQDN と組み合わされた ApplianceName は、アプライアンス ID として考慮されます。</span><span class="sxs-lookup"><span data-stu-id="28db4-p101">Similar to the Register-CcAppliance cmdlet, SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity. Likewise, ApplianceName combined with the Mediation Server FQDN in the CloudConnector.ini file is considered an appliance identity.</span></span>
  
<span data-ttu-id="28db4-117">アプライアンスは、登録されているが、再起動、クラウドのコネクタの管理サービスとログの NetworkService アカウントとして。</span><span class="sxs-lookup"><span data-stu-id="28db4-117">After the appliance is unregistered, restart the Cloud Connector management service and log on as the NetworkService account.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="28db4-118">パラメーター</span><span class="sxs-lookup"><span data-stu-id="28db4-118">Parameters</span></span>
<span data-ttu-id="28db4-119"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="28db4-119"></span></span>

|<span data-ttu-id="28db4-120">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="28db4-120">**Parameter**</span></span>|<span data-ttu-id="28db4-121">**必須**</span><span class="sxs-lookup"><span data-stu-id="28db4-121">**Required**</span></span>|<span data-ttu-id="28db4-122">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="28db4-122">**Type**</span></span>|<span data-ttu-id="28db4-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="28db4-123">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="28db4-124">サイト名</span><span class="sxs-lookup"><span data-stu-id="28db4-124">SiteName</span></span> <br/> |<span data-ttu-id="28db4-125">省略可能</span><span class="sxs-lookup"><span data-stu-id="28db4-125">Optional</span></span>  <br/> |<span data-ttu-id="28db4-126">System.String</span><span class="sxs-lookup"><span data-stu-id="28db4-126">System.String</span></span>  <br/> |<span data-ttu-id="28db4-p102">アプライアンスが登録されている PSTN サイトの名前。既定値は CloudConnector.ini ファイル内の SiteName 値です。</span><span class="sxs-lookup"><span data-stu-id="28db4-p102">PSTN site name where the appliance is registered. Default value is SiteName value in CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="28db4-129">アプライアンス名</span><span class="sxs-lookup"><span data-stu-id="28db4-129">ApplianceName</span></span>  <br/> |<span data-ttu-id="28db4-130">省略可能</span><span class="sxs-lookup"><span data-stu-id="28db4-130">Optional</span></span>  <br/> |<span data-ttu-id="28db4-131">System.String</span><span class="sxs-lookup"><span data-stu-id="28db4-131">System.String</span></span>  <br/> |<span data-ttu-id="28db4-p103">現在のアプライアンスの名前。既定の値はホスト サーバーのコンピューター名です。</span><span class="sxs-lookup"><span data-stu-id="28db4-p103">Name of the current appliance. Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="28db4-134">Local</span><span class="sxs-lookup"><span data-stu-id="28db4-134">Local</span></span>  <br/> |<span data-ttu-id="28db4-135">省略可能</span><span class="sxs-lookup"><span data-stu-id="28db4-135">Optional</span></span>  <br/> |<span data-ttu-id="28db4-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="28db4-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="28db4-137">オンライン テナント構成に接続することなく、ローカルで登録するための構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="28db4-137">Check configuration for registration locally without connecting to an online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="28db4-138">入力の種類</span><span class="sxs-lookup"><span data-stu-id="28db4-138">Input Types</span></span>
<span data-ttu-id="28db4-139"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="28db4-139"></span></span>

<span data-ttu-id="28db4-p104">なし。Unregister-CcAppliance コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="28db4-p104">None. The Unregister-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="28db4-142">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="28db4-142">Return Types</span></span>
<span data-ttu-id="28db4-143"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="28db4-143"></span></span>

<span data-ttu-id="28db4-144">なし</span><span class="sxs-lookup"><span data-stu-id="28db4-144">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="28db4-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="28db4-145">See also</span></span>
<span data-ttu-id="28db4-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="28db4-146"></span></span>

[<span data-ttu-id="28db4-147">登録 CcAppliance</span><span class="sxs-lookup"><span data-stu-id="28db4-147">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="28db4-148">インストール CcAppliance</span><span class="sxs-lookup"><span data-stu-id="28db4-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="28db4-149">アンインストール CcAppliance</span><span class="sxs-lookup"><span data-stu-id="28db4-149">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="28db4-150">発行 CcAppliance</span><span class="sxs-lookup"><span data-stu-id="28db4-150">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  

