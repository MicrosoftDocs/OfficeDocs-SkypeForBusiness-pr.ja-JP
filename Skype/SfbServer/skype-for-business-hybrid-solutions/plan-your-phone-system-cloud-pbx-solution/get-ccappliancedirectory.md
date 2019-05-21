---
title: Get-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: Get-CcApplianceDirectory コマンドレットは、Skype for Business Cloud Connector エディションのホスト サーバーでの作業ディレクトリを取得します。すべての展開ファイルはこのディレクトリに保存されます。
ms.openlocfilehash: ada1b587b738d882f81557e61438d6642aa03fff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287392"
---
# <a name="get-ccappliancedirectory"></a><span data-ttu-id="253fe-104">Get-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="253fe-104">Get-CcApplianceDirectory</span></span>
 
<span data-ttu-id="253fe-p102">Get-CcApplianceDirectory コマンドレットは、Skype for Business Cloud Connector エディションのホスト サーバーでの作業ディレクトリを取得します。すべての展開ファイルはこのディレクトリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="253fe-p102">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span> 
  
<span data-ttu-id="253fe-107">このコマンドレットは Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="253fe-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcApplianceDirectory
```

## <a name="parameters"></a><span data-ttu-id="253fe-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="253fe-108">Parameters</span></span>

<span data-ttu-id="253fe-109">なし</span><span class="sxs-lookup"><span data-stu-id="253fe-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="253fe-110">例</span><span class="sxs-lookup"><span data-stu-id="253fe-110">Examples</span></span>
<span data-ttu-id="253fe-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="253fe-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="253fe-112">例 1</span><span class="sxs-lookup"><span data-stu-id="253fe-112">Example 1</span></span>

<span data-ttu-id="253fe-113">次の例は、クラウドコネクタコンポーネントの構成ファイルと仮想マシンファイルが保存されている現在のフォルダーを示しています。</span><span class="sxs-lookup"><span data-stu-id="253fe-113">The following example shows the current folder where configuration and virtual machine files of Cloud Connector components are stored:</span></span>
  
```
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="253fe-114">解説</span><span class="sxs-lookup"><span data-stu-id="253fe-114">Detailed Description</span></span>
<span data-ttu-id="253fe-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="253fe-115"></span></span>

<span data-ttu-id="253fe-116">CcApplianceDirectory コマンドレットは、クラウドコネクタアプライアンスのすべての構成ファイル、仮想マシンのファイル、ログ、外部証明書が保存されている場所を示します。</span><span class="sxs-lookup"><span data-stu-id="253fe-116">The Get-CcApplianceDirectory cmdlet shows where all configuration and virtual machine files, logs, and external certificates are stored for the Cloud Connector appliance.</span></span>
  
<span data-ttu-id="253fe-117">各クラウドコネクタアプライアンスには、仲介サーバー、中央管理ストア、エッジサーバー、ドメインコントローラーという4つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="253fe-117">Each Cloud Connector appliance has four components: Mediation Server, Central Management Store, Edge Server, and a Domain Controller.</span></span> <span data-ttu-id="253fe-118">既定のフォルダーは C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="253fe-118">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span></span> <span data-ttu-id="253fe-119">Set-CCApplianceDirectory コマンドレットを使用してこのフォルダーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="253fe-119">You can change this folder by using the Set-CCApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="253fe-120">入力の種類</span><span class="sxs-lookup"><span data-stu-id="253fe-120">Input Types</span></span>
<span data-ttu-id="253fe-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="253fe-121"></span></span>

<span data-ttu-id="253fe-p104">なし。Get-CCApplianceDirectory コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="253fe-p104">None. The Get-CCApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="253fe-124">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="253fe-124">Return Types</span></span>
<span data-ttu-id="253fe-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="253fe-125"></span></span>

<span data-ttu-id="253fe-126">このコマンドはファイル パスを返します。</span><span class="sxs-lookup"><span data-stu-id="253fe-126">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="253fe-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="253fe-127">See also</span></span>
<span data-ttu-id="253fe-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="253fe-128"></span></span>

[<span data-ttu-id="253fe-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="253fe-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

