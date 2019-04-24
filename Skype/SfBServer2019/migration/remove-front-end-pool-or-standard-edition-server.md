---
title: フロントエンド プールまたは Standard Edition サーバーの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: このトピックでは、フロント エンド プールまたはサーバーを標準的な版フロント エンド サーバーを削除するプロセスについて説明します。 フロント エンド プールを削除すると、各フロント エンド サーバー プールの削除処理の一部として、プールに属しているを削除します。 標準 Edition フロント エンド サーバーを削除すると、トポロジ ビルダーで SQL ストアの定義を削除する必要があります。
ms.openlocfilehash: 394edcd6f5c89478ed98abebe0be29720d009107
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231547"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="81f8b-105">フロントエンド プールまたは Standard Edition サーバーの削除</span><span class="sxs-lookup"><span data-stu-id="81f8b-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="81f8b-106">この資料では、フロント エンド プールまたはサーバーを標準的な版フロント エンド サーバーを削除するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="81f8b-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="81f8b-107">フロント エンド プールを削除すると、各フロント エンド サーバー プールの削除処理の一部として、プールに属しているを削除します。</span><span class="sxs-lookup"><span data-stu-id="81f8b-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="81f8b-108">標準 Edition フロント エンド サーバーを削除すると、トポロジ ビルダーで SQL ストアの定義を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81f8b-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="81f8b-109">フロント エンド サーバー プールを削除するには</span><span class="sxs-lookup"><span data-stu-id="81f8b-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="81f8b-110">トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="81f8b-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="81f8b-111">従来のノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="81f8b-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="81f8b-112">**エンタープライズ エディションのフロント エンド プール**] を展開フロント エンド プールを展開しを削除するには、フロント エンド プールを右クリックし、し、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81f8b-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="81f8b-113">トポロジを公開、レプリケーション ・ ステータスを確認、必要に応じて、従来の展開ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="81f8b-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="81f8b-114">標準のエディションのフロント エンド サーバーを削除するには</span><span class="sxs-lookup"><span data-stu-id="81f8b-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="81f8b-115">トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="81f8b-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="81f8b-116">バージョンのインストール] ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="81f8b-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="81f8b-117">**標準のエディションのフロント エンド サーバー**を展開を削除するには、フロント エンド サーバーを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81f8b-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="81f8b-118">**SQL ストア**を展開し、標準のエディションのフロント エンド サーバーに関連付けられている SQL Server データベースを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81f8b-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="81f8b-119">標準のエディションのフロント エンド サーバーから配置されている SQL Server データベースの定義を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81f8b-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="81f8b-120">トポロジを公開、レプリケーション ・ ステータスを確認し、必要に応じて、展開ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="81f8b-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

