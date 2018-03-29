---
title: 終了 CcUpdate
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
ms.openlocfilehash: f7b913fd6aaa77a18df66fd86a36d5d4838f69d4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="exit-ccupdate"></a><span data-ttu-id="81a44-103">終了 CcUpdate</span><span class="sxs-lookup"><span data-stu-id="81a44-103">Exit-CcUpdate</span></span>
 
<span data-ttu-id="81a44-104">Exit-CcUpdate コマンドレットは、Skype for Business Cloud Connector エディションのホスト サーバーでの更新のメンテナンス モードを終了します。</span><span class="sxs-lookup"><span data-stu-id="81a44-104">The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
<span data-ttu-id="81a44-105">このコマンドレットは Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="81a44-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span> 
  
```
Exit-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="81a44-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81a44-106">Parameters</span></span>

<span data-ttu-id="81a44-107">なし</span><span class="sxs-lookup"><span data-stu-id="81a44-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="81a44-108">例</span><span class="sxs-lookup"><span data-stu-id="81a44-108">Examples</span></span>
<span data-ttu-id="81a44-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="81a44-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="81a44-110">例 1</span><span class="sxs-lookup"><span data-stu-id="81a44-110">Example 1</span></span>

<span data-ttu-id="81a44-111">次のコマンドは、アプライアンスを実稼働モードに戻って実行する状態にします。</span><span class="sxs-lookup"><span data-stu-id="81a44-111">The following command puts the appliance on which it runs back into production mode:</span></span> 
  
```
Exit-CcUpdate
```

## <a name="detailed-description"></a><span data-ttu-id="81a44-112">解説</span><span class="sxs-lookup"><span data-stu-id="81a44-112">Detailed Description</span></span>
<span data-ttu-id="81a44-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="81a44-113"></span></span>

<span data-ttu-id="81a44-114">Enter-CcUpdate コマンドレットを指定してメンテナンス モードにしたアプライアンスがある場合、Exit-CcUpdate コマンドレットは、これらのアプライアンスを実稼働モードに戻します。</span><span class="sxs-lookup"><span data-stu-id="81a44-114">If you have appliances that you have put in maintenance mode by specifying the Enter-CcUpdate cmdlet, the Exit-CcUpdate cmdlet will put these back into production mode.</span></span> 
  
<span data-ttu-id="81a44-115">アプライアンスをメンテナンス モードにすることの詳細については、Enter-CcUpdate を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81a44-115">For more information about putting appliances in maintenance mode, see Enter-CcUpdate.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="81a44-116">入力の種類</span><span class="sxs-lookup"><span data-stu-id="81a44-116">Input Types</span></span>
<span data-ttu-id="81a44-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="81a44-117"></span></span>

<span data-ttu-id="81a44-p101">なし。Exit-CcUpdate　コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="81a44-p101">None. The Exit-CcUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="81a44-120">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="81a44-120">Return Types</span></span>
<span data-ttu-id="81a44-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="81a44-121"></span></span>

<span data-ttu-id="81a44-122">なし</span><span class="sxs-lookup"><span data-stu-id="81a44-122">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="81a44-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="81a44-123">See also</span></span>
<span data-ttu-id="81a44-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="81a44-124"></span></span>

[<span data-ttu-id="81a44-125">入力 CcUpdate</span><span class="sxs-lookup"><span data-stu-id="81a44-125">Enter-CcUpdate</span></span>](enter-ccupdate.md)
  

