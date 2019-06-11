---
title: Exchange Server との統合を使用するときにアーカイブするためのポリシーを設定する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up policies for Archiving when using Exchange Server integration
ms:assetid: 8b9b2bad-a4b3-42e1-85a7-04022e9442ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205063(v=OCS.15)
ms:contentKeyID: 48184742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78e5f5bf1bcfa9b11a96722df1f6ff7535912bb1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-policies-for-archiving-in-lync-server-2013-when-using-exchange-server-integration"></a><span data-ttu-id="c6888-102">Exchange Server との統合を使用するときに、Lync Server 2013 でアーカイブするためのポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="c6888-102">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6888-103">_**最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="c6888-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="c6888-104">Exchange 2013 を使用しているユーザーのメールボックスがインプレースホールドに配置されている場合、これらのユーザーのために、インプレースホールドポリシーが Exchange によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="c6888-104">If users homed on Exchange 2013 have their mailboxes put on In-Place Hold, Exchange In-Place Hold policies control archiving for those users.</span></span> <span data-ttu-id="c6888-105">展開に Microsoft Exchange の統合を使用している場合2013、exchange 2013 のユーザーに対して Lync Server アーカイブポリシーが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="c6888-105">If you use Microsoft Exchange integration for your deployment, Exchange 2013 policies override Lync Server Archiving policies for users who are homed on Exchange 2013.</span></span> <span data-ttu-id="c6888-106">Exchange アーカイブポリシーの構成の詳細については、Exchange 2013 に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6888-106">For information about configuring Exchange Archiving policies, see the Exchange 2013 documentation.</span></span> <span data-ttu-id="c6888-107">Lync Server 2013 を使用するユーザー向けのユーザーポリシーのセットアップの詳細については、展開ドキュメントの「 [Lync server 2013 でアーカイブ用のユーザーポリシーを設定](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6888-107">For details about setting up user policies for users homed on Lync Server 2013, see [Setting up user policies for Archiving in Lync Server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md) in the Deployment documentation.</span></span> <span data-ttu-id="c6888-108">ポリシーのしくみの詳細については、計画ドキュメント、展開ドキュメント、または運用マニュアルの「 [Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6888-108">For details about how policies work, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="c6888-109">同じフォレストに Exchange 2013 と Lync Server 2013 を展開している場合、Exchange 2013 インプレースホールドポリシーでアーカイブを制御します。</span><span class="sxs-lookup"><span data-stu-id="c6888-109">If you deploy Exchange 2013 and Lync Server 2013 in the same forest, your Exchange 2013 In-Place Hold policies control archiving.</span></span> <span data-ttu-id="c6888-110">Exchange 2013 と Lync Server 2013 を別々のフォレストに展開する場合は、「 <A href="lync-server-2013-deployment-checklist-for-archiving.md">lync server 2013 でのアーカイブの展開のチェックリスト</A>」の「別のフォレストでの lync Server と Microsoft Exchange の展開」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6888-110">If you deploy Exchange 2013 and Lync Server 2013 in separate forests, see “Deploying Lync Server and Microsoft Exchange in Different Forests” in <A href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

