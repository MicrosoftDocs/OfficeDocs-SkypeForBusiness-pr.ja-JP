---
title: 'Lync Server 2013: ディレクターの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48185393
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cf4e40f211cb992e914be20dc9962d55f229bc2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215883"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-director-in-lync-server-2013"></a><span data-ttu-id="46707-102">Lync Server 2013 のディレクターの概要</span><span class="sxs-lookup"><span data-stu-id="46707-102">Overview of the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46707-103">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="46707-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="46707-104">ディレクターは、ユーザーの要求を認証する Lync Server 2013 を実行しているサーバーですが、ユーザーアカウントをホームにするわけではありません。</span><span class="sxs-lookup"><span data-stu-id="46707-104">A Director is a server running Lync Server 2013 that authenticates user requests, but does not home any user accounts.</span></span> <span data-ttu-id="46707-105">必要に応じて、次の2つのシナリオでディレクターを展開できます。</span><span class="sxs-lookup"><span data-stu-id="46707-105">You optionally can deploy a Director in the following two scenarios:</span></span>

  - <span data-ttu-id="46707-106">エッジサーバーを展開して外部ユーザーのアクセスを有効にする場合は、ディレクターも展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46707-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="46707-107">このシナリオでは、ディレクターが外部ユーザーを認証し、そのトラフィックを内部サーバーに渡します。</span><span class="sxs-lookup"><span data-stu-id="46707-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="46707-108">ディレクターが外部ユーザーの認証に使用される場合、フロントエンドプールサーバーは、これらのユーザーの認証を実行することによるオーバーヘッドから解放されます。</span><span class="sxs-lookup"><span data-stu-id="46707-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="46707-109">また、サービス拒否攻撃などの悪意のあるトラフィックから内部フロントエンドプールを保護するのにも役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="46707-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="46707-110">このような攻撃でネットワークに無効な外部トラフィックが殺到しても、このトラフィックはディレクターで終了します。</span><span class="sxs-lookup"><span data-stu-id="46707-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>

  - <span data-ttu-id="46707-111">中央サイトに複数のフロントエンドプールを展開する場合は、そのサイトにディレクターを追加することで、認証要求を合理化し、パフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="46707-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="46707-112">このシナリオでは、すべての要求が最初にディレクターに送信されてから、適切なフロントエンドプールに転送されます。</span><span class="sxs-lookup"><span data-stu-id="46707-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

