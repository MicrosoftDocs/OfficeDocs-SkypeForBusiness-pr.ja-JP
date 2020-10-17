---
title: 'Lync Server 2013: アーカイブオプションの構成'
description: 'Lync Server 2013: アーカイブオプションの構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205182(v=OCS.15)
ms:contentKeyID: 48185158
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99d57f016d76f9ae6a538ef28663a4b4c965b0a6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562523"
---
# <a name="configuring-archiving-options-in-lync-server-2013"></a><span data-ttu-id="2d33c-103">Lync Server 2013 でのアーカイブオプションの構成</span><span class="sxs-lookup"><span data-stu-id="2d33c-103">Configuring Archiving options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d33c-104">_**トピックの最終更新日:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="2d33c-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="2d33c-105">Lync Server 2013 コントロールパネルでは、アーカイブ構成を使用してアーカイブの実装方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d33c-105">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="2d33c-106">これには、次のアーカイブ構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2d33c-106">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="2d33c-107">Lync Server 2013 を展開するときに既定で作成されるグローバル構成。</span><span class="sxs-lookup"><span data-stu-id="2d33c-107">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="2d33c-108">特定のサイトまたはプールに対するアーカイブの実装方法を指定するために作成して使用できる、オプションのサイトレベルおよびプールレベルのポリシー。</span><span class="sxs-lookup"><span data-stu-id="2d33c-108">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="2d33c-109">アーカイブ構成は、最初はアーカイブの展開時に設定しますが、展開後に変更、追加、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="2d33c-109">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="2d33c-110">Lync Server 2013 コントロールパネルでは、**アーカイブおよび監視**グループの [**アーカイブ構成**] ページを使用して、グローバルレベル、サイトレベル、およびプールレベルで構成を管理できます。</span><span class="sxs-lookup"><span data-stu-id="2d33c-110">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="2d33c-111">指定できるオプションやアーカイブ構成の階層など、アーカイブ構成の実装方法の詳細については、「計画」のドキュメント、「展開」、または「操作」のドキュメントの「 [Lync Server 2013 でのアーカイブの仕組み](lync-server-2013-how-archiving-works.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d33c-111">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="2d33c-112">展開後に構成を管理する方法の詳細については、「操作」のドキュメントの「 [Lync Server 2013 での組織、サイト、およびプールのアーカイブ構成オプションの管理](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d33c-112">For details about how to manage configurations after deployment, see [Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2d33c-113">アーカイブを使用するには、アーカイブポリシーを構成して、内部通信、外部通信、または Lync Server 2013 に所属するユーザーの両方に対してアーカイブを有効にするかどうかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d33c-113">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="2d33c-114">既定では、アーカイブは内部通信および外部通信のどちらに対しても有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="2d33c-114">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="2d33c-115">ポリシーでアーカイブを有効にする前に、このセクションの説明に従って、展開に対して、また必要に応じて特定のサイトやプールに対して、適切なアーカイブ構成を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d33c-115">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="2d33c-116">アーカイブを有効にする方法の詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013 でのアーカイブポリシーの構成と割り当て</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d33c-116">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="2d33c-117">展開内のすべてのユーザーに対して Microsoft Exchange 統合を使用しない場合、アーカイブポリシーを構成して、内部通信、外部通信、またはその両方のアーカイブを有効にするかどうかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d33c-117">If you do not use Microsoft Exchange integration for all users in your deployment, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both.</span></span> <span data-ttu-id="2d33c-118">既定では、Lync Server 2013 アーカイブデータベースを使用するときに、データのアーカイブの内部通信または外部通信のどちらかのアーカイブが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="2d33c-118">By default, archiving is not enabled for either internal or external communications for archiving of data when using Lync Server 2013 Archiving databases.</span></span> <span data-ttu-id="2d33c-119">ポリシーでアーカイブを有効にする前に、このセクションの説明に従って、展開および必要に応じて特定のサイトやプールに対して適切なアーカイブ構成を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d33c-119">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="2d33c-120">Lync Server 2013 アーカイブデータベースで使用するアーカイブを有効にする方法の詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync server 2013 でのアーカイブポリシーの構成と割り当て</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d33c-120">For details about enabling Archiving for use with Lync Server 2013 Archiving databases, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2d33c-121">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2d33c-121">In This Section</span></span>

  - [<span data-ttu-id="2d33c-122">Lync Server 2013 のグローバルレベルでのアーカイブオプションの構成</span><span class="sxs-lookup"><span data-stu-id="2d33c-122">Configuring Archiving options at the global level in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [<span data-ttu-id="2d33c-123">Lync Server 2013 でのサイトのアーカイブオプションの構成</span><span class="sxs-lookup"><span data-stu-id="2d33c-123">Configuring Archiving options for a site in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [<span data-ttu-id="2d33c-124">Lync Server 2013 でのプールのアーカイブオプションの構成</span><span class="sxs-lookup"><span data-stu-id="2d33c-124">Configuring Archiving options for a pool in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

