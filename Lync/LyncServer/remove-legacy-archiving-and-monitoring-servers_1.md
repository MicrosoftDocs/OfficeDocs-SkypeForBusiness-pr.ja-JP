---
title: 従来のアーカイブ サーバーおよび監視サーバーの削除
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: bca6b419-d5bc-4a46-af42-1dd51b99a26b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205215(v=OCS.15)
ms:contentKeyID: 48185261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca128443410b1a693a4718dd2360b9ec35985435
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500004"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="45aab-102">従来のアーカイブ サーバーおよび監視サーバーの削除</span><span class="sxs-lookup"><span data-stu-id="45aab-102">Remove legacy Archiving and Monitoring servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45aab-103">_**トピックの最終更新日:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="45aab-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="45aab-104">Office Communications Server 2007 R2 展開にアーカイブサーバーまたは監視サーバーが含まれている場合は、Lync Server 2013 に移行した後、これらのサーバーを従来の環境から削除できます。すべてのユーザーが、残りの Office Communications Server 2007 R2 プールからすべて削除されています。</span><span class="sxs-lookup"><span data-stu-id="45aab-104">If your Office Communications Server 2007 R2 deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="45aab-105">アーカイブ サーバーまたは監視サーバーはどのような順序で削除してもかまいません。</span><span class="sxs-lookup"><span data-stu-id="45aab-105">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="45aab-106">重要な要件は、すべてのユーザーが残りの Office Communications Server 2007 R2 プールから削除されているということです。</span><span class="sxs-lookup"><span data-stu-id="45aab-106">The key requirement is that all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span>

<span data-ttu-id="45aab-107">[「フェーズ 6: ユーザーをパイロットプールに移動](phase-6-move-users-to-the-pilot-pool.md)する」で説明されている手順に従って、Office Communications Server 2007 R2 から Lync Server 2013 にユーザーを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="45aab-107">You can move users from Office Communications Server 2007 R2 to Lync Server 2013 by following the procedures outlined in [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="45aab-108">すべてのユーザーが残りのプールから削除されたことを確認した後、「サーバーとサーバーの役割を削除する」の手順に従い [https://go.microsoft.com/fwlink/p/?linkId=205887](https://go.microsoft.com/fwlink/p/?linkid=205887) ます。</span><span class="sxs-lookup"><span data-stu-id="45aab-108">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Removing Servers and Server Roles" at [https://go.microsoft.com/fwlink/p/?linkId=205887](https://go.microsoft.com/fwlink/p/?linkid=205887).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

