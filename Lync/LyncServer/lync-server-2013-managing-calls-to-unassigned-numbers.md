---
title: 'Lync Server 2013: 未割り当ての電話番号への通話を管理する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing calls to unassigned numbers
ms:assetid: a45a7546-5ee6-4c1e-ab13-20a71a058f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688167(v=OCS.15)
ms:contentKeyID: 49733772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50a6c7fe05729f705bd7ea752658f7c890188159
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-calls-to-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="0a3a1-102">Lync Server 2013 で未割り当ての電話番号への通話を管理する</span><span class="sxs-lookup"><span data-stu-id="0a3a1-102">Managing calls to unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a3a1-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0a3a1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0a3a1-104">Lync Server では、ダイヤルされた番号が組織で有効であるが、ユーザーまたは電話に割り当てられていない場合に、着信通話の処理を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="0a3a1-104">Lync Server lets you configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or phone.</span></span> <span data-ttu-id="0a3a1-105">アナウンスメントアプリケーションを使用すると、事前に定義された宛先 (電話番号、SIP URI、ボイスメール) に通話を転送したり、音声アナウンスを再生したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="0a3a1-105">You can use the Announcement application to transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="0a3a1-106">また、これらの通話を Exchange UM 自動応答の電話番号に転送することもできます。</span><span class="sxs-lookup"><span data-stu-id="0a3a1-106">You can also transfer these calls to an Exchange UM Auto Attendant phone number.</span></span> <span data-ttu-id="0a3a1-107">これらの方法のいずれかで、割り当てられていない電話番号への通話を処理すると、発信者がダイヤルした後にビジートーンが聞こえたり、SIP クライアントでエラーメッセージが表示されたりする状況を回避することができます。</span><span class="sxs-lookup"><span data-stu-id="0a3a1-107">Handling calls to unassigned numbers in one of these ways helps you avoid the situations in which a caller misdials and then hears a busy tone, or the SIP client receives an error message.</span></span>

<span data-ttu-id="0a3a1-108">このセクションでは、未割り当ての番号範囲を管理して、未割り当ての電話番号への通話を処理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0a3a1-108">This section describes how to manage unassigned number ranges to handle calls to unassigned phone numbers.</span></span> <span data-ttu-id="0a3a1-109">このセクションでは、停止中にこの機能が必要な場合に、障害回復中にお知らせを管理する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="0a3a1-109">The section also describes how to manage Announcements during disaster recovery if you want this functionality during an outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0a3a1-110">停止中に未使用の番号処理を使うことは任意です。</span><span class="sxs-lookup"><span data-stu-id="0a3a1-110">Using unassigned number handling during an outage is optional.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0a3a1-111">このセクション中</span><span class="sxs-lookup"><span data-stu-id="0a3a1-111">In This Section</span></span>

  - [<span data-ttu-id="0a3a1-112">Lync Server 2013 でお知らせを作成する</span><span class="sxs-lookup"><span data-stu-id="0a3a1-112">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="0a3a1-113">Lync Server 2013 で割り当てられていない電話番号を構成する</span><span class="sxs-lookup"><span data-stu-id="0a3a1-113">Configure unassigned phone numbers in Lync Server 2013</span></span>](lync-server-2013-configure-unassigned-phone-numbers.md)

  - [<span data-ttu-id="0a3a1-114">Lync Server 2013 での障害復旧時のアナウンスの管理</span><span class="sxs-lookup"><span data-stu-id="0a3a1-114">Manage announcements during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-announcements-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

