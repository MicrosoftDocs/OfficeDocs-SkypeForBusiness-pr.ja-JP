---
title: Get-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: Get-CcSiteDirectory コマンドレットは、サイト レベルの設定ファイルが格納されている現在のディレクトリを示します。 フォルダーにはベース VHD および Skype for Business Cloud Connector エディションのインストール ファイルが含まれます。 このフォルダーは、クラウドコネクタサイトの他のすべてのアプライアンスと共有する必要があります。
ms.openlocfilehash: 095776a680fbbcc8c43a8f99700b357175010b5a
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003367"
---
# <a name="get-ccsitedirectory"></a><span data-ttu-id="831e9-105">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="831e9-105">Get-CcSiteDirectory</span></span>
 
<span data-ttu-id="831e9-106">Get-CcSiteDirectory コマンドレットは、サイト レベルの設定ファイルが格納されている現在のディレクトリを示します。</span><span class="sxs-lookup"><span data-stu-id="831e9-106">The Get-CcSiteDirectory cmdlet shows the current directory where site level configuration files are stored.</span></span> <span data-ttu-id="831e9-107">フォルダーにはベース VHD および Skype for Business Cloud Connector エディションのインストール ファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="831e9-107">The folder contains the base VHD and Skype for Business Cloud Connector Edition installation files.</span></span> <span data-ttu-id="831e9-108">このフォルダーは、クラウドコネクタサイトの他のすべてのアプライアンスと共有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="831e9-108">This folder should be shared with all other appliances of a Cloud Connector site.</span></span>
  
<span data-ttu-id="831e9-109">このコマンドレットは Cloud Connector エディション 1.4.1、1.4.2 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="831e9-109">This cmdlet applies to Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a><span data-ttu-id="831e9-110">パラメーター</span><span class="sxs-lookup"><span data-stu-id="831e9-110">Parameters</span></span>

<span data-ttu-id="831e9-111">なし</span><span class="sxs-lookup"><span data-stu-id="831e9-111">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="831e9-112">例</span><span class="sxs-lookup"><span data-stu-id="831e9-112">Examples</span></span>
<span data-ttu-id="831e9-113"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="831e9-113"></span></span>

### <a name="example-1"></a><span data-ttu-id="831e9-114">例 1</span><span class="sxs-lookup"><span data-stu-id="831e9-114">Example 1</span></span>

<span data-ttu-id="831e9-115">次の例は、クラウドコネクタコンポーネントの configuration ファイルと virtual machines ファイルが保存されている現在のフォルダーを示しています。</span><span class="sxs-lookup"><span data-stu-id="831e9-115">The following example shows the current folder where the configuration and virtual machines files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="831e9-116">解説</span><span class="sxs-lookup"><span data-stu-id="831e9-116">Detailed Description</span></span>
<span data-ttu-id="831e9-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="831e9-117"></span></span>

<span data-ttu-id="831e9-118">ゲートウェイのアフィニティと高可用性を実現するには、クラウドコネクタのアプライアンスをサイトで組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="831e9-118">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="831e9-119">ユーザーは、クラウドコネクタアプライアンスの代わりにサイトに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="831e9-119">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="831e9-120">各サイトには、基本 VHD とクラウドコネクタのインストールファイルが保存されている共有フォルダーがあります。</span><span class="sxs-lookup"><span data-stu-id="831e9-120">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="831e9-121">このフォルダーは、アプライアンスによって展開時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="831e9-121">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="831e9-122">既定のフォルダーは C:\Users\%userprofile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="831e9-122">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="831e9-123">このパスは Set-CcSiteDirectory コマンドレットを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="831e9-123">You can change the path by using the Set-CcSiteDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="831e9-124">入力の種類</span><span class="sxs-lookup"><span data-stu-id="831e9-124">Input Types</span></span>
<span data-ttu-id="831e9-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="831e9-125"></span></span>

<span data-ttu-id="831e9-p104">なし。Get-CcSiteDirectory コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="831e9-p104">None. The Get-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="831e9-128">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="831e9-128">Return Types</span></span>
<span data-ttu-id="831e9-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="831e9-129"></span></span>

<span data-ttu-id="831e9-130">このコマンドはファイル パスを返します。</span><span class="sxs-lookup"><span data-stu-id="831e9-130">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="831e9-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="831e9-131">See also</span></span>
<span data-ttu-id="831e9-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="831e9-132"></span></span>

[<span data-ttu-id="831e9-133">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="831e9-133">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

