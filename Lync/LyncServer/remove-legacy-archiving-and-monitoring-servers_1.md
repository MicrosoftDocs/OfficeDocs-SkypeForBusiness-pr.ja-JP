---
title: 従来のアーカイブ サーバーおよび監視サーバーの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: bca6b419-d5bc-4a46-af42-1dd51b99a26b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205215(v=OCS.15)
ms:contentKeyID: 48185261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 816855b2661b8834264a2ff4b573ecbfe403d9b4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="32ade-102">従来のアーカイブ サーバーおよび監視サーバーの削除</span><span class="sxs-lookup"><span data-stu-id="32ade-102">Remove legacy Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32ade-103">_**最終更新日:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="32ade-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="32ade-104">Office Communications Server 2007 R2 の展開にアーカイブサーバーまたは監視サーバーが含まれている場合、Lync Server 2013 に移行した後、これらのサーバーは、すべてのユーザーが削除された従来の環境から削除することができます。Office Communications Server 2007 R2 プール。</span><span class="sxs-lookup"><span data-stu-id="32ade-104">If your Office Communications Server 2007 R2 deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="32ade-105">アーカイブサーバーまたは監視サーバーは、任意の順序で削除できます。</span><span class="sxs-lookup"><span data-stu-id="32ade-105">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="32ade-106">重要な要件は、すべてのユーザーが他の Office Communications Server 2007 R2 プールから削除されていることです。</span><span class="sxs-lookup"><span data-stu-id="32ade-106">The key requirement is that all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span>

<span data-ttu-id="32ade-107">[「フェーズ 6: ユーザーをパイロットプールに移動](phase-6-move-users-to-the-pilot-pool.md)する」で説明されている手順に従って、Office Communications Server 2007 R2 から Lync server 2013 にユーザーを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="32ade-107">You can move users from Office Communications Server 2007 R2 to Lync Server 2013 by following the procedures outlined in [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="32ade-108">すべてのユーザーが残りのプールから削除されたことを確認したら、「サーバーとサーバーの役割を削除する[http://go.microsoft.com/fwlink/p/?linkId=205887](http://go.microsoft.com/fwlink/p/?linkid=205887)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="32ade-108">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Removing Servers and Server Roles" at [http://go.microsoft.com/fwlink/p/?linkId=205887](http://go.microsoft.com/fwlink/p/?linkid=205887).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

