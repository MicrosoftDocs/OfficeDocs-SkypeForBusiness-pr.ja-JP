---
title: Lync Server 2013 のフロント エンド プールへの存続可能ブランチ アプライアンスの接続
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d73806f481cfe7c44a5eb9507d043565765a08f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a><span data-ttu-id="d1bee-102">Lync Server 2013 のフロント エンド プールへの存続可能ブランチ アプライアンスの接続</span><span class="sxs-lookup"><span data-stu-id="d1bee-102">Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1bee-103">_**最終更新日:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="d1bee-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="d1bee-104">すべての Survivable Branch Appliance (SBA) は、SBA のバックアップレジストラーとして提供されるフロントエンドプールと関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="d1bee-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool, which serves as a backup Registrar for the SBA.</span></span> <span data-ttu-id="d1bee-105">フロントエンドプールが Lync Server 2013 にアップグレードされた場合、フロントエンドプールがアップグレードされている間、SBA はフロントエンドプールとの関連付けを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1bee-105">When the Front End pool is upgraded to Lync Server 2013, the SBA must be disassociated from the Front End pool while the Front End pool is upgraded.</span></span> <span data-ttu-id="d1bee-106">フロントエンドプールがアップグレードされた後は、フロントエンドプールを使用して SBA を reassociated できます。</span><span class="sxs-lookup"><span data-stu-id="d1bee-106">After the Front End pool is upgraded, the SBA can be reassociated with the Front End pool.</span></span> <span data-ttu-id="d1bee-107">これには、トポロジビルダーのトポロジから SBA を削除してから、もう一度 SBA をトポロジビルダーに追加することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d1bee-107">This involves deleting the SBA from the topology in Topology Builder and then adding the SBA, again, to Topology Builder.</span></span> <span data-ttu-id="d1bee-108">トポロジから SBA を削除する前に、SBA をホームにしているユーザーを別のフロントエンドプールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1bee-108">Users homed on the SBA must be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="d1bee-109">SBA がトポロジに戻された後、それらのユーザーを SBA に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="d1bee-109">After the SBA is added back to the topology, those users can be moved back to the SBA.</span></span>

<span data-ttu-id="d1bee-110">以下に、これらの手順の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="d1bee-110">These steps are summarized below:</span></span>

1.  <span data-ttu-id="d1bee-111">SBA に置かれているブランチユーザーを別のフロントエンドプールに移動します。</span><span class="sxs-lookup"><span data-stu-id="d1bee-111">Move branch users homed on SBA to another Front End pool.</span></span>

2.  <span data-ttu-id="d1bee-112">トポロジから SBA を削除して、既存のフロントエンドプールとバックアップレジストラーの関連付けを解除します。</span><span class="sxs-lookup"><span data-stu-id="d1bee-112">Remove SBA from your topology to disassociate the existing Front End pool as the backup Registrar.</span></span>

3.  <span data-ttu-id="d1bee-113">フロントエンドプールを Microsoft Lync Server 2013 にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="d1bee-113">Upgrade Front End pool to Microsoft Lync Server 2013.</span></span>

4.  <span data-ttu-id="d1bee-114">SBA をトポロジに追加し直します。</span><span class="sxs-lookup"><span data-stu-id="d1bee-114">Add SBA back into your topology.</span></span>

5.  <span data-ttu-id="d1bee-115">新しいフロントエンドプールをバックアップレジストラーとして SBA に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="d1bee-115">Associate the new Front End pool to the SBA as a backup Registrar.</span></span>

6.  <span data-ttu-id="d1bee-116">ブランチユーザーを SBA に戻します。</span><span class="sxs-lookup"><span data-stu-id="d1bee-116">Move branch users back to the SBA.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d1bee-117">このセクション中</span><span class="sxs-lookup"><span data-stu-id="d1bee-117">In This Section</span></span>

  - [<span data-ttu-id="d1bee-118">トポロジへの Lync Server 2013 存続可能ブランチ アプライアンスのブランチ サイトの追加</span><span class="sxs-lookup"><span data-stu-id="d1bee-118">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [<span data-ttu-id="d1bee-119">トポロジへの Lync Server 2010 存続可能ブランチ アプライアンスのブランチ サイトの追加</span><span class="sxs-lookup"><span data-stu-id="d1bee-119">Add Lync Server 2010 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

