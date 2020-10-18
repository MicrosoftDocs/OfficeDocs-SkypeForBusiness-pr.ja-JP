---
title: Exchange Server 統合を使用する場合のアーカイブのポリシーの設定
description: Exchange Server 統合を使用する場合のアーカイブのポリシーのセットアップ。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up policies for Archiving when using Exchange Server integration
ms:assetid: 8b9b2bad-a4b3-42e1-85a7-04022e9442ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205063(v=OCS.15)
ms:contentKeyID: 48184742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8281d27101c049b1029a2005ed062a934438afc5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579463"
---
# <a name="setting-up-policies-for-archiving-in-lync-server-2013-when-using-exchange-server-integration"></a><span data-ttu-id="ce875-103">Exchange Server 統合を使用する場合の Lync Server 2013 でのアーカイブポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="ce875-103">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce875-104">_**トピックの最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="ce875-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="ce875-105">Exchange 2013 に所属するユーザーがメールボックスを In-Place ホールドに設定している場合、Exchange In-Place ホールドポリシーによってそれらのユーザーのアーカイブが制御されます。</span><span class="sxs-lookup"><span data-stu-id="ce875-105">If users homed on Exchange 2013 have their mailboxes put on In-Place Hold, Exchange In-Place Hold policies control archiving for those users.</span></span> <span data-ttu-id="ce875-106">展開に Microsoft Exchange 統合を使用している場合、exchange 2013 に所属しているユーザーの Lync Server アーカイブポリシーは Exchange 2013 のポリシーによって上書きされます。</span><span class="sxs-lookup"><span data-stu-id="ce875-106">If you use Microsoft Exchange integration for your deployment, Exchange 2013 policies override Lync Server Archiving policies for users who are homed on Exchange 2013.</span></span> <span data-ttu-id="ce875-107">Exchange アーカイブポリシーの構成の詳細については、Exchange 2013 のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce875-107">For information about configuring Exchange Archiving policies, see the Exchange 2013 documentation.</span></span> <span data-ttu-id="ce875-108">Lync Server 2013 に所属するユーザーのユーザーポリシーの設定の詳細については、「展開」のドキュメントの「 [setting up user policies In Lync server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce875-108">For details about setting up user policies for users homed on Lync Server 2013, see [Setting up user policies for Archiving in Lync Server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md) in the Deployment documentation.</span></span> <span data-ttu-id="ce875-109">ポリシーのしくみの詳細については、「計画」のドキュメント、「展開」、または「操作」のドキュメントの「 [Lync Server 2013 でのアーカイブの仕組み](lync-server-2013-how-archiving-works.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce875-109">For details about how policies work, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="ce875-110">Exchange 2013 と Lync Server 2013 を同じフォレストに展開する場合、Exchange 2013 In-Place は、アーカイブを制御するポリシーを保持します。</span><span class="sxs-lookup"><span data-stu-id="ce875-110">If you deploy Exchange 2013 and Lync Server 2013 in the same forest, your Exchange 2013 In-Place Hold policies control archiving.</span></span> <span data-ttu-id="ce875-111">Exchange 2013 と Lync Server 2013 を別のフォレストに展開する場合は、「 <A href="lync-server-2013-deployment-checklist-for-archiving.md">Lync server 2013 でのアーカイブの展開チェックリスト</A>」の「異なるフォレストへの lync Server と Microsoft Exchange の展開」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce875-111">If you deploy Exchange 2013 and Lync Server 2013 in separate forests, see “Deploying Lync Server and Microsoft Exchange in Different Forests” in <A href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

