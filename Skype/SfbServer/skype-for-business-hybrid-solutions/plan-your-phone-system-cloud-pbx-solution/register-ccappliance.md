---
title: Register-CcAppliance
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
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: Register-CcAppliance コマンドレットは、アプライアンス情報をオンライン テナント構成の PSTN サイトに登録します。 アプライアンスを Skype for Business Cloud Connector エディションの管理サービスで展開および管理する前に、アプライアンスの登録が必要です。
ms.openlocfilehash: a94f9d7189f4872fcee2439afd2b210933f8bb06
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824303"
---
# <a name="register-ccappliance"></a><span data-ttu-id="3cf27-104">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="3cf27-104">Register-CcAppliance</span></span>
 
<span data-ttu-id="3cf27-105">Register-CcAppliance コマンドレットは、アプライアンス情報をオンライン テナント構成の PSTN サイトに登録します。</span><span class="sxs-lookup"><span data-stu-id="3cf27-105">The Register-CcAppliance cmdlet registers appliance information to a PSTN site in an online tenant configuration.</span></span> <span data-ttu-id="3cf27-106">アプライアンスを Skype for Business Cloud Connector エディションの管理サービスで展開および管理する前に、アプライアンスの登録が必要です。</span><span class="sxs-lookup"><span data-stu-id="3cf27-106">An appliance must be registered before it can be deployed and managed by the Skype for Business Cloud Connector Edition management service.</span></span>
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="3cf27-107">例</span><span class="sxs-lookup"><span data-stu-id="3cf27-107">Examples</span></span>
<span data-ttu-id="3cf27-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3cf27-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="3cf27-109">例 1</span><span class="sxs-lookup"><span data-stu-id="3cf27-109">Example 1</span></span>

<span data-ttu-id="3cf27-110">次の例では、現在のアプライアンス情報をオンライン テナント構成に登録します。</span><span class="sxs-lookup"><span data-stu-id="3cf27-110">The following example registers the current appliance information to an online tenant configuration:</span></span>
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="3cf27-111">例 2</span><span class="sxs-lookup"><span data-stu-id="3cf27-111">Example 2</span></span>

<span data-ttu-id="3cf27-112">次の例では、オンライン テナント構成に接続せずにローカルで登録の構成をチェックします。</span><span class="sxs-lookup"><span data-stu-id="3cf27-112">The next example checks configuration for registration locally without connecting to an online tenant configuration:</span></span>
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="3cf27-113">例 3</span><span class="sxs-lookup"><span data-stu-id="3cf27-113">Example 3</span></span>

<span data-ttu-id="3cf27-114">次の例では、「Appliance1」という名前を持つ現在のアプライアンスを「Site1」という PSTN サイトに登録します。</span><span class="sxs-lookup"><span data-stu-id="3cf27-114">The next example registers the current appliance with the name "Appliance1" to the PSTN site "Site1":</span></span>
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="3cf27-115">解説</span><span class="sxs-lookup"><span data-stu-id="3cf27-115">Detailed Description</span></span>
<span data-ttu-id="3cf27-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3cf27-116"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="3cf27-117">テナント管理者のアカウント名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="3cf27-117">You must provide the tenant admin account name and password.</span></span> <span data-ttu-id="3cf27-118">Cloud Connector のオンライン管理用に作成したアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="3cf27-118">Use the account you have created for Cloud Connector online management.</span></span> 
  
<span data-ttu-id="3cf27-119">Release 1.4.2 以前のバージョンでは、次の手順に従って、外部証明書のパスワード、セーフモードのパスワード、ドメイン管理者のパスワード、VM 管理者のパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="3cf27-119">In release 1.4.2 and earlier, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="3cf27-120">リリース 2.0 以降の場合は、指示に従って外部証明書のパスワード、CceService パスワード、CABackupFile パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="3cf27-120">In release 2.0 and later, follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="3cf27-121">登録が終了したら、クラウドコネクタ管理サービスを再起動し、CceService アカウントとしてサービスにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3cf27-121">At the end of registration, restart the Cloud Connector management service and log on to the services as CceService account.</span></span>
  
<span data-ttu-id="3cf27-p104">CloudConnector.ini ファイルでエッジ サーバーの外部 FQDN と組み合わされた SiteName は PSTN サイトの ID として考慮されます。SiteName またはエッジ サーバーの外部 FQDN がサイトの登録に使用されない場合、このアプライアンスに対しては、オンライン テナント構成で新しいサイトが作成されます。PSTN サイトの ID が見つかった場合、PSTN サイトはこの ID を使用します。アプライアンスはこの PSTN サイトに登録されます。</span><span class="sxs-lookup"><span data-stu-id="3cf27-p104">SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity. If neither the SiteName nor the Edge Server external FQDN has been used to register a site, a new site will be created for this appliance in an online tenant configuration. If a PSTN site identity is found, a PSTN site will use this identity and the appliance will be registered to this PSTN site.</span></span> 
  
<span data-ttu-id="3cf27-125">次の場合、コマンドレットは失敗し、Site1 が既に登録されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="3cf27-125">In the following situation, the cmdlet will fail and indicate that Site1 is already registered:</span></span> 
  
- <span data-ttu-id="3cf27-126">SiteName が Site1 であり、エッジ サーバーの外部 FQDN が edgserver1.contoso.com である場合。</span><span class="sxs-lookup"><span data-stu-id="3cf27-126">SiteName is Site1 and the Edge Server external FQDN is edgserver1.contoso.com.</span></span> 
    
- <span data-ttu-id="3cf27-127">SiteName が Site1 であり、エッジ サーバーの外部 FQDN が edgserver.contoso.com である PSTN サイト。</span><span class="sxs-lookup"><span data-stu-id="3cf27-127">A PSTN site whose SiteName is Site1 and Edge Server external FQDN is edgserver.contoso.com.</span></span>
    
- <span data-ttu-id="3cf27-128">SiteName が NewSite で、エッジ サーバーの外部 FQDN が edgserver1.contoso.com である PSTN サイトがすでに登録されている場合。</span><span class="sxs-lookup"><span data-stu-id="3cf27-128">A PSTN site whose SiteName is NewSite and Edge Server external FQDN is edgserver1.contoso.com has been registered.</span></span> 
    
<span data-ttu-id="3cf27-p105">CloudConnector.ini ファイルで仲介サーバーの FQDN と組み合わされた ApplianceName は アプライアンスの ID として考慮されます。ApplianceName または仲介サーバーの FQDN がアプライアンスの登録に使用されない場合、オンライン テナント構成で新しいアプライアンスが作成されます。アプライアンスがすでに登録されている場合、コマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="3cf27-p105">ApplianceName combined with the Mediation Server FQDN in CloudConnector.ini file is considered an Appliance Identity. If neither the ApplianceName nor the Mediation Server FQDN has been used to register an appliance, a new appliance will be created in the online tenant configuration. If the appliance is already registered, the cmdlet will fail.</span></span>
  
<span data-ttu-id="3cf27-132">次の場合、コマンドレットは失敗し、アプライアンスがすでに登録されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="3cf27-132">In the following situation, the cmdlet will fail and indicate that the appliance is already registered:</span></span> 
  
- <span data-ttu-id="3cf27-133">ApplianceName が Appliance1 であり、仲介サーバーの FQDN が ms1.vdomain.com である場合 。</span><span class="sxs-lookup"><span data-stu-id="3cf27-133">ApplianceName is Appliance1 and Mediation server FQDN is ms1.vdomain.com.</span></span>
    
- <span data-ttu-id="3cf27-134">現在の PSTN サイトで、名前が Appliance1 で、仲介サーバーの FQDN が ms.vdomain.com であるアプライアンス、または名前が NewAppliance で、仲介サーバーの FQDN が ms1.vdomain.com であるアプライアンスがすでに登録されている場合。</span><span class="sxs-lookup"><span data-stu-id="3cf27-134">In the current PSTN site, if an appliance whose name Appliance1 and Mediation Server FQDN is ms.vdomain.com or an appliance whose name NewAppliance and Mediation server FQDN is ms1.vdomain.com has been registered.</span></span>
    
## <a name="parameters"></a><span data-ttu-id="3cf27-135">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3cf27-135">Parameters</span></span>
<span data-ttu-id="3cf27-136"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3cf27-136"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="3cf27-137">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="3cf27-137">**Parameter**</span></span>|<span data-ttu-id="3cf27-138">**必須**</span><span class="sxs-lookup"><span data-stu-id="3cf27-138">**Required**</span></span>|<span data-ttu-id="3cf27-139">**種類**</span><span class="sxs-lookup"><span data-stu-id="3cf27-139">**Type**</span></span>|<span data-ttu-id="3cf27-140">**説明**</span><span class="sxs-lookup"><span data-stu-id="3cf27-140">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3cf27-141">SiteName</span><span class="sxs-lookup"><span data-stu-id="3cf27-141">SiteName</span></span>  <br/> |<span data-ttu-id="3cf27-142">省略可能</span><span class="sxs-lookup"><span data-stu-id="3cf27-142">Optional</span></span>  <br/> |<span data-ttu-id="3cf27-143">System.String</span><span class="sxs-lookup"><span data-stu-id="3cf27-143">System.String</span></span>  <br/> |<span data-ttu-id="3cf27-p106">アプライアンスが登録される PSTN サイトの名前。既定の値は CloudConnector.ini ファイル内の SiteName 値です。</span><span class="sxs-lookup"><span data-stu-id="3cf27-p106">PSTN site name to which the appliance is registered. Default value is SiteName value in the CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="3cf27-146">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="3cf27-146">ApplianceName</span></span>  <br/> |<span data-ttu-id="3cf27-147">省略可能</span><span class="sxs-lookup"><span data-stu-id="3cf27-147">Optional</span></span>  <br/> |<span data-ttu-id="3cf27-148">System.String</span><span class="sxs-lookup"><span data-stu-id="3cf27-148">System.String</span></span>  <br/> |<span data-ttu-id="3cf27-p107">現在のアプライアンスの名前。既定の値はホスト サーバーのコンピューター名です。</span><span class="sxs-lookup"><span data-stu-id="3cf27-p107">Name of the current appliance. Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="3cf27-151">Local</span><span class="sxs-lookup"><span data-stu-id="3cf27-151">Local</span></span>  <br/> |<span data-ttu-id="3cf27-152">省略可能</span><span class="sxs-lookup"><span data-stu-id="3cf27-152">Optional</span></span>  <br/> |<span data-ttu-id="3cf27-153">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="3cf27-153">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="3cf27-154">オンライン テナント構成に接続せずにローカルで登録の構成をチェックします。</span><span class="sxs-lookup"><span data-stu-id="3cf27-154">Check configurations for registration locally without connecting to online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="3cf27-155">入力の種類</span><span class="sxs-lookup"><span data-stu-id="3cf27-155">Input Types</span></span>
<span data-ttu-id="3cf27-156"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3cf27-156"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="3cf27-p108">なし。Register-CcAppliance コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="3cf27-p108">None. The Register-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="3cf27-159">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="3cf27-159">Return Types</span></span>
<span data-ttu-id="3cf27-160"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3cf27-160"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="3cf27-161">なし</span><span class="sxs-lookup"><span data-stu-id="3cf27-161">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3cf27-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="3cf27-162">See also</span></span>
<span data-ttu-id="3cf27-163"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3cf27-163"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="3cf27-164">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="3cf27-164">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="3cf27-165">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="3cf27-165">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="3cf27-166">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="3cf27-166">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="3cf27-167">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="3cf27-167">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

