---
title: 移行のプロセス
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba15e7fc3d190970d8c7cbc5bf7f6465286d1bc5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848053"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="a4930-102">移行のプロセス</span><span class="sxs-lookup"><span data-stu-id="a4930-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4930-103">_**最終更新日:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="a4930-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="a4930-104">Lync Server 2013 の推奨およびサポートされている移行手順は、並列移行の手順です。</span><span class="sxs-lookup"><span data-stu-id="a4930-104">The recommended and supported migration procedure for Lync Server 2013 is the side-by-side migration procedure.</span></span> <span data-ttu-id="a4930-105">このトピックでは、サイドバイサイド移行を使用する必要がある理由と、共存に関する情報も含まれている理由について説明します。</span><span class="sxs-lookup"><span data-stu-id="a4930-105">This topic describes why you should use side-by-side migration and also includes information about coexistence.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="a4930-106">サイドバイサイド移行</span><span class="sxs-lookup"><span data-stu-id="a4930-106">Side-by-Side Migration</span></span>

<span data-ttu-id="a4930-107">ほぼすべての移行では、並列移行パスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4930-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="a4930-108">サイドバイサイドの移行では、Office Communications Server 2007 R2 を実行している対応サーバーと共に、Lync Server 2013 と共に新しいサーバーを展開して、新しいサーバーに操作を転送します。</span><span class="sxs-lookup"><span data-stu-id="a4930-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Office Communications Server 2007 R2, and then you transfer operations to the new server.</span></span> <span data-ttu-id="a4930-109">Office Communications Server 2007 R2 にロールバックする必要がある場合は、元のサーバーに戻す操作のみを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a4930-109">If it becomes necessary to roll back to Office Communications Server 2007 R2, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="a4930-110">この状況では、アップグレードされたクライアントによってスケジュールされた新しい会議が機能しなくなり、クライアントもダウングレードされる必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a4930-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="a4930-111">共存テスト</span><span class="sxs-lookup"><span data-stu-id="a4930-111">Coexistence Testing</span></span>

<span data-ttu-id="a4930-112">Office Communications Server 2007 R2 と並行して Lync Server 2013 を展開した後、トポロジは Lync Server 2013 と Office Communications Server 2007 R2 の共存テストの状態を表します。</span><span class="sxs-lookup"><span data-stu-id="a4930-112">After you have deployed Lync Server 2013 in parallel with Office Communications Server 2007 R2, the topology represents a coexistence testing state of Lync Server 2013 and Office Communications Server 2007 R2.</span></span> <span data-ttu-id="a4930-113">この状態では、サービスが開始されていることを確認し、各サイトを管理し、クライアントが現在のユーザーと従来のユーザーと通信できるようにすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="a4930-113">While in this state, it is important to test and ensure services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="a4930-114">すべてのユーザーを移行する前に、展開の状態を理解し、各展開が正常に機能して動作していることを確認することが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="a4930-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="a4930-115">通常、[共存テスト] フェーズは、Lync Server 2013 のパイロットテストを通じて行われます。</span><span class="sxs-lookup"><span data-stu-id="a4930-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="a4930-116">従来のユーザーは、アプリケーションの互換性と機能が適切に動作するように、しばらくの間 Lync Server 2013 に移動されます。</span><span class="sxs-lookup"><span data-stu-id="a4930-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="a4930-117">パイロットテストの後、ユーザーとアプリケーションは Lync Server 2013 の運用バージョンに移動され、Office Communications Server 2007 R2 の従来のプールとアプリケーションは廃止されます。</span><span class="sxs-lookup"><span data-stu-id="a4930-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Office Communications Server 2007 R2 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

