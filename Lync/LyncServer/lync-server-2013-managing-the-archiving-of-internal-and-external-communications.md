---
title: 社内および社外の通信のアーカイブを管理する
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
ms.openlocfilehash: ff349fcb7b012ed2604c4e75fe0f4bdd5ed99fc6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a><span data-ttu-id="0cfa1-102">Lync Server 2013 での内部および外部通信のアーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="0cfa1-102">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cfa1-103">_**最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="0cfa1-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="0cfa1-104">Lync Server 2013 では、アーカイブポリシーを使って内部通信と外部通信のアーカイブを有効または無効にすることができます。 Microsoft Exchange 統合を使用していない場合、または Exchange 2013 を使っていないユーザーがメールボックスを配置している場合インプレースホールド。</span><span class="sxs-lookup"><span data-stu-id="0cfa1-104">In Lync Server 2013, you use Archiving policies to enable and disable archiving for internal communications and external communications if you do not use Microsoft Exchange integration or you have users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="0cfa1-105">これには、次のアーカイブポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0cfa1-105">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="0cfa1-106">Lync Server 2013 を展開するときに既定で作成されるグローバルポリシー。</span><span class="sxs-lookup"><span data-stu-id="0cfa1-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="0cfa1-107">特定のサイトまたはユーザーに対するアーカイブの実装方法を指定するために作成および使用できる、オプションのサイトレベルとユーザーレベルのポリシー。</span><span class="sxs-lookup"><span data-stu-id="0cfa1-107">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="0cfa1-108">アーカイブの展開時にアーカイブポリシーを最初に設定しましたが、展開後にポリシーの変更、追加、削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0cfa1-108">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="0cfa1-109">Lync Server 2013 コントロールパネルで、[**アーカイブと監視**] グループの [**アーカイブポリシー** ] ページを使用して、グローバルレベル、サイトレベル、ユーザーレベルでポリシーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="0cfa1-109">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span> <span data-ttu-id="0cfa1-110">Lync Server ストレージと Exchange 2013 ストレージを統合すると、Exchange ユーザーポリシーは Lync Server 2013 アーカイブポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="0cfa1-110">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies.</span></span>

<span data-ttu-id="0cfa1-111">ポリシーの実装方法 (ポリシーの階層を含む) について詳しくは、「計画ドキュメント、展開ドキュメント、または運用ドキュメント」の「 [Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0cfa1-111">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="0cfa1-112">アーカイブの実装を制御するには、IM または会議のアーカイブ、重要モードの使用、削除オプションなど、アーカイブ構成のオプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cfa1-112">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="0cfa1-113">既定では、グローバルアーカイブ構成またはサイトまたはプールのアーカイブ構成では、どのオプションも有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="0cfa1-113">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="0cfa1-114">アーカイブポリシーで、内部または外部通信のアーカイブを有効にする前に、アーカイブ構成ですべての適切なオプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cfa1-114">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="0cfa1-115">詳細については、「 <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Lync Server 2013 でアーカイブ構成オプションを管理</A>する」を参照してください。この操作のドキュメントでは、組織、サイト、プールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0cfa1-115">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="0cfa1-116">展開に対して Microsoft Exchange の統合を有効にすると、exchange 2013 を使っているユーザーに対してアーカイブが有効になっているかどうかを Exchange ポリシーで制御し、そのメールボックスをインプレースホールドに入れます。</span><span class="sxs-lookup"><span data-stu-id="0cfa1-116">If you enable Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="0cfa1-117">詳細については、展開ドキュメントで<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server との統合を使用する場合の「Lync server 2013 でアーカイブするためのポリシーを設定する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cfa1-117">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0cfa1-118">このセクション中</span><span class="sxs-lookup"><span data-stu-id="0cfa1-118">In This Section</span></span>

  - [<span data-ttu-id="0cfa1-119">Lync Server 2013 でアーカイブポリシーを作成して、特定のサイトまたはユーザーの内部または外部の通信のアーカイブを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="0cfa1-119">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for specific sites or users</span></span>](lync-server-2013-create-archiving-policy-sites-users.md)

  - [<span data-ttu-id="0cfa1-120">Lync Server 2013 でアーカイブポリシーを変更して、組織、サイト、またはユーザーの内部または外部の通信のアーカイブを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="0cfa1-120">Changing an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for your organization, sites, or users</span></span>](lync-server-2013-change-archiving-policy-org-sites-users.md)

  - [<span data-ttu-id="0cfa1-121">Lync Server 2013 のユーザーにアーカイブポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="0cfa1-121">Applying an Archiving policy to users in Lync Server 2013</span></span>](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [<span data-ttu-id="0cfa1-122">Exchange Server との統合を使用するときに、Lync Server 2013 でアーカイブするためのポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="0cfa1-122">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [<span data-ttu-id="0cfa1-123">Lync Server 2013 でアーカイブポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="0cfa1-123">Deleting an Archiving policy in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

