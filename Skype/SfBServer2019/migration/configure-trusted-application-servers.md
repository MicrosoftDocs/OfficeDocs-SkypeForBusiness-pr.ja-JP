---
title: 信頼済みアプリケーション サーバーの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 混在環境で、新しい信頼されたアプリケーション サーバーを作成する場合、次ホップ プールのプールのビジネス サーバー 2019、Skype を設定する必要があります。 混在環境で、従来のプールとプールのビジネス サーバー 2019 Skype の両方がドロップ ダウン リストに表示されます。 従来のプールを選択することはサポートされていません。
ms.openlocfilehash: 79f4de527008d2d9bf295fcb82eee433d04a1691
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890889"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="9a11d-105">信頼済みアプリケーション サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="9a11d-105">Configure trusted application servers</span></span>

<span data-ttu-id="9a11d-106">混在環境で、新しい信頼されたアプリケーション サーバーを作成する場合、次ホップ プールのプールのビジネス サーバー 2019、Skype を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a11d-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="9a11d-107">混在環境で、従来のプールとプールのビジネス サーバー 2019 Skype の両方がドロップ ダウン リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9a11d-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="9a11d-108">従来のプールを選択することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9a11d-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9a11d-109">信頼されたアプリケーション サーバーを移行する場合もを使用している UCMA のバージョンを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a11d-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="9a11d-110">Skype のビジネス サーバー 2019 の新しい信頼されたアプリケーション プールを作成する場合は、Skype のビジネス サーバー 2019 に含まれているバージョンまたは最新バージョンに UCMA を更新してください。</span><span class="sxs-lookup"><span data-stu-id="9a11d-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="9a11d-111">信頼済みアプリケーション サーバーを作成するときは、次のホップとしてビジネス サーバー 2019 の Skype を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a11d-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="9a11d-112">トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="9a11d-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="9a11d-113">左側のウィンドウで**信頼済みアプリケーション サーバー** ] を右クリックし、**新しい信頼されたアプリケーション プール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a11d-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="9a11d-114">信頼されたアプリケーション プールの**プールの FQDN**を入力し、1 台のサーバーまたは複数のサーバーかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="9a11d-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="9a11d-115">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a11d-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="9a11d-116">**次ホップの選択**] ページで、ボックスの一覧からビジネス サーバー 2019 のフロント エンド プールの Skype を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a11d-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="9a11d-117">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a11d-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="9a11d-118">**Skype**ビジネス サーバーは、最上位のノードを選択し、 **[操作**] メニューから [**発行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a11d-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="9a11d-119">**信頼されたアプリケーション プール**が正常に作成されて、適切なフロント エンド プールに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a11d-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    

