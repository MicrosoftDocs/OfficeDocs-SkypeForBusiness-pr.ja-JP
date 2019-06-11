---
title: 'Lync Server 2013: コールパークの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Call Park
ms:assetid: 9554cdf6-8e7c-48c8-94dd-f28e2befefdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688140(v=OCS.15)
ms:contentKeyID: 49733740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30a92ef7f6f3cba14577e50f33fd1215f94711bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828111"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-call-park-in-lync-server-2013"></a><span data-ttu-id="c1eea-102">Lync Server 2013 でのコールパークの管理</span><span class="sxs-lookup"><span data-stu-id="c1eea-102">Managing Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1eea-103">_**最終更新日:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="c1eea-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="c1eea-104">コールパークアプリケーションを使うと、エンタープライズボイスユーザーは1つの電話から通話を保留にすることができ、その後で任意の電話から通話を受信することができます。</span><span class="sxs-lookup"><span data-stu-id="c1eea-104">The Call Park application enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later from any telephone.</span></span> <span data-ttu-id="c1eea-105">ユーザーが通話をパークすると、Lync Server は、着信が転送されるまでの\*\* 一時的な電話番号に通話を転送します。この番号は、だれかが通話を発信するか、またはタイムアウトします。</span><span class="sxs-lookup"><span data-stu-id="c1eea-105">When the user parks a call, Lync Server transfers the call to a temporary number, called an *orbit*, where the call is held until someone retrieves it or it times out.</span></span>

<span data-ttu-id="c1eea-106">このセクションのトピックでは、展開でコールパークアプリケーションをカスタマイズして維持するために実行できるタスクのステップバイステップの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="c1eea-106">Topics in this section provide step-by-step procedures for tasks that you can perform to customize and maintain the Call Park application in your deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c1eea-107">このセクション中</span><span class="sxs-lookup"><span data-stu-id="c1eea-107">In This Section</span></span>

  - [<span data-ttu-id="c1eea-108">Lync Server 2013 でのパーキング通話用の電話番号の内線番号を構成する</span><span class="sxs-lookup"><span data-stu-id="c1eea-108">Configure phone number extensions for parking calls in Lync Server 2013</span></span>](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)

  - [<span data-ttu-id="c1eea-109">Lync Server 2013 でのコールパーク設定の構成</span><span class="sxs-lookup"><span data-stu-id="c1eea-109">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="c1eea-110">通話パークをカスタマイズする Lync Server 2013 の保留中の音楽</span><span class="sxs-lookup"><span data-stu-id="c1eea-110">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="c1eea-111">Lync Server 2013 での障害復旧時のコール パークの管理</span><span class="sxs-lookup"><span data-stu-id="c1eea-111">Manage Call Park during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-call-park-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

