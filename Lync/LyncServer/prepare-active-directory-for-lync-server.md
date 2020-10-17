---
title: Lync Server の Active Directory の準備
description: Lync Server の Active Directory を準備します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prepare Active Directory for Lync Server
ms:assetid: 54cd597d-0c2d-479c-8c52-1babc53f71dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688059(v=OCS.15)
ms:contentKeyID: 49733653
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff9ff2de825d68f2c7ca9d90cbecdf71e5d00d55
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563703"
---
# <a name="prepare-active-directory-for-lync-server"></a><span data-ttu-id="10c91-103">Lync Server の Active Directory の準備</span><span class="sxs-lookup"><span data-stu-id="10c91-103">Prepare Active Directory for Lync Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10c91-104">_**トピックの最終更新日:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="10c91-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="10c91-105">Lync server 2010 で Lync Server 2013 を共存状態に展開する前に、追加の Active Directory タスクを実行して、Lync Server 2013 のスキーマ、フォレスト、およびドメインを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10c91-105">Prior to deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you must perform some additional Active Directory tasks to configure the schema, forest, and domain for Lync Server 2013.</span></span> <span data-ttu-id="10c91-106">スキーマ拡張機能によって、Lync Server 2013 で必要な Active Directory クラスと属性が追加されます。</span><span class="sxs-lookup"><span data-stu-id="10c91-106">The schema extensions add the Active Directory classes and attributes that are required by Lync Server 2013.</span></span> <span data-ttu-id="10c91-107">詳細については、「 [Lync Server 2013 用の Active Directory ドメインサービスの準備](lync-server-2013-preparing-active-directory-domain-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10c91-107">For additional information, see the topic [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

<span data-ttu-id="10c91-108">**Lync Server 2013 の Active Directory を準備するには**</span><span class="sxs-lookup"><span data-stu-id="10c91-108">**To prepare Active Directory for Lync Server 2013**</span></span>

1.  <span data-ttu-id="10c91-109">Lync Server 2013 フロントエンドサーバーで、Lync Server 2013 セットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="10c91-109">On the Lync Server 2013 Front End Server, run Lync Server 2013 Setup.</span></span>

2.  <span data-ttu-id="10c91-110">[**Active Directory の準備**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="10c91-110">Select **Prepare Active Directory**.</span></span>
    
    <span data-ttu-id="10c91-111">![Lync Server 2013 展開ウィザード、ウェルカムページ](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Lync Server 2013 展開ウィザード、ウェルカムページ")</span><span class="sxs-lookup"><span data-stu-id="10c91-111">![Lync Server 2013 Deployment Wizard, Welcome page](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Lync Server 2013 Deployment Wizard, Welcome page")</span></span>

3.  <span data-ttu-id="10c91-112">手順 1 ～ 5 を行います。</span><span class="sxs-lookup"><span data-stu-id="10c91-112">Complete steps 1 through 5.</span></span>
    
    <span data-ttu-id="10c91-113">![展開ウィザード、Active Directory](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "展開ウィザード、Active Directory")</span><span class="sxs-lookup"><span data-stu-id="10c91-113">![Deployment Wizard, Active Directory Prearation](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "Deployment Wizard, Active Directory Prearation")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

