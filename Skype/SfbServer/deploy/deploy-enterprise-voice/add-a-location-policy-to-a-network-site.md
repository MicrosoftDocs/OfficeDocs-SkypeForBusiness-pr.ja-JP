---
title: Skype for Business Server 2015 でのネットワーク サイトへの場所ポリシーの追加
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: ビジネス サーバーのエンタープライズ VoIP の Skype のネットワーク サイトへの ~ 9-1-1 の場所のポリシーを割り当てます。
ms.openlocfilehash: 5d6b343db63a309661720a8379d204a0abcac1f5
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server-2015"></a><span data-ttu-id="23650-103">Skype for Business Server 2015 でのネットワーク サイトへの場所ポリシーの追加</span><span class="sxs-lookup"><span data-stu-id="23650-103">Add a location policy to a network site in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="23650-104">ビジネス サーバーのエンタープライズ VoIP の Skype のネットワーク サイトへの ~ 9-1-1 の場所のポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="23650-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="23650-105">次の例は、既存のネットワーク サイトに[ビジネス サーバー 2015 の Skype で作成する場所のポリシー](create-location-policies.md)で定義された**Redmond**の場所のポリシーを追加する方法、および**Redmond**の場所を使用する新しいネットワーク サイトを作成する方法を表示します。ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="23650-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server 2015](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="23650-106">ネットワークのサイトの操作に関する詳細については、次のコマンドレットは Lync Server 管理シェルのマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="23650-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="23650-107">**新しい-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="23650-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="23650-108">**Get CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="23650-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="23650-109">**セット CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="23650-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="23650-110">**削除 CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="23650-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="23650-111">場所のポリシーを既存のネットワーク サイトに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="23650-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="23650-112">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="23650-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="23650-113">既存のネットワーク サイトを変更するには、以下のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="23650-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="23650-114">**Redmond** とマークされている場所のポリシーを、**Redmond** という名前の既存のネットワーク サイトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="23650-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
  ```
  Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

  ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="23650-115">場所のポリシーを新しいネットワーク サイトに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="23650-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="23650-116">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="23650-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="23650-117">新しいネットワーク サイトを作成するには、以下のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="23650-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="23650-118">ネットワーク地域の新しいネットワーク サイトを作成して、**Redmond** とマークされた場所のポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="23650-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


