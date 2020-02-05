---
title: Skype for Business Server のネットワークサイトに位置情報ポリシーを追加する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: E9-1 の場所のポリシーを Skype for Business Server Enterprise Voice のネットワークサイトに割り当てます。
ms.openlocfilehash: ef6395b2239256abce82612b4863a667ce3b27ab
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768280"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a><span data-ttu-id="2d35c-103">Skype for Business Server のネットワークサイトに位置情報ポリシーを追加する</span><span class="sxs-lookup"><span data-stu-id="2d35c-103">Add a location policy to a network site in Skype for Business Server</span></span>
 
<span data-ttu-id="2d35c-104">E9-1 の場所のポリシーを Skype for Business Server Enterprise Voice のネットワークサイトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2d35c-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="2d35c-105">次の例は、 [Skype For Business Server の [場所ポリシーの作成](create-location-policies.md)] で定義されている**redmond**の場所ポリシーを既存のネットワークサイトに追加する方法と、 **redmond**の場所ポリシーを使用する新しいネットワークサイトを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2d35c-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="2d35c-106">ネットワークサイトの操作の詳細については、次のコマンドレットの Lync Server 管理シェルに関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d35c-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="2d35c-107">**新しい-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="2d35c-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="2d35c-108">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="2d35c-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="2d35c-109">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="2d35c-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="2d35c-110">**CsNetworkSite の削除**</span><span class="sxs-lookup"><span data-stu-id="2d35c-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="2d35c-111">場所のポリシーを既存のネットワーク サイトに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="2d35c-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="2d35c-112">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d35c-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2d35c-113">既存のネットワーク サイトを変更するには、以下のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d35c-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="2d35c-114">**Redmond** とマークされている場所のポリシーを、**Redmond** という名前の既存のネットワーク サイトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2d35c-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="2d35c-115">場所のポリシーを新しいネットワーク サイトに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="2d35c-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="2d35c-116">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d35c-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2d35c-117">新しいネットワーク サイトを作成するには、以下のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d35c-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="2d35c-118">ネットワーク地域の新しいネットワーク サイトを作成して、**Redmond** とマークされた場所のポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2d35c-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


