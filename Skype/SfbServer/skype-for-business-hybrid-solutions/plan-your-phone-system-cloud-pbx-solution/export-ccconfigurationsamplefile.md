---
title: Export-CcConfigurationSampleFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: Export-CcConfigurationSampleFile コマンドレットは、Skype for Business Cloud Connector エディションのサンプル構成ファイル (.ini) を Cloud Connector アプライアンスのアプライアンス ディレクトリにエクスポートします。このファイルの名前は、お使いの展開での使用に合わせて変更できます。
ms.openlocfilehash: a29a3db8e77ee239263d015bd7a3efcf4f3f7c5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801007"
---
# <a name="export-ccconfigurationsamplefile"></a><span data-ttu-id="b5f0d-104">Export-CcConfigurationSampleFile</span><span class="sxs-lookup"><span data-stu-id="b5f0d-104">Export-CcConfigurationSampleFile</span></span>
 
<span data-ttu-id="b5f0d-p102">Export-CcConfigurationSampleFile コマンドレットは、Skype for Business Cloud Connector エディションのサンプル構成ファイル (.ini) を Cloud Connector アプライアンスのアプライアンス ディレクトリにエクスポートします。このファイルの名前は、お使いの展開での使用に合わせて変更できます。</span><span class="sxs-lookup"><span data-stu-id="b5f0d-p102">The Export-CcConfigurationSampleFile cmdlet exports a Skype for Business Cloud Connector Edition sample configuration file (.ini) to the appliance directory of a Cloud Connector appliance. You can modify and rename the file to use for your deployment.</span></span>
  
<span data-ttu-id="b5f0d-107">このコマンドレットは Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b5f0d-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a><span data-ttu-id="b5f0d-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b5f0d-108">Parameters</span></span>

<span data-ttu-id="b5f0d-109">なし</span><span class="sxs-lookup"><span data-stu-id="b5f0d-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="b5f0d-110">例</span><span class="sxs-lookup"><span data-stu-id="b5f0d-110">Examples</span></span>
<span data-ttu-id="b5f0d-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b5f0d-111"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="b5f0d-112">例 1</span><span class="sxs-lookup"><span data-stu-id="b5f0d-112">Example 1</span></span>

<span data-ttu-id="b5f0d-113">次の例では、Microsoft サイトからサンプルの構成ファイルをダウンロードし、クラウドコネクタのアプライアンスの appliance ディレクトリに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="b5f0d-113">The following example downloads a sample configuration file from the Microsoft site and writes it to the appliance directory of the Cloud Connector appliance:</span></span>
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a><span data-ttu-id="b5f0d-114">解説</span><span class="sxs-lookup"><span data-stu-id="b5f0d-114">Detailed Description</span></span>
<span data-ttu-id="b5f0d-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b5f0d-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="b5f0d-116">Cloud Connector の現在のバージョンでは、.ini ファイルにいくつかのパラメーターを指定する必要があります。たとえば、クラウドコネクタコンポーネントの仮想マシンの IP アドレス、コンポーネント名、ゲートウェイパラメーターなどのパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="b5f0d-116">The current version of Cloud Connector requires you to provide several parameters in the .ini file; for example, parameters such as the IP addresses of virtual machines for the Cloud Connector components, component names, gateway parameters, and so on.</span></span>
  
<span data-ttu-id="b5f0d-117">このコマンドレットは、クラウドコネクタのホストコンピューターで実行すると、Microsoft サイトの構成例と共にサンプルの .ini ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b5f0d-117">This cmdlet, when run on the host machine of Cloud Connector, downloads a sample .ini file with configuration examples from the Microsoft site.</span></span> <span data-ttu-id="b5f0d-118">このコマンドレットは、クラウドコネクタアプライアンスのアプライアンスディレクトリにファイルを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="b5f0d-118">The cmdlet writes the file to the appliance directory of the Cloud Connector appliance.</span></span> <span data-ttu-id="b5f0d-119">アプライアンス ディレクトリは Set-CcApplianceDirectory コマンドレットを使用して指定されます。</span><span class="sxs-lookup"><span data-stu-id="b5f0d-119">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="b5f0d-120">入力の種類</span><span class="sxs-lookup"><span data-stu-id="b5f0d-120">Input Types</span></span>
<span data-ttu-id="b5f0d-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b5f0d-121"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="b5f0d-p104">なし。Export-CcConfigurationSampleFile　コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="b5f0d-p104">None. The Export-CcConfigurationSampleFile cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="b5f0d-124">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="b5f0d-124">Return Types</span></span>
<span data-ttu-id="b5f0d-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b5f0d-125"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="b5f0d-126">なし</span><span class="sxs-lookup"><span data-stu-id="b5f0d-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b5f0d-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5f0d-127">See also</span></span>
<span data-ttu-id="b5f0d-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b5f0d-128"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="b5f0d-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="b5f0d-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

