---
title: アーカイブ サーバーと監視サーバーの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 902970548d4bd9e95e1bd4e7d6eba75e2fe405d3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="15e5b-102">アーカイブ サーバーと監視サーバーの移行</span><span class="sxs-lookup"><span data-stu-id="15e5b-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15e5b-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="15e5b-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="15e5b-104">Office Communications Server 2007 R2 でアーカイブサーバーと監視サーバーを展開した場合、フロントエンドプールを移行した後で、これらのサーバーを Lync Server 2013 環境に展開できます。</span><span class="sxs-lookup"><span data-stu-id="15e5b-104">If you deployed Archiving Server and Monitoring Server in your Office Communications Server 2007 R2, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="15e5b-105">ただし、アーカイブと監視の機能が組織にとって重要である場合は、移行を行う前に、アーカイブと監視を試験的なプールに追加することをお勧めします。これにより、移行プロセス中に機能を利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="15e5b-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="15e5b-106">移行と共存の段階でアーカイブと監視の機能が必要な場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="15e5b-106">If you want archiving and monitoring functionality during the migration and coexistence phase, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="15e5b-107">データのアーカイブとデータの監視は、Lync Server 2013 の展開には移行されません。</span><span class="sxs-lookup"><span data-stu-id="15e5b-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="15e5b-108">従来の環境を廃止する前にバックアップしたデータは、Office Communications Server 2007 R2 でのアクティビティの履歴となります。</span><span class="sxs-lookup"><span data-stu-id="15e5b-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="15e5b-109">Office Communications Server 2007 R2 バージョンのアーカイブサーバーと監視サーバーは、Office Communications Server 2007 R2 フロントエンドプールにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="15e5b-109">The Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server can be associated only with a Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="15e5b-110">Lync Server 2013 では、アーカイブと監視はサーバーの役割ではなくなりましたが、Lync Server 2013 フロントエンドプールに統合されたサービスです。</span><span class="sxs-lookup"><span data-stu-id="15e5b-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="15e5b-111">従来の、および Lync Server 2013 の展開が共存する間、Office Communications Server 2007 R2 バージョンのアーカイブサーバーと監視サーバーによって、Office Communications Server 2007 R2 プールを使用しているユーザーのデータが収集されます。</span><span class="sxs-lookup"><span data-stu-id="15e5b-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server gather data for users homed on Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="15e5b-112">Lync server 2013 バージョンのアーカイブサーバーと監視サーバーは、Lync Server 2013 プールに所属しているユーザーのデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="15e5b-112">The Lync Server 2013 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="15e5b-113">新しい Lync Server 2013 パイロットプールで従来のエッジサーバーを使用している場合、移行のフェーズ中に、office communications Server 2007 R2 バージョンのアーカイブサーバーでは、Office Communications Server 2007 を使っているユーザーのデータを収集し続けることができます。R2 プールと Lync Server 2013 バージョンのアーカイブサーバーでは、Lync Server 2013 プールに所属しているユーザーのデータが収集されます。</span><span class="sxs-lookup"><span data-stu-id="15e5b-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Office Communications Server 2007 R2 version of Archiving Server continues to gather data for users homed on Office Communications Server 2007 R2 pools and the Lync Server 2013 version of Archiving Server gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="15e5b-114">サードパーティのアーカイブと監視ソリューションをアーカイブサーバーおよび監視サーバーと組み合わせて使用する場合は、サードパーティソリューションと Lync Server 2013 を統合する時期とその方法について、ベンダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="15e5b-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving Server and Monitoring Server, talk to your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

