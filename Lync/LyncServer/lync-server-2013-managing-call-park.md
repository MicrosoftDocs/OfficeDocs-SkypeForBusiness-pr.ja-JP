---
title: 'Lync Server 2013: コールパークの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Call Park
ms:assetid: 9554cdf6-8e7c-48c8-94dd-f28e2befefdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688140(v=OCS.15)
ms:contentKeyID: 49733740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 046467dbe10e66d767d1ce8044984b3de0be1243
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505914"
---
# <a name="managing-call-park-in-lync-server-2013"></a><span data-ttu-id="12bbc-102">Lync Server 2013 でのコールパークの管理</span><span class="sxs-lookup"><span data-stu-id="12bbc-102">Managing Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12bbc-103">_**トピックの最終更新日:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="12bbc-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="12bbc-104">コールパークアプリケーションを使用すると、エンタープライズ Voip ユーザーは1つの電話から通話を保留した後、電話をかけて後で通話を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="12bbc-104">The Call Park application enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later from any telephone.</span></span> <span data-ttu-id="12bbc-105">ユーザーが電話をパークすると、Lync Server が通話を *オービット*と呼ばれる一時的な番号に転送します。この番号は、だれかが取得するか、タイムアウトになるまで通話を保持します。</span><span class="sxs-lookup"><span data-stu-id="12bbc-105">When the user parks a call, Lync Server transfers the call to a temporary number, called an *orbit*, where the call is held until someone retrieves it or it times out.</span></span>

<span data-ttu-id="12bbc-106">このセクションのトピックでは、展開でコールパークアプリケーションをカスタマイズして管理するために実行できるタスクの手順について順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="12bbc-106">Topics in this section provide step-by-step procedures for tasks that you can perform to customize and maintain the Call Park application in your deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="12bbc-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="12bbc-107">In This Section</span></span>

  - [<span data-ttu-id="12bbc-108">Lync Server 2013 でのパーキング呼び出しの内線電話番号の構成</span><span class="sxs-lookup"><span data-stu-id="12bbc-108">Configure phone number extensions for parking calls in Lync Server 2013</span></span>](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)

  - [<span data-ttu-id="12bbc-109">Lync Server 2013 でコールパーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="12bbc-109">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="12bbc-110">Lync Server 2013 でコールパーク保留音をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="12bbc-110">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="12bbc-111">Lync Server 2013 での障害復旧時のコールパークの管理</span><span class="sxs-lookup"><span data-stu-id="12bbc-111">Manage Call Park during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-call-park-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

