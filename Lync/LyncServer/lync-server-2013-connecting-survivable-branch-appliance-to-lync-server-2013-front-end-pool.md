---
title: Lync Server 2013 のフロントエンド プールへの存続可能ブランチ アプライアンスの接続
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
ms.openlocfilehash: d23b501738010a8e5e5ed1c5c2e9a8608b0709e4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a><span data-ttu-id="cb80d-102">Lync Server 2013 のフロントエンド プールへの存続可能ブランチ アプライアンスの接続</span><span class="sxs-lookup"><span data-stu-id="cb80d-102">Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb80d-103">_**トピックの最終更新日:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="cb80d-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="cb80d-104">すべての存続可能 Branch Appliance (SBA) は、SBA のバックアップレジストラーとして機能するフロントエンドプールに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="cb80d-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool, which serves as a backup Registrar for the SBA.</span></span> <span data-ttu-id="cb80d-105">フロントエンドプールが Lync Server 2013 にアップグレードされた場合、フロントエンドプールがアップグレードされている間は、フロントエンドプールとの関連付けを解除する必要があります。 SBA</span><span class="sxs-lookup"><span data-stu-id="cb80d-105">When the Front End pool is upgraded to Lync Server 2013, the SBA must be disassociated from the Front End pool while the Front End pool is upgraded.</span></span> <span data-ttu-id="cb80d-106">フロントエンドプールをアップグレードした後は、フロントエンドプールを使用して SBA を reassociated ことができます。</span><span class="sxs-lookup"><span data-stu-id="cb80d-106">After the Front End pool is upgraded, the SBA can be reassociated with the Front End pool.</span></span> <span data-ttu-id="cb80d-107">これには、トポロジ ビルダーのトポロジから SBA を削除し、再度 SBA をトポロジ ビルダーに追加する作業が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cb80d-107">This involves deleting the SBA from the topology in Topology Builder and then adding the SBA, again, to Topology Builder.</span></span> <span data-ttu-id="cb80d-108">トポロジから SBA を削除する前に、SBA に所属するユーザーを別のフロントエンドプールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb80d-108">Users homed on the SBA must be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="cb80d-109">SBA をトポロジに戻したら、これらのユーザーは SBA に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="cb80d-109">After the SBA is added back to the topology, those users can be moved back to the SBA.</span></span>

<span data-ttu-id="cb80d-110">これらの手順の概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cb80d-110">These steps are summarized below:</span></span>

1.  <span data-ttu-id="cb80d-111">SBA に所属するブランチユーザーを別のフロントエンドプールに移動します。</span><span class="sxs-lookup"><span data-stu-id="cb80d-111">Move branch users homed on SBA to another Front End pool.</span></span>

2.  <span data-ttu-id="cb80d-112">既存のフロントエンドプールとバックアップレジストラーの関連付けを解除するには、SBA をトポロジから削除します。</span><span class="sxs-lookup"><span data-stu-id="cb80d-112">Remove SBA from your topology to disassociate the existing Front End pool as the backup Registrar.</span></span>

3.  <span data-ttu-id="cb80d-113">フロントエンドプールを Microsoft Lync Server 2013 にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="cb80d-113">Upgrade Front End pool to Microsoft Lync Server 2013.</span></span>

4.  <span data-ttu-id="cb80d-114">SBA をトポロジに追加します。</span><span class="sxs-lookup"><span data-stu-id="cb80d-114">Add SBA back into your topology.</span></span>

5.  <span data-ttu-id="cb80d-115">新しいフロントエンドプールをバックアップレジストラーとして SBA に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="cb80d-115">Associate the new Front End pool to the SBA as a backup Registrar.</span></span>

6.  <span data-ttu-id="cb80d-116">ブランチ ユーザーを SBA に移動します。</span><span class="sxs-lookup"><span data-stu-id="cb80d-116">Move branch users back to the SBA.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cb80d-117">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="cb80d-117">In This Section</span></span>

  - [<span data-ttu-id="cb80d-118">Lync Server 2013 存続可能 Branch Appliance ブランチサイトをトポロジに追加する</span><span class="sxs-lookup"><span data-stu-id="cb80d-118">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [<span data-ttu-id="cb80d-119">Lync Server 2010 存続可能 Branch Appliance ブランチサイトをトポロジに追加する</span><span class="sxs-lookup"><span data-stu-id="cb80d-119">Add Lync Server 2010 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

