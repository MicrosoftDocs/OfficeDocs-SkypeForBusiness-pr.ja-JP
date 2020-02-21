---
title: 'Lync Server 2013: ユーザーのアーカイブポリシーの設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Archiving policies for users
ms:assetid: 1bbb45df-0590-4c66-9d65-d25526f57790
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204722(v=OCS.15)
ms:contentKeyID: 48183549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3d11b62f19c8828d17154ce5d96fe6904a78ab7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-archiving-policies-for-users-in-lync-server-2013"></a><span data-ttu-id="7cdfc-102">Lync Server 2013 でユーザーのアーカイブポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="7cdfc-102">Setting up Archiving policies for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7cdfc-103">_**トピックの最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="7cdfc-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="7cdfc-104">ユーザーのアーカイブ ポリシーを作成および構成し、そのポリシーを特定のユーザーまたはユーザー グループに適用することで、特定のユーザーに対してアーカイブを有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="7cdfc-104">You can enable or disable Archiving for specific users by creating and configuring an Archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="7cdfc-105">ユーザー ポリシーは、グローバル ポリシーやサイト ポリシーより優先されます。</span><span class="sxs-lookup"><span data-stu-id="7cdfc-105">User policies override any global policy or site policies.</span></span> <span data-ttu-id="7cdfc-106">アーカイブポリシーは、Microsoft Exchange 統合を使用していない場合、または Microsoft Exchange 統合を使用しているが、Exchange 2013 に所属しておらず、メールボックスがインプレース保持に配置されている場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="7cdfc-106">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="7cdfc-107">グローバルポリシー、サイトポリシー、およびユーザーポリシーの階層を含むアーカイブポリシーのしくみの詳細については、「 [Lync Server 2013](lync-server-2013-how-archiving-works.md)の計画に関するドキュメント、展開に関するドキュメント、または操作のドキュメントでのアーカイブの仕組み」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cdfc-107">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7cdfc-108">展開に対して Microsoft Exchange 統合を有効にすると、exchange 2013 に所属しているユーザーに対してアーカイブを有効にし、メールボックスをインプレース保持に設定するかどうかを Exchange のインプレース保持ポリシーで制御します。</span><span class="sxs-lookup"><span data-stu-id="7cdfc-108">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="7cdfc-109">詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies For Exchange server integration using The Lync server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cdfc-109">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="7cdfc-110">アーカイブ ポリシーで内部または外部の通信のアーカイブを有効にする前に、アーカイブ構成のすべてのオプションを適切に指定してください。</span><span class="sxs-lookup"><span data-stu-id="7cdfc-110">You should specify all appropriate options in the Archiving configurations before enabling Archiving of internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="7cdfc-111">詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 のアーカイブオプションの構成</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cdfc-111">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7cdfc-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7cdfc-112">In This Section</span></span>

  - [<span data-ttu-id="7cdfc-113">Lync Server 2013 でのアーカイブ用のユーザーポリシーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="7cdfc-113">Setting up user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="7cdfc-114">Exchange Server 統合を使用する場合の Lync Server 2013 でのアーカイブポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="7cdfc-114">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

