---
title: 'Lync Server 2013: 通話管理機能の展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying call management features
ms:assetid: 1667cfe4-76fa-4e10-91bb-b3efbedbf759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204706(v=OCS.15)
ms:contentKeyID: 48183504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c5f2664275b4c6c0e3c93810a7a9521f155f21f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-call-management-features-in-lync-server-2013"></a><span data-ttu-id="d2ea2-102">Lync Server 2013 での通話管理機能の展開</span><span class="sxs-lookup"><span data-stu-id="d2ea2-102">Deploying call management features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2ea2-103">_**トピックの最終更新日:** 2012-12-18_</span><span class="sxs-lookup"><span data-stu-id="d2ea2-103">_**Topic Last Modified:** 2012-12-18_</span></span>

<span data-ttu-id="d2ea2-104">エンタープライズ VoIP 通話管理機能は、着信通話のルーティング方法と応答方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="d2ea2-104">Enterprise Voice call management features control how incoming calls are routed and answered.</span></span> <span data-ttu-id="d2ea2-105">Lync Server 2013 には、次の通話管理機能があります。</span><span class="sxs-lookup"><span data-stu-id="d2ea2-105">Lync Server 2013 provides the following call management features:</span></span>

  - <span data-ttu-id="d2ea2-106">**コールパーク:** 音声ユーザーが通話を一時的にパークし、同じ電話または別の電話からそれを選択できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d2ea2-106">**Call Park:** Enables voice users to temporarily park a call and then pick it up from the same phone or another phone.</span></span>

  - <span data-ttu-id="d2ea2-107">**グループピックアップ:** ユーザーが、通話ピックアップグループ番号をダイヤルすることによって、ピックアップグループに割り当てられた別のユーザーに対して行われた通話に応答できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d2ea2-107">**Group Pickup:** Enables users to answer calls made to another user who is assigned to a pickup group by dialing the call pickup group number.</span></span>

  - <span data-ttu-id="d2ea2-108">**応答グループ:** ハントグループまたは対話型音声応答 (IVR) の質問と回答を使用して、着信通話をエージェントのグループにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="d2ea2-108">**Response Group:** Routes incoming calls to groups of agents by using hunt groups or interactive voice response (IVR) questions and answers.</span></span>

  - <span data-ttu-id="d2ea2-109">**アナウンス:** 割り当てられていない番号への通話に対してメッセージを再生するか、通話を別の場所またはその両方にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="d2ea2-109">**Announcement:** Plays a message for calls made to an unassigned number, or routes the call elsewhere, or both.</span></span>

<span data-ttu-id="d2ea2-110">このセクションでは、エンタープライズ Voip の展開時にこれらの通話管理機能を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d2ea2-110">This section describes how to configure these call management features during an Enterprise Voice deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d2ea2-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d2ea2-111">In This Section</span></span>

  - [<span data-ttu-id="d2ea2-112">Lync Server 2013 でのコールパークの構成</span><span class="sxs-lookup"><span data-stu-id="d2ea2-112">Configuring Call Park in Lync Server 2013</span></span>](lync-server-2013-configuring-call-park.md)

  - [<span data-ttu-id="d2ea2-113">Lync Server 2013 でグループ通話ピックアップを構成する</span><span class="sxs-lookup"><span data-stu-id="d2ea2-113">Configuring Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-configuring-group-call-pickup.md)

  - [<span data-ttu-id="d2ea2-114">Lync Server 2013 で応答グループを構成する</span><span class="sxs-lookup"><span data-stu-id="d2ea2-114">Configuring Response Group in Lync Server 2013</span></span>](lync-server-2013-configuring-response-group.md)

  - [<span data-ttu-id="d2ea2-115">Lync Server 2013 で割り当てられていない番号のアナウンスを構成する</span><span class="sxs-lookup"><span data-stu-id="d2ea2-115">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

