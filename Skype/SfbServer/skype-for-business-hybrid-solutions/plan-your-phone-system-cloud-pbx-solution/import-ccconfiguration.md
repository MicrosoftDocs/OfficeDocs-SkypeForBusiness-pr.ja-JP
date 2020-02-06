---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: ローカルファイルからクラウドコネクタホストサーバーに Skype for Business Cloud Connector エディションの構成をインポートします。
ms.openlocfilehash: 626ba52d4d67f99dd67d3d1f91d26d6e6d03f95e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799857"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="3f8c2-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="3f8c2-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="3f8c2-104">ローカルファイルからクラウドコネクタホストサーバーに Skype for Business Cloud Connector エディションの構成をインポートします。</span><span class="sxs-lookup"><span data-stu-id="3f8c2-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="3f8c2-105">例</span><span class="sxs-lookup"><span data-stu-id="3f8c2-105">Examples</span></span>
<span data-ttu-id="3f8c2-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3f8c2-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="3f8c2-107">例 1</span><span class="sxs-lookup"><span data-stu-id="3f8c2-107">Example 1</span></span>

<span data-ttu-id="3f8c2-108">次の例では、クラウドコネクタインスタンスのアプライアンスディレクトリから%SystemDrive%\ProgramData\CloudConnector ディレクトリに CloudConnector. .ini をコピーします。</span><span class="sxs-lookup"><span data-stu-id="3f8c2-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="3f8c2-109">解説</span><span class="sxs-lookup"><span data-stu-id="3f8c2-109">Detailed Description</span></span>
<span data-ttu-id="3f8c2-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3f8c2-110"><a name="Examples"> </a></span></span>

<span data-ttu-id="3f8c2-111">このコマンドレットは、クラウドコネクタアプライアンスのアプライアンスディレクトリから%SystemDrive%\ProgramData\CloudConnector ディレクトリに CloudConnector. .ini をコピーします。</span><span class="sxs-lookup"><span data-stu-id="3f8c2-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="3f8c2-112">アプライアンス ディレクトリは Set-CcApplianceDirectory コマンドレットを使用して指定されます。</span><span class="sxs-lookup"><span data-stu-id="3f8c2-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="3f8c2-113">このコマンドレットによって、%SystemDrive%\ProgramData\CloudConnector. 内の既存のファイルが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="3f8c2-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="3f8c2-114">このコマンドは、Cloud Connector エディションバージョン2.0.1 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3f8c2-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="3f8c2-115">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3f8c2-115">Parameters</span></span>
<span data-ttu-id="3f8c2-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3f8c2-116"><a name="Examples"> </a></span></span>

|<span data-ttu-id="3f8c2-117">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="3f8c2-117">**Parameter**</span></span>|<span data-ttu-id="3f8c2-118">**必須**</span><span class="sxs-lookup"><span data-stu-id="3f8c2-118">**Required**</span></span>|<span data-ttu-id="3f8c2-119">**種類**</span><span class="sxs-lookup"><span data-stu-id="3f8c2-119">**Type**</span></span>|<span data-ttu-id="3f8c2-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="3f8c2-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3f8c2-121">Force</span><span class="sxs-lookup"><span data-stu-id="3f8c2-121">Force</span></span>  <br/> |<span data-ttu-id="3f8c2-122">省略可能</span><span class="sxs-lookup"><span data-stu-id="3f8c2-122">Optional</span></span>  <br/> |<span data-ttu-id="3f8c2-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="3f8c2-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="3f8c2-124">%SystemDrive%\ProgramData\CloudConnector 内の既存のファイルを通知なしで上書きします。</span><span class="sxs-lookup"><span data-stu-id="3f8c2-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="3f8c2-125">入力の種類</span><span class="sxs-lookup"><span data-stu-id="3f8c2-125">Input Types</span></span>
<span data-ttu-id="3f8c2-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3f8c2-126"><a name="Examples"> </a></span></span>

<span data-ttu-id="3f8c2-127">なし。</span><span class="sxs-lookup"><span data-stu-id="3f8c2-127">None.</span></span> <span data-ttu-id="3f8c2-128">インポート-CcConfiguration コマンドレットはパイプライン入力を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="3f8c2-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="3f8c2-129">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="3f8c2-129">Return Types</span></span>
<span data-ttu-id="3f8c2-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3f8c2-130"><a name="Examples"> </a></span></span>

<span data-ttu-id="3f8c2-131">なし。</span><span class="sxs-lookup"><span data-stu-id="3f8c2-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3f8c2-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f8c2-132">See also</span></span>
<span data-ttu-id="3f8c2-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3f8c2-133"><a name="Examples"> </a></span></span>

<span data-ttu-id="3f8c2-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="3f8c2-134">Export-CcConfiguration</span></span>
  

