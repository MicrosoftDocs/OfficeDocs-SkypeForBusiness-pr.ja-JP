---
title: 'Lync Server 2013: 応答グループに対してサポートされるクライアント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Clients supported for Response Group
ms:assetid: 84911025-e754-41a8-ba48-e31c058fc557
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398674(v=OCS.15)
ms:contentKeyID: 48184705
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df73091da5c71451940362600a345ff2b2b96c7a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="clients-supported-for-response-group-in-lync-server-2013"></a><span data-ttu-id="53782-102">Lync Server 2013 の応答グループに対してサポートされているクライアント</span><span class="sxs-lookup"><span data-stu-id="53782-102">Clients supported for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53782-103">_**トピックの最終更新日:** 2014-03-28_</span><span class="sxs-lookup"><span data-stu-id="53782-103">_**Topic Last Modified:** 2014-03-28_</span></span>

<span data-ttu-id="53782-104">応答グループアプリケーションは、次のクライアントをサポートします。</span><span class="sxs-lookup"><span data-stu-id="53782-104">The Response Group application supports the following clients:</span></span>

  - <span data-ttu-id="53782-105">Lync 2013 デスクトップクライアント</span><span class="sxs-lookup"><span data-stu-id="53782-105">Lync 2013 desktop client</span></span>

  - <span data-ttu-id="53782-106">Lync 2010 デスクトップクライアント</span><span class="sxs-lookup"><span data-stu-id="53782-106">Lync 2010 desktop client</span></span>

  - <span data-ttu-id="53782-107">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="53782-107">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="53782-108">Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="53782-108">Office Communications Server 2007 R2 Attendant</span></span>

  - <span data-ttu-id="53782-109">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="53782-109">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="53782-110">応答グループアプリケーションは、Lync mobile クライアントではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="53782-110">The Response Group application is not supported on Lync mobile clients.</span></span>



</div>

<span data-ttu-id="53782-111">新機能の詳細については、「はじめに」のドキュメントの「 [Lync Server 2013 の新しい応答グループアプリケーション機能](lync-server-2013-new-response-group-application-features.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53782-111">For details about new features, see [New Response Group application features in Lync Server 2013](lync-server-2013-new-response-group-application-features.md) in the Getting Started documentation.</span></span>

<span data-ttu-id="53782-112">使用できる特定のクライアントは、応答グループのユーザーの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="53782-112">The specific client that you can use depends on the type of Response Group user that you are:</span></span>

  - <span data-ttu-id="53782-113">**発信者**は、先にリストされたクライアントのいずれかを使用するか、または公衆交換電話網 (PSTN) 経由で標準的な電話機を使用して、応答グループを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="53782-113">**Callers** can call a response group by using any of the clients listed previously, and by using a standard telephone over the public switched telephone network (PSTN).</span></span>

  - <span data-ttu-id="53782-114">**非公式のエージェント**(グループにサインインおよびサインアウトしないエージェント) は、アテンダント、lync、または lync Phone のエディションを使用して通話を受け付けることができます。</span><span class="sxs-lookup"><span data-stu-id="53782-114">**Informal agents** (agents who do not sign into and out of their groups to accept calls) can accept calls by using Attendant, Lync, or Lync Phone Edition.</span></span> <span data-ttu-id="53782-115">これらのクライアントの1つを使用して Lync Server 2013 にサインインすると、非公式のエージェントは自動的にグループにサインインします。</span><span class="sxs-lookup"><span data-stu-id="53782-115">Informal agents are automatically signed into their groups when they sign in to Lync Server 2013 by using one of these clients.</span></span>

  - <span data-ttu-id="53782-116">**正式なエージェント**(通話を受け入れるためにグループにサインインまたはログアウトする必要があるエージェント) は、Lync 2013 を使用して、メニュー項目からエージェントコンソールにアクセスするか、またはアテンダントを使用して Internet Explorer からエージェントコンソールに直接アクセスすることによって、呼び出しを受け付けることができます。</span><span class="sxs-lookup"><span data-stu-id="53782-116">**Formal agents** (agents who must sign into and out of their groups to accept calls) can accept calls by using Lync 2013 and accessing the agent console from the menu item, or by using Attendant and accessing the agent console directly from Internet Explorer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

