---
title: Set-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: Set-CcSiteDirectory コマンドレットは、Skype for Business Cloud Connector エディションのサイト レベルの設定ファイルが格納されるディレクトリを設定します。 フォルダーにはベース VHD および Cloud Connector の設定ファイルが含まれます。
ms.openlocfilehash: 1c03d0f91b3a724df6ce61d216138bb281fb0b87
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885583"
---
# <a name="set-ccsitedirectory"></a><span data-ttu-id="68a60-104">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="68a60-104">Set-CcSiteDirectory</span></span>
 
<span data-ttu-id="68a60-105">Set-CcSiteDirectory コマンドレットは、Skype for Business Cloud Connector エディションのサイト レベルの設定ファイルが格納されるディレクトリを設定します。</span><span class="sxs-lookup"><span data-stu-id="68a60-105">The Set-CcSiteDirectory cmdlet sets the directory where site level configuration files for Skype for Business Cloud Connector Edition will be stored.</span></span> <span data-ttu-id="68a60-106">フォルダーにはベース VHD および Cloud Connector の設定ファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="68a60-106">The folder will contain the base VHD and Cloud Connector configuration files.</span></span>
  
<span data-ttu-id="68a60-107">このコマンドレットは Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="68a60-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="68a60-108">例</span><span class="sxs-lookup"><span data-stu-id="68a60-108">Examples</span></span>
<span data-ttu-id="68a60-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="68a60-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="68a60-110">例 1</span><span class="sxs-lookup"><span data-stu-id="68a60-110">Example 1</span></span>

<span data-ttu-id="68a60-111">次の例では、サイトのルート ディレクトリを設定\\SiteShare\CloudConnector。</span><span class="sxs-lookup"><span data-stu-id="68a60-111">The following example sets the site root directory to \\SiteShare\CloudConnector:</span></span>
  
```
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a><span data-ttu-id="68a60-112">解説</span><span class="sxs-lookup"><span data-stu-id="68a60-112">Detailed Description</span></span>
<span data-ttu-id="68a60-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="68a60-113"></span></span>

<span data-ttu-id="68a60-114">ゲートウェイの類似性と高可用性を提供するには、サイトでコネクタのクラウド アプライアンスを組み合わせて指定できます。</span><span class="sxs-lookup"><span data-stu-id="68a60-114">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="68a60-115">ユーザーは、クラウドのコネクタのアプライアンスではなくサイトに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="68a60-115">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="68a60-116">各サイトには、ベース VHD とクラウドのコネクタのインストール ファイルが格納される共有フォルダーがあります。</span><span class="sxs-lookup"><span data-stu-id="68a60-116">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="68a60-117">このフォルダーは、アプライアンスによって展開時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="68a60-117">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="68a60-118">クラウド コネクタ サイト内の他のすべてのアプライアンスでは、このフォルダーを共有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68a60-118">This folder should be shared with all other appliances in a Cloud Connector site.</span></span>
  
<span data-ttu-id="68a60-119">既定のフォルダーは、C:\Users\%userprofile%\CloudConnector\SiteRoot。</span><span class="sxs-lookup"><span data-stu-id="68a60-119">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="68a60-120">このパスは Get-CcSiteDirectory コマンドレットを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="68a60-120">The path can be viewed by using the Get-CcSiteDirectory cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="68a60-121">パラメーター</span><span class="sxs-lookup"><span data-stu-id="68a60-121">Parameters</span></span>
<span data-ttu-id="68a60-122"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="68a60-122"></span></span>

|<span data-ttu-id="68a60-123">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="68a60-123">**Parameter**</span></span>|<span data-ttu-id="68a60-124">**必須**</span><span class="sxs-lookup"><span data-stu-id="68a60-124">**Required**</span></span>|<span data-ttu-id="68a60-125">**型**</span><span class="sxs-lookup"><span data-stu-id="68a60-125">**Type**</span></span>|<span data-ttu-id="68a60-126">**説明**</span><span class="sxs-lookup"><span data-stu-id="68a60-126">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="68a60-127">Path</span><span class="sxs-lookup"><span data-stu-id="68a60-127">Path</span></span> <br/> | <span data-ttu-id="68a60-128">必須</span><span class="sxs-lookup"><span data-stu-id="68a60-128">Required</span></span> <br/> | <span data-ttu-id="68a60-129">System.String</span><span class="sxs-lookup"><span data-stu-id="68a60-129">System.String</span></span> <br/> |<span data-ttu-id="68a60-130">クラウド コネクタ サイトのファイルを保存するフォルダーへのパスを提供します。</span><span class="sxs-lookup"><span data-stu-id="68a60-130">Provides the path to the folder where Cloud Connector site files will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="68a60-131">入力の種類</span><span class="sxs-lookup"><span data-stu-id="68a60-131">Input Types</span></span>
<span data-ttu-id="68a60-132"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="68a60-132"></span></span>

<span data-ttu-id="68a60-133">なし。</span><span class="sxs-lookup"><span data-stu-id="68a60-133">None.</span></span> <span data-ttu-id="68a60-134">Set-CcSiteDirectory コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="68a60-134">The Set-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="68a60-135">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="68a60-135">Return Types</span></span>
<span data-ttu-id="68a60-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="68a60-136"></span></span>

<span data-ttu-id="68a60-137">なし</span><span class="sxs-lookup"><span data-stu-id="68a60-137">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="68a60-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="68a60-138">See also</span></span>
<span data-ttu-id="68a60-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="68a60-139"></span></span>

[<span data-ttu-id="68a60-140">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="68a60-140">Get-CcSiteDirectory</span></span>](get-ccsitedirectory.md)
  

