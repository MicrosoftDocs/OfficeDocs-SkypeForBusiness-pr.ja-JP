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
ms.openlocfilehash: f718ac939fc665c0464d4986f51279d3afdee8a3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-archiving-in-lync-server-2013"></a><span data-ttu-id="00d7e-102">Lync Server 2013 のアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="00d7e-102">Overview of Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00d7e-103">_**最終更新日:** 2013-09-30_</span><span class="sxs-lookup"><span data-stu-id="00d7e-103">_**Topic Last Modified:** 2013-09-30_</span></span>

<span data-ttu-id="00d7e-104">Lync server 2013 でのアーカイブは、Lync Server 2013 経由で送信された通信をアーカイブするための手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="00d7e-104">Archiving in Lync Server 2013 provides a way for you to archive communications that are sent through Lync Server 2013.</span></span>

<span data-ttu-id="00d7e-105">最初の Lync Server 2013 の展開の一部としてアーカイブを実装することも、既存の展開に追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="00d7e-105">You can implement Archiving as part of your initial Lync Server 2013 deployment, or you can add it to an existing deployment.</span></span> <span data-ttu-id="00d7e-106">Lync Server 2013 アーカイブデータベース (SQL Server データベース) を使用してアーカイブデータを保存するには、トポロジビルダーを使用してデータベースをトポロジに追加してから、もう一度トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="00d7e-106">To use Lync Server 2013 Archiving databases (SQL Server databases) for storage of archiving data, you use Topology Builder to add the databases to your topology, and then publish the topology again.</span></span> <span data-ttu-id="00d7e-107">すべてのユーザーが Exchange 2013 を使用していて、メールボックスがインプレース保持されている場合、トポロジを更新する必要はありませんが、Microsoft Exchange の統合を有効にして、アーカイブされたデータを Exchange 2013 に保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00d7e-107">If all your users are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, you do not have to update your topology, but only need to enable Microsoft Exchange integration to store archived data in Exchange 2013.</span></span>

<span data-ttu-id="00d7e-108">アーカイブを実装するときに、アーカイブの内容を指定するように構成します。</span><span class="sxs-lookup"><span data-stu-id="00d7e-108">When you implement Archiving, you configure it to specify what is archived.</span></span> <span data-ttu-id="00d7e-109">既定では、何もアーカイブされません。</span><span class="sxs-lookup"><span data-stu-id="00d7e-109">By default, nothing is archived.</span></span> <span data-ttu-id="00d7e-110">アーカイブの構成と管理は、Lync Server 2013 コントロールパネルを使用して行います。</span><span class="sxs-lookup"><span data-stu-id="00d7e-110">You configure and manage Archiving by using Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="00d7e-111">内部通信、外部通信、またはその両方のアーカイブを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="00d7e-111">You can implement Archiving for internal communications, external communications, or both.</span></span> <span data-ttu-id="00d7e-112">組織全体のアーカイブ設定を構成することができます。また、必要に応じて、特定のサイト、特定のプール、特定のユーザーとユーザーグループのアーカイブ設定を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="00d7e-112">You can configure archiving settings your entire organization and, optionally, for specific sites, specific pools, and specific users and user groups.</span></span> <span data-ttu-id="00d7e-113">組織で適切なオプションを決定する方法の詳細については、計画ドキュメントの「 [Lync Server 2013 でアーカイブするための要件を定義](lync-server-2013-defining-your-requirements-for-archiving.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00d7e-113">For details about determining the appropriate options for your organization, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) in the Planning documentation.</span></span> <span data-ttu-id="00d7e-114">アーカイブポリシーと構成の実装方法、およびアーカイブできない情報の詳細については、計画ドキュメント、展開ドキュメント、または運用マニュアルの「 [Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00d7e-114">For details about how Archiving policies and configurations are implemented, and details about what information can or cannot be archived, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

