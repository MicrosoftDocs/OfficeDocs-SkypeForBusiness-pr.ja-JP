---
title: フロントエンド プールまたは Standard Edition サーバーの削除
description: フロントエンドプールまたは Standard Edition サーバーを削除します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c878d56b073558f4f4b50f31b6742fd581c80241
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570243"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="f0489-103">フロントエンド プールまたは Standard Edition サーバーの削除</span><span class="sxs-lookup"><span data-stu-id="f0489-103">Remove Front End pool or Standard Edition server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0489-104">_**トピックの最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="f0489-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="f0489-105">このトピックでは、フロントエンドプールまたは Standard Edition フロントエンドサーバーを削除するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f0489-105">This topic guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="f0489-106">フロントエンドプールを削除する場合は、プール削除処理の一部として、そのプールに属する各フロントエンドサーバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="f0489-106">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="f0489-107">Standard Edition フロントエンドサーバーを削除する場合は、トポロジビルダーから SQL ストア定義を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0489-107">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>

<div>

## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="f0489-108">フロントエンド サーバー プールを削除するには</span><span class="sxs-lookup"><span data-stu-id="f0489-108">To remove a Front End Server pool</span></span>

1.  <span data-ttu-id="f0489-109">トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="f0489-109">Open Topology Builder.</span></span>

2.  <span data-ttu-id="f0489-110">[Lync Server 2010 ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="f0489-110">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="f0489-111">[ **Enterprise Edition フロントエンド**プール] を展開し、フロントエンドプールを展開して、削除するフロントエンドプールを右クリックし、[ **削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0489-111">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="f0489-112">トポロジを公開し、レプリケーションの状態を確認してから、必要に応じて Lync Server 展開ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0489-112">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="f0489-113">Standard Edition フロントエンド サーバーを削除するには</span><span class="sxs-lookup"><span data-stu-id="f0489-113">To remove a Standard Edition Front End server</span></span>

1.  <span data-ttu-id="f0489-114">トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="f0489-114">Open Topology Builder.</span></span>

2.  <span data-ttu-id="f0489-115">[Lync Server 2010 ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="f0489-115">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="f0489-116">[ **Standard Edition フロントエンドサーバー**] を展開し、削除するフロントエンドサーバーを右クリックして、[ **削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0489-116">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="f0489-117">[ **Sql ストア**] を展開し、Standard Edition フロントエンドサーバーに関連付けられている sql Server データベースを右クリックし、[ **削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0489-117">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f0489-118">併置された SQL Server データベースの定義は、Standard Edition フロントエンドサーバーから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0489-118">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="f0489-119">トポロジを公開し、レプリケーションの状態を確認してから、必要に応じて Lync Server 展開ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0489-119">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

