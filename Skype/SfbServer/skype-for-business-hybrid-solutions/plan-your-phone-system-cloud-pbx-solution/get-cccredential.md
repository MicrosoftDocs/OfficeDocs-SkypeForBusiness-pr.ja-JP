---
title: Get-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: Get-CcCredential コマンドレットは、現在の Skype for Business Cloud Connector エディションの展開の資格情報を返します。
ms.openlocfilehash: 87dd3934767a4be7afb57889fd0641e8507fba13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287336"
---
# <a name="get-cccredential"></a><span data-ttu-id="73b55-103">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="73b55-103">Get-CcCredential</span></span>
 
<span data-ttu-id="73b55-104">Get-CcCredential コマンドレットは、現在の Skype for Business Cloud Connector エディションの展開の資格情報を返します。</span><span class="sxs-lookup"><span data-stu-id="73b55-104">The Get-CcCredential cmdlet returns the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="73b55-105">バージョン2.0 以降では、-DisplayPassword パラメーターを使用して、TenantAdmin、DomainAdmin、および VMAdmin のパスワードを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="73b55-105">With Version 2.0 and later, you can also use the -DisplayPassword parameter to show the passwords for TenantAdmin, DomainAdmin, and VMAdmin.</span></span>
  
```
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="73b55-106">例</span><span class="sxs-lookup"><span data-stu-id="73b55-106">Examples</span></span>
<span data-ttu-id="73b55-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="73b55-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="73b55-108">例 1</span><span class="sxs-lookup"><span data-stu-id="73b55-108">Example 1</span></span>

<span data-ttu-id="73b55-109">次の例は、Cloud Connector 仮想マシン ドメインのドメイン管理者の資格情報を返します。</span><span class="sxs-lookup"><span data-stu-id="73b55-109">The following example returns the credential of the domain administrator of the Cloud Connector virtual machine domain:</span></span>
  
```
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a><span data-ttu-id="73b55-110">解説</span><span class="sxs-lookup"><span data-stu-id="73b55-110">Detailed Description</span></span>
<span data-ttu-id="73b55-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="73b55-111"></span></span>

<span data-ttu-id="73b55-p101">Get-CcCredential コマンドレットは指定したアカウントの種類についての資格情報を返します。これらの資格情報は、現在のアプライアンスの展開時に Register-CcAppliance コマンドレットおよび Install-CcAppliance コマンドレットを実行する管理者によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="73b55-p101">The Get-CcCredential cmdlet returns the credential information about the specified account type. These credentials are specified by the administrator who runs the Register-CcAppliance and Install-CcAppliance cmdlets when deploying the current appliance.</span></span> 
  
<span data-ttu-id="73b55-p102">Get-CcCredential コマンドレットは、System.Management.Automation.PSCredential オブジェクトのインスタンスを返します。戻りオブジェクトのパスワード プロパティは　System.Security.SecureString です。</span><span class="sxs-lookup"><span data-stu-id="73b55-p102">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object. The password property of the return object is System.Security.SecureString.</span></span>
  
<span data-ttu-id="73b55-116">ドメイン管理者のパスワードのクリア テキストを取得する場合は、必ずホスト サーバーの現在のログオン アカウントでパスワードが入力されるようにしてから、PowerShell コンソールを管理者として開いて以下のスクリプトを実行してください。</span><span class="sxs-lookup"><span data-stu-id="73b55-116">If you want to get the clear text of the domain administrator password, be sure the password is input by your current logon account on the host server, and then open a PowerShell console as administrator and run the below script:</span></span>
  
```
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a><span data-ttu-id="73b55-117">パラメーター</span><span class="sxs-lookup"><span data-stu-id="73b55-117">Parameters</span></span>
<span data-ttu-id="73b55-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="73b55-118"></span></span>

|<span data-ttu-id="73b55-119">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="73b55-119">**Parameter**</span></span>|<span data-ttu-id="73b55-120">**必須**</span><span class="sxs-lookup"><span data-stu-id="73b55-120">**Required**</span></span>|<span data-ttu-id="73b55-121">**型**</span><span class="sxs-lookup"><span data-stu-id="73b55-121">**Type**</span></span>|<span data-ttu-id="73b55-122">**説明**</span><span class="sxs-lookup"><span data-stu-id="73b55-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="73b55-123">AccountType</span><span class="sxs-lookup"><span data-stu-id="73b55-123">AccountType</span></span> <br/> |<span data-ttu-id="73b55-124">必須</span><span class="sxs-lookup"><span data-stu-id="73b55-124">Required</span></span>  <br/> | <span data-ttu-id="73b55-125">System.String</span><span class="sxs-lookup"><span data-stu-id="73b55-125">System.String</span></span> <br/> | <span data-ttu-id="73b55-126">AccountType の値は次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="73b55-126">AccountType value can be one of the following:</span></span> <br/>  <span data-ttu-id="73b55-127">VmAdmin: クラウドコネクタ仮想マシンのローカル管理者。</span><span class="sxs-lookup"><span data-stu-id="73b55-127">VmAdmin: the local administrator of Cloud Connector virtual machines.</span></span> <br/>  <span data-ttu-id="73b55-128">DomainAdmin: Cloud Connector 仮想マシン ドメインのドメイン管理者。</span><span class="sxs-lookup"><span data-stu-id="73b55-128">DomainAdmin: Domain administrator of Cloud Connector virtual machine domain.</span></span> <br/>  <span data-ttu-id="73b55-129">SafeModeAdmin: Cloud Connector 仮想マシンのドメイン コントローラーの SafeModeAdmin。</span><span class="sxs-lookup"><span data-stu-id="73b55-129">SafeModeAdmin: SafeModeAdmin of Cloud Connector virtual machine domain controller.</span></span> <br/>  <span data-ttu-id="73b55-130">ExternalCert: エッジー サーバー上にインストールされた外部証明書のアカウント。</span><span class="sxs-lookup"><span data-stu-id="73b55-130">ExternalCert: Account of external certificate installed on the Edge Server.</span></span> <br/>  <span data-ttu-id="73b55-131">TenantAdmin: O365 テナントの管理者。</span><span class="sxs-lookup"><span data-stu-id="73b55-131">TenantAdmin: Administrator of the O365 tenant.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="73b55-132">入力の種類</span><span class="sxs-lookup"><span data-stu-id="73b55-132">Input Types</span></span>
<span data-ttu-id="73b55-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="73b55-133"></span></span>

<span data-ttu-id="73b55-p103">なし。Get-CcCredential コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="73b55-p103">None. The Get-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="73b55-136">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="73b55-136">Return Types</span></span>
<span data-ttu-id="73b55-137"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="73b55-137"></span></span>

<span data-ttu-id="73b55-138">Get-CcCredential コマンドレットは、System.Management.Automation.PSCredential オブジェクトのインスタンスを返します。</span><span class="sxs-lookup"><span data-stu-id="73b55-138">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="73b55-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="73b55-139">See also</span></span>
<span data-ttu-id="73b55-140"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="73b55-140"></span></span>

[<span data-ttu-id="73b55-141">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="73b55-141">Set-CcCredential</span></span>](set-cccredential.md)
  

