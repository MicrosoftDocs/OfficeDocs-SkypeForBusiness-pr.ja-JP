---
title: 'Lync Server 2013: 応答グループに対してサポートされるクライアント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Clients supported for Response Group
ms:assetid: 84911025-e754-41a8-ba48-e31c058fc557
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398674(v=OCS.15)
ms:contentKeyID: 48184705
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3da4701a2520f38bd6b4718f51f60342bd6685e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840547"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clients-supported-for-response-group-in-lync-server-2013"></a><span data-ttu-id="04b2d-102">Lync Server 2013 の応答グループに対してサポートされるクライアント</span><span class="sxs-lookup"><span data-stu-id="04b2d-102">Clients supported for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04b2d-103">_**最終更新日:** 2014-03-28_</span><span class="sxs-lookup"><span data-stu-id="04b2d-103">_**Topic Last Modified:** 2014-03-28_</span></span>

<span data-ttu-id="04b2d-104">応答グループのアプリケーションでは、次のクライアントがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="04b2d-104">The Response Group application supports the following clients:</span></span>

  - <span data-ttu-id="04b2d-105">Lync 2013 デスクトップクライアント</span><span class="sxs-lookup"><span data-stu-id="04b2d-105">Lync 2013 desktop client</span></span>

  - <span data-ttu-id="04b2d-106">Lync 2010 デスクトップクライアント</span><span class="sxs-lookup"><span data-stu-id="04b2d-106">Lync 2010 desktop client</span></span>

  - <span data-ttu-id="04b2d-107">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="04b2d-107">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="04b2d-108">Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="04b2d-108">Office Communications Server 2007 R2 Attendant</span></span>

  - <span data-ttu-id="04b2d-109">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="04b2d-109">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="04b2d-110">応答グループアプリケーションは、Lync モバイルクライアントではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="04b2d-110">The Response Group application is not supported on Lync mobile clients.</span></span>



</div>

<span data-ttu-id="04b2d-111">新機能の詳細については、「はじめに」のドキュメントで「 [Lync Server 2013 の新しい応答グループアプリケーションの機能](lync-server-2013-new-response-group-application-features.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04b2d-111">For details about new features, see [New Response Group application features in Lync Server 2013](lync-server-2013-new-response-group-application-features.md) in the Getting Started documentation.</span></span>

<span data-ttu-id="04b2d-112">使用できる特定のクライアントは、応答グループのユーザーの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="04b2d-112">The specific client that you can use depends on the type of Response Group user that you are:</span></span>

  - <span data-ttu-id="04b2d-113">**発信者**は、先にリストされたクライアントのいずれかを使用するか、または公衆交換電話網 (PSTN) 経由で標準的な電話機を使用して、応答グループを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="04b2d-113">**Callers** can call a response group by using any of the clients listed previously, and by using a standard telephone over the public switched telephone network (PSTN).</span></span>

  - <span data-ttu-id="04b2d-114">**非公式のエージェント**(通話を許可するためにグループにサインインまたはサインアウトしないエージェント) は、アテンダント、Lync、Lync Phone Edition を使用して通話を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="04b2d-114">**Informal agents** (agents who do not sign into and out of their groups to accept calls) can accept calls by using Attendant, Lync, or Lync Phone Edition.</span></span> <span data-ttu-id="04b2d-115">非公式のエージェントは、これらのクライアントのいずれかを使って Lync Server 2013 にサインインしたときに、自動的にグループにサインインされます。</span><span class="sxs-lookup"><span data-stu-id="04b2d-115">Informal agents are automatically signed into their groups when they sign in to Lync Server 2013 by using one of these clients.</span></span>

  - <span data-ttu-id="04b2d-116">**正式なエージェント**(通話を許可するには、グループにサインインまたはサインアウトする必要があるエージェント) は、Lync 2013 を使用して、メニュー項目からエージェントコンソールにアクセスするか、または応答を使用して、Internet Explorer から直接エージェントコンソールにアクセスすることで、通話を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="04b2d-116">**Formal agents** (agents who must sign into and out of their groups to accept calls) can accept calls by using Lync 2013 and accessing the agent console from the menu item, or by using Attendant and accessing the agent console directly from Internet Explorer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

