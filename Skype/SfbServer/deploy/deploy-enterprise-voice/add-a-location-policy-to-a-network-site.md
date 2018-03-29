---
title: Skype for Business Server 2015 でのネットワーク サイトへの場所ポリシーの追加
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: ビジネス サーバーのエンタープライズ VoIP の Skype のネットワーク サイトへの ~ 9-1-1 の場所のポリシーを割り当てます。
ms.openlocfilehash: bf2b8675ebaa14e98f8a362b3a0714037000de95
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server-2015"></a><span data-ttu-id="8f4ea-103">Skype for Business Server 2015 でのネットワーク サイトへの場所ポリシーの追加</span><span class="sxs-lookup"><span data-stu-id="8f4ea-103">Add a location policy to a network site in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8f4ea-104">ビジネス サーバーのエンタープライズ VoIP の Skype のネットワーク サイトへの ~ 9-1-1 の場所のポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8f4ea-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="8f4ea-105">次の例は、既存のネットワーク サイトに[ビジネス サーバー 2015 の Skype で作成する場所のポリシー](create-location-policies.md)で定義された**Redmond**の場所のポリシーを追加する方法、および**Redmond**の場所を使用する新しいネットワーク サイトを作成する方法を表示します。ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="8f4ea-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server 2015](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="8f4ea-106">ネットワークのサイトの操作に関する詳細については、次のコマンドレットは Lync Server 管理シェルのマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f4ea-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="8f4ea-107">**新しい-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="8f4ea-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="8f4ea-108">**Get CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="8f4ea-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="8f4ea-109">**セット CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="8f4ea-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="8f4ea-110">**削除 CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="8f4ea-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="8f4ea-111">場所のポリシーを既存のネットワーク サイトに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="8f4ea-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="8f4ea-112">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f4ea-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8f4ea-113">既存のネットワーク サイトを変更するには、以下のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="8f4ea-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="8f4ea-114">**Redmond** とマークされている場所のポリシーを、**Redmond** という名前の既存のネットワーク サイトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8f4ea-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
  ```
  Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

  ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="8f4ea-115">場所のポリシーを新しいネットワーク サイトに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="8f4ea-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="8f4ea-116">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f4ea-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8f4ea-117">新しいネットワーク サイトを作成するには、以下のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="8f4ea-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="8f4ea-118">ネットワーク地域の新しいネットワーク サイトを作成して、**Redmond** とマークされた場所のポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8f4ea-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


