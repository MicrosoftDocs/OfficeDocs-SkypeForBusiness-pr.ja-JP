---
title: Install-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: Install-CcAppliance コマンドレットは、AD、中央管理ストア (CMS)、仲介サーバー、エッジ サーバー仮想マシンなどの、Skype for Business Cloud Connector エディションのアプライアンスをホスト　サーバーにインストールします。
ms.openlocfilehash: 01c689c4a4639c12292d59def6b698281f402299
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287273"
---
# <a name="install-ccappliance"></a><span data-ttu-id="63083-103">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="63083-103">Install-CcAppliance</span></span>
 
<span data-ttu-id="63083-104">Install-CcAppliance コマンドレットは、AD、中央管理ストア (CMS)、仲介サーバー、エッジ サーバー仮想マシンなどの、Skype for Business Cloud Connector エディションのアプライアンスをホスト　サーバーにインストールします。</span><span class="sxs-lookup"><span data-stu-id="63083-104">The Install-CcAppliance cmdlet installs the Skype for Business Cloud Connector Edition appliance—including the AD, Central Management Store, Mediation Server, and Edge Server virtual machines—on the host server.</span></span> 
  
```
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="63083-105">例</span><span class="sxs-lookup"><span data-stu-id="63083-105">Examples</span></span>
<span data-ttu-id="63083-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="63083-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="63083-107">例 1</span><span class="sxs-lookup"><span data-stu-id="63083-107">Example 1</span></span>

<span data-ttu-id="63083-108">次の例では、新しいクラウドコネクタアプライアンスをホストサーバーにインストールします。</span><span class="sxs-lookup"><span data-stu-id="63083-108">The following example installs a new Cloud Connector appliance on the host server:</span></span>
  
```
Install-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="63083-109">例 2</span><span class="sxs-lookup"><span data-stu-id="63083-109">Example 2</span></span>

<span data-ttu-id="63083-110">次の例では、Cloud Connector を最新バージョンにアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="63083-110">The following example upgrades Cloud Connector to the latest version:</span></span>
  
```
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a><span data-ttu-id="63083-111">例 3</span><span class="sxs-lookup"><span data-stu-id="63083-111">Example 3</span></span>

<span data-ttu-id="63083-112">次の例では、ホストサーバーにキャッシュされているすべてのクラウドコネクタの資格情報を削除し、すべての資格情報をもう一度指定するようにユーザーに求めるメッセージを表示して、次にクラウドコネクタをインストールします。</span><span class="sxs-lookup"><span data-stu-id="63083-112">The following example removes all Cloud Connector credentials cached on the host server, prompts the user to specify all credential information again, and then installs Cloud Connector:</span></span>
  
```
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a><span data-ttu-id="63083-113">例 4</span><span class="sxs-lookup"><span data-stu-id="63083-113">Example 4</span></span>

<span data-ttu-id="63083-114">次の例は、PowerShell コンソールでの展開のすべての手順を示します。</span><span class="sxs-lookup"><span data-stu-id="63083-114">The following example displays all deployment steps in the PowerShell console:</span></span>
  
```
Install-CcAppliance -ShowStepsOnly
```

<span data-ttu-id="63083-115">ShowStepsOnly パラメーターは、トラブルシューティングのみで使用されます。</span><span class="sxs-lookup"><span data-stu-id="63083-115">The -ShowStepsOnly parameter is for troubleshooting only.</span></span>
  
### <a name="example-5"></a><span data-ttu-id="63083-116">例 5</span><span class="sxs-lookup"><span data-stu-id="63083-116">Example 5</span></span>

<span data-ttu-id="63083-117">次の例では、ホスト サーバーでの展開の各手順で構成ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="63083-117">The following example generates configuration files for each deployment step on the host server.</span></span> <span data-ttu-id="63083-118">構成ファイルは、ホストサーバー \<上\>の ApplianceRoot\\\\>Instances <Version フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="63083-118">Configuration files are saved to the \<ApplianceRoot\>\Instances\\<Version\>-default\ExportedConfig folder on the host server:</span></span>
  
```
Install-CcAppliance -PrepareOnly
```

<span data-ttu-id="63083-119">アプライアンスのルートを判別するには、Get-CcApplianceDirectory コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="63083-119">To determine the appliance root, run the Get-CcApplianceDirectory cmdlet.</span></span> 
  
### <a name="example-6"></a><span data-ttu-id="63083-120">例 6</span><span class="sxs-lookup"><span data-stu-id="63083-120">Example 6</span></span>

<span data-ttu-id="63083-p102">次の例では、Cloud Connector が展開の手順 1、2、3 を実行して仮想スイッチの作成、AD 仮想マシンの作成、および AD サーバーへのドメイン サービスのインストールを行います。既に実行済みの手順はスキップされます。</span><span class="sxs-lookup"><span data-stu-id="63083-p102">In the following example, Cloud Connector runs deployment steps 1, 2, and 3 to create virtual switches, create an AD virtual machine, and install the domain service on the AD server. It skips the step if the step has already been executed:</span></span>
  
```
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

<span data-ttu-id="63083-123">SkipExistingObjects パラメーターは、Steps パラメーターと共に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63083-123">The SkipExistingObjects parameter must be used in conjunction with the Steps parameter.</span></span>
  
> [!NOTE]
> <span data-ttu-id="63083-124">Steps パラメーターは、トラブルシューティングのみで使用されます。</span><span class="sxs-lookup"><span data-stu-id="63083-124">The Steps parameter is for troubleshooting purposes only.</span></span> <span data-ttu-id="63083-125">アプライアンスを展開したり、サービス中のアプライアンスをアップグレードしたりするために、このパラメーターを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="63083-125">Do not use this parameter to deploy an appliance or to upgrade an appliance that is in service.</span></span> 
  
<span data-ttu-id="63083-126">展開の手順を判別するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="63083-126">To determine the steps of the deployment, run the following command:</span></span>
  
<span data-ttu-id="63083-127">Install-CcAppliance -ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="63083-127">Install-CcAppliance -ShowStepsOnly</span></span>
  
## <a name="detailed-description"></a><span data-ttu-id="63083-128">解説</span><span class="sxs-lookup"><span data-stu-id="63083-128">Detailed Description</span></span>
<span data-ttu-id="63083-129"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="63083-129"></span></span>

<span data-ttu-id="63083-130">CcAppliance コマンドレットを使用して、新しいアプライアンスにクラウドコネクタを展開したり、既存のアプライアンスを最新バージョンにアップグレードしたりします。</span><span class="sxs-lookup"><span data-stu-id="63083-130">The Install-CcAppliance cmdlet is used to deploy Cloud Connector to a new appliance or to upgrade an existing appliance to the latest version.</span></span>
  
<span data-ttu-id="63083-131">新しいアプライアンスがある場合は、最初に必ず「Cloud Connector 1.4.1 の展開環境の準備」を読んでから、Register-CcAppliance コマンドレットを実行してアプライアンスを登録し、Install-CcAppliance コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="63083-131">If you have a new appliance, be sure to read Prepare your environment for Cloud Connector first, run the Register-CcAppliance cmdlet to register the appliance, and then run the Install-CcAppliance cmdlet.</span></span> <span data-ttu-id="63083-132">詳細については、「[Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md)」および「[Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63083-132">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
<span data-ttu-id="63083-133">クラウドコネクタの既存の展開を使用していて、アップグレードする場合は、「[新しいバージョンの Cloud connector にアップグレード](upgrade-to-a-new-version-of-cloud-connector.md)する」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="63083-133">If you have an existing deployment of Cloud Connector and you want to upgrade, please follow the instructions in [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
## <a name="parameters"></a><span data-ttu-id="63083-134">パラメーター</span><span class="sxs-lookup"><span data-stu-id="63083-134">Parameters</span></span>
<span data-ttu-id="63083-135"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="63083-135"></span></span>

|<span data-ttu-id="63083-136">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="63083-136">**Parameter**</span></span>|<span data-ttu-id="63083-137">**必須**</span><span class="sxs-lookup"><span data-stu-id="63083-137">**Required**</span></span>|<span data-ttu-id="63083-138">**型**</span><span class="sxs-lookup"><span data-stu-id="63083-138">**Type**</span></span>|<span data-ttu-id="63083-139">**説明**</span><span class="sxs-lookup"><span data-stu-id="63083-139">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="63083-140">PrepareOnly</span><span class="sxs-lookup"><span data-stu-id="63083-140">PrepareOnly</span></span>  <br/> |<span data-ttu-id="63083-141">省略可能</span><span class="sxs-lookup"><span data-stu-id="63083-141">Optional</span></span>  <br/> |<span data-ttu-id="63083-142">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="63083-142">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="63083-p105">展開の各手順について、構成ファイルを生成します。このパラメーターは、トラブルシューティングのみで使用されます。</span><span class="sxs-lookup"><span data-stu-id="63083-p105">Generate configuration files for each deployment step. This parameter is for troubleshooting only.</span></span> <br/> |
|<span data-ttu-id="63083-145">ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="63083-145">ShowStepsOnly</span></span>  <br/> |<span data-ttu-id="63083-146">省略可能</span><span class="sxs-lookup"><span data-stu-id="63083-146">Optional</span></span>  <br/> |<span data-ttu-id="63083-147">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="63083-147">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="63083-p106">展開の手順の名前のみを表示します。このパラメーターは、トラブルシューティングのみで使用されます。</span><span class="sxs-lookup"><span data-stu-id="63083-p106">Display deployment step names only. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="63083-150">SkipExistingObjects</span><span class="sxs-lookup"><span data-stu-id="63083-150">SkipExistingObjects</span></span>  <br/> |<span data-ttu-id="63083-151">省略可能</span><span class="sxs-lookup"><span data-stu-id="63083-151">Optional</span></span>  <br/> |<span data-ttu-id="63083-152">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="63083-152">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="63083-p107">このパラメーターは、Steps パラメーターと共に使用する必要があります。このパラメーターは、トラブルシューティングのみで使用されます。</span><span class="sxs-lookup"><span data-stu-id="63083-p107">This parameter must be used in conjunction with the Steps parameter. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="63083-155">Steps</span><span class="sxs-lookup"><span data-stu-id="63083-155">Steps</span></span>  <br/> |<span data-ttu-id="63083-156">省略可能</span><span class="sxs-lookup"><span data-stu-id="63083-156">Optional</span></span>  <br/> |<span data-ttu-id="63083-157">System.Array</span><span class="sxs-lookup"><span data-stu-id="63083-157">System.Array</span></span>  <br/> |<span data-ttu-id="63083-p108">展開の手順を実行します。このパラメーターは、トラブルシューティングのみで使用されます。</span><span class="sxs-lookup"><span data-stu-id="63083-p108">Run the deployment steps. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="63083-160">Upgrade</span><span class="sxs-lookup"><span data-stu-id="63083-160">Upgrade</span></span>  <br/> |<span data-ttu-id="63083-161">省略可能</span><span class="sxs-lookup"><span data-stu-id="63083-161">Optional</span></span>  <br/> |<span data-ttu-id="63083-162">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="63083-162">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="63083-163">既存の Cloud Connector を最新バージョンに更新します。</span><span class="sxs-lookup"><span data-stu-id="63083-163">Upgrade existing Cloud Connector to the latest version.</span></span>  <br/> |
|<span data-ttu-id="63083-164">UpdateAllCredentials</span><span class="sxs-lookup"><span data-stu-id="63083-164">UpdateAllCredentials</span></span>  <br/> |<span data-ttu-id="63083-165">省略可能</span><span class="sxs-lookup"><span data-stu-id="63083-165">Optional</span></span>  <br/> |<span data-ttu-id="63083-166">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="63083-166">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="63083-167">キャッシュ内のすべてのクラウドコネクタの資格情報を削除します。</span><span class="sxs-lookup"><span data-stu-id="63083-167">Remove all Cloud Connector credentials in the cache.</span></span> <span data-ttu-id="63083-168">ユーザーにインストールのための新しい資格情報を指定するよう求めます。</span><span class="sxs-lookup"><span data-stu-id="63083-168">Prompt the user to specify new credential information for the installation.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="63083-169">入力の種類</span><span class="sxs-lookup"><span data-stu-id="63083-169">Input Types</span></span>
<span data-ttu-id="63083-170"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="63083-170"></span></span>

<span data-ttu-id="63083-p110">なし。Install-CcAppliance  コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="63083-p110">None. The Install-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="63083-173">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="63083-173">Return Types</span></span>
<span data-ttu-id="63083-174"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="63083-174"></span></span>

<span data-ttu-id="63083-175">なし</span><span class="sxs-lookup"><span data-stu-id="63083-175">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="63083-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="63083-176">See also</span></span>
<span data-ttu-id="63083-177"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="63083-177"></span></span>

[<span data-ttu-id="63083-178">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="63083-178">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="63083-179">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="63083-179">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="63083-180">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="63083-180">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="63083-181">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="63083-181">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

