---
title: 監視データへのアクセス
TOCTitle: 監視データへのアクセス
ms:assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688116(v=OCS.15)
ms:contentKeyID: 49887031
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 監視データへのアクセス

 

_**トピックの最終更新日:** 2012-09-05_

監視データは、2 つの SQL Server データベースに格納されます。LcsCdr には通話詳細記録データが格納され、QoEMetrics には QoE (Quality of Experience) データが格納されます。これら 2 つのデータベースについて特別なことは何もありません。つまり、これらのデータベースに格納されているデータには、SQL Server データのアクセスと分析に使用する一般的なツールでアクセスできます。

監視データのアクセスと分析に使用できるツールの 1 つは、Lync Server 監視レポートです。監視レポートは、Microsoft SQL Server Reporting Services によって公開された標準レポートのセットです。これらのレポートには、Web ブラウザーを使用してアクセスでき、使用状況、通話診断情報、およびメディア品質情報が示されます。これらの情報はすべて、通話詳細記録 (CDR) および Quality of Experience (QoE) データベースに格納されている CDR および QoE データに基づいて提供されます。監視レポートは Lync Server 2013 に付属しており、Lync Server をインストールして監視を構成した後、Lync Server 展開ウィザードからインストールできます。

説明したように、監視レポートには SQL Server Reporting Service を使用する必要があります。SQL Server Reporting Service は、SQL Server のインストールと同時に、または SQL Server 自体をインストールした後でいつでも、インストールできます。

詳細については、Lync Server 2013 展開ガイドのトピック「[Lync Server 2013 監視レポートのインストール](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)」を参照してください。

