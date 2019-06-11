---
title: フロントエンド プールまたは Standard Edition サーバーの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5a3b08d6e8b4f0b792063b19a47889de11283c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847962"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="9be6a-102">フロントエンド プールまたは Standard Edition サーバーの削除</span><span class="sxs-lookup"><span data-stu-id="9be6a-102">Remove Front End pool or Standard Edition server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9be6a-103">_**最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="9be6a-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="9be6a-104">このトピックでは、フロントエンドプールまたは標準エディションのフロントエンドサーバーを削除する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="9be6a-104">This topic guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="9be6a-105">フロントエンドプールを削除する場合は、プールに属している各フロントエンドサーバーをプール削除プロセスの一部として削除します。</span><span class="sxs-lookup"><span data-stu-id="9be6a-105">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="9be6a-106">Standard Edition のフロントエンドサーバーを削除する場合は、トポロジビルダーから SQL ストアの定義を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9be6a-106">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>

<div>

## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="9be6a-107">フロントエンドサーバープールを削除するには</span><span class="sxs-lookup"><span data-stu-id="9be6a-107">To remove a Front End Server pool</span></span>

1.  <span data-ttu-id="9be6a-108">トポロジビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="9be6a-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="9be6a-109">Lync Server 2010 ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="9be6a-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="9be6a-110">**Enterprise Edition のフロントエンド**プールを展開し、フロントエンドプールを展開して、削除するフロントエンドプールを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9be6a-110">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="9be6a-111">トポロジを公開し、レプリケーションの状態を確認してから、必要に応じて Lync Server 展開ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="9be6a-111">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="9be6a-112">Standard Edition フロントエンドサーバーを削除するには</span><span class="sxs-lookup"><span data-stu-id="9be6a-112">To remove a Standard Edition Front End server</span></span>

1.  <span data-ttu-id="9be6a-113">トポロジビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="9be6a-113">Open Topology Builder.</span></span>

2.  <span data-ttu-id="9be6a-114">Lync Server 2010 ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="9be6a-114">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="9be6a-115">**Standard Edition のフロントエンド**サーバーを展開し、削除するフロントエンドサーバーを右クリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9be6a-115">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="9be6a-116">[ **Sql ストア**] を展開し、Standard Edition フロントエンドサーバーに関連付けられている sql Server データベースを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9be6a-116">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9be6a-117">併置された SQL Server データベースの定義は、Standard Edition のフロントエンドサーバーから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9be6a-117">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="9be6a-118">トポロジを公開し、レプリケーションの状態を確認してから、必要に応じて Lync Server 展開ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="9be6a-118">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

