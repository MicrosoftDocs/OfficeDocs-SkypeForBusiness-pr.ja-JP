---
title: 'Lync Server 2013: アーカイブオプションを構成する'
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
ms.openlocfilehash: 9aa49aceacbd5053ead1af6b881be87c74b2ea30
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734877"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-in-lync-server-2013"></a><span data-ttu-id="77650-102">Lync Server 2013 でアーカイブオプションを構成する</span><span class="sxs-lookup"><span data-stu-id="77650-102">Configuring Archiving options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77650-103">_**最終更新日:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="77650-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="77650-104">Lync Server 2013 コントロールパネルで、アーカイブの実装方法を指定するには、アーカイブ構成を使います。</span><span class="sxs-lookup"><span data-stu-id="77650-104">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="77650-105">これには、次のアーカイブ構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="77650-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="77650-106">Lync Server 2013 を展開するときに既定で作成されるグローバル構成。</span><span class="sxs-lookup"><span data-stu-id="77650-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="77650-107">作成および使用して、特定のサイトまたはプールに対するアーカイブの実装方法を指定することができる、オプションのサイトレベルとプールレベルの構成。</span><span class="sxs-lookup"><span data-stu-id="77650-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="77650-108">アーカイブの展開時にアーカイブ構成を最初に設定しましたが、展開後に構成の変更、追加、削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="77650-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="77650-109">Lync Server 2013 コントロールパネルで、[**アーカイブと監視**] グループの [**アーカイブの構成**] ページを使用して、グローバルレベル、サイトレベル、プールレベルで構成を管理できます。</span><span class="sxs-lookup"><span data-stu-id="77650-109">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="77650-110">アーカイブ構成の実装方法について詳しくは、「指定できるオプションやアーカイブ構成の階層」をご覧ください。「計画ドキュメント、展開ドキュメント、または操作のドキュメントでの[Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77650-110">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="77650-111">展開後に構成を管理する方法について詳しくは、「 [Lync Server 2013 でアーカイブ構成オプションを管理](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)する」を参照してください。この操作については、「運用ドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77650-111">For details about how to manage configurations after deployment, see [Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77650-112">アーカイブを使用するには、内部通信のアーカイブを有効にするか、外部通信を有効にするか、または Lync Server 2013 を使用しているユーザーに対してアーカイブを有効にするかを指定するようにアーカイブポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77650-112">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="77650-113">既定では、内部または外部の通信でアーカイブは有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="77650-113">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="77650-114">すべてのポリシーでアーカイブを有効にする前に、このセクションで説明するように、展開に適したアーカイブ構成を指定し、必要に応じて特定のサイトとプールを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77650-114">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="77650-115">アーカイブを有効にする方法の詳細については、展開ドキュメントの「 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013 でアーカイブポリシーを構成して割り当てる</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77650-115">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="77650-116">展開内のすべてのユーザーに対して Microsoft Exchange の統合を使用しない場合は、内部通信のアーカイブを有効にするか、外部通信を有効にするか、または両方を有効にするかを指定するようにアーカイブポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77650-116">If you do not use Microsoft Exchange integration for all users in your deployment, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both.</span></span> <span data-ttu-id="77650-117">既定では、Lync Server 2013 アーカイブデータベースを使用しているときに、データをアーカイブするための内部通信または外部通信は、アーカイブが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="77650-117">By default, archiving is not enabled for either internal or external communications for archiving of data when using Lync Server 2013 Archiving databases.</span></span> <span data-ttu-id="77650-118">すべてのポリシーでアーカイブを有効にする前に、このセクションで説明するように、展開用に適切なアーカイブ構成を指定し、必要に応じて特定のサイトとプールを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77650-118">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="77650-119">Lync Server 2013 アーカイブデータベースで使用するためのアーカイブを有効にする方法について詳しくは、「展開ドキュメントの<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013 でのアーカイブポリシーの構成と割り当て</A>」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="77650-119">For details about enabling Archiving for use with Lync Server 2013 Archiving databases, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="77650-120">このセクション中</span><span class="sxs-lookup"><span data-stu-id="77650-120">In This Section</span></span>

  - [<span data-ttu-id="77650-121">Lync Server 2013 のグローバルレベルでアーカイブオプションを構成する</span><span class="sxs-lookup"><span data-stu-id="77650-121">Configuring Archiving options at the global level in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [<span data-ttu-id="77650-122">Lync Server 2013 でサイトのアーカイブオプションを構成する</span><span class="sxs-lookup"><span data-stu-id="77650-122">Configuring Archiving options for a site in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [<span data-ttu-id="77650-123">Lync Server 2013 でプールのアーカイブオプションを構成する</span><span class="sxs-lookup"><span data-stu-id="77650-123">Configuring Archiving options for a pool in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

