---
title: 移行のプロセス
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53021b37baca7a859c79a6c47bfbf3d587a3466d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="204f1-102">移行のプロセス</span><span class="sxs-lookup"><span data-stu-id="204f1-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="204f1-103">_**最終更新日:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="204f1-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="204f1-104">Lync Server 2013 の推奨およびサポートされる移行手順は、並行して移行されます。</span><span class="sxs-lookup"><span data-stu-id="204f1-104">The recommended and supported migration procedure for Lync Server 2013 is side-by-side migration.</span></span> <span data-ttu-id="204f1-105">このトピックでは、サイドバイサイド移行を使用する必要がある理由と、共存テストに関する情報も含まれている理由について説明します。</span><span class="sxs-lookup"><span data-stu-id="204f1-105">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="204f1-106">サイドバイサイド移行</span><span class="sxs-lookup"><span data-stu-id="204f1-106">Side-By-Side Migration</span></span>

<span data-ttu-id="204f1-107">ほぼすべての移行では、並列移行パスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="204f1-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="204f1-108">サイドバイサイドの移行では、lync server 2010 を実行している対応サーバーと共に、Lync Server 2013 と共に新しいサーバーを展開して、新しいサーバーに操作を転送します。</span><span class="sxs-lookup"><span data-stu-id="204f1-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Lync Server 2010, and then transfer operations to the new server.</span></span> <span data-ttu-id="204f1-109">Lync Server 2010 にロールバックすることが必要になった場合は、元のサーバーに戻す操作のみを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="204f1-109">If it becomes necessary to roll back to Lync Server 2010, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="204f1-110">この状況では、アップグレードされたクライアントによってスケジュールされた新しい会議が機能しなくなり、クライアントもダウングレードされる必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="204f1-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="204f1-111">共存テスト</span><span class="sxs-lookup"><span data-stu-id="204f1-111">Coexistence Testing</span></span>

<span data-ttu-id="204f1-112">Lync server 2010 と同時に Lync Server 2013 を展開した後、展開は Lync Server 2013 および Lync Server 2010 の共存テストの状態を表します。</span><span class="sxs-lookup"><span data-stu-id="204f1-112">After you have deployed Lync Server 2013 in parallel with Lync Server 2010, the deployment represents a coexistence testing state of Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="204f1-113">この状態では、サービスが開始されていること、各サイトが管理可能であること、クライアントが現在のユーザーと従来のユーザーと通信できることをテストして確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="204f1-113">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="204f1-114">すべてのユーザーを移行する前に、展開の状態を理解し、各展開が正常に機能して動作していることを確認することが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="204f1-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="204f1-115">通常、[共存テスト] フェーズは、Lync Server 2013 のパイロットテストを通じて行われます。</span><span class="sxs-lookup"><span data-stu-id="204f1-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="204f1-116">従来のユーザーは、アプリケーションの互換性と機能が適切に動作するように、しばらくの間 Lync Server 2013 に移動されます。</span><span class="sxs-lookup"><span data-stu-id="204f1-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="204f1-117">パイロットテストの後、ユーザーとアプリケーションは Lync Server 2013 の運用バージョンに移動され、Lync Server 2010 の従来のプールとアプリケーションは廃止されます。</span><span class="sxs-lookup"><span data-stu-id="204f1-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Lync Server 2010 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

