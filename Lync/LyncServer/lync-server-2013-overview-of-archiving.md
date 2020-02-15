---
title: 'Lync Server 2013: アーカイブの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Archiving
ms:assetid: 1e3c2ef1-f561-4f57-8b6a-7d78addc1ed1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204729(v=OCS.15)
ms:contentKeyID: 48183570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe615b0bf434b0c87a452a35528aa565c85fe5d0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-archiving-in-lync-server-2013"></a><span data-ttu-id="4ddb8-102">Lync Server 2013 でのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="4ddb8-102">Overview of Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ddb8-103">_**トピックの最終更新日:** 2013-09-30_</span><span class="sxs-lookup"><span data-stu-id="4ddb8-103">_**Topic Last Modified:** 2013-09-30_</span></span>

<span data-ttu-id="4ddb8-104">Lync Server 2013 のアーカイブを使用すると、Lync Server 2013 経由で送信される通信をアーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="4ddb8-104">Archiving in Lync Server 2013 provides a way for you to archive communications that are sent through Lync Server 2013.</span></span>

<span data-ttu-id="4ddb8-105">最初の Lync Server 2013 展開の一部としてアーカイブを実装することも、既存の展開に追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="4ddb8-105">You can implement Archiving as part of your initial Lync Server 2013 deployment, or you can add it to an existing deployment.</span></span> <span data-ttu-id="4ddb8-106">Lync Server 2013 アーカイブデータベース (SQL Server データベース) をアーカイブデータの格納に使用するには、トポロジビルダーを使用してデータベースをトポロジに追加した後、トポロジを再度発行します。</span><span class="sxs-lookup"><span data-stu-id="4ddb8-106">To use Lync Server 2013 Archiving databases (SQL Server databases) for storage of archiving data, you use Topology Builder to add the databases to your topology, and then publish the topology again.</span></span> <span data-ttu-id="4ddb8-107">すべてのユーザーが Exchange 2013 に所属しており、メールボックスがインプレース保持に配置されている場合は、トポロジを更新する必要はありませんが、アーカイブされたデータを Exchange 2013 に保存するために Microsoft Exchange 統合を有効にするだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="4ddb8-107">If all your users are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, you do not have to update your topology, but only need to enable Microsoft Exchange integration to store archived data in Exchange 2013.</span></span>

<span data-ttu-id="4ddb8-108">アーカイブを実装するときは、アーカイブを構成して処理の対象を指定します。</span><span class="sxs-lookup"><span data-stu-id="4ddb8-108">When you implement Archiving, you configure it to specify what is archived.</span></span> <span data-ttu-id="4ddb8-109">既定では、何もアーカイブされません。</span><span class="sxs-lookup"><span data-stu-id="4ddb8-109">By default, nothing is archived.</span></span> <span data-ttu-id="4ddb8-110">Lync Server 2013 コントロールパネルを使用して、アーカイブを構成および管理します。</span><span class="sxs-lookup"><span data-stu-id="4ddb8-110">You configure and manage Archiving by using Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="4ddb8-111">アーカイブは、内部通信、外部通信、またはその両方に対して実装できます。</span><span class="sxs-lookup"><span data-stu-id="4ddb8-111">You can implement Archiving for internal communications, external communications, or both.</span></span> <span data-ttu-id="4ddb8-112">アーカイブ設定は、組織全体と、必要に応じて特定のサイト、特定のプール、および特定のユーザーとユーザー グループに対して構成できます。</span><span class="sxs-lookup"><span data-stu-id="4ddb8-112">You can configure archiving settings your entire organization and, optionally, for specific sites, specific pools, and specific users and user groups.</span></span> <span data-ttu-id="4ddb8-113">組織に適したオプションの決定の詳細については、「計画」のドキュメントの「 [Lync Server 2013 でのアーカイブの要件の定義](lync-server-2013-defining-your-requirements-for-archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ddb8-113">For details about determining the appropriate options for your organization, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) in the Planning documentation.</span></span> <span data-ttu-id="4ddb8-114">アーカイブポリシーと構成の実装方法、およびアーカイブすることができる情報とアーカイブできない情報の詳細については、「計画」、「展開」、または「操作」のドキュメントの「 [Lync Server 2013 でのアーカイブの仕組み](lync-server-2013-how-archiving-works.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ddb8-114">For details about how Archiving policies and configurations are implemented, and details about what information can or cannot be archived, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

