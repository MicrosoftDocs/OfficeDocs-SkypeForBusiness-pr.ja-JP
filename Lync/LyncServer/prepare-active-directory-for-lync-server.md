---
title: Lync Server の Active Directory の準備
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Prepare Active Directory for Lync Server
ms:assetid: 54cd597d-0c2d-479c-8c52-1babc53f71dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688059(v=OCS.15)
ms:contentKeyID: 49733653
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ff5be6fbf3849c51979f3cf94dbc36d14e5b282
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prepare-active-directory-for-lync-server"></a><span data-ttu-id="2c309-102">Lync Server の Active Directory の準備</span><span class="sxs-lookup"><span data-stu-id="2c309-102">Prepare Active Directory for Lync Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c309-103">_**最終更新日:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="2c309-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="2c309-104">Lync server 2013 を共存2010状態で展開する前に、lync Server 2013 のスキーマ、フォレスト、ドメインを構成するために、追加の Active Directory タスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c309-104">Prior to deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you must perform some additional Active Directory tasks to configure the schema, forest, and domain for Lync Server 2013.</span></span> <span data-ttu-id="2c309-105">スキーマの拡張機能によって、Lync Server 2013 で必要な Active Directory のクラスと属性が追加されます。</span><span class="sxs-lookup"><span data-stu-id="2c309-105">The schema extensions add the Active Directory classes and attributes that are required by Lync Server 2013.</span></span> <span data-ttu-id="2c309-106">詳細については、「 [Lync Server 2013 用の Active Directory ドメインサービスの準備](lync-server-2013-preparing-active-directory-domain-services.md)」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c309-106">For additional information, see the topic [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

<span data-ttu-id="2c309-107">**Lync Server 2013 用に Active Directory を準備するには**</span><span class="sxs-lookup"><span data-stu-id="2c309-107">**To prepare Active Directory for Lync Server 2013**</span></span>

1.  <span data-ttu-id="2c309-108">Lync Server 2013 フロントエンドサーバーで、Lync Server 2013 のセットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="2c309-108">On the Lync Server 2013 Front End Server, run Lync Server 2013 Setup.</span></span>

2.  <span data-ttu-id="2c309-109">[ **Active Directory の準備**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2c309-109">Select **Prepare Active Directory**.</span></span>
    
    <span data-ttu-id="2c309-110">![Lync Server 2013 展開ウィザードの [ようこそ] ページ](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Lync Server 2013 展開ウィザードの [ようこそ] ページ")</span><span class="sxs-lookup"><span data-stu-id="2c309-110">![Lync Server 2013 Deployment Wizard, Welcome page](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Lync Server 2013 Deployment Wizard, Welcome page")</span></span>

3.  <span data-ttu-id="2c309-111">手順1から5を実行します。</span><span class="sxs-lookup"><span data-stu-id="2c309-111">Complete steps 1 through 5.</span></span>
    
    <span data-ttu-id="2c309-112">![展開ウィザードの [Active Directory]](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "展開ウィザードの [Active Directory]")</span><span class="sxs-lookup"><span data-stu-id="2c309-112">![Deployment Wizard, Active Directory Prearation](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "Deployment Wizard, Active Directory Prearation")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

