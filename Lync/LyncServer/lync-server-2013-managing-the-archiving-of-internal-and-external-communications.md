---
title: 内部通信と外部通信のアーカイブの管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Archiving of internal and external communications
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48184417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14df9a4472d920e5b583e4d2abe2deeb3fba0c98
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525034"
---
# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a><span data-ttu-id="38b14-102">Lync Server 2013 での内部および外部通信のアーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="38b14-102">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38b14-103">_**トピックの最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="38b14-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="38b14-104">Lync Server 2013 では、アーカイブポリシーを使用して、内部通信と外部通信のアーカイブを有効または無効にします。 Microsoft Exchange 統合を使用していない場合、または Exchange 2013 に所属していないユーザーがメールボックスを In-Place ホールドにしている場合。</span><span class="sxs-lookup"><span data-stu-id="38b14-104">In Lync Server 2013, you use Archiving policies to enable and disable archiving for internal communications and external communications if you do not use Microsoft Exchange integration or you have users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="38b14-105">これには、次のアーカイブ ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="38b14-105">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="38b14-106">Lync Server 2013 を展開するときに既定で作成されるグローバルポリシー。</span><span class="sxs-lookup"><span data-stu-id="38b14-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="38b14-107">特定のサイトまたはユーザーに対するアーカイブの実装方法を指定するために作成して使用できるオプションのサイトレベルおよびユーザーレベルのポリシー。</span><span class="sxs-lookup"><span data-stu-id="38b14-107">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="38b14-108">アーカイブ ポリシーは、最初はアーカイブの展開時にセットアップしますが、展開後に変更、追加、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="38b14-108">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="38b14-109">Lync Server 2013 コントロールパネルでは、**アーカイブおよび監視**グループの [**アーカイブポリシー** ] ページを使用して、グローバルレベル、サイトレベル、およびユーザーレベルでポリシーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="38b14-109">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span> <span data-ttu-id="38b14-110">Lync Server ストレージと Exchange 2013 ストレージを統合すると、Exchange ユーザーポリシーは Lync Server 2013 アーカイブポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="38b14-110">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies.</span></span>

<span data-ttu-id="38b14-111">ポリシーの階層など、ポリシーの実装方法の詳細については、「計画」、「展開」、または「操作」のドキュメントの「 [Lync Server 2013 でのアーカイブの仕組み](lync-server-2013-how-archiving-works.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38b14-111">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="38b14-112">アーカイブの実装を制御するには、重要モード、削除オプション、IM と会議のどちらをアーカイブするかなどのアーカイブ構成のオプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38b14-112">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="38b14-113">既定では、グローバル アーカイブ構成やサイトまたはプール アーカイブ構成で有効になっているオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="38b14-113">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="38b14-114">アーカイブ ポリシーで内部通信または外部通信のアーカイブを有効にする前に、すべての該当するオプションをアーカイブ構成で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38b14-114">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="38b14-115">詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Lync Server 2013 での組織、サイト、およびプールのアーカイブ構成オプションの管理</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38b14-115">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="38b14-116">展開に対して Microsoft Exchange 統合を有効にした場合は、exchange 2013 に所属しているユーザーに対してアーカイブを有効にするかどうかを制御し、メールボックスを In-Place ホールドにします。</span><span class="sxs-lookup"><span data-stu-id="38b14-116">If you enable Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="38b14-117">詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies For Exchange server integration using The Lync server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38b14-117">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="38b14-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="38b14-118">In This Section</span></span>

  - [<span data-ttu-id="38b14-119">Lync Server 2013 のアーカイブポリシーを作成して、特定のサイトまたはユーザーの内部通信または外部通信のアーカイブを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="38b14-119">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for specific sites or users</span></span>](lync-server-2013-create-archiving-policy-sites-users.md)

  - [<span data-ttu-id="38b14-120">組織、サイト、ユーザーの内部通信または外部通信のアーカイブを有効または無効にするための Lync Server 2013 のアーカイブポリシーの変更</span><span class="sxs-lookup"><span data-stu-id="38b14-120">Changing an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for your organization, sites, or users</span></span>](lync-server-2013-change-archiving-policy-org-sites-users.md)

  - [<span data-ttu-id="38b14-121">Lync Server 2013 でのユーザーへのアーカイブポリシーの適用</span><span class="sxs-lookup"><span data-stu-id="38b14-121">Applying an Archiving policy to users in Lync Server 2013</span></span>](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [<span data-ttu-id="38b14-122">Exchange Server 統合を使用する場合の Lync Server 2013 でのアーカイブポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="38b14-122">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [<span data-ttu-id="38b14-123">Lync Server 2013 でのアーカイブポリシーの削除</span><span class="sxs-lookup"><span data-stu-id="38b14-123">Deleting an Archiving policy in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

