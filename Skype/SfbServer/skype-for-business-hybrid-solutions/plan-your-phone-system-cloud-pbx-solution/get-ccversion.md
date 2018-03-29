---
title: Get CcVersion
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
ms.openlocfilehash: 8391264603a73e3f594122dcdd2eb62b9ba19978
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccversion"></a><span data-ttu-id="7af6b-104">Get CcVersion</span><span class="sxs-lookup"><span data-stu-id="7af6b-104">Get-CcVersion</span></span>
 
<span data-ttu-id="7af6b-105">Cloud Connector アプライアンスのバージョンを返します。</span><span class="sxs-lookup"><span data-stu-id="7af6b-105">Returns the version of the Cloud Connector appliance.</span></span> <span data-ttu-id="7af6b-106">Get-CCVersion は Cloud Connector のホスト マシンでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="7af6b-106">Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="7af6b-107">解説</span><span class="sxs-lookup"><span data-stu-id="7af6b-107">Detailed Description</span></span>

<span data-ttu-id="7af6b-108">アプライアンス ディレクトリ、およびホスト サーバーに配置される仮想マシンのクラウド コネクタ アプライアンス ・ ベースの PowerShell スクリプトがインストールされている、ファイルのバージョンを返します。</span><span class="sxs-lookup"><span data-stu-id="7af6b-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="7af6b-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7af6b-109">Parameters</span></span>

|<span data-ttu-id="7af6b-110">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="7af6b-110">**Parameter**</span></span>|<span data-ttu-id="7af6b-111">**必須**</span><span class="sxs-lookup"><span data-stu-id="7af6b-111">**Required**</span></span>|<span data-ttu-id="7af6b-112">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="7af6b-112">**Type**</span></span>|<span data-ttu-id="7af6b-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="7af6b-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7af6b-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="7af6b-114">VersionType</span></span>  <br/> |<span data-ttu-id="7af6b-115">省略可能</span><span class="sxs-lookup"><span data-stu-id="7af6b-115">Optional</span></span>  <br/> |<span data-ttu-id="7af6b-116">System.String</span><span class="sxs-lookup"><span data-stu-id="7af6b-116">System.String</span></span>  <br/> |<span data-ttu-id="7af6b-117">バージョンのタイプ。</span><span class="sxs-lookup"><span data-stu-id="7af6b-117">Type of version.</span></span> <span data-ttu-id="7af6b-118">パラメーターの値は、RunningScripts、RunningBits、BackupBits または All になります。</span><span class="sxs-lookup"><span data-stu-id="7af6b-118">Value of parameter can be RunningScripts, RunningBits, BackupBits or All.</span></span> <span data-ttu-id="7af6b-119">既定値は RunningScripts です。</span><span class="sxs-lookup"><span data-stu-id="7af6b-119">Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="7af6b-120">例</span><span class="sxs-lookup"><span data-stu-id="7af6b-120">Examples</span></span>
<span data-ttu-id="7af6b-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="7af6b-121"></span></span>

### <a name="example-1"></a><span data-ttu-id="7af6b-122">例 1</span><span class="sxs-lookup"><span data-stu-id="7af6b-122">Example 1</span></span>

<span data-ttu-id="7af6b-123">次の例では、PowerShell コンソールを開くに現在実行中のスクリプトのクラウドのコネクタのバージョンを示しています。</span><span class="sxs-lookup"><span data-stu-id="7af6b-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="7af6b-124">例 2</span><span class="sxs-lookup"><span data-stu-id="7af6b-124">Example 2</span></span>

<span data-ttu-id="7af6b-125">次の例では、現在実行中の仮想マシンに展開バイナリのクラウドのコネクタのバージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="7af6b-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="7af6b-126">バージョンは、Hyper-v Manager において実行中の仮想マシンの名前から確認できます。</span><span class="sxs-lookup"><span data-stu-id="7af6b-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="7af6b-127">入力の種類</span><span class="sxs-lookup"><span data-stu-id="7af6b-127">Input Types</span></span>
<span data-ttu-id="7af6b-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="7af6b-128"></span></span>

<span data-ttu-id="7af6b-129">なし。</span><span class="sxs-lookup"><span data-stu-id="7af6b-129">None.</span></span> <span data-ttu-id="7af6b-130">Get-CcVersion コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="7af6b-130">The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="7af6b-131">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="7af6b-131">Return Types</span></span>
<span data-ttu-id="7af6b-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="7af6b-132"></span></span>

<span data-ttu-id="7af6b-133">なし。</span><span class="sxs-lookup"><span data-stu-id="7af6b-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7af6b-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="7af6b-134">See also</span></span>
<span data-ttu-id="7af6b-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="7af6b-135"></span></span>

<span data-ttu-id="7af6b-136">なし。</span><span class="sxs-lookup"><span data-stu-id="7af6b-136">None.</span></span>
  

