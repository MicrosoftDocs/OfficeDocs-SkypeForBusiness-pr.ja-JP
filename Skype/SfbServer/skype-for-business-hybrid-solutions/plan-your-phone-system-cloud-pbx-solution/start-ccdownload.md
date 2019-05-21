---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: Start-CcDownload コマンドレットは Skype for Business Cloud Connector エディションのビットと msi ファイルを同期してダウンロードします。
ms.openlocfilehash: 184c15d1932a179bb9ae07da515eeacfc115dfae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286944"
---
# <a name="start-ccdownload"></a><span data-ttu-id="607b7-103">Start-CcDownload</span><span class="sxs-lookup"><span data-stu-id="607b7-103">Start-CcDownload</span></span>
 
<span data-ttu-id="607b7-104">Start-CcDownload コマンドレットは Skype for Business Cloud Connector エディションのビットと msi ファイルを同期してダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="607b7-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span></span>
  
<span data-ttu-id="607b7-105">Cloud Connector バージョン 2.0 以降の場合、DownloadBitsOnly パラメーターも指定できます。</span><span class="sxs-lookup"><span data-stu-id="607b7-105">With Cloud Connector version 2.0 and later, you can also specify the DownloadBitsOnly parameter.</span></span>
  
```
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="607b7-106">例</span><span class="sxs-lookup"><span data-stu-id="607b7-106">Examples</span></span>
<span data-ttu-id="607b7-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="607b7-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="607b7-108">例 1</span><span class="sxs-lookup"><span data-stu-id="607b7-108">Example 1</span></span>

<span data-ttu-id="607b7-109">次の例では、クラウドコネクタのパブリックダウンロードサイトからクラウドコネクタの bits と msi ファイルを同期的にダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="607b7-109">The following example downloads the Cloud Connector bits and msi file synchronously from the Cloud Connector public download site:</span></span>
  
```
Start-CcDownload
```

### <a name="example-2"></a><span data-ttu-id="607b7-110">例 2</span><span class="sxs-lookup"><span data-stu-id="607b7-110">Example 2</span></span>

<span data-ttu-id="607b7-111">次の例では、プライベートダウンロードサイトからクラウドコネクタの bits と msi ファイルを同期的にダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="607b7-111">The next example downloads the Cloud Connector bits and msi file synchronously from a private download site:</span></span>
  
```
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a><span data-ttu-id="607b7-112">例 3</span><span class="sxs-lookup"><span data-stu-id="607b7-112">Example 3</span></span>

<span data-ttu-id="607b7-113">3 つ目の例では、Cloud Connector ビットおよび msi ファイルをプライベート ダウンロード サイトから同期的にダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="607b7-113">The third example downloads the Cloud Connector bits and msi file synchronously from a private download site.</span></span>
  
```
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a><span data-ttu-id="607b7-114">解説</span><span class="sxs-lookup"><span data-stu-id="607b7-114">Detailed Description</span></span>
<span data-ttu-id="607b7-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="607b7-115"></span></span>

<span data-ttu-id="607b7-116">ダウンロードサイトで利用可能な新しいバージョンがある場合は、ダウンロードサイトから msi ファイルをダウンロードしてインストールしてから、クラウドコネクタの bits を同期的にダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="607b7-116">If there's a new version available in the download site, Start-CcDownload will download and install the msi file from the download site, and then download the Cloud Connector bits synchronously.</span></span> <span data-ttu-id="607b7-117">新しいバージョンの msi ファイルがない場合、Start-CcDownload によって Cloud Connector ビットのみがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="607b7-117">If there is no new version of the msi file, Start-CcDownload will download the Cloud Connector bits only.</span></span> <span data-ttu-id="607b7-118">Cloud Connector ビットが既にダウンロードされている場合、Start-CcDownload は実行されません。</span><span class="sxs-lookup"><span data-stu-id="607b7-118">If the Cloud Connector bits are already downloaded, Start-CcDownload does not execute.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="607b7-119">パラメーター</span><span class="sxs-lookup"><span data-stu-id="607b7-119">Parameters</span></span>
<span data-ttu-id="607b7-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="607b7-120"></span></span>

|<span data-ttu-id="607b7-121">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="607b7-121">**Parameter**</span></span>|<span data-ttu-id="607b7-122">**必須**</span><span class="sxs-lookup"><span data-stu-id="607b7-122">**Required**</span></span>|<span data-ttu-id="607b7-123">**型**</span><span class="sxs-lookup"><span data-stu-id="607b7-123">**Type**</span></span>|<span data-ttu-id="607b7-124">**説明**</span><span class="sxs-lookup"><span data-stu-id="607b7-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="607b7-125">DownloadUrlRoot </span><span class="sxs-lookup"><span data-stu-id="607b7-125">DownloadUrlRoot</span></span>  <br/> | <span data-ttu-id="607b7-126">省略可能</span><span class="sxs-lookup"><span data-stu-id="607b7-126">Optional</span></span> <br/> |<span data-ttu-id="607b7-127">System.String</span><span class="sxs-lookup"><span data-stu-id="607b7-127">System.String</span></span>  <br/> | <span data-ttu-id="607b7-128">プライベートダウンロードサイト内の特定のバージョンのクラウドコネクタの完全な URL です。</span><span class="sxs-lookup"><span data-stu-id="607b7-128">The full URL of a specific version of Cloud Connector in the private download site.</span></span> <span data-ttu-id="607b7-129">このパラメーターは注意して使用してください。ダウンロードするクラウドコネクタのバージョンを確認してください。</span><span class="sxs-lookup"><span data-stu-id="607b7-129">Use this parameter with caution—be sure you are aware of which version of Cloud Connector you are downloading.</span></span> <br/> |
|<span data-ttu-id="607b7-130">DownloadBitsOnly </span><span class="sxs-lookup"><span data-stu-id="607b7-130">DownloadBitsOnly</span></span>  <br/> |<span data-ttu-id="607b7-131">省略可能</span><span class="sxs-lookup"><span data-stu-id="607b7-131">Optional</span></span>  <br/> |<span data-ttu-id="607b7-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="607b7-132">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="607b7-133">ダウンロード サイトから MSI をダウンロードおよびインストールする手順をスキップして、Cloud Connector ビットのみをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="607b7-133">Skip the step to download and install MSI from download site, download the Cloud Connector bits only.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="607b7-134">入力の種類</span><span class="sxs-lookup"><span data-stu-id="607b7-134">Input Types</span></span>
<span data-ttu-id="607b7-135"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="607b7-135"></span></span>

<span data-ttu-id="607b7-p103">なし。 Start-CcDownload コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="607b7-p103">None. The Start-CcDownload cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="607b7-138">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="607b7-138">Return Types</span></span>
<span data-ttu-id="607b7-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="607b7-139"></span></span>

<span data-ttu-id="607b7-140">なし</span><span class="sxs-lookup"><span data-stu-id="607b7-140">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="607b7-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="607b7-141">See also</span></span>
<span data-ttu-id="607b7-142"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="607b7-142"></span></span>

<span data-ttu-id="607b7-143">なし</span><span class="sxs-lookup"><span data-stu-id="607b7-143">None</span></span>
  

