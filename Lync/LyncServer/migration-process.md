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
ms.openlocfilehash: 4d941b97080bf4ffd0efc87549c5a4fb80c1275c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="ef12e-102">移行のプロセス</span><span class="sxs-lookup"><span data-stu-id="ef12e-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef12e-103">_**トピックの最終更新日:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="ef12e-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="ef12e-104">Lync Server 2013 の推奨およびサポートされる移行手順は、並行して移行されます。</span><span class="sxs-lookup"><span data-stu-id="ef12e-104">The recommended and supported migration procedure for Lync Server 2013 is side-by-side migration.</span></span> <span data-ttu-id="ef12e-105">このトピックでは、サイド バイ サイド移行を使用する理由について説明し、共存のテストに関する情報も示します。</span><span class="sxs-lookup"><span data-stu-id="ef12e-105">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="ef12e-106">サイド バイ サイド移行</span><span class="sxs-lookup"><span data-stu-id="ef12e-106">Side-By-Side Migration</span></span>

<span data-ttu-id="ef12e-107">ほとんどすべての移行では、サイド バイ サイド移行パスの使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ef12e-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="ef12e-108">Side-by-side 移行では、Lync Server 2010 を実行している対応するサーバーと共に Lync Server 2013 を使用して新しいサーバーを展開し、次にその操作を新しいサーバーに転送します。</span><span class="sxs-lookup"><span data-stu-id="ef12e-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Lync Server 2010, and then transfer operations to the new server.</span></span> <span data-ttu-id="ef12e-109">Lync Server 2010 にロールバックする必要が生じた場合は、元のサーバーに戻す操作のみを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef12e-109">If it becomes necessary to roll back to Lync Server 2010, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="ef12e-110">ただし、この状況では、アップグレードされたクライアントによって新しい会議がスケジュールされていた場合、それらの会議がすべて機能しなくなるのでクライアントのダウングレードも必要になります。</span><span class="sxs-lookup"><span data-stu-id="ef12e-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="ef12e-111">共存のテスト</span><span class="sxs-lookup"><span data-stu-id="ef12e-111">Coexistence Testing</span></span>

<span data-ttu-id="ef12e-112">Lync server 2013 2010 と共に Lync Server を展開した後、展開は Lync Server 2013 と Lync Server 2010 の共存テスト状態を表します。</span><span class="sxs-lookup"><span data-stu-id="ef12e-112">After you have deployed Lync Server 2013 in parallel with Lync Server 2010, the deployment represents a coexistence testing state of Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="ef12e-113">この状態のときに、サービスが開始されていること、各サイトを管理できること、クライアントが現在および従来のユーザーと通信できることをテストして確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="ef12e-113">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="ef12e-114">すべてのユーザーを移行する前に、各展開の状態を把握し、各展開が適切に機能および動作することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef12e-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="ef12e-115">通常、Lync Server 2013 のパイロットテストにおいて、共存のテスト段階が存在します。</span><span class="sxs-lookup"><span data-stu-id="ef12e-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="ef12e-116">従来のユーザーは、アプリケーションの互換性と機能が適切に動作するように、長期間 Lync Server 2013 に移動されます。</span><span class="sxs-lookup"><span data-stu-id="ef12e-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="ef12e-117">パイロットテストの後、ユーザーとアプリケーションは Lync Server 2013 の運用バージョンに移行され、Lync Server 2010 の従来のプールとアプリケーションは廃止されました。</span><span class="sxs-lookup"><span data-stu-id="ef12e-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Lync Server 2010 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

