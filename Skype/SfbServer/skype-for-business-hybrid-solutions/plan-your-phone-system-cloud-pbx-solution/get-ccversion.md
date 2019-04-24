---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Cloud Connector アプライアンスのバージョンを返します。 Get-CCVersion は Cloud Connector のホスト マシンでのみ使用できます。
ms.openlocfilehash: 5e5428e53d53eec66bafa9eb566059ef1b5a5833
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233758"
---
# <a name="get-ccversion"></a><span data-ttu-id="1f0f6-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="1f0f6-104">Get-CcVersion</span></span>
 
<span data-ttu-id="1f0f6-p102">Cloud Connector アプライアンスのバージョンを返します。 Get-CCVersion は Cloud Connector のホスト マシンでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-p102">Returns the version of the Cloud Connector appliance. Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="1f0f6-107">解説</span><span class="sxs-lookup"><span data-stu-id="1f0f6-107">Detailed Description</span></span>

<span data-ttu-id="1f0f6-108">アプライアンス ディレクトリ、およびホスト サーバーに配置される仮想マシンのクラウド コネクタ アプライアンス ・ ベースの PowerShell スクリプトがインストールされている、ファイルのバージョンを返します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="1f0f6-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1f0f6-109">Parameters</span></span>

|<span data-ttu-id="1f0f6-110">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="1f0f6-110">**Parameter**</span></span>|<span data-ttu-id="1f0f6-111">**必須**</span><span class="sxs-lookup"><span data-stu-id="1f0f6-111">**Required**</span></span>|<span data-ttu-id="1f0f6-112">**型**</span><span class="sxs-lookup"><span data-stu-id="1f0f6-112">**Type**</span></span>|<span data-ttu-id="1f0f6-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="1f0f6-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1f0f6-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="1f0f6-114">VersionType</span></span>  <br/> |<span data-ttu-id="1f0f6-115">省略可能</span><span class="sxs-lookup"><span data-stu-id="1f0f6-115">Optional</span></span>  <br/> |<span data-ttu-id="1f0f6-116">System.String</span><span class="sxs-lookup"><span data-stu-id="1f0f6-116">System.String</span></span>  <br/> |<span data-ttu-id="1f0f6-p103">バージョンのタイプ。 パラメーターの値は、RunningScripts、RunningBits、BackupBits または All になります。 既定値は RunningScripts です。 </span><span class="sxs-lookup"><span data-stu-id="1f0f6-p103">Type of version. Value of parameter can be RunningScripts, RunningBits, BackupBits or All. Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="1f0f6-120">例</span><span class="sxs-lookup"><span data-stu-id="1f0f6-120">Examples</span></span>
<span data-ttu-id="1f0f6-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1f0f6-121"></span></span>

### <a name="example-1"></a><span data-ttu-id="1f0f6-122">例 1</span><span class="sxs-lookup"><span data-stu-id="1f0f6-122">Example 1</span></span>

<span data-ttu-id="1f0f6-123">次の例では、PowerShell コンソールを開くに現在実行中のスクリプトのクラウドのコネクタのバージョンを示しています。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="1f0f6-124">例 2</span><span class="sxs-lookup"><span data-stu-id="1f0f6-124">Example 2</span></span>

<span data-ttu-id="1f0f6-125">次の例では、現在実行中の仮想マシンに展開バイナリのクラウドのコネクタのバージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="1f0f6-126">バージョンは、Hyper-v Manager において実行中の仮想マシンの名前から確認できます。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="1f0f6-127">入力の種類</span><span class="sxs-lookup"><span data-stu-id="1f0f6-127">Input Types</span></span>
<span data-ttu-id="1f0f6-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1f0f6-128"></span></span>

<span data-ttu-id="1f0f6-p105">なし。 Get-CcVersion コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-p105">None. The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="1f0f6-131">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="1f0f6-131">Return Types</span></span>
<span data-ttu-id="1f0f6-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1f0f6-132"></span></span>

<span data-ttu-id="1f0f6-133">なし。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1f0f6-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f0f6-134">See also</span></span>
<span data-ttu-id="1f0f6-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1f0f6-135"></span></span>

<span data-ttu-id="1f0f6-136">なし。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-136">None.</span></span>
  

