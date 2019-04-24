---
title: Exit-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: Exit-CcUpdate コマンドレットは、Skype for Business Cloud Connector エディションのホスト サーバーでの更新のメンテナンス モードを終了します。
ms.openlocfilehash: 7ac36e9cbab8e479a4ec7b070b773b3585370e8f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234042"
---
# <a name="exit-ccupdate"></a><span data-ttu-id="f3255-103">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="f3255-103">Exit-CcUpdate</span></span>
 
<span data-ttu-id="f3255-104">Exit-CcUpdate コマンドレットは、Skype for Business Cloud Connector エディションのホスト サーバーでの更新のメンテナンス モードを終了します。</span><span class="sxs-lookup"><span data-stu-id="f3255-104">The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
<span data-ttu-id="f3255-105">このコマンドレットは Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="f3255-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span> 
  
```
Exit-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="f3255-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f3255-106">Parameters</span></span>

<span data-ttu-id="f3255-107">なし</span><span class="sxs-lookup"><span data-stu-id="f3255-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="f3255-108">例</span><span class="sxs-lookup"><span data-stu-id="f3255-108">Examples</span></span>
<span data-ttu-id="f3255-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f3255-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="f3255-110">例 1</span><span class="sxs-lookup"><span data-stu-id="f3255-110">Example 1</span></span>

<span data-ttu-id="f3255-111">次のコマンドは、アプライアンスを実稼働モードに戻って実行する状態にします。</span><span class="sxs-lookup"><span data-stu-id="f3255-111">The following command puts the appliance on which it runs back into production mode:</span></span> 
  
```
Exit-CcUpdate
```

## <a name="detailed-description"></a><span data-ttu-id="f3255-112">解説</span><span class="sxs-lookup"><span data-stu-id="f3255-112">Detailed Description</span></span>
<span data-ttu-id="f3255-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f3255-113"></span></span>

<span data-ttu-id="f3255-114">Enter-CcUpdate コマンドレットを指定してメンテナンス モードにしたアプライアンスがある場合、Exit-CcUpdate コマンドレットは、これらのアプライアンスを実稼働モードに戻します。</span><span class="sxs-lookup"><span data-stu-id="f3255-114">If you have appliances that you have put in maintenance mode by specifying the Enter-CcUpdate cmdlet, the Exit-CcUpdate cmdlet will put these back into production mode.</span></span> 
  
<span data-ttu-id="f3255-115">アプライアンスをメンテナンス モードにすることの詳細については、Enter-CcUpdate を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3255-115">For more information about putting appliances in maintenance mode, see Enter-CcUpdate.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="f3255-116">入力の種類</span><span class="sxs-lookup"><span data-stu-id="f3255-116">Input Types</span></span>
<span data-ttu-id="f3255-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f3255-117"></span></span>

<span data-ttu-id="f3255-p101">なし。Exit-CcUpdate　コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="f3255-p101">None. The Exit-CcUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f3255-120">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="f3255-120">Return Types</span></span>
<span data-ttu-id="f3255-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f3255-121"></span></span>

<span data-ttu-id="f3255-122">なし</span><span class="sxs-lookup"><span data-stu-id="f3255-122">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f3255-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3255-123">See also</span></span>
<span data-ttu-id="f3255-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f3255-124"></span></span>

[<span data-ttu-id="f3255-125">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="f3255-125">Enter-CcUpdate</span></span>](enter-ccupdate.md)
  

