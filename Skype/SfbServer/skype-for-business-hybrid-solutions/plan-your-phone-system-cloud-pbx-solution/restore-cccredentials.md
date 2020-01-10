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
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: '[Cc-Credentials の復元] コマンドレットは、現在の Skype for Business Cloud Connector エディションの展開のすべての資格情報を復元します。'
ms.openlocfilehash: adac3f0b9ca6cf392b537a9c5d0f2095021c7120
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003247"
---
# <a name="restore-cccredentials"></a><span data-ttu-id="dd6c3-103">Restore-CcCredentials</span><span class="sxs-lookup"><span data-stu-id="dd6c3-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="dd6c3-104">[Cc-Credentials の復元] コマンドレットは、現在の Skype for Business Cloud Connector エディションの展開のすべての資格情報を復元します。</span><span class="sxs-lookup"><span data-stu-id="dd6c3-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="dd6c3-105">このコマンドレットは、Skype for Business Cloud Connector エディション2.1 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="dd6c3-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="dd6c3-106">解説</span><span class="sxs-lookup"><span data-stu-id="dd6c3-106">Detailed Description</span></span>

<span data-ttu-id="dd6c3-107">Restore/CcCredentials コマンドレットはすべての資格情報を消去し、現在の Skype for Business Cloud Connector の展開で使用されるすべての資格情報を再入力するように求めます。</span><span class="sxs-lookup"><span data-stu-id="dd6c3-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="dd6c3-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dd6c3-108">Parameters</span></span>

<span data-ttu-id="dd6c3-109">なし</span><span class="sxs-lookup"><span data-stu-id="dd6c3-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="dd6c3-110">入力の種類</span><span class="sxs-lookup"><span data-stu-id="dd6c3-110">Input Types</span></span>

<span data-ttu-id="dd6c3-111">なし。</span><span class="sxs-lookup"><span data-stu-id="dd6c3-111">None.</span></span> <span data-ttu-id="dd6c3-112">Restore-CcCredentials コマンドレットはパイプライン入力を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="dd6c3-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="dd6c3-113">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="dd6c3-113">Return Types</span></span>

<span data-ttu-id="dd6c3-114">なし。</span><span class="sxs-lookup"><span data-stu-id="dd6c3-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="dd6c3-115">例</span><span class="sxs-lookup"><span data-stu-id="dd6c3-115">Example</span></span>

<span data-ttu-id="dd6c3-116">次の例では、現在のクラウドコネクタ展開のすべての資格情報を復元します。</span><span class="sxs-lookup"><span data-stu-id="dd6c3-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="dd6c3-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd6c3-117">See also</span></span>

[<span data-ttu-id="dd6c3-118">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="dd6c3-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="dd6c3-119">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="dd6c3-119">Set-CcCredential</span></span>](set-cccredential.md)
  

