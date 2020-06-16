---
title: 仲介サーバーの移行
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80c6dbc55e41324ad9c3e7d83bb593d8b8e93c64
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a><span data-ttu-id="93bfe-102">仲介サーバーの移行</span><span class="sxs-lookup"><span data-stu-id="93bfe-102">Migrate Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93bfe-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="93bfe-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="93bfe-104">マージウィザードを実行すると、仲介サーバーが Lync Server 2013 パイロットトポロジに統合されます。</span><span class="sxs-lookup"><span data-stu-id="93bfe-104">Your Mediation Server is merged into your Lync Server 2013 pilot topology when you run the Merge wizard.</span></span> <span data-ttu-id="93bfe-105">ただし、Office Communications Server 2007 R2 プールは Lync Server 2013 仲介サーバーと通信できないため、すべてのユーザーを移行した後に、Lync Server 2013 仲介サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="93bfe-105">You configure the Lync Server 2013 Mediation Server, however, after all users are migrated because an Office Communications Server 2007 R2 pool cannot communicate with a Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="93bfe-106">サイドバイサイドの移行中に、Lync Server 2013 プールは、Office Communications Server 2007 R2 仲介サーバーと通信します。</span><span class="sxs-lookup"><span data-stu-id="93bfe-106">During the side-by-side migration, the Lync Server 2013 pool communicates with the Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="93bfe-107">Lync Server 2013 仲介サーバーを構成する場合は、Office Communications Server 2007 R2 ゲートウェイもアップグレードまたは置換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93bfe-107">When you configure your Lync Server 2013 Mediation Server, you must also upgrade or replace your Office Communications Server 2007 R2 gateways.</span></span> <span data-ttu-id="93bfe-108">Office Communications Server 2007 R2 ゲートウェイは、Lync Server 2013 仲介サーバーをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="93bfe-108">Office Communications Server 2007 R2 gateways do not support Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="93bfe-109">Lync Server 2013 に認定されているゲートウェイを展開し、Lync Server 2013 仲介サーバーに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="93bfe-109">You need to deploy gateways that are certified for Lync Server 2013 and associate them with the Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="93bfe-110">Office Communications Server 2007 R2 展開を完全に使用停止にするには、この手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="93bfe-110">This step is required before you can completely decommission your Office Communications Server 2007 R2 deployment.</span></span>

<span data-ttu-id="93bfe-111">このセクションのトピックでは、Lync Server 2013 仲介サーバーの移行を完了した後に実行する必要がある構成タスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="93bfe-111">The topics in this section describe configuration tasks that you need to perform after you have completed your migration of Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="93bfe-112">併置された仲介サーバーからスタンドアロンの仲介サーバーへの移行は、オプションのタスクです。</span><span class="sxs-lookup"><span data-stu-id="93bfe-112">Transitioning the collocated Mediation Server to a stand-alone Mediation Server is an optional task.</span></span>

  - [<span data-ttu-id="93bfe-113">仲介サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="93bfe-113">Configure Mediation Server</span></span>](configure-mediation-server.md)

  - [<span data-ttu-id="93bfe-114">新しい Lync Server 2013 仲介サーバーを使用するように音声ルートを変更する</span><span class="sxs-lookup"><span data-stu-id="93bfe-114">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [<span data-ttu-id="93bfe-115">併置された仲介サーバーをスタンドアロンの仲介サーバーに移行する (オプション)</span><span class="sxs-lookup"><span data-stu-id="93bfe-115">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

