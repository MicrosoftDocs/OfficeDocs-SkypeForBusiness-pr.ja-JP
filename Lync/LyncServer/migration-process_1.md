---
title: 移行のプロセス
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2da65ead79d33ff03a66f4ec5ef54fa4e2167890
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="ce550-102">移行のプロセス</span><span class="sxs-lookup"><span data-stu-id="ce550-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce550-103">_**トピックの最終更新日:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="ce550-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="ce550-104">Lync Server 2013 の推奨およびサポートされている移行手順は、side-by-side 移行の手順です。</span><span class="sxs-lookup"><span data-stu-id="ce550-104">The recommended and supported migration procedure for Lync Server 2013 is the side-by-side migration procedure.</span></span> <span data-ttu-id="ce550-105">ここでは、サイド バイ サイド移行の手順を使用する理由、および共存に関する情報についても説明します。</span><span class="sxs-lookup"><span data-stu-id="ce550-105">This topic describes why you should use side-by-side migration and also includes information about coexistence.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="ce550-106">サイド バイ サイド移行</span><span class="sxs-lookup"><span data-stu-id="ce550-106">Side-by-Side Migration</span></span>

<span data-ttu-id="ce550-107">ほとんどすべての移行では、サイド バイ サイド移行パスの使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ce550-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="ce550-108">Side-by-side 移行では、Office Communications Server 2007 R2 を実行している対応するサーバーと共に Lync Server 2013 を使用して新しいサーバーを展開し、新しいサーバーに操作を転送します。</span><span class="sxs-lookup"><span data-stu-id="ce550-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Office Communications Server 2007 R2, and then you transfer operations to the new server.</span></span> <span data-ttu-id="ce550-109">Office Communications Server 2007 R2 にロールバックする必要が生じた場合は、元のサーバーに戻す操作のみを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce550-109">If it becomes necessary to roll back to Office Communications Server 2007 R2, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="ce550-110">ただし、この状況では、アップグレードされたクライアントによって新しい会議がスケジュールされていた場合、それらの会議がすべて機能しなくなるのでクライアントのダウングレードも必要になります。</span><span class="sxs-lookup"><span data-stu-id="ce550-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="ce550-111">共存のテスト</span><span class="sxs-lookup"><span data-stu-id="ce550-111">Coexistence Testing</span></span>

<span data-ttu-id="ce550-112">Lync Server 2013 を Office Communications Server 2007 R2 と並行して展開した後、このトポロジは Lync Server 2013 および Office Communications Server 2007 R2 の共存テストの状態を表します。</span><span class="sxs-lookup"><span data-stu-id="ce550-112">After you have deployed Lync Server 2013 in parallel with Office Communications Server 2007 R2, the topology represents a coexistence testing state of Lync Server 2013 and Office Communications Server 2007 R2.</span></span> <span data-ttu-id="ce550-113">この状態で、サービスが開始されること、各サイトを管理できること、クライアントが現在のユーザーおよび従来のユーザーと通信できることをテストして確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="ce550-113">While in this state, it is important to test and ensure services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="ce550-114">すべてのユーザーの移行の前に、各展開の状態を理解し、各展開が正常に機能および動作することを確認することが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="ce550-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="ce550-115">通常、Lync Server 2013 のパイロットテストにおいて、共存のテスト段階が存在します。</span><span class="sxs-lookup"><span data-stu-id="ce550-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="ce550-116">従来のユーザーは、アプリケーションの互換性と機能が適切に動作するように、長期間 Lync Server 2013 に移動されます。</span><span class="sxs-lookup"><span data-stu-id="ce550-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="ce550-117">パイロットテストの後、ユーザーとアプリケーションが Lync Server 2013 の運用バージョンに移行され、Office Communications Server 2007 R2 の従来のプールとアプリケーションが廃止されました。</span><span class="sxs-lookup"><span data-stu-id="ce550-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Office Communications Server 2007 R2 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

