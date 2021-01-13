---
title: Skype for Business Server のネットワーク サイトに場所ポリシーを追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Skype for Business Server のネットワーク サイトに E9-1-1 の場所ポリシーを割り当エンタープライズ VoIP。
ms.openlocfilehash: 887c2fcab63acd5d143ba80f6be6976e8fe2b39f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804277"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a><span data-ttu-id="124b9-103">Skype for Business Server のネットワーク サイトに場所ポリシーを追加する</span><span class="sxs-lookup"><span data-stu-id="124b9-103">Add a location policy to a network site in Skype for Business Server</span></span>
 
<span data-ttu-id="124b9-104">Skype for Business Server のネットワーク サイトに E9-1-1 の場所ポリシーを割り当エンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="124b9-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="124b9-105">次の例は [、「Create location policies in Skype for Business Server」](create-location-policies.md)で定義されている Redmond の場所ポリシーを既存のネットワーク サイトに追加する方法と **、Redmond** の場所ポリシーを使用する新しいネットワーク サイトを作成する方法を示しています。 </span><span class="sxs-lookup"><span data-stu-id="124b9-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="124b9-106">ネットワーク サイトの操作の詳細については、次のコマンドレットの Lync Server 管理シェルのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="124b9-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="124b9-107">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="124b9-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="124b9-108">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="124b9-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="124b9-109">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="124b9-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="124b9-110">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="124b9-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="124b9-111">場所のポリシーを既存のネットワーク サイトに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="124b9-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="124b9-112">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="124b9-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="124b9-113">既存のネットワーク サイトを変更するには、以下のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="124b9-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="124b9-114">**Redmond というタグ付** きの場所ポリシーを Redmond という名前の既存のネットワーク サイトに **割り当てる**。</span><span class="sxs-lookup"><span data-stu-id="124b9-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="124b9-115">場所のポリシーを新しいネットワーク サイトに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="124b9-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="124b9-116">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="124b9-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="124b9-117">新しいネットワーク サイトを作成するには、以下のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="124b9-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="124b9-118">ネットワーク地域の新しいネットワーク サイトを作成して、**Redmond** とマークされた場所のポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="124b9-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


