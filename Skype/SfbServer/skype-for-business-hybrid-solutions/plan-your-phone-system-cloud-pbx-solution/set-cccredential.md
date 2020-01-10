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
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: Set-CcCredential コマンドレットは、現在の Skype for Business Cloud Connector エディションの展開の資格情報を設定します。
ms.openlocfilehash: bcb88f11fb78d995e6d8271593c2e09bb0b11d22
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003217"
---
# <a name="set-cccredential"></a><span data-ttu-id="2fca0-103">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="2fca0-103">Set-CcCredential</span></span>
 
<span data-ttu-id="2fca0-104">Set-CcCredential コマンドレットは、現在の Skype for Business Cloud Connector エディションの展開の資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="2fca0-104">The Set-CcCredential cmdlet sets the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="2fca0-105">Cloud Connector バージョン2.0 以降では、このコマンドレットでは、仮想マシン管理者とドメイン管理者のアカウント情報を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="2fca0-105">With Cloud Connector version 2.0 and later, this cmdlet can also set the account information for the virtual machine administrator and for the domain administrator.</span></span>
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="2fca0-106">例</span><span class="sxs-lookup"><span data-stu-id="2fca0-106">Examples</span></span>
<span data-ttu-id="2fca0-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2fca0-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="2fca0-108">例 1</span><span class="sxs-lookup"><span data-stu-id="2fca0-108">Example 1</span></span>

<span data-ttu-id="2fca0-109">次の例は、テナント管理者のアカウント名とパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="2fca0-109">The following example specifies the account name and password for the tenant administrator:</span></span>
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a><span data-ttu-id="2fca0-110">解説</span><span class="sxs-lookup"><span data-stu-id="2fca0-110">Detailed Description</span></span>
<span data-ttu-id="2fca0-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2fca0-111"></span></span>

<span data-ttu-id="2fca0-112">Set-CcCredential コマンドレットによって、テナント管理者のアカウント名とパスワードが設定されます。</span><span class="sxs-lookup"><span data-stu-id="2fca0-112">The Set-CcCredential cmdlet sets the account name and password for the tenant administrator.</span></span> <span data-ttu-id="2fca0-113">2.0 より前のリリースでは、この管理者は、Office 365 の全体管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fca0-113">For releases prior to 2.0, this administrator must be an Office 365 Global Administrator.</span></span> <span data-ttu-id="2fca0-114">クラウドコネクタはこのアカウントを使用して、構成情報を取得し、構成パラメーターを設定し、アプライアンスの状態を Office 365 テナント構成に更新します。</span><span class="sxs-lookup"><span data-stu-id="2fca0-114">Cloud Connector uses this account to get configuration information, set configuration parameters, and update appliance status to the Office 365 tenant configuration.</span></span> <span data-ttu-id="2fca0-115">リリース2.0 以降では、このコマンドレットを使用して、VmAdmin および DomainAdmin アカウントのパスワードを更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="2fca0-115">With release 2.0 and later, you can also use this cmdlet to update the passwords for the VmAdmin and DomainAdmin accounts.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="2fca0-116">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2fca0-116">Parameters</span></span>
<span data-ttu-id="2fca0-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2fca0-117"></span></span>

|<span data-ttu-id="2fca0-118">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="2fca0-118">**Parameter**</span></span>|<span data-ttu-id="2fca0-119">**必須**</span><span class="sxs-lookup"><span data-stu-id="2fca0-119">**Required**</span></span>|<span data-ttu-id="2fca0-120">**種類**</span><span class="sxs-lookup"><span data-stu-id="2fca0-120">**Type**</span></span>|<span data-ttu-id="2fca0-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="2fca0-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="2fca0-122">AccountType</span><span class="sxs-lookup"><span data-stu-id="2fca0-122">AccountType</span></span> <br/> | <span data-ttu-id="2fca0-123">必須</span><span class="sxs-lookup"><span data-stu-id="2fca0-123">Required</span></span> <br/> |<span data-ttu-id="2fca0-124">System.String</span><span class="sxs-lookup"><span data-stu-id="2fca0-124">System.String</span></span>  <br/> | <span data-ttu-id="2fca0-125">パラメーター値は「TenantAdmin」、「VmAdmin」、または「DomainAdmin」にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fca0-125">Parameter value must be "TenantAdmin", "VmAdmin", or "DomainAdmin".</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="2fca0-126">入力の種類</span><span class="sxs-lookup"><span data-stu-id="2fca0-126">Input Types</span></span>
<span data-ttu-id="2fca0-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2fca0-127"></span></span>

<span data-ttu-id="2fca0-p102">なし。Set-CcCredential コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="2fca0-p102">None. The Set-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2fca0-130">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="2fca0-130">Return Types</span></span>
<span data-ttu-id="2fca0-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2fca0-131"></span></span>

<span data-ttu-id="2fca0-132">なし</span><span class="sxs-lookup"><span data-stu-id="2fca0-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2fca0-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="2fca0-133">See also</span></span>
<span data-ttu-id="2fca0-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2fca0-134"></span></span>

[<span data-ttu-id="2fca0-135">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="2fca0-135">Get-CcCredential</span></span>](get-cccredential.md)
  

