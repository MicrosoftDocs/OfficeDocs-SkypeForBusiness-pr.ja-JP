---
title: 'Lync Server 2013: 割り当てられていない番号への通話の管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing calls to unassigned numbers
ms:assetid: a45a7546-5ee6-4c1e-ab13-20a71a058f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688167(v=OCS.15)
ms:contentKeyID: 49733772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12809736c67a4ad606503a3a663532b51a1a191b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-calls-to-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="eac03-102">Lync Server 2013 で割り当てられていない番号への通話を管理する</span><span class="sxs-lookup"><span data-stu-id="eac03-102">Managing calls to unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eac03-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="eac03-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="eac03-104">Lync Server を使用すると、ダイヤル番号が組織に対して有効でも、ユーザーまたは電話に割り当てられていない場合に、着信通話の処理を構成できます。</span><span class="sxs-lookup"><span data-stu-id="eac03-104">Lync Server lets you configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or phone.</span></span> <span data-ttu-id="eac03-105">アナウンスアプリケーションを使用して、これらの通話を事前に定義した宛先 (電話番号、SIP URI、またはボイスメール) に転送したり、音声アナウンスを再生したり、あるいはその両方を実行したりできます。</span><span class="sxs-lookup"><span data-stu-id="eac03-105">You can use the Announcement application to transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="eac03-106">これらの通話を Exchange UM 自動応答電話番号に転送することもできます。</span><span class="sxs-lookup"><span data-stu-id="eac03-106">You can also transfer these calls to an Exchange UM Auto Attendant phone number.</span></span> <span data-ttu-id="eac03-107">割り当てられていない番号への通話をこれらのいずれかの方法で処理することにより、発信者が誤ってダイヤルしたり、話し中の音が流されたり、または SIP クライアントがエラー メッセージを受け取ったりするような状況を避けることができます。</span><span class="sxs-lookup"><span data-stu-id="eac03-107">Handling calls to unassigned numbers in one of these ways helps you avoid the situations in which a caller misdials and then hears a busy tone, or the SIP client receives an error message.</span></span>

<span data-ttu-id="eac03-p102">ここでは、割り当てられていない電話番号への通話を処理するための割り当てられていない番号範囲の管理と、障害復旧時のアナウンスの管理について説明します。</span><span class="sxs-lookup"><span data-stu-id="eac03-p102">This section describes how to manage unassigned number ranges to handle calls to unassigned phone numbers. The section also describes how to manage Announcements during disaster recovery if you want this functionality during an outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eac03-110">停止中の割り当てられていない番号の処理の使用は任意です。</span><span class="sxs-lookup"><span data-stu-id="eac03-110">Using unassigned number handling during an outage is optional.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="eac03-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="eac03-111">In This Section</span></span>

  - [<span data-ttu-id="eac03-112">Lync Server 2013 でアナウンスを作成する</span><span class="sxs-lookup"><span data-stu-id="eac03-112">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="eac03-113">Lync Server 2013 で割り当てられていない電話番号を構成する</span><span class="sxs-lookup"><span data-stu-id="eac03-113">Configure unassigned phone numbers in Lync Server 2013</span></span>](lync-server-2013-configure-unassigned-phone-numbers.md)

  - [<span data-ttu-id="eac03-114">Lync Server 2013 での障害復旧時のアナウンスの管理</span><span class="sxs-lookup"><span data-stu-id="eac03-114">Manage announcements during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-announcements-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

