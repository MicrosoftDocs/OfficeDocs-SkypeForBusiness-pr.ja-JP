---
title: 'Lync Server 2013: 監視データにアクセスする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Accessing monitoring data
ms:assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688116(v=OCS.15)
ms:contentKeyID: 49733714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45f6033c927a0d0c27b139d889c5fb0b0d9d4825
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-monitoring-data-in-lync-server-2013"></a>Lync Server 2013 での監視データへのアクセス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-05_

監視データは、2 つの SQL Server データベースに格納されます。LcsCdr には通話詳細記録データが格納され、QoEMetrics には QoE (Quality of Experience) データが格納されます。これら 2 つのデータベースについて特別なことは何もありません。つまり、これらのデータベースに格納されているデータには、SQL Server データのアクセスと分析に使用する一般的なツールでアクセスできます。

監視データへのアクセスと分析について考慮すべきツールの1つは、Lync Server Monitoring レポートです。 レポートの監視は、Microsoft SQL Server Reporting Service によって公開された標準レポートのセットです。 これらのレポートは、web ブラウザーを使用してアクセスできます。これらのレポートは、CDR と QoE データベースに保存されている通話の詳細記録 (CDR) と Quality of Experience (QoE) レコードに基づいて提供されます。 Lync server 2013 に付属している監視レポートと lync server をインストールして、監視が構成された後に Lync Server 展開ウィザードからインストールすることができます。

説明したように、監視レポートには SQL Server Reporting Service を使用する必要があります。SQL Server Reporting Service は、SQL Server のインストールと同時に、または SQL Server 自体をインストールした後でいつでも、インストールできます。

詳細については、「Lync Server 2013 展開ガイド」で「 [Lync server 2013 監視レポートをインストールする](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)」のトピックを参照してください。

</div>

<span> </span>

</div>

</div>

</div>

