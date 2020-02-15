---
title: 'Lync Server 2013: 監視データへのアクセス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing monitoring data
ms:assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688116(v=OCS.15)
ms:contentKeyID: 49733714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3acb91831a57ba68648ee513af337abe6a894849
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-monitoring-data-in-lync-server-2013"></a><span data-ttu-id="c7cd0-102">Lync Server 2013 での監視データへのアクセス</span><span class="sxs-lookup"><span data-stu-id="c7cd0-102">Accessing monitoring data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7cd0-103">_**トピックの最終更新日:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="c7cd0-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="c7cd0-p101">監視データは、2 つの SQL Server データベースに格納されます。LcsCdr には通話詳細記録データが格納され、QoEMetrics には QoE (Quality of Experience) データが格納されます。これら 2 つのデータベースについて特別なことは何もありません。つまり、これらのデータベースに格納されているデータには、SQL Server データのアクセスと分析に使用する一般的なツールでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c7cd0-p101">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data. There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>

<span data-ttu-id="c7cd0-106">監視データへのアクセスと分析について考慮する必要がある1つのツールは、Lync Server の監視レポートです。</span><span class="sxs-lookup"><span data-stu-id="c7cd0-106">One tool you should consider for accessing and analyzing monitoring data is the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="c7cd0-107">監視レポートは、Microsoft SQL Server Reporting Service によって発行される標準レポートのセットです。</span><span class="sxs-lookup"><span data-stu-id="c7cd0-107">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="c7cd0-108">これらのレポートは、web ブラウザーを使用してアクセスできます。これらのレポートには、使用状況、通話診断情報、およびメディア品質情報があります。これには、CDR および QoE データベースに格納されているすべての通話詳細記録 (CDR) および QoE (Quality of Experience) レコードに基づいています。</span><span class="sxs-lookup"><span data-stu-id="c7cd0-108">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="c7cd0-109">監視レポートは Lync Server 2013 に付属しており、lync Server をインストールして監視を構成した後で、Lync server 展開ウィザードからインストールできます。</span><span class="sxs-lookup"><span data-stu-id="c7cd0-109">Monitoring Reports ship with Lync Server 2013 and can be installed from the Lync Server Deployment Wizard after Lync Server has been installed and monitoring has been configured.</span></span>

<span data-ttu-id="c7cd0-p103">説明したように、監視レポートには SQL Server Reporting Service を使用する必要があります。SQL Server Reporting Service は、SQL Server のインストールと同時に、または SQL Server 自体をインストールした後でいつでも、インストールできます。</span><span class="sxs-lookup"><span data-stu-id="c7cd0-p103">As noted, Monitoring Reports requires the use of SQL Server Reporting Service. SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>

<span data-ttu-id="c7cd0-112">詳細については、「Lync Server 2013 の展開ガイド」の「 [Lync server 2013 の監視レポートのインストール](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7cd0-112">For more information, see the topic [Installing Lync Server 2013 Monitoring Reports](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) in the Lync Server 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

