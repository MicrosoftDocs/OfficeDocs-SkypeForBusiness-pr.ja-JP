---
title: 標準移行シナリオ - 概要
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69349b90c6845d8a3f3d5ed13544da4fe4832eb8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847945"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a><span data-ttu-id="638d3-102">標準移行シナリオ - 概要</span><span class="sxs-lookup"><span data-stu-id="638d3-102">Standard migration scenario - high-level</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="638d3-103">_**最終更新日:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="638d3-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="638d3-104">Lync Server 2010、グループチャット、または Office Communications Server 2007 R2 グループチャットを Lync Server 2013、常設チャットサーバーに移行する場合は、次の項目を出発点として使用します。</span><span class="sxs-lookup"><span data-stu-id="638d3-104">Use the following items as a starting point when migrating Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="638d3-105">標準の Lync Server 2013 の移行パスは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="638d3-105">The standard Lync Server 2013 migration path is as follows:</span></span>

  - <span data-ttu-id="638d3-106">組織が以前に Lync Server 2010、グループチャット、または Office Communications Server 2007 R2 グループチャットを展開しており、Lync Server 2013、常設チャットサーバーを展開している。</span><span class="sxs-lookup"><span data-stu-id="638d3-106">Your organization has previously deployed Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat, and you want to deploy Lync Server 2013, Persistent Chat Server.</span></span>

  - <span data-ttu-id="638d3-107">Lync Server 2013 を展開して、常設チャットサーバープールを展開します。</span><span class="sxs-lookup"><span data-stu-id="638d3-107">Deploy Lync Server 2013, and then deploy Persistent Chat Server pool(s).</span></span>

  - <span data-ttu-id="638d3-108">常設チャットルームの移行を準備および計画し、移行のためにシステムをシャットダウンする適切な時間を決定します。</span><span class="sxs-lookup"><span data-stu-id="638d3-108">Prepare and plan for migration of your Persistent Chat rooms, and determine an appropriate time to shut down the system for migration.</span></span>

  - <span data-ttu-id="638d3-109">移行用の Windows PowerShell コマンドレット (**エクスポート-CsPersistentChatData**と**インポート-CsPersistentChatData**) を実行して、コンテンツを永続的なチャットサーバーに移動します。</span><span class="sxs-lookup"><span data-stu-id="638d3-109">Run the Windows PowerShell cmdlets for migration (**Export-CsPersistentChatData** and **Import-CsPersistentChatData**) to move content to Persistent Chat Server.</span></span>

  - <span data-ttu-id="638d3-110">移行が正常に完了したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="638d3-110">Verify that migration has succeeded.</span></span>

  - <span data-ttu-id="638d3-111">従来の展開を廃止します。</span><span class="sxs-lookup"><span data-stu-id="638d3-111">Decommission your legacy deployment.</span></span>

  - <span data-ttu-id="638d3-112">レガシクライアントが Lync Server 2013 の常設チャットサーバーに接続できるように、常設チャットサーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="638d3-112">Configure Persistent Chat Server so that legacy clients can connect to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="638d3-113">これが必要なのは、新しいクライアントを展開するのに時間がかかるためです。また、従来のクライアントを使用する既存のユーザーができるだけ早くチャットルームにアクセスできるようにしたいと考えています。</span><span class="sxs-lookup"><span data-stu-id="638d3-113">This is necessary because it takes time to deploy new clients, and you want to enable existing users with legacy clients to have access to their chat rooms as soon as possible.</span></span>

  - <span data-ttu-id="638d3-114">新しいクライアントを展開しながら、従来のグループチャット (クライアント) のワーカが自分のチャットルームにアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="638d3-114">Deploy new clients, while continuing to help ensure that workers with legacy Group Chat (clients) can get to their chat rooms.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

