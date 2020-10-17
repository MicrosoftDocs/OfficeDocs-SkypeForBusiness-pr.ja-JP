---
title: 'Lync Server 2013: 割り当てられていない番号への通話の管理'
description: 'Lync Server 2013: 割り当てられていない番号への通話の管理。'
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
ms.openlocfilehash: a91c1ec30ea1e942fa3ea27fbcd369572884a52a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569153"
---
# <a name="managing-calls-to-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="a9e01-103">Lync Server 2013 で割り当てられていない番号への通話を管理する</span><span class="sxs-lookup"><span data-stu-id="a9e01-103">Managing calls to unassigned numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9e01-104">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a9e01-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a9e01-105">Lync Server を使用すると、ダイヤル番号が組織に対して有効でも、ユーザーまたは電話に割り当てられていない場合に、着信通話の処理を構成できます。</span><span class="sxs-lookup"><span data-stu-id="a9e01-105">Lync Server lets you configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or phone.</span></span> <span data-ttu-id="a9e01-106">アナウンスアプリケーションを使用して、これらの通話を事前に定義した宛先 (電話番号、SIP URI、またはボイスメール) に転送したり、音声アナウンスを再生したり、あるいはその両方を実行したりできます。</span><span class="sxs-lookup"><span data-stu-id="a9e01-106">You can use the Announcement application to transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="a9e01-107">これらの通話を Exchange UM 自動応答電話番号に転送することもできます。</span><span class="sxs-lookup"><span data-stu-id="a9e01-107">You can also transfer these calls to an Exchange UM Auto Attendant phone number.</span></span> <span data-ttu-id="a9e01-108">割り当てられていない番号への通話をこれらのいずれかの方法で処理することにより、発信者が誤ってダイヤルしたり、話し中の音が流されたり、または SIP クライアントがエラー メッセージを受け取ったりするような状況を避けることができます。</span><span class="sxs-lookup"><span data-stu-id="a9e01-108">Handling calls to unassigned numbers in one of these ways helps you avoid the situations in which a caller misdials and then hears a busy tone, or the SIP client receives an error message.</span></span>

<span data-ttu-id="a9e01-p102">ここでは、割り当てられていない電話番号への通話を処理するための割り当てられていない番号範囲の管理と、障害復旧時のアナウンスの管理について説明します。</span><span class="sxs-lookup"><span data-stu-id="a9e01-p102">This section describes how to manage unassigned number ranges to handle calls to unassigned phone numbers. The section also describes how to manage Announcements during disaster recovery if you want this functionality during an outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a9e01-111">停止中の割り当てられていない番号の処理の使用は任意です。</span><span class="sxs-lookup"><span data-stu-id="a9e01-111">Using unassigned number handling during an outage is optional.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a9e01-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a9e01-112">In This Section</span></span>

  - [<span data-ttu-id="a9e01-113">Lync Server 2013 でアナウンスを作成する</span><span class="sxs-lookup"><span data-stu-id="a9e01-113">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="a9e01-114">Lync Server 2013 で割り当てられていない電話番号を構成する</span><span class="sxs-lookup"><span data-stu-id="a9e01-114">Configure unassigned phone numbers in Lync Server 2013</span></span>](lync-server-2013-configure-unassigned-phone-numbers.md)

  - [<span data-ttu-id="a9e01-115">Lync Server 2013 での障害復旧時のアナウンスの管理</span><span class="sxs-lookup"><span data-stu-id="a9e01-115">Manage announcements during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-announcements-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

