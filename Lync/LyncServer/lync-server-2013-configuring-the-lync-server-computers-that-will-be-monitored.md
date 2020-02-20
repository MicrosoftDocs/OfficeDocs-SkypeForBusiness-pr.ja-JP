---
title: 'Lync Server 2013: 監視対象となる Lync Server コンピューターの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computers that will be monitored
ms:assetid: 9f1b2b91-d5af-42ad-a27d-b0815f762ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205118(v=OCS.15)
ms:contentKeyID: 48184927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71188be470d6f2d561a068840c3cfee9e3e5ad9d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-computers-that-will-be-monitored-in-lync-server-2013"></a><span data-ttu-id="cc12d-102">Lync Server 2013 で監視される Lync Server コンピューターの構成</span><span class="sxs-lookup"><span data-stu-id="cc12d-102">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc12d-103">_**トピックの最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="cc12d-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="cc12d-104">Lync Server 2013 では、Microsoft Lync Server 2010 で使用される中央の探索プロセスは使用されないため、監視する各 Lync Server 2013 コンピューターは、その管理サーバーへのその存在を自己報告できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc12d-104">Because Lync Server 2013 does not use the central discovery process used in Microsoft Lync Server 2010, each Lync Server 2013 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="cc12d-105">このことを可能にするには、監視する各コンピューターに Operations Manager エージェントファイルをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc12d-105">To make this possible, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="cc12d-106">エージェントファイルをインストールした後、システムセンタープロキシとして動作するようにコンピューターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc12d-106">After the agent files have been installed, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="cc12d-107">これらの手順は、これらのコンピューターに Lync Server をインストールして構成した後に実行する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cc12d-107">Note that these procedures should be carried out after you have installed and configured Lync Server on these computers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

