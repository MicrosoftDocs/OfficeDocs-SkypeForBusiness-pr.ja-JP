---
title: Restore-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: '[Cc-Credentials の復元] コマンドレットは、現在の Skype for Business Cloud Connector エディションの展開のすべての資格情報を復元します。'
ms.openlocfilehash: b2cd35b284bcd7e49aabbaa3055c397915565d09
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824243"
---
# <a name="restore-cccredentials"></a><span data-ttu-id="f083a-103">Restore-CcCredentials</span><span class="sxs-lookup"><span data-stu-id="f083a-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="f083a-104">[Cc-Credentials の復元] コマンドレットは、現在の Skype for Business Cloud Connector エディションの展開のすべての資格情報を復元します。</span><span class="sxs-lookup"><span data-stu-id="f083a-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="f083a-105">このコマンドレットは、Skype for Business Cloud Connector エディション2.1 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="f083a-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="f083a-106">解説</span><span class="sxs-lookup"><span data-stu-id="f083a-106">Detailed Description</span></span>

<span data-ttu-id="f083a-107">Restore/CcCredentials コマンドレットはすべての資格情報を消去し、現在の Skype for Business Cloud Connector の展開で使用されるすべての資格情報を再入力するように求めます。</span><span class="sxs-lookup"><span data-stu-id="f083a-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="f083a-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f083a-108">Parameters</span></span>

<span data-ttu-id="f083a-109">なし</span><span class="sxs-lookup"><span data-stu-id="f083a-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="f083a-110">入力の種類</span><span class="sxs-lookup"><span data-stu-id="f083a-110">Input Types</span></span>

<span data-ttu-id="f083a-111">なし。</span><span class="sxs-lookup"><span data-stu-id="f083a-111">None.</span></span> <span data-ttu-id="f083a-112">Restore-CcCredentials コマンドレットはパイプライン入力を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="f083a-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f083a-113">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="f083a-113">Return Types</span></span>

<span data-ttu-id="f083a-114">なし。</span><span class="sxs-lookup"><span data-stu-id="f083a-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="f083a-115">例</span><span class="sxs-lookup"><span data-stu-id="f083a-115">Example</span></span>

<span data-ttu-id="f083a-116">次の例では、現在のクラウドコネクタ展開のすべての資格情報を復元します。</span><span class="sxs-lookup"><span data-stu-id="f083a-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="f083a-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="f083a-117">See also</span></span>

[<span data-ttu-id="f083a-118">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="f083a-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="f083a-119">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="f083a-119">Set-CcCredential</span></span>](set-cccredential.md)
  

