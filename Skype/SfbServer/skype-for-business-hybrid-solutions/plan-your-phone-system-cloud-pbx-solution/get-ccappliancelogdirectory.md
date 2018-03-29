---
title: Get CcApplianceLogDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: Get-CcApplianceLogDirectory コマンドレットは、Skype for Business Cloud Connector エディションのアプライアンスのログが保存されている現在のディレクトリを示します。
ms.openlocfilehash: 9b7d4853deb9ab16c7ae61279a20a30778774072
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccappliancelogdirectory"></a><span data-ttu-id="5b940-103">Get CcApplianceLogDirectory</span><span class="sxs-lookup"><span data-stu-id="5b940-103">Get-CcApplianceLogDirectory</span></span>
 
<span data-ttu-id="5b940-104">Get-CcApplianceLogDirectory コマンドレットは、Skype for Business Cloud Connector エディションのアプライアンスのログが保存されている現在のディレクトリを示します。</span><span class="sxs-lookup"><span data-stu-id="5b940-104">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.</span></span>
  
<span data-ttu-id="5b940-105">このコマンドレットは Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="5b940-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="5b940-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5b940-106">Parameters</span></span>

<span data-ttu-id="5b940-107">なし</span><span class="sxs-lookup"><span data-stu-id="5b940-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="5b940-108">例</span><span class="sxs-lookup"><span data-stu-id="5b940-108">Examples</span></span>
<span data-ttu-id="5b940-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5b940-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="5b940-110">例 1</span><span class="sxs-lookup"><span data-stu-id="5b940-110">Example 1</span></span>

<span data-ttu-id="5b940-111">クラウド コネクタの現在のアプライアンスは、ログが保存されている現在のフォルダーを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="5b940-111">The following example shows the current folder where logs for the current appliance of Cloud Connector are stored:</span></span>
  
```
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="5b940-112">解説</span><span class="sxs-lookup"><span data-stu-id="5b940-112">Detailed Description</span></span>
<span data-ttu-id="5b940-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5b940-113"></span></span>

<span data-ttu-id="5b940-114">Get CcApplianceLogDirectory コマンドレットでは、コネクタのクラウド アプライアンスは、ログが保存されている現在のディレクトリを示しています。</span><span class="sxs-lookup"><span data-stu-id="5b940-114">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Cloud Connector appliance are stored.</span></span> <span data-ttu-id="5b940-115">既定のフォルダーは、C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs。</span><span class="sxs-lookup"><span data-stu-id="5b940-115">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span></span> 
  
<span data-ttu-id="5b940-116">このディレクトリは、Set-CcApplianceDirectory コマンドレットを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="5b940-116">You can change the directory by using the Set-CcApplianceDirectory cmdlet.</span></span> 
  
<span data-ttu-id="5b940-117">メモ: アプライアンス ディレクトリを変更することなく、ログ フォルダーの場所のみを変更するコマンドレットはありません。</span><span class="sxs-lookup"><span data-stu-id="5b940-117">Note: There is no cmdlet that changes only the log folder location without changing the appliance directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="5b940-118">入力の種類</span><span class="sxs-lookup"><span data-stu-id="5b940-118">Input Types</span></span>
<span data-ttu-id="5b940-119"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5b940-119"></span></span>

<span data-ttu-id="5b940-p102">なし。Get-CcApplianceLogDirectory コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="5b940-p102">None. The Get-CcApplianceLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5b940-122">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="5b940-122">Return Types</span></span>
<span data-ttu-id="5b940-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5b940-123"></span></span>

<span data-ttu-id="5b940-124">このコマンドはファイル パスを返します。</span><span class="sxs-lookup"><span data-stu-id="5b940-124">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5b940-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b940-125">See also</span></span>
<span data-ttu-id="5b940-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5b940-126"></span></span>

[<span data-ttu-id="5b940-127">セット CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="5b940-127">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

