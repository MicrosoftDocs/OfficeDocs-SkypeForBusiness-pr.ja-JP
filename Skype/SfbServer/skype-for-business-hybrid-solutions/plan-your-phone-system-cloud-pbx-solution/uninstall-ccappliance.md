---
title: アンインストール CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: Uninstall-CcAppliance コマンドレットは実行中の Skype for Business Cloud Connector エディションのアプライアンスをホスト サーバーからアンインストールします。
ms.openlocfilehash: 325e21d28ef87f9d27e87721452bc3d67d197169
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="uninstall-ccappliance"></a><span data-ttu-id="42481-103">アンインストール CcAppliance</span><span class="sxs-lookup"><span data-stu-id="42481-103">Uninstall-CcAppliance</span></span>
 
<span data-ttu-id="42481-104">Uninstall-CcAppliance コマンドレットは実行中の Skype for Business Cloud Connector エディションのアプライアンスをホスト サーバーからアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="42481-104">The Uninstall-CcAppliance cmdlet uninstalls the running Skype for Business Cloud Connector Edition appliance from the host server.</span></span> 
  
```
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="42481-105">例</span><span class="sxs-lookup"><span data-stu-id="42481-105">Examples</span></span>
<span data-ttu-id="42481-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="42481-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="42481-107">例 1</span><span class="sxs-lookup"><span data-stu-id="42481-107">Example 1</span></span>

<span data-ttu-id="42481-108">次の例では、回収されてしまったし、クラウド コネクタ アプライアンスをホスト サーバーからアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="42481-108">The following example drains and uninstalls the Cloud Connector appliance from the host server:</span></span>
  
```
Uninstall-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="42481-109">例 2</span><span class="sxs-lookup"><span data-stu-id="42481-109">Example 2</span></span>

<span data-ttu-id="42481-110">次の例では、回収されてしまったし、ドレン処理が失敗した場合でも、ホスト サーバーで実行されているクラウド コネクタ アプライアンスを強制的にアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="42481-110">The next example drains and forcibly uninstalls the running Cloud Connector appliance on the host server even if the drain process failed:</span></span>
  
```
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a><span data-ttu-id="42481-111">例 3</span><span class="sxs-lookup"><span data-stu-id="42481-111">Example 3</span></span>

<span data-ttu-id="42481-112">次の使用例は、ユーザーの確認なしのクラウドのコネクタのバックアップ バージョンをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="42481-112">The next example uninstalls a Cloud Connector backup version without the user's confirmation:</span></span>
  
```
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a><span data-ttu-id="42481-113">解説</span><span class="sxs-lookup"><span data-stu-id="42481-113">Detailed Description</span></span>
<span data-ttu-id="42481-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="42481-114"></span></span>

<span data-ttu-id="42481-115">クラウド コネクタの現在実行中のバージョンをアンインストールする場合はドレン サービス最初同時呼び出しの仮想マシンをアンインストールする前に完了させるには、仲介サーバーとエッジ サーバーで実行されます。</span><span class="sxs-lookup"><span data-stu-id="42481-115">If you are uninstalling the current running version of Cloud Connector, drain services are first run on the Mediation Server and Edge Server to let concurrent calls finish before uninstalling the virtual machines.</span></span> <span data-ttu-id="42481-116">バックアップ バージョンをアンインストールしている場合は、ドレイン処理は実行されません。</span><span class="sxs-lookup"><span data-stu-id="42481-116">If you are uninstalling a backup version, draining is not performed.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="42481-117">パラメーター</span><span class="sxs-lookup"><span data-stu-id="42481-117">Parameters</span></span>
<span data-ttu-id="42481-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="42481-118"></span></span>

|<span data-ttu-id="42481-119">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="42481-119">**Parameter**</span></span>|<span data-ttu-id="42481-120">**必須**</span><span class="sxs-lookup"><span data-stu-id="42481-120">**Required**</span></span>|<span data-ttu-id="42481-121">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="42481-121">**Type**</span></span>|<span data-ttu-id="42481-122">**説明**</span><span class="sxs-lookup"><span data-stu-id="42481-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="42481-123">Version</span><span class="sxs-lookup"><span data-stu-id="42481-123">Version</span></span> <br/> | <span data-ttu-id="42481-124">省略可能</span><span class="sxs-lookup"><span data-stu-id="42481-124">Optional</span></span> <br/> |<span data-ttu-id="42481-125">System.String</span><span class="sxs-lookup"><span data-stu-id="42481-125">System.String</span></span>  <br/> | <span data-ttu-id="42481-126">ホスト サーバーからアンインストールされるクラウド コネクタのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="42481-126">The version of Cloud Connector that will be uninstalled from the host server.</span></span> <span data-ttu-id="42481-127">指定されていない場合、現在実行中のバージョンをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="42481-127">If not specified, uninstall the current running version.</span></span> <br/> |
|<span data-ttu-id="42481-128">Force</span><span class="sxs-lookup"><span data-stu-id="42481-128">Force</span></span>  <br/> |<span data-ttu-id="42481-129">省略可能</span><span class="sxs-lookup"><span data-stu-id="42481-129">Optional</span></span>  <br/> |<span data-ttu-id="42481-130">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="42481-130">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="42481-p103">現在の実行中バージョンをアンインストールする場合、仮想マシンをアンインストールする前に仲介サーバーとエッジ サーバーで、サーバーのドレイン処理を試みます。「Force」スイッチを指定すると、ドレイン サービスが失敗した場合でも、仮想マシンはアンインストールされます。このパラメーターは現在の実行中バージョンをアンインストールするためのみに使用されます。</span><span class="sxs-lookup"><span data-stu-id="42481-p103">If uninstalling the current running version, attempt to drain servers on Mediation Server and Edge Server before uninstalling the virtual machines. If you specify the "Force" switch, even if the drain services fail, the virtual machines will be uninstalled. This parameter is only used to uninstall the current running version.</span></span>  <br/> |
|<span data-ttu-id="42481-134">Confirm</span><span class="sxs-lookup"><span data-stu-id="42481-134">Confirm</span></span>  <br/> |<span data-ttu-id="42481-135">省略可能</span><span class="sxs-lookup"><span data-stu-id="42481-135">Optional</span></span>  <br/> |<span data-ttu-id="42481-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="42481-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="42481-137">仮想マシンをアンインストールするのにはユーザーの確認を依頼してください。</span><span class="sxs-lookup"><span data-stu-id="42481-137">Ask user's confirmation to uninstall the virtual machines.</span></span> <span data-ttu-id="42481-138">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="42481-138">Default value is TRUE.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="42481-139">入力の種類</span><span class="sxs-lookup"><span data-stu-id="42481-139">Input Types</span></span>
<span data-ttu-id="42481-140"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="42481-140"></span></span>

<span data-ttu-id="42481-p105">なし。Uninstall-CcAppliance コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="42481-p105">None. The Uninstall-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="42481-143">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="42481-143">Return Types</span></span>
<span data-ttu-id="42481-144"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="42481-144"></span></span>

<span data-ttu-id="42481-145">なし</span><span class="sxs-lookup"><span data-stu-id="42481-145">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="42481-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="42481-146">See also</span></span>
<span data-ttu-id="42481-147"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="42481-147"></span></span>

[<span data-ttu-id="42481-148">インストール CcAppliance</span><span class="sxs-lookup"><span data-stu-id="42481-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="42481-149">発行 CcAppliance</span><span class="sxs-lookup"><span data-stu-id="42481-149">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="42481-150">登録 CcAppliance</span><span class="sxs-lookup"><span data-stu-id="42481-150">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="42481-151">登録解除 CcAppliance</span><span class="sxs-lookup"><span data-stu-id="42481-151">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

