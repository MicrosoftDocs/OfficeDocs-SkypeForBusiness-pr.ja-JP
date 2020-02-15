---
title: 'Lync Server 2013: アーカイブの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server 2013 Archiving
ms:assetid: 48c6cc8c-c2c1-4534-9a8a-fd5eb738076a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520990(v=OCS.15)
ms:contentKeyID: 48184003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16c9b901575e844954b9dd3454c4ecc7c86e7c3b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-archiving"></a><span data-ttu-id="928ca-102">Lync Server 2013 アーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="928ca-102">Managing Lync Server 2013 Archiving</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="928ca-103">_**トピックの最終更新日:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="928ca-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="928ca-104">組織のアーカイブを展開するときは、展開時に初期構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="928ca-104">When you deploy Archiving for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="928ca-105">ただし、日常の管理のためのアーカイブサポートの実装方法を変更したり、組織の新しい要件を満たす必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="928ca-105">However, there may be times when you want to change how you implement archiving support for day-to-day management or to meet new requirements in your organization.</span></span> <span data-ttu-id="928ca-106">たとえば、組織内の特定のサイト、プール、またはユーザーについて、アーカイブサポートを異なる方法で設定する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="928ca-106">For example, you may need to set up archiving support differently for a specific site, pool, or users within your organization.</span></span> <span data-ttu-id="928ca-107">Lync Server 2013 に所属するユーザーは、アーカイブポリシーと構成を作成してカスタマイズすることになります。</span><span class="sxs-lookup"><span data-stu-id="928ca-107">For users homed on Lync Server 2013, you do this be creating and customizing archiving policies and configurations.</span></span> <span data-ttu-id="928ca-108">Microsoft Exchange 統合を使用する場合は、Exchange 2013 設定も構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="928ca-108">If you use Microsoft Exchange integration, you must also configure Exchange 2013 settings.</span></span> <span data-ttu-id="928ca-109">このセクションでは、アーカイブ展開を変更できるようにするための情報と手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="928ca-109">This section provides information and procedures to enable you to make changes to your Archiving deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="928ca-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="928ca-110">In This Section</span></span>

  - [<span data-ttu-id="928ca-111">Lync Server 2013 でのアーカイブのしくみ</span><span class="sxs-lookup"><span data-stu-id="928ca-111">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="928ca-112">Lync Server 2013 での内部および外部通信のアーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="928ca-112">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

  - [<span data-ttu-id="928ca-113">組織、サイト、およびプールの Lync Server 2013 でのアーカイブ構成オプションの管理</span><span class="sxs-lookup"><span data-stu-id="928ca-113">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

  - [<span data-ttu-id="928ca-114">Lync Server 2013 でのアーカイブデータベースオプションの変更</span><span class="sxs-lookup"><span data-stu-id="928ca-114">Changing Archiving database options in Lync Server 2013</span></span>](lync-server-2013-changing-archiving-database-options.md)

  - [<span data-ttu-id="928ca-115">Lync Server 2013 からのアーカイブされたデータのエクスポート</span><span class="sxs-lookup"><span data-stu-id="928ca-115">Exporting archived data from Lync Server 2013</span></span>](lync-server-2013-exporting-archived-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

