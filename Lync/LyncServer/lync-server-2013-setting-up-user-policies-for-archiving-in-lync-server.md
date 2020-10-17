---
title: 'Lync Server 2013: Lync Server でのアーカイブ用のユーザーポリシーのセットアップ'
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
ms.openlocfilehash: ee2074aa9608dad4adcfe85845e7b2e045276f59
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497514"
---
# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="e0b37-102">Lync Server 2013 でのアーカイブ用のユーザーポリシーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="e0b37-102">Setting up user policies for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0b37-103">_**トピックの最終更新日:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="e0b37-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="e0b37-104">Lync Server 2013 に所属する特定のユーザーに対してアーカイブを有効または無効にするには、1つ以上のユーザーポリシーを作成して構成し、特定のユーザーまたはユーザーグループに適切なポリシーを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0b37-104">Enabling or disabling Archiving for specific users homed on Lync Server 2013 requires creating and configuring one or more user policies, and then applying the appropriate policy to specific users or user groups.</span></span> <span data-ttu-id="e0b37-105">ユーザーポリシーは、サイトポリシーとグローバルポリシーより優先されますが、Lync Server 2013 に所属するユーザーのみが対象となります。</span><span class="sxs-lookup"><span data-stu-id="e0b37-105">User policies override site and global policies, but only for users homed on Lync Server 2013.</span></span>

<span data-ttu-id="e0b37-106">ユーザーは常に Lync Server に所属しています。</span><span class="sxs-lookup"><span data-stu-id="e0b37-106">Users are always homed in Lync Server.</span></span> <span data-ttu-id="e0b37-107">Microsoft Exchange 統合が有効になっている場合は、メールボックスが Microsoft Exchange Server 2013 にあるユーザーは、Lync Server でのアーカイブポリシーを管理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e0b37-107">If Microsoft Exchange integration is enabled, users whose mailboxes are in Microsoft Exchange Server 2013 don’t need to have their Archiving policies in Lync Server managed.</span></span> <span data-ttu-id="e0b37-108">アーカイブを使用するこれらのユーザーは、Exchange In-Place ホールドによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="e0b37-108">These users with Archiving will be managed by Exchange In-Place Hold.</span></span>

<span data-ttu-id="e0b37-109">グローバルポリシー、サイトポリシー、およびユーザーポリシーの階層を含むアーカイブポリシーのしくみの詳細については、「計画」、「展開」、または「操作」のドキュメントの「 [Lync Server 2013 でのアーカイブの仕組み](lync-server-2013-how-archiving-works.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0b37-109">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e0b37-110">展開に対して Microsoft Exchange 統合を有効にした場合、exchange In-Place 保持ポリシーは、Exchange 2013 に所属しているユーザーに対してアーカイブを有効にするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="e0b37-110">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013.</span></span> <span data-ttu-id="e0b37-111">これらのユーザーのアーカイブでは、ユーザーのメールボックスがインプレース保持の状態になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0b37-111">Archiving for these users requires that they have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="e0b37-112">詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies For Exchange server integration using The Lync server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0b37-112">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="e0b37-113">アーカイブを有効にするには、その前にアーカイブ構成で適切なオプションをすべて指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0b37-113">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="e0b37-114">詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 のアーカイブオプションの構成</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0b37-114">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e0b37-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e0b37-115">In This Section</span></span>

  - [<span data-ttu-id="e0b37-116">Lync Server 2013 でのアーカイブ用のユーザーポリシーの作成と構成</span><span class="sxs-lookup"><span data-stu-id="e0b37-116">Creating and configuring user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="e0b37-117">Lync server 2013 のユーザーへの Lync Server アーカイブポリシーの適用</span><span class="sxs-lookup"><span data-stu-id="e0b37-117">Applying a Lync Server Archiving policy to a user in Lync Server 2013</span></span>](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

