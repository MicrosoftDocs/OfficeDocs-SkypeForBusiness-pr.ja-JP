---
title: Get CcApplianceDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: Get-CcApplianceDirectory コマンドレットは、Skype for Business Cloud Connector エディションのホスト サーバーでの作業ディレクトリを取得します。すべての展開ファイルはこのディレクトリに保存されます。
ms.openlocfilehash: c5c445e6017d8af81b681b70bbabcf2ba8bedd78
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccappliancedirectory"></a><span data-ttu-id="2655f-104">Get CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="2655f-104">Get-CcApplianceDirectory</span></span>
 
<span data-ttu-id="2655f-p102">Get-CcApplianceDirectory コマンドレットは、Skype for Business Cloud Connector エディションのホスト サーバーでの作業ディレクトリを取得します。すべての展開ファイルはこのディレクトリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="2655f-p102">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span> 
  
<span data-ttu-id="2655f-107">このコマンドレットは Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="2655f-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcApplianceDirectory
```

## <a name="parameters"></a><span data-ttu-id="2655f-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2655f-108">Parameters</span></span>

<span data-ttu-id="2655f-109">なし</span><span class="sxs-lookup"><span data-stu-id="2655f-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="2655f-110">例</span><span class="sxs-lookup"><span data-stu-id="2655f-110">Examples</span></span>
<span data-ttu-id="2655f-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2655f-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="2655f-112">例 1</span><span class="sxs-lookup"><span data-stu-id="2655f-112">Example 1</span></span>

<span data-ttu-id="2655f-113">次の使用例は、クラウドのコネクタ コンポーネントの構成と仮想マシンのファイルが保存されている現在のフォルダーを示しています。</span><span class="sxs-lookup"><span data-stu-id="2655f-113">The following example shows the current folder where configuration and virtual machine files of Cloud Connector components are stored:</span></span>
  
```
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="2655f-114">解説</span><span class="sxs-lookup"><span data-stu-id="2655f-114">Detailed Description</span></span>
<span data-ttu-id="2655f-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2655f-115"></span></span>

<span data-ttu-id="2655f-116">Get CcApplianceDirectory コマンドレットは、クラウドのコネクタのアプライアンスのすべての構成および仮想マシン ・ ファイル、ログ、および外部の証明書を保存する場所を示します。</span><span class="sxs-lookup"><span data-stu-id="2655f-116">The Get-CcApplianceDirectory cmdlet shows where all configuration and virtual machine files, logs, and external certificates are stored for the Cloud Connector appliance.</span></span>
  
<span data-ttu-id="2655f-117">各コネクタのクラウド アプライアンスには 4 つのコンポーネント: 仲介サーバー、中央管理ストア、エッジ サーバー、およびドメイン コント ローラーです。</span><span class="sxs-lookup"><span data-stu-id="2655f-117">Each Cloud Connector appliance has four components: Mediation Server, Central Management Store, Edge Server, and a Domain Controller.</span></span> <span data-ttu-id="2655f-118">既定のフォルダーは、C:\Users\%userprofile%\CloudConnector\ApplianceRoot。</span><span class="sxs-lookup"><span data-stu-id="2655f-118">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span></span> <span data-ttu-id="2655f-119">Set-CCApplianceDirectory コマンドレットを使用してこのフォルダーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="2655f-119">You can change this folder by using the Set-CCApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="2655f-120">入力の種類</span><span class="sxs-lookup"><span data-stu-id="2655f-120">Input Types</span></span>
<span data-ttu-id="2655f-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2655f-121"></span></span>

<span data-ttu-id="2655f-p104">なし。Get-CCApplianceDirectory コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="2655f-p104">None. The Get-CCApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2655f-124">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="2655f-124">Return Types</span></span>
<span data-ttu-id="2655f-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2655f-125"></span></span>

<span data-ttu-id="2655f-126">このコマンドはファイル パスを返します。</span><span class="sxs-lookup"><span data-stu-id="2655f-126">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2655f-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="2655f-127">See also</span></span>
<span data-ttu-id="2655f-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2655f-128"></span></span>

[<span data-ttu-id="2655f-129">セット CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="2655f-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

