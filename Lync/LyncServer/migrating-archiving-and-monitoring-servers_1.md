---
title: アーカイブ サーバーと監視サーバーの移行
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43b7c7509dcf678967db651900c67cdfb3d26685
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="fa2a9-102">アーカイブ サーバーと監視サーバーの移行</span><span class="sxs-lookup"><span data-stu-id="fa2a9-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa2a9-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="fa2a9-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="fa2a9-104">Office Communications Server 2007 R2 にアーカイブサーバーと監視サーバーを展開した場合は、フロントエンドプールを移行した後に、これらのサーバーを Lync Server 2013 環境に展開することができます。</span><span class="sxs-lookup"><span data-stu-id="fa2a9-104">If you deployed Archiving Server and Monitoring Server in your Office Communications Server 2007 R2, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="fa2a9-105">組織にアーカイブ機能と監視機能が欠かせない場合は、移行前にアーカイブと監視をパイロット プールに追加して、移行プロセス中もアーカイブ機能と監視機能を使用できるように対処する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa2a9-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="fa2a9-106">移行および共存フェーズで、アーカイブ機能と監視機能が必要な場合は、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="fa2a9-106">If you want archiving and monitoring functionality during the migration and coexistence phase, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="fa2a9-107">アーカイブデータと監視データは、Lync Server 2013 展開に移動されません。</span><span class="sxs-lookup"><span data-stu-id="fa2a9-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="fa2a9-108">従来の環境を使用停止にする前にバックアップしたデータは、Office Communications Server 2007 R2 のアクティビティの履歴になります。</span><span class="sxs-lookup"><span data-stu-id="fa2a9-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="fa2a9-109">Office Communications Server 2007 R2 バージョンのアーカイブサーバーと監視サーバーは、Office Communications Server 2007 R2 フロントエンドプールにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="fa2a9-109">The Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server can be associated only with a Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="fa2a9-110">Lync Server 2013 では、アーカイブと監視はサーバーの役割ではなく、Lync Server 2013 フロントエンドプールに統合されたサービスです。</span><span class="sxs-lookup"><span data-stu-id="fa2a9-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="fa2a9-111">レガシおよび Lync Server 2013 の展開が共存する時間に、office Communications Server 2007 R2 バージョンのアーカイブサーバーと監視サーバーは、Office Communications Server 2007 R2 プールに所属するユーザーのデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="fa2a9-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server gather data for users homed on Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="fa2a9-112">Lync server 2013 バージョンのアーカイブサーバーおよび監視サーバーは、Lync Server 2013 プールに所属しているユーザーのデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="fa2a9-112">The Lync Server 2013 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fa2a9-113">移行のフェーズでは、新しい Lync Server 2013 パイロットプールで従来のエッジサーバーを使用している場合、office communications server 2007 R2 バージョンのアーカイブサーバーは、Office Communications Server 2007 R2 プールおよび Lync Server 2013 バージョンのアーカイブサーバーに所属するユーザーのデータを収集し続け、Lync Server の2013プールに所属しているユーザーのデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="fa2a9-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Office Communications Server 2007 R2 version of Archiving Server continues to gather data for users homed on Office Communications Server 2007 R2 pools and the Lync Server 2013 version of Archiving Server gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="fa2a9-114">サードパーティ製のアーカイブおよび監視ソリューションをアーカイブサーバーおよび監視サーバーと組み合わせて使用する場合は、サードパーティ製ソリューションと Lync Server 2013 を統合する時期と方法について、ベンダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="fa2a9-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving Server and Monitoring Server, talk to your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

