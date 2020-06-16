---
title: プールからのフロントエンド サーバーの削除
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ef9df56c094bb5d7a3972a7c062905cbc4a844a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="7f5f9-102">プールからのフロントエンド サーバーの削除</span><span class="sxs-lookup"><span data-stu-id="7f5f9-102">Remove a Front End Server from a pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f5f9-103">_**トピックの最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="7f5f9-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="7f5f9-104">Microsoft Lync Server 2010 Enterprise Edition フロントエンドサーバーは、スタンドアロンコンピューターとしては存在できません。</span><span class="sxs-lookup"><span data-stu-id="7f5f9-104">The Microsoft Lync Server 2010 Enterprise Edition Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="7f5f9-105">プール内にコンピューターが1台しかない場合でも、フロントエンドプールとして定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f5f9-105">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>

<span data-ttu-id="7f5f9-106">このトピックでは、既存のフロントエンドプールから個々のフロントエンドサーバーを削除するプロセスについて手順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="7f5f9-106">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="7f5f9-107">フロントエンドサーバーがプール内の最後のサーバーである場合、またはプールを完全に削除する場合は、「 [Remove Front end pool Or Standard Edition Server](remove-front-end-pool-or-standard-edition-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f5f9-107">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="7f5f9-108">フロントエンドプールを削除する前に、個々のフロントエンドサーバーを削除する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7f5f9-108">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="7f5f9-109">プールを削除すると、各フロントエンドサーバーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="7f5f9-109">When you remove the pool, you remove each Front End Server.</span></span>

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="7f5f9-110">フロントエンド サーバーをプールから削除するには</span><span class="sxs-lookup"><span data-stu-id="7f5f9-110">To remove a Front End Server from a pool</span></span>

1.  <span data-ttu-id="7f5f9-111">Lync Server 2013 フロントエンドサーバーを開き、トポロジビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="7f5f9-111">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="7f5f9-112">[Lync Server 2010 ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="7f5f9-112">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="7f5f9-113">[ **Enterprise Edition フロントエンドプール**] を展開し、削除するフロントエンドサーバーのフロントエンドプールを展開して、削除するフロントエンドサーバーを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7f5f9-113">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

