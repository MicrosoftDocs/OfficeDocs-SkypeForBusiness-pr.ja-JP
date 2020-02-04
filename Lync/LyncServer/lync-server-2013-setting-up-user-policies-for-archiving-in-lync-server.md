---
title: 'Lync Server 2013: Lync Server でアーカイブ用のユーザーポリシーを設定する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa8f377c2a78275419c7d4906a51a9550864b8ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="860d5-102">Lync Server 2013 でアーカイブ用のユーザーポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="860d5-102">Setting up user policies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="860d5-103">_**最終更新日:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="860d5-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="860d5-104">Lync Server 2013 上にある特定のユーザーに対してアーカイブを有効または無効にするには、1つ以上のユーザーポリシーを作成して構成し、適切なポリシーを特定のユーザーまたはユーザーグループに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="860d5-104">Enabling or disabling Archiving for specific users homed on Lync Server 2013 requires creating and configuring one or more user policies, and then applying the appropriate policy to specific users or user groups.</span></span> <span data-ttu-id="860d5-105">ユーザーポリシーは、サイトとグローバルポリシーを上書きします。ただし、Lync Server 2013 に所属しているユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="860d5-105">User policies override site and global policies, but only for users homed on Lync Server 2013.</span></span>

<span data-ttu-id="860d5-106">ユーザーは常に Lync Server に置かれています。</span><span class="sxs-lookup"><span data-stu-id="860d5-106">Users are always homed in Lync Server.</span></span> <span data-ttu-id="860d5-107">Microsoft Exchange の統合が有効になっている場合、メールボックスが Microsoft Exchange Server 2013 にあるユーザーは、Lync Server で管理されているアーカイブポリシーを持っている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="860d5-107">If Microsoft Exchange integration is enabled, users whose mailboxes are in Microsoft Exchange Server 2013 don’t need to have their Archiving policies in Lync Server managed.</span></span> <span data-ttu-id="860d5-108">アーカイブを使用するユーザーは、インプレースホールドで管理されます。</span><span class="sxs-lookup"><span data-stu-id="860d5-108">These users with Archiving will be managed by Exchange In-Place Hold.</span></span>

<span data-ttu-id="860d5-109">グローバル、サイト、ユーザーのポリシーの階層など、アーカイブポリシーの動作について詳しくは、「計画ドキュメント、展開ドキュメント、または操作のドキュメント」の「 [Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="860d5-109">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="860d5-110">展開で Microsoft Exchange の統合を有効にしている場合、exchange 2013 を使っているユーザーに対してアーカイブが有効になっているかどうかは、インプレースホールドポリシーによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="860d5-110">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013.</span></span> <span data-ttu-id="860d5-111">これらのユーザーのアーカイブでは、メールボックスがインプレース保持されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="860d5-111">Archiving for these users requires that they have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="860d5-112">詳細については、展開ドキュメントで<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server との統合を使用する場合の「Lync server 2013 でアーカイブするためのポリシーを設定する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="860d5-112">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="860d5-113">アーカイブを有効にする前に、アーカイブ構成ですべての適切なオプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="860d5-113">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="860d5-114">詳細については、展開ドキュメントの「 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 でアーカイブオプションを構成する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="860d5-114">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="860d5-115">このセクション中</span><span class="sxs-lookup"><span data-stu-id="860d5-115">In This Section</span></span>

  - [<span data-ttu-id="860d5-116">Lync Server 2013 でアーカイブ用のユーザーポリシーを作成および構成する</span><span class="sxs-lookup"><span data-stu-id="860d5-116">Creating and configuring user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="860d5-117">Lync server 2013 でユーザーに Lync Server のアーカイブポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="860d5-117">Applying a Lync Server Archiving policy to a user in Lync Server 2013</span></span>](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

