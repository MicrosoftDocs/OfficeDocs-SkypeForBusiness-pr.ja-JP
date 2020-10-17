---
title: 標準移行シナリオ-高レベル
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62a557d8b5a0f2a3e1e0f248b01795e75c02b3a1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529804"
---
# <a name="standard-migration-scenario---high-level"></a><span data-ttu-id="ac690-102">標準移行シナリオ-高レベル</span><span class="sxs-lookup"><span data-stu-id="ac690-102">Standard migration scenario - high-level</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac690-103">_**トピックの最終更新日:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="ac690-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="ac690-104">Lync Server 2010、グループチャットまたは Office Communications Server 2007 R2 グループチャットから Lync Server 2013、常設チャットサーバーへの移行時には、次の項目を開始点として使用します。</span><span class="sxs-lookup"><span data-stu-id="ac690-104">Use the following items as a starting point when migrating Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="ac690-105">Lync Server 2013 の標準の移行パスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ac690-105">The standard Lync Server 2013 migration path is as follows:</span></span>

  - <span data-ttu-id="ac690-106">組織が以前に Lync Server 2010、グループチャットまたは Office Communications Server 2007 R2 グループチャットを展開していて、Lync Server 2013、常設チャットサーバーを展開している。</span><span class="sxs-lookup"><span data-stu-id="ac690-106">Your organization has previously deployed Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat, and you want to deploy Lync Server 2013, Persistent Chat Server.</span></span>

  - <span data-ttu-id="ac690-107">Lync Server 2013 を展開し、次に常設チャットサーバープールを展開します。</span><span class="sxs-lookup"><span data-stu-id="ac690-107">Deploy Lync Server 2013, and then deploy Persistent Chat Server pool(s).</span></span>

  - <span data-ttu-id="ac690-108">常設チャットルームの移行の準備と計画を行い、移行のためにシステムをシャットダウンするための適切な時間を決定します。</span><span class="sxs-lookup"><span data-stu-id="ac690-108">Prepare and plan for migration of your Persistent Chat rooms, and determine an appropriate time to shut down the system for migration.</span></span>

  - <span data-ttu-id="ac690-109">移行用の Windows PowerShell コマンドレット (**export-cspersistentchatdata** および **export-cspersistentchatdata**) を実行して、コンテンツを常設チャットサーバーに移動します。</span><span class="sxs-lookup"><span data-stu-id="ac690-109">Run the Windows PowerShell cmdlets for migration (**Export-CsPersistentChatData** and **Import-CsPersistentChatData**) to move content to Persistent Chat Server.</span></span>

  - <span data-ttu-id="ac690-110">移行が成功したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac690-110">Verify that migration has succeeded.</span></span>

  - <span data-ttu-id="ac690-111">従来の展開を使用停止にします。</span><span class="sxs-lookup"><span data-stu-id="ac690-111">Decommission your legacy deployment.</span></span>

  - <span data-ttu-id="ac690-112">従来のクライアントが Lync Server 2013 の常設チャットサーバーに接続できるように常設チャットサーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="ac690-112">Configure Persistent Chat Server so that legacy clients can connect to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="ac690-113">新しいクライアントの展開には時間がかかるので、従来のクライアントのユーザーがチャット ルームに可能な限り早急にアクセスできるようにするには、この操作が必要になります。</span><span class="sxs-lookup"><span data-stu-id="ac690-113">This is necessary because it takes time to deploy new clients, and you want to enable existing users with legacy clients to have access to their chat rooms as soon as possible.</span></span>

  - <span data-ttu-id="ac690-114">新しいクライアントを展開する一方で、従来のグループチャット (クライアント) を使用しているワーカーが自分のチャットルームにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="ac690-114">Deploy new clients, while continuing to help ensure that workers with legacy Group Chat (clients) can get to their chat rooms.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

