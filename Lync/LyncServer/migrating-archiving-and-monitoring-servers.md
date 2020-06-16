---
title: アーカイブ サーバーと監視サーバーの移行
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba86de15ea86844b677db1abb0f47f7e1995c7e8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="8af9c-102">アーカイブ サーバーと監視サーバーの移行</span><span class="sxs-lookup"><span data-stu-id="8af9c-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8af9c-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="8af9c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="8af9c-104">Lync Server 2010 環境にアーカイブサーバーと監視サーバーを展開した場合は、フロントエンドプールを移行した後に、これらのサーバーを Lync Server 2013 環境に展開することができます。</span><span class="sxs-lookup"><span data-stu-id="8af9c-104">If you deployed Archiving Server and Monitoring Server in your Lync Server 2010 environment, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="8af9c-105">ただし、アーカイブおよび監視機能が組織にとって重要な場合は、移行の前に Lync Server 2013 パイロットプールにアーカイブと監視を追加して、移行プロセス中に機能を利用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8af9c-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Lync Server 2013 pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="8af9c-106">移行プロセスで、アーカイブ機能と監視機能が必要な場合は、以下の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="8af9c-106">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="8af9c-107">アーカイブデータと監視データは、Lync Server 2013 展開に移動されません。</span><span class="sxs-lookup"><span data-stu-id="8af9c-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="8af9c-108">レガシ環境を使用停止にする前にバックアップしたデータは、Lync Server 2010 環境でのアクティビティの履歴になります。</span><span class="sxs-lookup"><span data-stu-id="8af9c-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Lync Server 2010 environment.</span></span>

  - <span data-ttu-id="8af9c-109">Lync Server 2010 バージョンのアーカイブサーバーと監視サーバーは、Lync Server 2010 のフロントエンドプールにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="8af9c-109">The Lync Server 2010 version of Archiving Server and Monitoring Server can be associated only with a Lync Server 2010 Front End pool.</span></span> <span data-ttu-id="8af9c-110">Lync Server 2013 では、アーカイブと監視はサーバーの役割ではなく、Lync Server 2013 フロントエンドプールに統合されたサービスです。</span><span class="sxs-lookup"><span data-stu-id="8af9c-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="8af9c-111">従来の展開と Lync Server 2013 の展開が共存している間に、lync server 2010 バージョンのアーカイブサーバーと監視サーバーは、Lync Server の2010プールに所属するユーザーに対してデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="8af9c-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Lync Server 2010 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2010 pools.</span></span> <span data-ttu-id="8af9c-112">Lync Server 2013 でのアーカイブと監視 Lync Server 2013 プールに所属するユーザーのためにデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="8af9c-112">Archiving and Monitoring in Lync Server 2013 gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8af9c-113">移行のフェーズでは、新しい Lync Server 2013 パイロットプールを使用して従来のエッジサーバーを引き続き使用している場合、lync server 2010 バージョンのアーカイブサーバーは、lync server 2010 プールに所属するユーザーのデータを引き続き収集し、lync server 2013 のアーカイブによって lync Server の2013プールに所属するユーザーのデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="8af9c-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Lync Server 2010 version of Archiving Server continues to gather data for users homed on Lync Server 2010 pools and Archiving in Lync Server 2013 gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="8af9c-114">Lync Server 2013 でのアーカイブと監視と共にサードパーティのアーカイブおよび監視ソリューションを使用する場合は、サードパーティ製ソリューションと Lync Server 2013 を統合する時期と方法についてベンダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="8af9c-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Lync Server 2013, consult with your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

