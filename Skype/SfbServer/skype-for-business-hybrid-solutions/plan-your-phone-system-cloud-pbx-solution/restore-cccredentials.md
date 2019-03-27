---
title: Restore-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: Cc-資格情報の復元コマンドレットでは、ビジネスのクラウド コネクタのエディションの展開の現在の Skype のすべての資格情報を復元します。
ms.openlocfilehash: 0b790b9f2edab9fade2738c3c95348be864f9017
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891469"
---
# <a name="restore-cccredentials"></a><span data-ttu-id="972c3-103">Restore-CcCredentials</span><span class="sxs-lookup"><span data-stu-id="972c3-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="972c3-104">Cc-資格情報の復元コマンドレットでは、ビジネスのクラウド コネクタのエディションの展開の現在の Skype のすべての資格情報を復元します。</span><span class="sxs-lookup"><span data-stu-id="972c3-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="972c3-105">このコマンドレットは、クラウド コネクタ版 2.1 のビジネスには、Skype に適用されます。</span><span class="sxs-lookup"><span data-stu-id="972c3-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```
Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="972c3-106">解説</span><span class="sxs-lookup"><span data-stu-id="972c3-106">Detailed Description</span></span>

<span data-ttu-id="972c3-107">復元 CcCredentials コマンドレットでは、すべての資格情報をクリーンアップし、ビジネスのクラウドのコネクタの配置の現在の Skype を使用するすべての資格情報を再入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="972c3-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="972c3-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="972c3-108">Parameters</span></span>

<span data-ttu-id="972c3-109">なし</span><span class="sxs-lookup"><span data-stu-id="972c3-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="972c3-110">入力の種類</span><span class="sxs-lookup"><span data-stu-id="972c3-110">Input Types</span></span>

<span data-ttu-id="972c3-111">なし。</span><span class="sxs-lookup"><span data-stu-id="972c3-111">None.</span></span> <span data-ttu-id="972c3-112">復元 CcCredentials コマンドレットでは、パイプラインの入力は受け付けられません。</span><span class="sxs-lookup"><span data-stu-id="972c3-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="972c3-113">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="972c3-113">Return Types</span></span>

<span data-ttu-id="972c3-114">なし。</span><span class="sxs-lookup"><span data-stu-id="972c3-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="972c3-115">例</span><span class="sxs-lookup"><span data-stu-id="972c3-115">Example</span></span>

<span data-ttu-id="972c3-116">次の例では、現在のクラウドのコネクタの配置のすべての資格情報が復元されます。</span><span class="sxs-lookup"><span data-stu-id="972c3-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="972c3-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="972c3-117">See also</span></span>

[<span data-ttu-id="972c3-118">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="972c3-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="972c3-119">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="972c3-119">Set-CcCredential</span></span>](set-cccredential.md)
  

