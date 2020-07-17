---
title: 信頼されたアプリケーション サーバーを構成する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 混在環境では、信頼されたアプリケーションサーバーを新たに作成する場合は、次ホッププールを Skype for Business Server 2019 プールとして設定する必要があります。 混在環境では、ドロップダウンリストに従来のプールと Skype for Business Server 2019 プールの両方が表示されます。 従来のプールを選択することはできません。
ms.openlocfilehash: 1c0aac1efa4f83a81ccf2f3bb5ecbc925ee58839
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753947"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="03f28-105">信頼されたアプリケーション サーバーを構成する</span><span class="sxs-lookup"><span data-stu-id="03f28-105">Configure trusted application servers</span></span>

<span data-ttu-id="03f28-106">混在環境では、信頼されたアプリケーションサーバーを新たに作成する場合は、次ホッププールを Skype for Business Server 2019 プールとして設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03f28-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="03f28-107">混在環境では、ドロップダウンリストに従来のプールと Skype for Business Server 2019 プールの両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="03f28-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="03f28-108">従来のプールを選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="03f28-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="03f28-109">信頼されたアプリケーションサーバーを移行する場合は、使用している UCMA のバージョンも更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03f28-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="03f28-110">Skype for business Server 2019 用の新しい信頼されたアプリケーションプールを作成する場合は、UCMA を Skype for Business Server 2019 に含まれているバージョンまたは利用可能な最新バージョンに更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03f28-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="03f28-111">信頼されたアプリケーションサーバーを作成するときは、次ホップとして Skype for Business Server 2019 を選択します。</span><span class="sxs-lookup"><span data-stu-id="03f28-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="03f28-112">トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="03f28-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="03f28-113">左側のウィンドウで、[**信頼済みアプリケーションサーバー** ] を右クリックし、[**新しい信頼済みアプリケーションプール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03f28-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="03f28-114">信頼されたアプリケーションプールの [**プールの FQDN** ] を入力し、単一サーバーにするか複数サーバーにするかを選択します。</span><span class="sxs-lookup"><span data-stu-id="03f28-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="03f28-115">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03f28-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="03f28-116">[**次ホップの選択**] ページで、リストから [Skype For business Server 2019 フロントエンドプール] を選択します。</span><span class="sxs-lookup"><span data-stu-id="03f28-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="03f28-117">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03f28-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="03f28-118">最上位の [ **Skype For Business Server**] ノードを選択し、[**アクション**] メニューの [**発行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="03f28-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="03f28-119">**信頼済みアプリケーションプール**が正常に作成され、適切なフロントエンドプールに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="03f28-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    

