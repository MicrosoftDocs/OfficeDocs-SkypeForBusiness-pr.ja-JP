---
title: Lync Server 2013 のフロントエンド プールへの存続可能ブランチ アプライアンスの接続
description: 存続可能 Branch Appliance から Lync Server 2013 フロントエンドプールへの接続。
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
ms.openlocfilehash: 6ef917d3db6a1d653ac716d6c078e1df240fb31d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571663"
---
# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a><span data-ttu-id="65dc4-103">Lync Server 2013 のフロントエンド プールへの存続可能ブランチ アプライアンスの接続</span><span class="sxs-lookup"><span data-stu-id="65dc4-103">Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65dc4-104">_**トピックの最終更新日:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="65dc4-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="65dc4-105">すべての存続可能 Branch Appliance (SBA) は、SBA のバックアップレジストラーとして機能するフロントエンドプールに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="65dc4-105">Every Survivable Branch Appliance (SBA) is associated with a Front End pool, which serves as a backup Registrar for the SBA.</span></span> <span data-ttu-id="65dc4-106">フロントエンドプールが Lync Server 2013 にアップグレードされた場合、フロントエンドプールがアップグレードされている間は、フロントエンドプールとの関連付けを解除する必要があります。 SBA</span><span class="sxs-lookup"><span data-stu-id="65dc4-106">When the Front End pool is upgraded to Lync Server 2013, the SBA must be disassociated from the Front End pool while the Front End pool is upgraded.</span></span> <span data-ttu-id="65dc4-107">フロントエンドプールをアップグレードした後は、フロントエンドプールを使用して SBA を reassociated ことができます。</span><span class="sxs-lookup"><span data-stu-id="65dc4-107">After the Front End pool is upgraded, the SBA can be reassociated with the Front End pool.</span></span> <span data-ttu-id="65dc4-108">これには、トポロジ ビルダーのトポロジから SBA を削除し、再度 SBA をトポロジ ビルダーに追加する作業が含まれます。</span><span class="sxs-lookup"><span data-stu-id="65dc4-108">This involves deleting the SBA from the topology in Topology Builder and then adding the SBA, again, to Topology Builder.</span></span> <span data-ttu-id="65dc4-109">トポロジから SBA を削除する前に、SBA に所属するユーザーを別のフロントエンドプールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65dc4-109">Users homed on the SBA must be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="65dc4-110">SBA をトポロジに戻したら、これらのユーザーは SBA に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="65dc4-110">After the SBA is added back to the topology, those users can be moved back to the SBA.</span></span>

<span data-ttu-id="65dc4-111">これらの手順の概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="65dc4-111">These steps are summarized below:</span></span>

1.  <span data-ttu-id="65dc4-112">SBA に所属するブランチユーザーを別のフロントエンドプールに移動します。</span><span class="sxs-lookup"><span data-stu-id="65dc4-112">Move branch users homed on SBA to another Front End pool.</span></span>

2.  <span data-ttu-id="65dc4-113">既存のフロントエンドプールとバックアップレジストラーの関連付けを解除するには、SBA をトポロジから削除します。</span><span class="sxs-lookup"><span data-stu-id="65dc4-113">Remove SBA from your topology to disassociate the existing Front End pool as the backup Registrar.</span></span>

3.  <span data-ttu-id="65dc4-114">フロントエンドプールを Microsoft Lync Server 2013 にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="65dc4-114">Upgrade Front End pool to Microsoft Lync Server 2013.</span></span>

4.  <span data-ttu-id="65dc4-115">SBA をトポロジに追加します。</span><span class="sxs-lookup"><span data-stu-id="65dc4-115">Add SBA back into your topology.</span></span>

5.  <span data-ttu-id="65dc4-116">新しいフロントエンドプールをバックアップレジストラーとして SBA に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="65dc4-116">Associate the new Front End pool to the SBA as a backup Registrar.</span></span>

6.  <span data-ttu-id="65dc4-117">ブランチ ユーザーを SBA に移動します。</span><span class="sxs-lookup"><span data-stu-id="65dc4-117">Move branch users back to the SBA.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="65dc4-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="65dc4-118">In This Section</span></span>

  - [<span data-ttu-id="65dc4-119">Lync Server 2013 存続可能 Branch Appliance ブランチサイトをトポロジに追加する</span><span class="sxs-lookup"><span data-stu-id="65dc4-119">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [<span data-ttu-id="65dc4-120">Lync Server 2010 存続可能 Branch Appliance ブランチサイトをトポロジに追加する</span><span class="sxs-lookup"><span data-stu-id="65dc4-120">Add Lync Server 2010 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

