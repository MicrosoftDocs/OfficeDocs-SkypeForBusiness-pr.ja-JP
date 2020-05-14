---
title: Set-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: CcCredential コマンドレットは、現在の Skype for Business Cloud Connector エディションの展開の資格情報を設定します。
ms.openlocfilehash: 3717eb0dcaa46bb6708f40ecb7f94869f24774a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221571"
---
# <a name="set-cccredential"></a><span data-ttu-id="42075-103">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="42075-103">Set-CcCredential</span></span>
 
<span data-ttu-id="42075-104">CcCredential コマンドレットは、現在の Skype for Business Cloud Connector エディションの展開の資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="42075-104">The Set-CcCredential cmdlet sets the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="42075-105">Cloud Connector バージョン2.0 以降では、このコマンドレットを使用して、仮想マシン管理者とドメイン管理者のアカウント情報を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="42075-105">With Cloud Connector version 2.0 and later, this cmdlet can also set the account information for the virtual machine administrator and for the domain administrator.</span></span>
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="42075-106">例</span><span class="sxs-lookup"><span data-stu-id="42075-106">Examples</span></span>
<span data-ttu-id="42075-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="42075-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="42075-108">例 1</span><span class="sxs-lookup"><span data-stu-id="42075-108">Example 1</span></span>

<span data-ttu-id="42075-109">次の例では、テナント管理者のアカウント名とパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="42075-109">The following example specifies the account name and password for the tenant administrator:</span></span>
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a><span data-ttu-id="42075-110">解説</span><span class="sxs-lookup"><span data-stu-id="42075-110">Detailed Description</span></span>
<span data-ttu-id="42075-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="42075-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="42075-112">CcCredential コマンドレットは、テナント管理者のアカウント名とパスワードを設定します。</span><span class="sxs-lookup"><span data-stu-id="42075-112">The Set-CcCredential cmdlet sets the account name and password for the tenant administrator.</span></span> <span data-ttu-id="42075-113">2.0 より前のリリースでは、この管理者はグローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="42075-113">For releases prior to 2.0, this administrator must be a Global Administrator.</span></span> <span data-ttu-id="42075-114">Cloud Connector はこのアカウントを使用して、構成情報を取得し、構成パラメーターを設定し、アプライアンスの状態を Microsoft 365 または Office 365 組織の構成に更新します。</span><span class="sxs-lookup"><span data-stu-id="42075-114">Cloud Connector uses this account to get configuration information, set configuration parameters, and update appliance status to the Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="42075-115">リリース2.0 以降では、このコマンドレットを使用して、VmAdmin および DomainAdmin アカウントのパスワードを更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="42075-115">With release 2.0 and later, you can also use this cmdlet to update the passwords for the VmAdmin and DomainAdmin accounts.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="42075-116">パラメーター</span><span class="sxs-lookup"><span data-stu-id="42075-116">Parameters</span></span>
<span data-ttu-id="42075-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="42075-117"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="42075-118">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="42075-118">**Parameter**</span></span>|<span data-ttu-id="42075-119">**Required**</span><span class="sxs-lookup"><span data-stu-id="42075-119">**Required**</span></span>|<span data-ttu-id="42075-120">**Type**</span><span class="sxs-lookup"><span data-stu-id="42075-120">**Type**</span></span>|<span data-ttu-id="42075-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="42075-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="42075-122">AccountType</span><span class="sxs-lookup"><span data-stu-id="42075-122">AccountType</span></span> <br/> | <span data-ttu-id="42075-123">必須</span><span class="sxs-lookup"><span data-stu-id="42075-123">Required</span></span> <br/> |<span data-ttu-id="42075-124">System.String</span><span class="sxs-lookup"><span data-stu-id="42075-124">System.String</span></span>  <br/> | <span data-ttu-id="42075-125">パラメーターの値は、"TenantAdmin"、"VmAdmin"、または "DomainAdmin" である必要があります。</span><span class="sxs-lookup"><span data-stu-id="42075-125">Parameter value must be "TenantAdmin", "VmAdmin", or "DomainAdmin".</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="42075-126">入力の種類</span><span class="sxs-lookup"><span data-stu-id="42075-126">Input Types</span></span>
<span data-ttu-id="42075-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="42075-127"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="42075-128">なし。</span><span class="sxs-lookup"><span data-stu-id="42075-128">None.</span></span> <span data-ttu-id="42075-129">CcCredential コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="42075-129">The Set-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="42075-130">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="42075-130">Return Types</span></span>
<span data-ttu-id="42075-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="42075-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="42075-132">なし</span><span class="sxs-lookup"><span data-stu-id="42075-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="42075-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="42075-133">See also</span></span>
<span data-ttu-id="42075-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="42075-134"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="42075-135">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="42075-135">Get-CcCredential</span></span>](get-cccredential.md)
  

