---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Cloud Connector アプライアンスのバージョンを返します。 Get-CCVersion は Cloud Connector のホスト マシンでのみ使用できます。
ms.openlocfilehash: 706b480c2f8e277b7f41fe28e88cc062fea6603a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799847"
---
# <a name="get-ccversion"></a><span data-ttu-id="735c5-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="735c5-104">Get-CcVersion</span></span>
 
<span data-ttu-id="735c5-p102">Cloud Connector アプライアンスのバージョンを返します。 Get-CCVersion は Cloud Connector のホスト マシンでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="735c5-p102">Returns the version of the Cloud Connector appliance. Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="735c5-107">解説</span><span class="sxs-lookup"><span data-stu-id="735c5-107">Detailed Description</span></span>

<span data-ttu-id="735c5-108">インストールされている PowerShell スクリプト、およびアプライアンスディレクトリ内のファイル、ホストサーバーに展開されている仮想マシンに基づいて、クラウドコネクタアプライアンスのバージョンを返します。</span><span class="sxs-lookup"><span data-stu-id="735c5-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="735c5-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="735c5-109">Parameters</span></span>

|<span data-ttu-id="735c5-110">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="735c5-110">**Parameter**</span></span>|<span data-ttu-id="735c5-111">**必須**</span><span class="sxs-lookup"><span data-stu-id="735c5-111">**Required**</span></span>|<span data-ttu-id="735c5-112">**種類**</span><span class="sxs-lookup"><span data-stu-id="735c5-112">**Type**</span></span>|<span data-ttu-id="735c5-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="735c5-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="735c5-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="735c5-114">VersionType</span></span>  <br/> |<span data-ttu-id="735c5-115">省略可能</span><span class="sxs-lookup"><span data-stu-id="735c5-115">Optional</span></span>  <br/> |<span data-ttu-id="735c5-116">System.String</span><span class="sxs-lookup"><span data-stu-id="735c5-116">System.String</span></span>  <br/> |<span data-ttu-id="735c5-p103">バージョンのタイプ。 パラメーターの値は、RunningScripts、RunningBits、BackupBits または All になります。 既定値は RunningScripts です。 </span><span class="sxs-lookup"><span data-stu-id="735c5-p103">Type of version. Value of parameter can be RunningScripts, RunningBits, BackupBits or All. Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="735c5-120">例</span><span class="sxs-lookup"><span data-stu-id="735c5-120">Examples</span></span>
<span data-ttu-id="735c5-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="735c5-121"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="735c5-122">例 1</span><span class="sxs-lookup"><span data-stu-id="735c5-122">Example 1</span></span>

<span data-ttu-id="735c5-123">次の例は、開いている PowerShell コンソールで現在実行されているスクリプトのクラウドコネクタバージョンを示しています。</span><span class="sxs-lookup"><span data-stu-id="735c5-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="735c5-124">例 2</span><span class="sxs-lookup"><span data-stu-id="735c5-124">Example 2</span></span>

<span data-ttu-id="735c5-125">次の例は、仮想マシンに展開されている現在実行されているバイナリのクラウドコネクタバージョンを示しています。</span><span class="sxs-lookup"><span data-stu-id="735c5-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="735c5-126">バージョンは、Hyper-v Manager において実行中の仮想マシンの名前から確認できます。</span><span class="sxs-lookup"><span data-stu-id="735c5-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="735c5-127">入力の種類</span><span class="sxs-lookup"><span data-stu-id="735c5-127">Input Types</span></span>
<span data-ttu-id="735c5-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="735c5-128"><a name="Examples"> </a></span></span>

<span data-ttu-id="735c5-p105">なし。 Get-CcVersion コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="735c5-p105">None. The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="735c5-131">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="735c5-131">Return Types</span></span>
<span data-ttu-id="735c5-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="735c5-132"><a name="Examples"> </a></span></span>

<span data-ttu-id="735c5-133">なし。</span><span class="sxs-lookup"><span data-stu-id="735c5-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="735c5-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="735c5-134">See also</span></span>
<span data-ttu-id="735c5-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="735c5-135"><a name="Examples"> </a></span></span>

<span data-ttu-id="735c5-136">なし。</span><span class="sxs-lookup"><span data-stu-id="735c5-136">None.</span></span>
  

