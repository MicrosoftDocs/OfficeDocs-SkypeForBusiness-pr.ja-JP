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
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: ローカルファイルからクラウドコネクタホストサーバーに Skype for Business Cloud Connector エディションの構成をインポートします。
ms.openlocfilehash: 3e165250b5158513aa683770d5eb1768c0e1e29c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287280"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="333b9-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="333b9-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="333b9-104">ローカルファイルからクラウドコネクタホストサーバーに Skype for Business Cloud Connector エディションの構成をインポートします。</span><span class="sxs-lookup"><span data-stu-id="333b9-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="333b9-105">例</span><span class="sxs-lookup"><span data-stu-id="333b9-105">Examples</span></span>
<span data-ttu-id="333b9-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="333b9-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="333b9-107">例 1</span><span class="sxs-lookup"><span data-stu-id="333b9-107">Example 1</span></span>

<span data-ttu-id="333b9-108">次の例では、クラウドコネクタインスタンスのアプライアンスディレクトリから%SystemDrive%\ProgramData\CloudConnector ディレクトリに CloudConnector. .ini をコピーします。</span><span class="sxs-lookup"><span data-stu-id="333b9-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="333b9-109">解説</span><span class="sxs-lookup"><span data-stu-id="333b9-109">Detailed Description</span></span>
<span data-ttu-id="333b9-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="333b9-110"></span></span>

<span data-ttu-id="333b9-111">このコマンドレットは、クラウドコネクタアプライアンスのアプライアンスディレクトリから%SystemDrive%\ProgramData\CloudConnector ディレクトリに CloudConnector. .ini をコピーします。</span><span class="sxs-lookup"><span data-stu-id="333b9-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="333b9-112">アプライアンス ディレクトリは Set-CcApplianceDirectory コマンドレットを使用して指定されます。</span><span class="sxs-lookup"><span data-stu-id="333b9-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="333b9-113">このコマンドレットによって、%SystemDrive%\ProgramData\CloudConnector. 内の既存のファイルが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="333b9-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="333b9-114">このコマンドは、Cloud Connector エディションバージョン2.0.1 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="333b9-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="333b9-115">パラメーター</span><span class="sxs-lookup"><span data-stu-id="333b9-115">Parameters</span></span>
<span data-ttu-id="333b9-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="333b9-116"></span></span>

|<span data-ttu-id="333b9-117">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="333b9-117">**Parameter**</span></span>|<span data-ttu-id="333b9-118">**必須**</span><span class="sxs-lookup"><span data-stu-id="333b9-118">**Required**</span></span>|<span data-ttu-id="333b9-119">**型**</span><span class="sxs-lookup"><span data-stu-id="333b9-119">**Type**</span></span>|<span data-ttu-id="333b9-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="333b9-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="333b9-121">Force</span><span class="sxs-lookup"><span data-stu-id="333b9-121">Force</span></span>  <br/> |<span data-ttu-id="333b9-122">省略可能</span><span class="sxs-lookup"><span data-stu-id="333b9-122">Optional</span></span>  <br/> |<span data-ttu-id="333b9-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="333b9-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="333b9-124">%SystemDrive%\ProgramData\CloudConnector 内の既存のファイルを通知なしで上書きします。</span><span class="sxs-lookup"><span data-stu-id="333b9-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="333b9-125">入力の種類</span><span class="sxs-lookup"><span data-stu-id="333b9-125">Input Types</span></span>
<span data-ttu-id="333b9-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="333b9-126"></span></span>

<span data-ttu-id="333b9-127">なし。</span><span class="sxs-lookup"><span data-stu-id="333b9-127">None.</span></span> <span data-ttu-id="333b9-128">インポート-CcConfiguration コマンドレットはパイプライン入力を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="333b9-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="333b9-129">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="333b9-129">Return Types</span></span>
<span data-ttu-id="333b9-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="333b9-130"></span></span>

<span data-ttu-id="333b9-131">なし。</span><span class="sxs-lookup"><span data-stu-id="333b9-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="333b9-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="333b9-132">See also</span></span>
<span data-ttu-id="333b9-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="333b9-133"></span></span>

<span data-ttu-id="333b9-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="333b9-134">Export-CcConfiguration</span></span>
  

