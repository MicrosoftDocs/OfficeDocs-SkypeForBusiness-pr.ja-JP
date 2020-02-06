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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: Get-CcApplianceDirectory コマンドレットは、Skype for Business Cloud Connector エディションのホスト サーバーでの作業ディレクトリを取得します。すべての展開ファイルはこのディレクトリに保存されます。
ms.openlocfilehash: 04764f312138132fb34c0979423da5dc4696ee63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800847"
---
# <a name="get-ccappliancedirectory"></a><span data-ttu-id="8eaf4-104">Get-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="8eaf4-104">Get-CcApplianceDirectory</span></span>
 
<span data-ttu-id="8eaf4-p102">Get-CcApplianceDirectory コマンドレットは、Skype for Business Cloud Connector エディションのホスト サーバーでの作業ディレクトリを取得します。すべての展開ファイルはこのディレクトリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="8eaf4-p102">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span> 
  
<span data-ttu-id="8eaf4-107">このコマンドレットは Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8eaf4-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a><span data-ttu-id="8eaf4-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8eaf4-108">Parameters</span></span>

<span data-ttu-id="8eaf4-109">なし</span><span class="sxs-lookup"><span data-stu-id="8eaf4-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="8eaf4-110">例</span><span class="sxs-lookup"><span data-stu-id="8eaf4-110">Examples</span></span>
<span data-ttu-id="8eaf4-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="8eaf4-111"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="8eaf4-112">例 1</span><span class="sxs-lookup"><span data-stu-id="8eaf4-112">Example 1</span></span>

<span data-ttu-id="8eaf4-113">次の例は、クラウドコネクタコンポーネントの構成ファイルと仮想マシンファイルが保存されている現在のフォルダーを示しています。</span><span class="sxs-lookup"><span data-stu-id="8eaf4-113">The following example shows the current folder where configuration and virtual machine files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="8eaf4-114">解説</span><span class="sxs-lookup"><span data-stu-id="8eaf4-114">Detailed Description</span></span>
<span data-ttu-id="8eaf4-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8eaf4-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="8eaf4-116">CcApplianceDirectory コマンドレットは、クラウドコネクタアプライアンスのすべての構成ファイル、仮想マシンのファイル、ログ、外部証明書が保存されている場所を示します。</span><span class="sxs-lookup"><span data-stu-id="8eaf4-116">The Get-CcApplianceDirectory cmdlet shows where all configuration and virtual machine files, logs, and external certificates are stored for the Cloud Connector appliance.</span></span>
  
<span data-ttu-id="8eaf4-117">各クラウドコネクタアプライアンスには、仲介サーバー、中央管理ストア、エッジサーバー、ドメインコントローラーという4つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="8eaf4-117">Each Cloud Connector appliance has four components: Mediation Server, Central Management Store, Edge Server, and a Domain Controller.</span></span> <span data-ttu-id="8eaf4-118">既定のフォルダーは C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="8eaf4-118">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span></span> <span data-ttu-id="8eaf4-119">Set-CCApplianceDirectory コマンドレットを使用してこのフォルダーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="8eaf4-119">You can change this folder by using the Set-CCApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="8eaf4-120">入力の種類</span><span class="sxs-lookup"><span data-stu-id="8eaf4-120">Input Types</span></span>
<span data-ttu-id="8eaf4-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8eaf4-121"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="8eaf4-p104">なし。Get-CCApplianceDirectory コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="8eaf4-p104">None. The Get-CCApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="8eaf4-124">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="8eaf4-124">Return Types</span></span>
<span data-ttu-id="8eaf4-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8eaf4-125"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="8eaf4-126">このコマンドはファイル パスを返します。</span><span class="sxs-lookup"><span data-stu-id="8eaf4-126">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8eaf4-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="8eaf4-127">See also</span></span>
<span data-ttu-id="8eaf4-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8eaf4-128"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="8eaf4-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="8eaf4-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

