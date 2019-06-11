---
title: 'Lync Server 2013: 通話管理機能の管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing call management features
ms:assetid: c1261140-7a17-4bb2-9823-aa2cf307067c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721872(v=OCS.15)
ms:contentKeyID: 49733805
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e254b127d4773a97d322771c6b9a94eaa71cf667
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828132"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-call-management-features-in-lync-server-2013"></a><span data-ttu-id="8da1b-102">Lync Server 2013 での通話管理機能の管理</span><span class="sxs-lookup"><span data-stu-id="8da1b-102">Managing call management features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8da1b-103">_**最終更新日:** 2012-12-18_</span><span class="sxs-lookup"><span data-stu-id="8da1b-103">_**Topic Last Modified:** 2012-12-18_</span></span>

<span data-ttu-id="8da1b-104">エンタープライズ音声通話管理機能は、着信通話のルーティングと応答の方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="8da1b-104">Enterprise Voice call management features control how incoming calls are routed and answered.</span></span> <span data-ttu-id="8da1b-105">Lync Server 2013 には、次のような通話管理機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="8da1b-105">Lync Server 2013 provides the following call management features:</span></span>

  - <span data-ttu-id="8da1b-106">**コールパーク:** 音声ユーザーが一時的に通話をパークして、同じ電話または別の電話から通話を受け取れるようにします。</span><span class="sxs-lookup"><span data-stu-id="8da1b-106">**Call Park:** Enables voice users to temporarily park a call and then pick it up from the same phone or another phone.</span></span>

  - <span data-ttu-id="8da1b-107">**グループピックアップ:** 通話の集配グループ番号にダイヤルすることで、ユーザーが他のユーザーの着信を受け取れるようにします。</span><span class="sxs-lookup"><span data-stu-id="8da1b-107">**Group Pickup:** Enables users to pick up calls that are ringing for other users by dialing a call pickup group number.</span></span>

  - <span data-ttu-id="8da1b-108">**応答グループ:** ハントグループまたはインタラクティブな音声応答 (IVR) の質問と回答を使って、着信通話をエージェントのグループにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="8da1b-108">**Response Group:** Routes incoming calls to groups of agents by using hunt groups or interactive voice response (IVR) questions and answers.</span></span>

  - <span data-ttu-id="8da1b-109">**お知らせ:** 割り当てられていない番号への通話に対してメッセージを再生するか、通話を別の場所またはその両方にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="8da1b-109">**Announcement:** Plays a message for calls made to an unassigned number, or routes the call elsewhere, or both.</span></span>

<span data-ttu-id="8da1b-110">このセクションでは、エンタープライズ Voip 展開でこれらの通話管理機能を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8da1b-110">This section describes how to manage these call management features in your Enterprise Voice deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8da1b-111">このセクション中</span><span class="sxs-lookup"><span data-stu-id="8da1b-111">In This Section</span></span>

  - [<span data-ttu-id="8da1b-112">Lync Server 2013 でのコールパークの管理</span><span class="sxs-lookup"><span data-stu-id="8da1b-112">Managing Call Park in Lync Server 2013</span></span>](lync-server-2013-managing-call-park.md)

  - [<span data-ttu-id="8da1b-113">Lync Server 2013 でグループ通話のピックアップを管理する</span><span class="sxs-lookup"><span data-stu-id="8da1b-113">Managing Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-managing-group-call-pickup.md)

  - [<span data-ttu-id="8da1b-114">Lync Server 2013 での応答グループの管理</span><span class="sxs-lookup"><span data-stu-id="8da1b-114">Managing response groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-groups.md)

  - [<span data-ttu-id="8da1b-115">Lync Server 2013 で未割り当ての電話番号への通話を管理する</span><span class="sxs-lookup"><span data-stu-id="8da1b-115">Managing calls to unassigned numbers in Lync Server 2013</span></span>](lync-server-2013-managing-calls-to-unassigned-numbers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

