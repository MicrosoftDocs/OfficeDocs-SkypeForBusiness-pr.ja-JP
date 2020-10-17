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
ms.openlocfilehash: f763fe840a630ffd7ff2ee132d3251b009be6f34
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505134"
---
# <a name="accessing-monitoring-data-in-lync-server-2013"></a>Lync Server 2013 での監視データへのアクセス

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-05_

監視データは、2 つの SQL Server データベースに格納されます。LcsCdr には通話詳細記録データが格納され、QoEMetrics には QoE (Quality of Experience) データが格納されます。これら 2 つのデータベースについて特別なことは何もありません。つまり、これらのデータベースに格納されているデータには、SQL Server データのアクセスと分析に使用する一般的なツールでアクセスできます。

監視データへのアクセスと分析について考慮する必要がある1つのツールは、Lync Server の監視レポートです。 監視レポートは、Microsoft SQL Server Reporting Service によって発行される標準レポートのセットです。 これらのレポートは、web ブラウザーを使用してアクセスできます。これらのレポートには、使用状況、通話診断情報、およびメディア品質情報があります。これには、CDR および QoE データベースに格納されているすべての通話詳細記録 (CDR) および QoE (Quality of Experience) レコードに基づいています。 監視レポートは Lync Server 2013 に付属しており、lync Server をインストールして監視を構成した後で、Lync server 展開ウィザードからインストールできます。

説明したように、監視レポートには SQL Server Reporting Service を使用する必要があります。SQL Server Reporting Service は、SQL Server のインストールと同時に、または SQL Server 自体をインストールした後でいつでも、インストールできます。

詳細については、「Lync Server 2013 の展開ガイド」の「 [Lync server 2013 の監視レポートのインストール](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) 」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

