---
title: 'Lync Server 2013: アーカイブポリシーの構成と割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8b3b4f1f9465684d7c9139b8cd548caacf91c41
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a><span data-ttu-id="905c8-102">Lync Server 2013 でアーカイブポリシーを構成して割り当てる</span><span class="sxs-lookup"><span data-stu-id="905c8-102">Configuring and assigning Archiving policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="905c8-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="905c8-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="905c8-104">Lync server 2013 では、ポリシーを使って、内部通信のアーカイブを有効または無効にすることができます。また、Lync Server 2013 を使用しているユーザー向けの外部通信を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="905c8-104">In Lync Server 2013, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="905c8-105">これには、次のアーカイブポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="905c8-105">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="905c8-106">Lync Server 2013 を展開するときに既定で作成されるグローバルポリシー。</span><span class="sxs-lookup"><span data-stu-id="905c8-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="905c8-107">特定のサイトまたはユーザーに対するアーカイブの実装方法を指定するために作成および使用できる、オプションのサイトレベルとユーザーレベルのポリシー。</span><span class="sxs-lookup"><span data-stu-id="905c8-107">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="905c8-108">アーカイブの展開時にアーカイブポリシーを最初に設定しましたが、展開後にポリシーの変更、追加、削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="905c8-108">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="905c8-109">Lync Server 2013 コントロールパネルで、[**アーカイブと監視**] グループの [**アーカイブポリシー** ] ページを使用して、グローバルレベル、サイトレベル、ユーザーレベルでポリシーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="905c8-109">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="905c8-110">アーカイブの実装を制御するには、IM または会議のアーカイブ、重要モードの使用、削除オプションなど、アーカイブ構成のオプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="905c8-110">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="905c8-111">既定では、グローバルアーカイブ構成またはサイトまたはプールのアーカイブ構成では、どのオプションも有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="905c8-111">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="905c8-112">アーカイブポリシーで、内部または外部通信のアーカイブを有効にする前に、アーカイブ構成ですべての適切なオプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="905c8-112">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="905c8-113">詳細については、「 <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Lync Server 2013 でアーカイブ構成オプションを管理</A>する」を参照してください。この操作のドキュメントでは、組織、サイト、プールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="905c8-113">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="905c8-114">Lync Server ストレージを Exchange 2013 ストレージと統合する場合、Exchange ユーザーのポリシーは、Lync Server 2013 アーカイブポリシーよりも優先されますが、Exchange 2013 を使用しているユーザーに対して、メールボックスがインプレースホールドに組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="905c8-114">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies but only for those users who are homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span>



</div>

<span data-ttu-id="905c8-115">ポリシーの実装方法 (ポリシーの階層を含む) について詳しくは、「計画ドキュメント、展開ドキュメント、または運用ドキュメント」の「 [Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="905c8-115">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="905c8-116">展開後にポリシーを管理する方法について詳しくは、「運用ドキュメントの「 [Lync Server 2013 での社内および社外の通信のアーカイブを管理](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="905c8-116">For details about how to manage policies after deployment, see [Managing the Archiving of internal and external communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="905c8-117">このセクション中</span><span class="sxs-lookup"><span data-stu-id="905c8-117">In This Section</span></span>

  - [<span data-ttu-id="905c8-118">Lync Server 2013 でアーカイブ用のグローバルポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="905c8-118">Configuring the global policy for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [<span data-ttu-id="905c8-119">Lync Server 2013 でアーカイブ用のサイトポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="905c8-119">Setting up site policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [<span data-ttu-id="905c8-120">Lync Server 2013 でユーザーのアーカイブポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="905c8-120">Setting up Archiving policies for users in Lync Server 2013</span></span>](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

