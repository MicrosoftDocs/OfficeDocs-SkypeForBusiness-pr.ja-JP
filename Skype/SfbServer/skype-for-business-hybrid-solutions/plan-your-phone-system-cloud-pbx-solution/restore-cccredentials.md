---
title: 復元 CcCredentials
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
ms.openlocfilehash: 045d7f651408b1cbdbd508966da3272ac61d7c04
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="restore-cccredentials"></a><span data-ttu-id="5a1ed-103">復元 CcCredentials</span><span class="sxs-lookup"><span data-stu-id="5a1ed-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="5a1ed-104">Cc-資格情報の復元コマンドレットでは、ビジネスのクラウド コネクタのエディションの展開の現在の Skype のすべての資格情報を復元します。</span><span class="sxs-lookup"><span data-stu-id="5a1ed-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="5a1ed-105">このコマンドレットは、クラウド コネクタ版 2.1 のビジネスには、Skype に適用されます。</span><span class="sxs-lookup"><span data-stu-id="5a1ed-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```

Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="5a1ed-106">解説</span><span class="sxs-lookup"><span data-stu-id="5a1ed-106">Detailed Description</span></span>

<span data-ttu-id="5a1ed-107">復元 CcCredentials コマンドレットでは、すべての資格情報をクリーンアップし、ビジネスのクラウドのコネクタの配置の現在の Skype を使用するすべての資格情報を再入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="5a1ed-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="5a1ed-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5a1ed-108">Parameters</span></span>

<span data-ttu-id="5a1ed-109">なし</span><span class="sxs-lookup"><span data-stu-id="5a1ed-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="5a1ed-110">入力の種類</span><span class="sxs-lookup"><span data-stu-id="5a1ed-110">Input Types</span></span>

<span data-ttu-id="5a1ed-111">なし。</span><span class="sxs-lookup"><span data-stu-id="5a1ed-111">None.</span></span> <span data-ttu-id="5a1ed-112">復元 CcCredentials コマンドレットでは、パイプラインの入力は受け付けられません。</span><span class="sxs-lookup"><span data-stu-id="5a1ed-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5a1ed-113">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="5a1ed-113">Return Types</span></span>

<span data-ttu-id="5a1ed-114">なし。</span><span class="sxs-lookup"><span data-stu-id="5a1ed-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="5a1ed-115">例</span><span class="sxs-lookup"><span data-stu-id="5a1ed-115">Example</span></span>

<span data-ttu-id="5a1ed-116">次の例では、現在のクラウドのコネクタの配置のすべての資格情報が復元されます。</span><span class="sxs-lookup"><span data-stu-id="5a1ed-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="5a1ed-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a1ed-117">See also</span></span>

[<span data-ttu-id="5a1ed-118">Get CcCredential</span><span class="sxs-lookup"><span data-stu-id="5a1ed-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="5a1ed-119">セット CcCredential</span><span class="sxs-lookup"><span data-stu-id="5a1ed-119">Set-CcCredential</span></span>](set-cccredential.md)
  

