---
title: 'Lync Server 2013: ディレクターのシナリオ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for the Director
ms:assetid: d2cf384a-0860-4779-80ce-cba2543be322
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398908(v=OCS.15)
ms:contentKeyID: 48185419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca2070032e355714faa25a3b1e6f8babe21de7f1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scenarios-for-the-director-in-lync-server-2013"></a><span data-ttu-id="806b0-102">Lync Server 2013 のディレクターのシナリオ</span><span class="sxs-lookup"><span data-stu-id="806b0-102">Scenarios for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="806b0-103">_**トピックの最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="806b0-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="806b0-104">ディレクターは、Microsoft Lync Server 2013 の通信ソフトウェアを実行しているサーバーで、ユーザーの要求を認証できますが、ユーザーアカウントは含まれません。</span><span class="sxs-lookup"><span data-stu-id="806b0-104">A Director is a server running Microsoft Lync Server 2013 communications software that can authenticate user requests, but does not home any user accounts.</span></span> <span data-ttu-id="806b0-105">ディレクターは、フロントエンドサーバーに似た web サービスもホストし、web チケット要求を認証し、その他のサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="806b0-105">The Director also hosts web services similar to the Front End Server and will authenticate web ticket requests and provide other services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="806b0-106">ディレクターを展開する場合は、フロントエンドサーバーの web サービスに加えて、リバースプロキシを介してディレクター web サービスを外部に公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="806b0-106">If you deploy Directors, you must publish the Director web services externally through the reverse proxy as well as the web services of the Front End Server.</span></span> <span data-ttu-id="806b0-107">以下のトピックでは、可能なディレクタートポロジの計画プロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="806b0-107">The topics following describe the planning process for the possible Director topologies.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="806b0-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="806b0-108">In This Section</span></span>

  - [<span data-ttu-id="806b0-109">Lync Server 2013 のディレクターの概要</span><span class="sxs-lookup"><span data-stu-id="806b0-109">Overview of the Director in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-director.md)

  - [<span data-ttu-id="806b0-110">Lync Server 2013 のディレクターに必要なコンポーネント</span><span class="sxs-lookup"><span data-stu-id="806b0-110">Components required for the Director in Lync Server 2013</span></span>](lync-server-2013-components-required-for-the-director.md)

  - [<span data-ttu-id="806b0-111">Lync Server 2013 のディレクターのハードウェアおよびソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="806b0-111">Hardware and software requirements for the Director in Lync Server 2013</span></span>](lync-server-2013-hardware-and-software-requirements-for-the-director.md)

  - [<span data-ttu-id="806b0-112">Lync Server 2013 の単一ディレクター</span><span class="sxs-lookup"><span data-stu-id="806b0-112">Single Director in Lync Server 2013</span></span>](lync-server-2013-single-director.md)

  - [<span data-ttu-id="806b0-113">Lync Server 2013 の拡張ディレクタープール</span><span class="sxs-lookup"><span data-stu-id="806b0-113">Scaled Director pool in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="806b0-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="806b0-114">See Also</span></span>


[<span data-ttu-id="806b0-115">Lync Server 2013 でサポートされているトポロジ</span><span class="sxs-lookup"><span data-stu-id="806b0-115">Supported topologies in Lync Server 2013</span></span>](lync-server-2013-supported-topologies.md)  
[<span data-ttu-id="806b0-116">Lync Server 2013 のサーバーハードウェアプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="806b0-116">Server hardware platforms for Lync Server 2013</span></span>](lync-server-2013-server-hardware-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

