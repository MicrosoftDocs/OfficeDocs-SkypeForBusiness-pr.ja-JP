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
ms.openlocfilehash: b3bb7ecac5204fc42b44e919dbbab8e9b720acc7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738867"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-archiving"></a><span data-ttu-id="def84-102">Lync Server 2013 アーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="def84-102">Managing Lync Server 2013 Archiving</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="def84-103">_**最終更新日:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="def84-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="def84-104">組織のアーカイブを展開するときは、展開時に初期構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="def84-104">When you deploy Archiving for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="def84-105">ただし、日常的な管理のためのアーカイブサポートの実装方法を変更したり、組織の新しい要件を満たすことが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="def84-105">However, there may be times when you want to change how you implement archiving support for day-to-day management or to meet new requirements in your organization.</span></span> <span data-ttu-id="def84-106">たとえば、組織内の特定のサイト、プール、またはユーザーについて、アーカイブのサポートを設定する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="def84-106">For example, you may need to set up archiving support differently for a specific site, pool, or users within your organization.</span></span> <span data-ttu-id="def84-107">Lync Server 2013 を使用しているユーザーは、アーカイブポリシーと構成の作成とカスタマイズを行います。</span><span class="sxs-lookup"><span data-stu-id="def84-107">For users homed on Lync Server 2013, you do this be creating and customizing archiving policies and configurations.</span></span> <span data-ttu-id="def84-108">Microsoft Exchange 統合を使用している場合は、Exchange 2013 の設定も構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="def84-108">If you use Microsoft Exchange integration, you must also configure Exchange 2013 settings.</span></span> <span data-ttu-id="def84-109">このセクションでは、アーカイブの展開を変更できるようにするための情報と手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="def84-109">This section provides information and procedures to enable you to make changes to your Archiving deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="def84-110">このセクション中</span><span class="sxs-lookup"><span data-stu-id="def84-110">In This Section</span></span>

  - [<span data-ttu-id="def84-111">Lync Server 2013 でのアーカイブのしくみ</span><span class="sxs-lookup"><span data-stu-id="def84-111">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="def84-112">Lync Server 2013 での内部および外部通信のアーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="def84-112">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

  - [<span data-ttu-id="def84-113">組織、サイト、およびプールの Lync Server 2013 でアーカイブ構成オプションを管理する</span><span class="sxs-lookup"><span data-stu-id="def84-113">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

  - [<span data-ttu-id="def84-114">Lync Server 2013 でアーカイブデータベースのオプションを変更する</span><span class="sxs-lookup"><span data-stu-id="def84-114">Changing Archiving database options in Lync Server 2013</span></span>](lync-server-2013-changing-archiving-database-options.md)

  - [<span data-ttu-id="def84-115">Lync Server 2013 からアーカイブデータをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="def84-115">Exporting archived data from Lync Server 2013</span></span>](lync-server-2013-exporting-archived-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

