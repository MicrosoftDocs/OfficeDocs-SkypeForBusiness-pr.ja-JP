---
title: セット CcCredential
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: Set-CcCredential コマンドレットは、現在の Skype for Business Cloud Connector エディションの展開の資格情報を設定します。
ms.openlocfilehash: 7680f863ccf082ddb8359c7d3fcefc2c058b6a40
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="set-cccredential"></a><span data-ttu-id="ae758-103">セット CcCredential</span><span class="sxs-lookup"><span data-stu-id="ae758-103">Set-CcCredential</span></span>
 
<span data-ttu-id="ae758-104">Set-CcCredential コマンドレットは、現在の Skype for Business Cloud Connector エディションの展開の資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="ae758-104">The Set-CcCredential cmdlet sets the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="ae758-105">クラウド コネクタ バージョン 2.0 以降では、このコマンドレットも設定できますアカウントについては、仮想マシンの管理者およびドメイン管理者。</span><span class="sxs-lookup"><span data-stu-id="ae758-105">With Cloud Connector version 2.0 and later, this cmdlet can also set the account information for the virtual machine administrator and for the domain administrator.</span></span>
  
```
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="ae758-106">例</span><span class="sxs-lookup"><span data-stu-id="ae758-106">Examples</span></span>
<span data-ttu-id="ae758-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ae758-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="ae758-108">例 1</span><span class="sxs-lookup"><span data-stu-id="ae758-108">Example 1</span></span>

<span data-ttu-id="ae758-109">次の例は、テナント管理者のアカウント名とパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae758-109">The following example specifies the account name and password for the tenant administrator:</span></span>
  
```
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a><span data-ttu-id="ae758-110">解説</span><span class="sxs-lookup"><span data-stu-id="ae758-110">Detailed Description</span></span>
<span data-ttu-id="ae758-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ae758-111"></span></span>

<span data-ttu-id="ae758-112">Set-CcCredential コマンドレットによって、テナント管理者のアカウント名とパスワードが設定されます。</span><span class="sxs-lookup"><span data-stu-id="ae758-112">The Set-CcCredential cmdlet sets the account name and password for the tenant administrator.</span></span> <span data-ttu-id="ae758-113">2.0 より前のリリース、この管理者は Office 365 のグローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae758-113">For releases prior to 2.0, this administrator must be an Office 365 Global Administrator.</span></span> <span data-ttu-id="ae758-114">クラウドのコネクタは、構成情報を取得、構成パラメーター、およびアプライアンスの状態の更新プログラムを Office 365 のテナント構成に設定するのにはこのアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae758-114">Cloud Connector uses this account to get configuration information, set configuration parameters, and update appliance status to the Office 365 tenant configuration.</span></span> <span data-ttu-id="ae758-115">2.0 のリリースし、後で使用することもこのコマンドレット、VmAdmin および DomainAdmin のアカウントのパスワードを更新します。</span><span class="sxs-lookup"><span data-stu-id="ae758-115">With release 2.0 and later, you can also use this cmdlet to update the passwords for the VmAdmin and DomainAdmin accounts.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="ae758-116">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ae758-116">Parameters</span></span>
<span data-ttu-id="ae758-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ae758-117"></span></span>

|<span data-ttu-id="ae758-118">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="ae758-118">**Parameter**</span></span>|<span data-ttu-id="ae758-119">**必須**</span><span class="sxs-lookup"><span data-stu-id="ae758-119">**Required**</span></span>|<span data-ttu-id="ae758-120">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="ae758-120">**Type**</span></span>|<span data-ttu-id="ae758-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="ae758-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="ae758-122">AccountType</span><span class="sxs-lookup"><span data-stu-id="ae758-122">AccountType</span></span> <br/> | <span data-ttu-id="ae758-123">必須</span><span class="sxs-lookup"><span data-stu-id="ae758-123">Required</span></span> <br/> |<span data-ttu-id="ae758-124">System.String</span><span class="sxs-lookup"><span data-stu-id="ae758-124">System.String</span></span>  <br/> | <span data-ttu-id="ae758-125">パラメーター値は「TenantAdmin」、「VmAdmin」、または「DomainAdmin」にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae758-125">Parameter value must be "TenantAdmin", "VmAdmin", or "DomainAdmin".</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="ae758-126">入力の種類</span><span class="sxs-lookup"><span data-stu-id="ae758-126">Input Types</span></span>
<span data-ttu-id="ae758-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ae758-127"></span></span>

<span data-ttu-id="ae758-p102">なし。Set-CcCredential コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="ae758-p102">None. The Set-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ae758-130">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="ae758-130">Return Types</span></span>
<span data-ttu-id="ae758-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ae758-131"></span></span>

<span data-ttu-id="ae758-132">なし</span><span class="sxs-lookup"><span data-stu-id="ae758-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ae758-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae758-133">See also</span></span>
<span data-ttu-id="ae758-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ae758-134"></span></span>

[<span data-ttu-id="ae758-135">Get CcCredential</span><span class="sxs-lookup"><span data-stu-id="ae758-135">Get-CcCredential</span></span>](get-cccredential.md)
  

