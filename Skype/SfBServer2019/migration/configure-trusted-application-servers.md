---
title: 信頼済みアプリケーション サーバーの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 混在環境では、新しい信頼できるアプリケーションサーバーを作成する場合は、次ホッププールを Skype for Business Server 2019 プールとして設定する必要があります。 混在環境では、ドロップダウンリストに従来のプールと Skype for Business Server 2019 プールの両方が表示されます。 従来のプールの選択はサポートされていません。
ms.openlocfilehash: a853065c8888ce9e160b34d182ec8bde6f4569f3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813775"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="5287e-105">信頼済みアプリケーション サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="5287e-105">Configure trusted application servers</span></span>

<span data-ttu-id="5287e-106">混在環境では、新しい信頼できるアプリケーションサーバーを作成する場合は、次ホッププールを Skype for Business Server 2019 プールとして設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5287e-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="5287e-107">混在環境では、ドロップダウンリストに従来のプールと Skype for Business Server 2019 プールの両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5287e-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="5287e-108">従来のプールの選択はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5287e-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5287e-109">信頼されているアプリケーションサーバーを移行する場合は、使用している UCMA のバージョンも更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5287e-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="5287e-110">Skype for Business Server 2019 用の新しい信頼できるアプリケーションプールを作成する場合は、UCMA を Skype for Business Server 2019 に含まれているバージョン、または利用可能な最新バージョンに更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5287e-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="5287e-111">信頼されたアプリケーションサーバーを作成するときに、[Skype for Business Server 2019 (次ホップ)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5287e-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="5287e-112">トポロジビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="5287e-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="5287e-113">左側のウィンドウで、[**信頼されたアプリケーションサーバー** ] を右クリックし、[**新しい信頼できるアプリケーションプール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5287e-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="5287e-114">信頼されているアプリケーションプールの**プール FQDN**を入力し、シングルサーバーとマルチサーバーのどちらにするかを選択します。</span><span class="sxs-lookup"><span data-stu-id="5287e-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="5287e-115">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5287e-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="5287e-116">**[次ホップの選択**] ページで、一覧から [Skype For business Server 2019 フロントエンドプール] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5287e-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="5287e-117">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5287e-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="5287e-118">トップノードの**Skype For Business Server**を選び、[**アクション**] メニューから [**発行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5287e-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="5287e-119">信頼された**アプリケーションプール**が正常に作成され、正しいフロントエンドプールに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5287e-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    

