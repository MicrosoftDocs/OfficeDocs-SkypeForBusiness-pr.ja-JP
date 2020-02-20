---
title: 'Lync Server 2013: 新しい仮想化機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New virtualization features
ms:assetid: edeb2c41-765e-47b8-8a2b-7a7ce09de2ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721926(v=OCS.15)
ms:contentKeyID: 49733861
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28932ba130d7dd67a81c3a4f4f9ab16c1bbbccac
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-virtualization-features-in-lync-server-2013"></a><span data-ttu-id="5a85f-102">Lync Server 2013 の新しい仮想化機能</span><span class="sxs-lookup"><span data-stu-id="5a85f-102">New virtualization features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a85f-103">_**トピックの最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="5a85f-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="5a85f-104">Lync Server 2013 は、Windows Server 2012、Windows Server 2012 R2、Windows Server 2008 R2 の両方で仮想化をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5a85f-104">Lync Server 2013 supports virtualization on both Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span> <span data-ttu-id="5a85f-105">Windows Server 2012 および Windows Server 2012 R2 のサポートには、単一のルート i/o 仮想化 (sr-iov) 機能のサポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5a85f-105">Support on Windows Server 2012 and Windows Server 2012 R2 includes support for the Single Root I/O Virtualization (SR-IOV) capabilities.</span></span> <span data-ttu-id="5a85f-106">SR-IOV では、物理ネットワーク アダプターの仮想機能が仮想コンピューターに直接割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="5a85f-106">With SR-IOV, the virtual function of a physical network adapter is assigned directly to a virtual machine.</span></span> <span data-ttu-id="5a85f-107">ネットワーク スループットを向上させ、ネットワーク遅延を緩和すると共に、ネットワーク トラフィックを処理するために必要なホスト CPU の負荷も軽減します。</span><span class="sxs-lookup"><span data-stu-id="5a85f-107">This increases network throughput and reduces network latency while also reducing the host CPU overhead that is required for processing network traffic.</span></span> <span data-ttu-id="5a85f-108">SR-IOV を利用するには、SR-IOV をサポートする BIOS を搭載したホスト サーバーを使用し、さらに SR-IOV をサポートするネットワーク アダプターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a85f-108">To take advantage of SR-IOV, you must use a host server which has BIOS which supports SR-IOV, as well as use network adapters that support SR-IOV.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

