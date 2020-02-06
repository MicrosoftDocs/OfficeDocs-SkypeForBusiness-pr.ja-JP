---
title: Set-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: Set-CcSiteDirectory コマンドレットは、Skype for Business Cloud Connector エディションのサイト レベルの設定ファイルが格納されるディレクトリを設定します。 フォルダーにはベース VHD および Cloud Connector の設定ファイルが含まれます。
ms.openlocfilehash: 1e66c735e888fe9d5701b8f71baf462ec449acd4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824191"
---
# <a name="set-ccsitedirectory"></a><span data-ttu-id="c9efa-104">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="c9efa-104">Set-CcSiteDirectory</span></span>
 
<span data-ttu-id="c9efa-105">Set-CcSiteDirectory コマンドレットは、Skype for Business Cloud Connector エディションのサイト レベルの設定ファイルが格納されるディレクトリを設定します。</span><span class="sxs-lookup"><span data-stu-id="c9efa-105">The Set-CcSiteDirectory cmdlet sets the directory where site level configuration files for Skype for Business Cloud Connector Edition will be stored.</span></span> <span data-ttu-id="c9efa-106">フォルダーにはベース VHD および Cloud Connector の設定ファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c9efa-106">The folder will contain the base VHD and Cloud Connector configuration files.</span></span>
  
<span data-ttu-id="c9efa-107">このコマンドレットは Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c9efa-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="c9efa-108">例</span><span class="sxs-lookup"><span data-stu-id="c9efa-108">Examples</span></span>
<span data-ttu-id="c9efa-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c9efa-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="c9efa-110">例 1</span><span class="sxs-lookup"><span data-stu-id="c9efa-110">Example 1</span></span>

<span data-ttu-id="c9efa-111">次の例では、サイトのルート\\ディレクトリを SiteShare\CloudConnector に設定します。</span><span class="sxs-lookup"><span data-stu-id="c9efa-111">The following example sets the site root directory to \\SiteShare\CloudConnector:</span></span>
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a><span data-ttu-id="c9efa-112">解説</span><span class="sxs-lookup"><span data-stu-id="c9efa-112">Detailed Description</span></span>
<span data-ttu-id="c9efa-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c9efa-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="c9efa-114">ゲートウェイのアフィニティと高可用性を実現するには、クラウドコネクタのアプライアンスをサイトで組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="c9efa-114">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="c9efa-115">ユーザーは、クラウドコネクタアプライアンスの代わりにサイトに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="c9efa-115">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="c9efa-116">各サイトには、基本 VHD とクラウドコネクタのインストールファイルが保存されている共有フォルダーがあります。</span><span class="sxs-lookup"><span data-stu-id="c9efa-116">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="c9efa-117">このフォルダーは、アプライアンスによって展開時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c9efa-117">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="c9efa-118">このフォルダーは、クラウドコネクタサイト内の他のすべてのアプライアンスと共有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9efa-118">This folder should be shared with all other appliances in a Cloud Connector site.</span></span>
  
<span data-ttu-id="c9efa-119">既定のフォルダーは C:\Users\%userprofile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="c9efa-119">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="c9efa-120">このパスは Get-CcSiteDirectory コマンドレットを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="c9efa-120">The path can be viewed by using the Get-CcSiteDirectory cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="c9efa-121">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c9efa-121">Parameters</span></span>
<span data-ttu-id="c9efa-122"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c9efa-122"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="c9efa-123">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="c9efa-123">**Parameter**</span></span>|<span data-ttu-id="c9efa-124">**必須**</span><span class="sxs-lookup"><span data-stu-id="c9efa-124">**Required**</span></span>|<span data-ttu-id="c9efa-125">**種類**</span><span class="sxs-lookup"><span data-stu-id="c9efa-125">**Type**</span></span>|<span data-ttu-id="c9efa-126">**説明**</span><span class="sxs-lookup"><span data-stu-id="c9efa-126">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="c9efa-127">Path</span><span class="sxs-lookup"><span data-stu-id="c9efa-127">Path</span></span> <br/> | <span data-ttu-id="c9efa-128">必須</span><span class="sxs-lookup"><span data-stu-id="c9efa-128">Required</span></span> <br/> | <span data-ttu-id="c9efa-129">System.String</span><span class="sxs-lookup"><span data-stu-id="c9efa-129">System.String</span></span> <br/> |<span data-ttu-id="c9efa-130">クラウドコネクタサイトファイルが保存されるフォルダーのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c9efa-130">Provides the path to the folder where Cloud Connector site files will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="c9efa-131">入力の種類</span><span class="sxs-lookup"><span data-stu-id="c9efa-131">Input Types</span></span>
<span data-ttu-id="c9efa-132"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c9efa-132"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="c9efa-133">なし。</span><span class="sxs-lookup"><span data-stu-id="c9efa-133">None.</span></span> <span data-ttu-id="c9efa-134">Set-CcSiteDirectory コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="c9efa-134">The Set-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c9efa-135">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="c9efa-135">Return Types</span></span>
<span data-ttu-id="c9efa-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c9efa-136"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="c9efa-137">なし</span><span class="sxs-lookup"><span data-stu-id="c9efa-137">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c9efa-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9efa-138">See also</span></span>
<span data-ttu-id="c9efa-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c9efa-139"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="c9efa-140">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="c9efa-140">Get-CcSiteDirectory</span></span>](get-ccsitedirectory.md)
  

