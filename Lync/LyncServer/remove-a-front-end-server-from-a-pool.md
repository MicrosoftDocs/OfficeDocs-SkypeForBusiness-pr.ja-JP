---
title: プールからのフロントエンド サーバーの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0637754c6e7b1a03c233025703297c182dc3099
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="29104-102">プールからのフロントエンド サーバーの削除</span><span class="sxs-lookup"><span data-stu-id="29104-102">Remove a Front End Server from a pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29104-103">_**最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="29104-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="29104-104">Microsoft Lync Server 2010 Enterprise Edition のフロントエンドサーバーは、スタンドアロンコンピューターとして存在することはできません。</span><span class="sxs-lookup"><span data-stu-id="29104-104">The Microsoft Lync Server 2010 Enterprise Edition Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="29104-105">プールに1台のコンピュータしかない場合でも、フロントエンドプールとして定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29104-105">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>

<span data-ttu-id="29104-106">このトピックでは、既存のフロントエンドプールから個々のフロントエンドサーバーを削除する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="29104-106">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="29104-107">フロントエンドサーバーがプール内の最後のサーバーである場合、またはプールを完全に削除する場合は、「[フロントエンドプールまたは Standard Edition サーバーを削除](remove-front-end-pool-or-standard-edition-server.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29104-107">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="29104-108">フロントエンドプールを削除する前に、個々のフロントエンドサーバーを削除する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="29104-108">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="29104-109">プールを削除すると、各フロントエンドサーバーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="29104-109">When you remove the pool, you remove each Front End Server.</span></span>

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="29104-110">プールからフロントエンドサーバーを削除するには</span><span class="sxs-lookup"><span data-stu-id="29104-110">To remove a Front End Server from a pool</span></span>

1.  <span data-ttu-id="29104-111">Lync Server 2013 フロントエンドサーバーを開き、[トポロジビルダー] を開きます。</span><span class="sxs-lookup"><span data-stu-id="29104-111">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="29104-112">Lync Server 2010 ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="29104-112">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="29104-113">[ **Enterprise Edition のフロントエンドプール**] を展開し、削除するフロントエンドサーバーでフロントエンドプールを展開して、削除するフロントエンドサーバーを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29104-113">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

