---
title: 'Lync Server 2013: データと設定の復元'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring data and settings
ms:assetid: b07f5dd7-7bed-4819-8cb5-617f5acd478e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202185(v=OCS.15)
ms:contentKeyID: 51541503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 396899d636572e89782112ca7fa445ef1cb255e6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511434"
---
# <a name="restoring-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="a45da-102">Lync Server 2013 でのデータと設定の復元</span><span class="sxs-lookup"><span data-stu-id="a45da-102">Restoring data and settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a45da-103">_**トピックの最終更新日:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="a45da-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="a45da-104">プールのペアを使用して障害復旧トポロジを実装していて、それらのフロントエンドプールのうちの1つがダウンしていて、ユーザーにサービスを迅速に復元する必要がある場合は、「 [Lync Server 2013 でプールをフェールオーバー](lync-server-2013-failing-over-a-pool.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a45da-104">If you have implemented a disaster recovery topology with paired pools, and one of those Front End pools has gone down and you need to quickly restore service to your users, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="a45da-105">それ以外の場合は、以下のトピックの情報を、 [Lync server 2013 のバックアップおよび復元ワークシート](lync-server-2013-backup-and-restoration-worksheets.md)のワークシートと共に使用して、障害または停止の後に lync server を復元します。</span><span class="sxs-lookup"><span data-stu-id="a45da-105">Otherwise, use the information in the following topics, along with the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md), to restore Lync Server after a failure or outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a45da-106">ダウンタイムとデータ損失の可能性を軽減するために、このドキュメントで説明する復元手順は、問題を特定して修正する際にトラブルシューティング手順が効果的でない場合にのみ実行してください。</span><span class="sxs-lookup"><span data-stu-id="a45da-106">To reduce downtime and potential data loss, perform the restoration procedures described in this document only if troubleshooting procedures are not effective in identifying and correcting the problem.</span></span> <span data-ttu-id="a45da-107">トラブルシューティングの際に、サーバーをシャットダウンして再起動すると、他のサーバーやコンポーネントへの影響を最小限に抑えるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="a45da-107">During troubleshooting, try to minimize the impact on other servers and components as you shut down and restart servers.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a45da-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a45da-108">In This Section</span></span>

  - [<span data-ttu-id="a45da-109">Lync Server 2013 の復元の準備</span><span class="sxs-lookup"><span data-stu-id="a45da-109">Preparing to restore Lync Server 2013</span></span>](lync-server-2013-preparing-to-restore-lync-server.md)

  - [<span data-ttu-id="a45da-110">Lync Server 2013 での Standard Edition サーバーの復元</span><span class="sxs-lookup"><span data-stu-id="a45da-110">Restoring a Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-restoring-a-standard-edition-server.md)

  - [<span data-ttu-id="a45da-111">Lync Server 2013 で中央管理ストアをホストしているサーバーを復元する</span><span class="sxs-lookup"><span data-stu-id="a45da-111">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)

  - [<span data-ttu-id="a45da-112">Lync Server 2013 で Enterprise Edition バックエンドサーバーを復元する</span><span class="sxs-lookup"><span data-stu-id="a45da-112">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)

  - [<span data-ttu-id="a45da-113">Lync Server 2013 での Enterprise Edition メンバーサーバーの復元</span><span class="sxs-lookup"><span data-stu-id="a45da-113">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-member-server.md)

  - [<span data-ttu-id="a45da-114">Lync server 2013 での Lync Server プールの復元</span><span class="sxs-lookup"><span data-stu-id="a45da-114">Restoring a Lync Server pool in Lync Server 2013</span></span>](lync-server-2013-restoring-a-lync-server-pool.md)

  - [<span data-ttu-id="a45da-115">Lync Server 2013 での ABC フロントエンドプールのフェールオーバーの実行</span><span class="sxs-lookup"><span data-stu-id="a45da-115">Performing an ABC Front End pool failover in Lync Server 2013</span></span>](lync-server-2013-performing-an-abc-front-end-pool-failover.md)

  - [<span data-ttu-id="a45da-116">Lync Server 2013 でのファイルストアの復元</span><span class="sxs-lookup"><span data-stu-id="a45da-116">Restoring a file store in Lync Server 2013</span></span>](lync-server-2013-restoring-a-file-store.md)

  - [<span data-ttu-id="a45da-117">Lync Server 2013 での監視またはアーカイブデータの復元</span><span class="sxs-lookup"><span data-stu-id="a45da-117">Restoring monitoring or archiving data in Lync Server 2013</span></span>](lync-server-2013-restoring-monitoring-or-archiving-data.md)

  - [<span data-ttu-id="a45da-118">Lync Server 2013 での常設チャットデータの復元</span><span class="sxs-lookup"><span data-stu-id="a45da-118">Restoring Persistent Chat data in Lync Server 2013</span></span>](lync-server-2013-restoring-persistent-chat-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

