---
title: フロントエンド プールまたは Standard Edition サーバーの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: このトピックでは、フロントエンドプールまたは標準エディションのフロントエンドサーバーを削除する手順について説明します。 フロントエンドプールを削除する場合は、プールに属している各フロントエンドサーバーをプール削除プロセスの一部として削除します。 Standard Edition のフロントエンドサーバーを削除する場合は、トポロジビルダーから SQL ストアの定義を削除する必要があります。
ms.openlocfilehash: fd43682fca67b961ac93c01813ca6ea9e702b644
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301133"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="a39b4-105">フロントエンド プールまたは Standard Edition サーバーの削除</span><span class="sxs-lookup"><span data-stu-id="a39b4-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="a39b4-106">この記事では、フロントエンドプールまたは標準エディションのフロントエンドサーバーを削除するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a39b4-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="a39b4-107">フロントエンドプールを削除する場合は、プールに属している各フロントエンドサーバーをプール削除プロセスの一部として削除します。</span><span class="sxs-lookup"><span data-stu-id="a39b4-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="a39b4-108">Standard Edition のフロントエンドサーバーを削除する場合は、トポロジビルダーから SQL ストアの定義を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a39b4-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="a39b4-109">フロントエンドサーバープールを削除するには</span><span class="sxs-lookup"><span data-stu-id="a39b4-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="a39b4-110">トポロジビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="a39b4-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="a39b4-111">従来のノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="a39b4-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="a39b4-112">**Enterprise Edition のフロントエンド**プールを展開し、フロントエンドプールを展開して、削除するフロントエンドプールを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a39b4-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="a39b4-113">トポロジを公開し、レプリケーションの状態を確認します。次に、必要に応じて従来の展開ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="a39b4-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="a39b4-114">Standard Edition フロントエンドサーバーを削除するには</span><span class="sxs-lookup"><span data-stu-id="a39b4-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="a39b4-115">トポロジビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="a39b4-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="a39b4-116">従来のインストールノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="a39b4-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="a39b4-117">**Standard Edition のフロントエンド**サーバーを展開し、削除するフロントエンドサーバーを右クリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a39b4-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="a39b4-118">[ **Sql ストア**] を展開し、Standard Edition フロントエンドサーバーに関連付けられている sql Server データベースを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a39b4-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a39b4-119">併置された SQL Server データベースの定義は、Standard Edition のフロントエンドサーバーから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a39b4-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="a39b4-120">トポロジを公開し、レプリケーションの状態を確認してから、必要に応じて展開ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="a39b4-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

