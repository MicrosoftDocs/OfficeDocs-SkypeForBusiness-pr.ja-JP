---
title: Convert-CcIsoToVhdx
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: Convert-CcIsoToVhdx コマンドレットは、顧客支給の Windows Server 2012 R2 ISO ファイルを使用してベース仮想ハード ディスク　ファイル (VHDX) を作成します。VHDX ファイルは、Skype for Business Cloud Connector エディションの展開時に使用されます。
ms.openlocfilehash: 181d1af762d1f8c9c8f3e65a4411b317ab36ce4a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898488"
---
# <a name="convert-ccisotovhdx"></a><span data-ttu-id="64bdb-104">Convert-CcIsoToVhdx</span><span class="sxs-lookup"><span data-stu-id="64bdb-104">Convert-CcIsoToVhdx</span></span>
 
<span data-ttu-id="64bdb-p102">Convert-CcIsoToVhdx コマンドレットは、顧客支給の Windows Server 2012 R2 ISO ファイルを使用してベース仮想ハード ディスク　ファイル (VHDX) を作成します。VHDX ファイルは、Skype for Business Cloud Connector エディションの展開時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="64bdb-p102">The Convert-CcIsoToVhdx cmdlet creates a base virtual hard disk file (VHDX) using a customer supplied Windows Server 2012 R2 ISO file. The VHDX file will be used during the deployment of Skype for Business Cloud Connector Edition.</span></span>
  
```
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a><span data-ttu-id="64bdb-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="64bdb-107">Parameters</span></span>

|<span data-ttu-id="64bdb-108">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="64bdb-108">**Parameter**</span></span>|<span data-ttu-id="64bdb-109">**必須**</span><span class="sxs-lookup"><span data-stu-id="64bdb-109">**Required**</span></span>|<span data-ttu-id="64bdb-110">**型**</span><span class="sxs-lookup"><span data-stu-id="64bdb-110">**Type**</span></span>|<span data-ttu-id="64bdb-111">**説明**</span><span class="sxs-lookup"><span data-stu-id="64bdb-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="64bdb-112">IsoFilePath</span><span class="sxs-lookup"><span data-stu-id="64bdb-112">IsoFilePath</span></span>  <br/> | <span data-ttu-id="64bdb-113">必須</span><span class="sxs-lookup"><span data-stu-id="64bdb-113">Required</span></span> <br/> |<span data-ttu-id="64bdb-114">System.String</span><span class="sxs-lookup"><span data-stu-id="64bdb-114">System.String</span></span>  <br/> | <span data-ttu-id="64bdb-115">Windows Server 2012 R2 ISO ファイルのパス。</span><span class="sxs-lookup"><span data-stu-id="64bdb-115">The path to the Windows Server 2012 R2 ISO file.</span></span> <br/> |
|<span data-ttu-id="64bdb-116">GeneralizeOnly</span><span class="sxs-lookup"><span data-stu-id="64bdb-116">GeneralizeOnly</span></span>  <br/> |<span data-ttu-id="64bdb-117">省略可能</span><span class="sxs-lookup"><span data-stu-id="64bdb-117">Optional</span></span>  <br/> |<span data-ttu-id="64bdb-118">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="64bdb-118">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="64bdb-p103">Windows の更新中に変換処理が失敗する場合は、ネットワーク/プロキシの構成を行い、手動で Windows を更新することができます。手動による作業が完了したら、-GeneralizeOnly　パラメーターを指定したコマンドレットを実行して残りのジョブを完了することができます。</span><span class="sxs-lookup"><span data-stu-id="64bdb-p103">If the conversion process fails during Windows update, you can try to configure a network/proxy and update Windows manually. After the manual work is done, you can run this cmdlet with the -GeneralizeOnly parameter and it will complete the remaining jobs.</span></span>  <br/> |
|<span data-ttu-id="64bdb-121">PauseBeforeUpdate</span><span class="sxs-lookup"><span data-stu-id="64bdb-121">PauseBeforeUpdate</span></span>  <br/> |<span data-ttu-id="64bdb-122">省略可能</span><span class="sxs-lookup"><span data-stu-id="64bdb-122">Optional</span></span>  <br/> |<span data-ttu-id="64bdb-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="64bdb-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="64bdb-p104">Windows を更新するために、ベース VM で手動によるネットワーク/プロキシの構成が必要になる場合があります。このパラメーターが指定されている場合、Windows の更新前に変換プロセスは一時停止します。手動による構成を完了した後に、プロセスを再開できます。</span><span class="sxs-lookup"><span data-stu-id="64bdb-p104">To update Windows, some manual network/proxy configuration on the base VM might be necessary. The conversion process will pause before Windows update if this parameter is provided. After the manual configuration is done, you can resume the process.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="64bdb-127">例</span><span class="sxs-lookup"><span data-stu-id="64bdb-127">Examples</span></span>
<span data-ttu-id="64bdb-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="64bdb-128"></span></span>

### <a name="example-1"></a><span data-ttu-id="64bdb-129">例 1</span><span class="sxs-lookup"><span data-stu-id="64bdb-129">Example 1</span></span>

<span data-ttu-id="64bdb-130">次の例では、「C:\Windows_Server_2012_R2-EN-US-x64.ISO」に配置されている Windows Server 2012 R2 ISO ファイルを使用して、ベース VHDX ファイルを用意します。</span><span class="sxs-lookup"><span data-stu-id="64bdb-130">The following example prepares the base VHDX file using a Windows Server 2012 R2 ISO file located at "C:\Windows_Server_2012_R2-EN-US-x64.ISO":</span></span> 
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a><span data-ttu-id="64bdb-131">例 2</span><span class="sxs-lookup"><span data-stu-id="64bdb-131">Example 2</span></span>

<span data-ttu-id="64bdb-132">変換 CcIsoToVhdx コマンドレットが実行中に障害が発生した場合は、Windows update、不適切なネットワークやプロキシの構成によっては可能性があります。</span><span class="sxs-lookup"><span data-stu-id="64bdb-132">If the Convert-CcIsoToVhdx cmdlet fails during Windows update, it's probably because of incorrect network/proxy configuration.</span></span> <span data-ttu-id="64bdb-133">エラー メッセージ内の指示に従って、ベース仮想マシンにログ オンしてこの問題を修正し、手動で Windows を更新することができます。</span><span class="sxs-lookup"><span data-stu-id="64bdb-133">You can follow the instructions in the error message and log on to the base virtual machine to fix the issue and update Windows manually.</span></span> <span data-ttu-id="64bdb-134">手動による作業が完了したら、-GeneralizeOnly パラメーターを指定したコマンドレットを再び実行して、残りのジョブを完了します。</span><span class="sxs-lookup"><span data-stu-id="64bdb-134">After the manual work is done, run the cmdlet again with the -GeneralizeOnly parameter to complete the remaining jobs:</span></span> 
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a><span data-ttu-id="64bdb-135">例 3</span><span class="sxs-lookup"><span data-stu-id="64bdb-135">Example 3</span></span>

<span data-ttu-id="64bdb-136">Windows を更新するのに手動による構成が必要な場合、-PauseBeforeUpdate パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="64bdb-136">If manual configuration is necessary to update Windows, you can use the -PauseBeforeUpdate parameter.</span></span> <span data-ttu-id="64bdb-137">このパラメーターでは、Windows プロセスを更新する前にクラウドのコネクタが一時停止します。</span><span class="sxs-lookup"><span data-stu-id="64bdb-137">With this parameter, Cloud Connector will pause before the Windows update process.</span></span> <span data-ttu-id="64bdb-138">その後、手動による構成を完了して、次のように変換処理を再開できます。</span><span class="sxs-lookup"><span data-stu-id="64bdb-138">You can then complete the manual configuration and resume the conversion process as follows:</span></span>
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="64bdb-139">解説</span><span class="sxs-lookup"><span data-stu-id="64bdb-139">Detailed Description</span></span>
<span data-ttu-id="64bdb-140"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="64bdb-140"></span></span>

<span data-ttu-id="64bdb-141">変換 CcIsoToVhdx コマンドレットでは、VM が 1 つは、クラウド コネクタに依存し、Windows の更新プログラムをインストールし、いくつかの基本的なコンポーネントをインストールするベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="64bdb-141">The Convert-CcIsoToVhdx cmdlet creates a base VM first, installs some basic components that Cloud Connector depends on, and then installs Windows updates.</span></span> <span data-ttu-id="64bdb-142">最後に、コネクタのクラウド アプライアンスのバーチャル マシンによって使用される基本 VHDX ファイルを取得するには、仮想マシン (sysprep) を一般化します。</span><span class="sxs-lookup"><span data-stu-id="64bdb-142">Finally, it generalizes the virtual machine (sysprep) to get a base VHDX file that will be used by the virtual machines of a Cloud Connector appliance.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="64bdb-143">入力の種類</span><span class="sxs-lookup"><span data-stu-id="64bdb-143">Input Types</span></span>
<span data-ttu-id="64bdb-144"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="64bdb-144"></span></span>

<span data-ttu-id="64bdb-p108">なし。Convert-CcIsoToVhdx　コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="64bdb-p108">None. The Convert-CcIsoToVhdx cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="64bdb-147">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="64bdb-147">Return Types</span></span>
<span data-ttu-id="64bdb-148"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="64bdb-148"></span></span>

<span data-ttu-id="64bdb-149">なし</span><span class="sxs-lookup"><span data-stu-id="64bdb-149">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="64bdb-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="64bdb-150">See also</span></span>
<span data-ttu-id="64bdb-151"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="64bdb-151"></span></span>

<span data-ttu-id="64bdb-152">なし</span><span class="sxs-lookup"><span data-stu-id="64bdb-152">None</span></span>
  

