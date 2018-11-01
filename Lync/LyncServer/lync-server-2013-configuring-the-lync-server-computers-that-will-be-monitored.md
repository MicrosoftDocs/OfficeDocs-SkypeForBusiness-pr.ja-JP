---
title: Lync Server コンピューターを監視する構成
TOCTitle: Lync Server コンピューターを監視する構成
ms:assetid: 9f1b2b91-d5af-42ad-a27d-b0815f762ad8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205118(v=OCS.15)
ms:contentKeyID: 48273045
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server コンピューターを監視する構成

 

_**トピックの最終更新日:** 2012-10-20_

Lync Server 2013 では、Microsoft Lync Server 2010 で使用されていた中央検出プロセスは使用されていないため、監視対象の各 Lync Server 2013 コンピューターが自身の存在を管理サーバーに自己報告できる必要があります。これを実現するには、監視対象の各コンピューターに Operations Manager エージェント ファイルをインストールする必要があります。エージェント ファイルをインストールした後、System Center プロキシとして動作するようにコンピューターを構成する必要があります。なお、これらの手順は、それらのコンピューターで Lync Server のインストールと構成が完了してから実行する必要があります。

