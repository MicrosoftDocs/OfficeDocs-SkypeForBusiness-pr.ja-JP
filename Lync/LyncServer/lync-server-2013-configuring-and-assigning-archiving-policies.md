---
title: 'Lync Server 2013: アーカイブポリシーの構成と割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26b4e49bb6ba25fb9c7230cdf171dc7d31433619
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a><span data-ttu-id="6587c-102">Lync Server 2013 でのアーカイブポリシーの構成と割り当て</span><span class="sxs-lookup"><span data-stu-id="6587c-102">Configuring and assigning Archiving policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6587c-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="6587c-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="6587c-104">Lync Server 2013 では、ポリシーを使用して、Lync Server 2013 に所属しているユーザーの内部通信と外部通信のアーカイブを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="6587c-104">In Lync Server 2013, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="6587c-105">これには、次のアーカイブ ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6587c-105">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="6587c-106">Lync Server 2013 を展開するときに既定で作成されるグローバルポリシー。</span><span class="sxs-lookup"><span data-stu-id="6587c-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="6587c-107">特定のサイトまたはユーザーに対するアーカイブの実装方法を指定するために作成して使用できるオプションのサイトレベルおよびユーザーレベルのポリシー。</span><span class="sxs-lookup"><span data-stu-id="6587c-107">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="6587c-108">アーカイブ ポリシーは、最初はアーカイブの展開時にセットアップしますが、展開後に変更、追加、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="6587c-108">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="6587c-109">Lync Server 2013 コントロールパネルでは、**アーカイブおよび監視**グループの [**アーカイブポリシー** ] ページを使用して、グローバルレベル、サイトレベル、およびユーザーレベルでポリシーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="6587c-109">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6587c-110">アーカイブの実装を制御するには、重要モード、削除オプション、IM と会議のどちらをアーカイブするかなどのアーカイブ構成のオプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6587c-110">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="6587c-111">既定では、グローバル アーカイブ構成やサイトまたはプール アーカイブ構成で有効になっているオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="6587c-111">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="6587c-112">アーカイブ ポリシーで内部通信または外部通信のアーカイブを有効にする前に、すべての該当するオプションをアーカイブ構成で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6587c-112">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="6587c-113">詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Lync Server 2013 での組織、サイト、およびプールのアーカイブ構成オプションの管理</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6587c-113">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="6587c-114">Lync Server ストレージを Exchange 2013 ストレージと統合する場合、Exchange ユーザーポリシーは Lync Server 2013 アーカイブポリシーよりも優先されますが、メールボックスをインプレース保持に配置している Exchange 2013 に所属しているユーザーに対してのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="6587c-114">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies but only for those users who are homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span>



</div>

<span data-ttu-id="6587c-115">ポリシーの階層など、ポリシーの実装方法の詳細については、「計画」、「展開」、または「操作」のドキュメントの「 [Lync Server 2013 でのアーカイブの仕組み](lync-server-2013-how-archiving-works.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6587c-115">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="6587c-116">展開後にポリシーを管理する方法の詳細については、「操作」のドキュメントの「 [Lync Server 2013 での内部および外部通信のアーカイブの管理](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6587c-116">For details about how to manage policies after deployment, see [Managing the Archiving of internal and external communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6587c-117">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6587c-117">In This Section</span></span>

  - [<span data-ttu-id="6587c-118">Lync Server 2013 でのアーカイブ用のグローバルポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="6587c-118">Configuring the global policy for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [<span data-ttu-id="6587c-119">Lync Server 2013 でのアーカイブ用のサイトポリシーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="6587c-119">Setting up site policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [<span data-ttu-id="6587c-120">Lync Server 2013 でユーザーのアーカイブポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="6587c-120">Setting up Archiving policies for users in Lync Server 2013</span></span>](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

