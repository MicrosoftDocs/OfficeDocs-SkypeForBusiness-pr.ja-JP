---
title: Get-CcApplianceLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: Get-CcApplianceLogDirectory コマンドレットは、Skype for Business Cloud Connector エディションのアプライアンスのログが保存されている現在のディレクトリを示します。
ms.openlocfilehash: a8b7e1b13302bec27c2fe784804f8f43fe2e023c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003397"
---
# <a name="get-ccappliancelogdirectory"></a><span data-ttu-id="6269c-103">Get-CcApplianceLogDirectory</span><span class="sxs-lookup"><span data-stu-id="6269c-103">Get-CcApplianceLogDirectory</span></span>
 
<span data-ttu-id="6269c-104">Get-CcApplianceLogDirectory コマンドレットは、Skype for Business Cloud Connector エディションのアプライアンスのログが保存されている現在のディレクトリを示します。</span><span class="sxs-lookup"><span data-stu-id="6269c-104">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.</span></span>
  
<span data-ttu-id="6269c-105">このコマンドレットは Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="6269c-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="6269c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6269c-106">Parameters</span></span>

<span data-ttu-id="6269c-107">なし</span><span class="sxs-lookup"><span data-stu-id="6269c-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="6269c-108">例</span><span class="sxs-lookup"><span data-stu-id="6269c-108">Examples</span></span>
<span data-ttu-id="6269c-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6269c-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="6269c-110">例 1</span><span class="sxs-lookup"><span data-stu-id="6269c-110">Example 1</span></span>

<span data-ttu-id="6269c-111">次の例は、Cloud Connector の現在のアプライアンスのログが保存されている現在のフォルダーを示しています。</span><span class="sxs-lookup"><span data-stu-id="6269c-111">The following example shows the current folder where logs for the current appliance of Cloud Connector are stored:</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="6269c-112">解説</span><span class="sxs-lookup"><span data-stu-id="6269c-112">Detailed Description</span></span>
<span data-ttu-id="6269c-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="6269c-113"></span></span>

<span data-ttu-id="6269c-114">CcApplianceLogDirectory コマンドレットは、クラウドコネクタアプライアンスのログが保存されている現在のディレクトリを示しています。</span><span class="sxs-lookup"><span data-stu-id="6269c-114">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Cloud Connector appliance are stored.</span></span> <span data-ttu-id="6269c-115">既定のフォルダーは C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="6269c-115">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span></span> 
  
<span data-ttu-id="6269c-116">このディレクトリは、Set-CcApplianceDirectory コマンドレットを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="6269c-116">You can change the directory by using the Set-CcApplianceDirectory cmdlet.</span></span> 
  
<span data-ttu-id="6269c-117">メモ: アプライアンス ディレクトリを変更することなく、ログ フォルダーの場所のみを変更するコマンドレットはありません。</span><span class="sxs-lookup"><span data-stu-id="6269c-117">Note: There is no cmdlet that changes only the log folder location without changing the appliance directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="6269c-118">入力の種類</span><span class="sxs-lookup"><span data-stu-id="6269c-118">Input Types</span></span>
<span data-ttu-id="6269c-119"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6269c-119"></span></span>

<span data-ttu-id="6269c-p102">なし。Get-CcApplianceLogDirectory コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="6269c-p102">None. The Get-CcApplianceLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="6269c-122">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="6269c-122">Return Types</span></span>
<span data-ttu-id="6269c-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6269c-123"></span></span>

<span data-ttu-id="6269c-124">このコマンドはファイル パスを返します。</span><span class="sxs-lookup"><span data-stu-id="6269c-124">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6269c-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="6269c-125">See also</span></span>
<span data-ttu-id="6269c-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6269c-126"></span></span>

[<span data-ttu-id="6269c-127">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="6269c-127">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

