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
ms.openlocfilehash: 1188f80c5dc8555b53f54e7a13c60f97817eaba2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-call-park-in-lync-server-2013"></a><span data-ttu-id="92fdd-102">Lync Server 2013 でのコールパークの管理</span><span class="sxs-lookup"><span data-stu-id="92fdd-102">Managing Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92fdd-103">_**最終更新日:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="92fdd-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="92fdd-104">コールパークアプリケーションを使うと、エンタープライズボイスユーザーは1つの電話から通話を保留にすることができ、その後で任意の電話から通話を受信することができます。</span><span class="sxs-lookup"><span data-stu-id="92fdd-104">The Call Park application enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later from any telephone.</span></span> <span data-ttu-id="92fdd-105">ユーザーが通話をパークすると、Lync Server は、着信が転送されるまでの一時的な電話番号に通話を*転送します*。この番号は、だれかが通話を発信するか、またはタイムアウトします。</span><span class="sxs-lookup"><span data-stu-id="92fdd-105">When the user parks a call, Lync Server transfers the call to a temporary number, called an *orbit*, where the call is held until someone retrieves it or it times out.</span></span>

<span data-ttu-id="92fdd-106">このセクションのトピックでは、展開でコールパークアプリケーションをカスタマイズして維持するために実行できるタスクのステップバイステップの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="92fdd-106">Topics in this section provide step-by-step procedures for tasks that you can perform to customize and maintain the Call Park application in your deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="92fdd-107">このセクション中</span><span class="sxs-lookup"><span data-stu-id="92fdd-107">In This Section</span></span>

  - [<span data-ttu-id="92fdd-108">Lync Server 2013 でのパーキング通話用の電話番号の内線番号を構成する</span><span class="sxs-lookup"><span data-stu-id="92fdd-108">Configure phone number extensions for parking calls in Lync Server 2013</span></span>](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)

  - [<span data-ttu-id="92fdd-109">Lync Server 2013 でのコールパーク設定の構成</span><span class="sxs-lookup"><span data-stu-id="92fdd-109">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="92fdd-110">通話パークをカスタマイズする Lync Server 2013 の保留中の音楽</span><span class="sxs-lookup"><span data-stu-id="92fdd-110">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="92fdd-111">Lync Server 2013 での障害復旧時のコール パークの管理</span><span class="sxs-lookup"><span data-stu-id="92fdd-111">Manage Call Park during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-call-park-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

