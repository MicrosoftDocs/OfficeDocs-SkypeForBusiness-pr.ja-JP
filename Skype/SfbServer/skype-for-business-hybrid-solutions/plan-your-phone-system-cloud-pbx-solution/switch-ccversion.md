---
title: Switch-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: 'Switch-CcVersion コマンドレットは、実行中のアプライアンスとスイッチの、新規に展開されたアプライアンスまたはバックアップ インスタンスへの接続を切断します。 '
ms.openlocfilehash: e63c5ea6d74e979f7fc9fe5a4c5eae97a0689e1e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286930"
---
# <a name="switch-ccversion"></a><span data-ttu-id="586a0-103">Switch-CcVersion</span><span class="sxs-lookup"><span data-stu-id="586a0-103">Switch-CcVersion</span></span>
 
<span data-ttu-id="586a0-104">Switch-CcVersion コマンドレットは、実行中のアプライアンスとスイッチの、新規に展開されたアプライアンスまたはバックアップ インスタンスへの接続を切断します。 </span><span class="sxs-lookup"><span data-stu-id="586a0-104">The Switch-CcVersion cmdlet disconnects the running appliance and switches to a newly deployed or backup appliance.</span></span> 
  
```
Switch-CcVersion [-Force]
```

## <a name="examples"></a><span data-ttu-id="586a0-105">例</span><span class="sxs-lookup"><span data-stu-id="586a0-105">Examples</span></span>
<span data-ttu-id="586a0-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="586a0-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="586a0-107">例 1</span><span class="sxs-lookup"><span data-stu-id="586a0-107">Example 1</span></span>

<span data-ttu-id="586a0-108">次の例では、現在実行中のアプライアンスのサービスをドレインして、新規に展開されたアプライアンスまたはバックアップ アプライアンスに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="586a0-108">The following example drains the services of the current running appliance, and then switches to a newly deployed or backup appliance:</span></span>
  
```
Switch-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="586a0-109">例 2</span><span class="sxs-lookup"><span data-stu-id="586a0-109">Example 2</span></span>

<span data-ttu-id="586a0-110">次の例では、現在実行中のアプライアンスのサービスをドレインし、サービスのドレインに失敗した場合は強制的にサービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="586a0-110">The next example drains the services of the current running appliance, and stops services forcibly if draining the services fails.</span></span> <span data-ttu-id="586a0-111">コマンドにより、新規に展開されたアプライアンスまたはバックアップ アプライアンスへの接続が切断されます。</span><span class="sxs-lookup"><span data-stu-id="586a0-111">The command then switches to a newly deployed or backup appliance:</span></span>
  
```
Switch-CcVersion -Force
```

## <a name="detailed-description"></a><span data-ttu-id="586a0-112">解説</span><span class="sxs-lookup"><span data-stu-id="586a0-112">Detailed Description</span></span>
<span data-ttu-id="586a0-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="586a0-113"></span></span>

<span data-ttu-id="586a0-114">スイッチ-CcVersion コマンドレットは、仲介サーバーとエッジサーバー上のクラウドコネクタサービスを消費します。</span><span class="sxs-lookup"><span data-stu-id="586a0-114">The Switch-CcVersion cmdlet drains the Cloud Connector services on the Mediation Server and Edge Server.</span></span> <span data-ttu-id="586a0-115">すべての実行中の通話は終了しますが、新しい通話はアプライアンスによって拒否されます。</span><span class="sxs-lookup"><span data-stu-id="586a0-115">All running calls will be completed, but the appliance will reject any new calls.</span></span> <span data-ttu-id="586a0-116">ドレイン後、コマンドレットにより企業ネットワークおよびインターネット ネットワークから実行中のアプライアンスが切断され、アプライアンスに属しているすべての仮想マシンがオフになり、企業ネットワークおよびインターネット ネットワークにバックアップ アプライアンスが接続されます。</span><span class="sxs-lookup"><span data-stu-id="586a0-116">After draining, the cmdlet disconnects the running appliance from the corporate and Internet networks, turns off all the virtual machines belonging to the appliance, and then connects the backup appliance to the corporate and Internet networks.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="586a0-117">パラメーター</span><span class="sxs-lookup"><span data-stu-id="586a0-117">Parameters</span></span>
<span data-ttu-id="586a0-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="586a0-118"></span></span>

|<span data-ttu-id="586a0-119">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="586a0-119">**Parameter**</span></span>|<span data-ttu-id="586a0-120">**必須**</span><span class="sxs-lookup"><span data-stu-id="586a0-120">**Required**</span></span>|<span data-ttu-id="586a0-121">**型**</span><span class="sxs-lookup"><span data-stu-id="586a0-121">**Type**</span></span>|<span data-ttu-id="586a0-122">**説明**</span><span class="sxs-lookup"><span data-stu-id="586a0-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="586a0-123">Force</span><span class="sxs-lookup"><span data-stu-id="586a0-123">Force</span></span> <br/> | <span data-ttu-id="586a0-124">省略可能</span><span class="sxs-lookup"><span data-stu-id="586a0-124">Optional</span></span> <br/> |<span data-ttu-id="586a0-125">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="586a0-125">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="586a0-126"> サービスのドレインに失敗した場合は強制的にサービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="586a0-126">Stops services forcibly if draining the services fails.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="586a0-127">入力の種類</span><span class="sxs-lookup"><span data-stu-id="586a0-127">Input Types</span></span>
<span data-ttu-id="586a0-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="586a0-128"></span></span>

<span data-ttu-id="586a0-129">なし</span><span class="sxs-lookup"><span data-stu-id="586a0-129">None</span></span>
  
## <a name="return-types"></a><span data-ttu-id="586a0-130">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="586a0-130">Return Types</span></span>
<span data-ttu-id="586a0-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="586a0-131"></span></span>

<span data-ttu-id="586a0-132">なし</span><span class="sxs-lookup"><span data-stu-id="586a0-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="586a0-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="586a0-133">See also</span></span>
<span data-ttu-id="586a0-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="586a0-134"></span></span>

<span data-ttu-id="586a0-135">なし</span><span class="sxs-lookup"><span data-stu-id="586a0-135">None</span></span>
  

