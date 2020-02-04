---
title: 'Lync Server 2013: 監視対象の Lync Server コンピューターを構成する'
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
ms.openlocfilehash: 68dccef2e9451e4c077f5292398bb663f1acb514
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-computers-that-will-be-monitored-in-lync-server-2013"></a><span data-ttu-id="36fc6-102">Lync Server 2013 で監視される Lync Server コンピューターを構成する</span><span class="sxs-lookup"><span data-stu-id="36fc6-102">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36fc6-103">_**最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="36fc6-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="36fc6-104">Lync Server 2013 は、Microsoft Lync Server 2010 で使用されるセントラル検出プロセスを使用していないため、監視する各 Lync Server 2013 コンピューターは、管理サーバーにその存在を自己報告できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="36fc6-104">Because Lync Server 2013 does not use the central discovery process used in Microsoft Lync Server 2010, each Lync Server 2013 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="36fc6-105">これを可能にするには、監視する各コンピューターに Operations Manager エージェントファイルをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="36fc6-105">To make this possible, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="36fc6-106">エージェントファイルをインストールしたら、System Center プロキシとして動作するようにコンピューターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36fc6-106">After the agent files have been installed, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="36fc6-107">これらの手順は、これらのコンピューターに Lync Server をインストールして構成した後に実行する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="36fc6-107">Note that these procedures should be carried out after you have installed and configured Lync Server on these computers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

