---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: クラウド コネクタのホスト サーバーにローカル ファイルから、Skype ビジネス クラウド コネクタのエディション構成をインポートします。
ms.openlocfilehash: 497568f45fad6b4363581785bf0be95eabfeaebf
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896624"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="9eac0-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="9eac0-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="9eac0-104">クラウド コネクタのホスト サーバーにローカル ファイルから、Skype ビジネス クラウド コネクタのエディション構成をインポートします。</span><span class="sxs-lookup"><span data-stu-id="9eac0-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="9eac0-105">例</span><span class="sxs-lookup"><span data-stu-id="9eac0-105">Examples</span></span>
<span data-ttu-id="9eac0-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9eac0-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="9eac0-107">例 1</span><span class="sxs-lookup"><span data-stu-id="9eac0-107">Example 1</span></span>

<span data-ttu-id="9eac0-108">次の例では、%SystemDrive%\ProgramData\CloudConnector ディレクトリに、クラウドのコネクタ インスタンスのアプライアンスのディレクトリから、CloudConnector.ini をコピーします。</span><span class="sxs-lookup"><span data-stu-id="9eac0-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="9eac0-109">解説</span><span class="sxs-lookup"><span data-stu-id="9eac0-109">Detailed Description</span></span>
<span data-ttu-id="9eac0-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9eac0-110"></span></span>

<span data-ttu-id="9eac0-111">このコマンドレットは、クラウドのコネクタのアプライアンスのアプライアンスのディレクトリから %SystemDrive%\ProgramData\CloudConnector ディレクトリに、CloudConnector.ini をコピーします。</span><span class="sxs-lookup"><span data-stu-id="9eac0-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="9eac0-112">アプライアンス ディレクトリは Set-CcApplianceDirectory コマンドレットを使用して指定されます。</span><span class="sxs-lookup"><span data-stu-id="9eac0-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="9eac0-113">コマンドレットは、%systemdrive%\programdata\cloudconnector で既存のファイルで上書きされます。</span><span class="sxs-lookup"><span data-stu-id="9eac0-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="9eac0-114">クラウド コネクタ版 2.0.1 にこのコマンドが適用されると、後で。</span><span class="sxs-lookup"><span data-stu-id="9eac0-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="9eac0-115">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9eac0-115">Parameters</span></span>
<span data-ttu-id="9eac0-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9eac0-116"></span></span>

|<span data-ttu-id="9eac0-117">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="9eac0-117">**Parameter**</span></span>|<span data-ttu-id="9eac0-118">**必須**</span><span class="sxs-lookup"><span data-stu-id="9eac0-118">**Required**</span></span>|<span data-ttu-id="9eac0-119">**型**</span><span class="sxs-lookup"><span data-stu-id="9eac0-119">**Type**</span></span>|<span data-ttu-id="9eac0-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="9eac0-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9eac0-121">Force</span><span class="sxs-lookup"><span data-stu-id="9eac0-121">Force</span></span>  <br/> |<span data-ttu-id="9eac0-122">省略可能</span><span class="sxs-lookup"><span data-stu-id="9eac0-122">Optional</span></span>  <br/> |<span data-ttu-id="9eac0-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9eac0-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="9eac0-124">%SystemDrive%\ProgramData\CloudConnector 警告を表示せずに既存のファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="9eac0-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="9eac0-125">入力の種類</span><span class="sxs-lookup"><span data-stu-id="9eac0-125">Input Types</span></span>
<span data-ttu-id="9eac0-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9eac0-126"></span></span>

<span data-ttu-id="9eac0-127">なし。</span><span class="sxs-lookup"><span data-stu-id="9eac0-127">None.</span></span> <span data-ttu-id="9eac0-128">インポート CcConfiguration コマンドレットでは、パイプラインの入力は受け付けられません。</span><span class="sxs-lookup"><span data-stu-id="9eac0-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="9eac0-129">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="9eac0-129">Return Types</span></span>
<span data-ttu-id="9eac0-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9eac0-130"></span></span>

<span data-ttu-id="9eac0-131">なし。</span><span class="sxs-lookup"><span data-stu-id="9eac0-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9eac0-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="9eac0-132">See also</span></span>
<span data-ttu-id="9eac0-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9eac0-133"></span></span>

<span data-ttu-id="9eac0-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="9eac0-134">Export-CcConfiguration</span></span>
  

