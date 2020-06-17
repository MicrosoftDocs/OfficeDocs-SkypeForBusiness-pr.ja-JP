---
title: フロントエンド プールまたは Standard Edition サーバーの削除
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
description: このトピックでは、フロントエンドプールまたは Standard Edition フロントエンドサーバーを削除するプロセスについて説明します。 フロントエンドプールを削除する場合は、プール削除処理の一部として、そのプールに属する各フロントエンドサーバーを削除します。 Standard Edition フロントエンドサーバーを削除する場合は、トポロジビルダーから SQL ストア定義を削除する必要があります。
ms.openlocfilehash: 305a353ced45fe7e21ba479c0c3571df236aa09b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752279"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="7fb2a-105">フロントエンド プールまたは Standard Edition サーバーの削除</span><span class="sxs-lookup"><span data-stu-id="7fb2a-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="7fb2a-106">この記事では、フロントエンドプールまたは Standard Edition フロントエンドサーバーを削除するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="7fb2a-107">フロントエンドプールを削除する場合は、プール削除処理の一部として、そのプールに属する各フロントエンドサーバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="7fb2a-108">Standard Edition フロントエンドサーバーを削除する場合は、トポロジビルダーから SQL ストア定義を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="7fb2a-109">フロントエンド サーバー プールを削除するには</span><span class="sxs-lookup"><span data-stu-id="7fb2a-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="7fb2a-110">トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="7fb2a-111">従来のノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="7fb2a-112">[ **Enterprise Edition フロントエンド**プール] を展開し、フロントエンドプールを展開して、削除するフロントエンドプールを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="7fb2a-113">トポロジを公開し、レプリケーションの状態を確認してから、必要に応じて従来の展開ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="7fb2a-114">Standard Edition フロントエンド サーバーを削除するには</span><span class="sxs-lookup"><span data-stu-id="7fb2a-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="7fb2a-115">トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="7fb2a-116">[従来のインストールのノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="7fb2a-117">[ **Standard Edition フロントエンドサーバー**] を展開し、削除するフロントエンドサーバーを右クリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="7fb2a-118">[ **Sql ストア**] を展開し、Standard Edition フロントエンドサーバーに関連付けられている sql Server データベースを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7fb2a-119">併置された SQL Server データベースの定義は、Standard Edition フロントエンドサーバーから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="7fb2a-120">トポロジを公開し、レプリケーションの状態を確認してから、必要に応じて展開ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

