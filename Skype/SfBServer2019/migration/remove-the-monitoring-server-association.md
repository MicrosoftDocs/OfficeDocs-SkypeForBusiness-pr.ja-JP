---
title: 監視サーバーの関連付けの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 監視サーバーを削除するには、関連するフロントエンドプール、フロントエンドサーバー、Survivable Branch Appliance、および Survivable Branch Server の依存関係を変更またはクリアする必要があります。 フロントエンドプール、フロントエンドサーバー、Survivable Branch Appliance、Survivable Branch Server のプロパティを編集して、依存関係を削除します。 [トポロジビルダー] で、依存関係を消去してサーバーを削除すると、関連付けられているデータベースストアオブジェクトもトポロジビルダーで削除されることが通知されます。
ms.openlocfilehash: 366bb67815df99542b893e9ced79c1fc1f0e3e9f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301098"
---
# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="400bc-105">監視サーバーの関連付けの削除</span><span class="sxs-lookup"><span data-stu-id="400bc-105">Remove the Monitoring server association</span></span>

<span data-ttu-id="400bc-106">監視サーバーを削除するには、関連するフロントエンドプール、フロントエンドサーバー、Survivable Branch Appliance、および Survivable Branch Server の依存関係を変更またはクリアする必要があります。</span><span class="sxs-lookup"><span data-stu-id="400bc-106">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="400bc-107">フロントエンドプール、フロントエンドサーバー、Survivable Branch Appliance、Survivable Branch Server のプロパティを編集して、依存関係を削除します。</span><span class="sxs-lookup"><span data-stu-id="400bc-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="400bc-108">[トポロジビルダー] で、依存関係を消去してサーバーを削除すると、関連付けられているデータベースストアオブジェクトもトポロジビルダーで削除されることが通知されます。</span><span class="sxs-lookup"><span data-stu-id="400bc-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="400bc-109">監視サーバーの関連付けを削除するには</span><span class="sxs-lookup"><span data-stu-id="400bc-109">To remove the Monitoring Server association</span></span>

1. <span data-ttu-id="400bc-110">Skype for Business Server 2019 フロントエンドサーバーで、[トポロジビルダー] を開きます。</span><span class="sxs-lookup"><span data-stu-id="400bc-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="400bc-111">従来のインストールノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="400bc-111">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="400bc-112">[トポロジビルダー] で、監視サーバーが定義されている場所に応じて、 **Enterprise Edition のフロントエンドプール**、**標準エディションのフロントエンドサーバー**、または**ブランチサイト**を展開します。</span><span class="sxs-lookup"><span data-stu-id="400bc-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Monitoring Server is defined.</span></span>
    
4. <span data-ttu-id="400bc-113">Survivable Branch Server が関連付けられている場合は、[**ブランチサイト**] を展開し、[ブランチサイト名] を展開して、[ **Survivable branch アプライアンス**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="400bc-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="400bc-114">ユーザーインターフェイス内の**Survivable Branch アプライアンス**は、Survivable branch Server と Survivable branch Appliance の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="400bc-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="400bc-115">監視サーバーと関連付けられているプール、サーバー、またはデバイスを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="400bc-115">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="400bc-116">[**プロパティの編集**] の [**一般的な** > **関連付け**] で [**監視サーバーの関連付け**] チェックボックスをオフにして、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="400bc-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="400bc-117">監視サーバーに関連付けられているその他のプール、サーバー、またはデバイスについて、前の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="400bc-117">Repeat the previous step for any other pool, server, or device associated with the Monitoring Server.</span></span>
    
8. <span data-ttu-id="400bc-118">監視サーバーを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="400bc-118">Right-click the Monitoring Server, and then click **Delete**.</span></span> 
    
9. <span data-ttu-id="400bc-119">[**依存**しているストアの削除] で、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="400bc-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="400bc-120">トポロジを公開し、レプリケーションの状態を確認し、必要に応じて Skype for Business Server Deployment ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="400bc-120">Publish the topology, check replication status, and run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

