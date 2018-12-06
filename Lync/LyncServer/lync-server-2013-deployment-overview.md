---
title: 'Lync Server 2013: 展開の概要'
TOCTitle: 展開の概要
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48273740
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の展開の概要

 

_**トピックの最終更新日:** 2013-03-12_

Lync Server 2013  Enterprise Edition と Lync Server 2013  Standard Edition の主な違いは、Standard Edition が Enterprise Edition の高可用性機能をサポートしないことです。高可用性機能では、複数の フロント エンド サーバーをプールに展開すると、SQL Server を実行しているサーバーがミラー化できます。Enterprise Edition を使用すれば、共存させるか、スタンドアロンの 仲介サーバーを定義するかを選択できます。監視サーバーおよび アーカイブ サーバーは、SQL Server を実行しているスタンドアロンのサーバーを使用できます。あるいは、フロント エンド サーバーおよびプール用に、データベース サーバー上で実行されている SQL Server のインスタンスを持つことができます。

Lync Server 2013Standard Edition を実行しているサーバーは、より小規模な組織および組織の主要な展開から地理的に離れたリモートの場所を対象としています。2 台の Standard Edition サーバー サーバーをペアにして障害時のフェールオーバーを実現し、最大 5,000 ユーザーをサポートできます。 Enterprise Edition で フロント エンド サーバーをプールできるように、Standard Edition サーバーをプールすることはできません。また、Standard Edition が使用する SQL Server データベースは、Standard Edition サーバーのワークロードを処理するように指定された SQL Server Express を実行している併置サーバーです。これは、すべての役割を Standard Edition サーバーに配置する必要があることを意味しているわけではありません。スタンドアロンの 仲介サーバーおよび エッジ サーバーを使用できます。 中央管理ストア用および Lync Server 2013 のための SQL Server データベースは、SQL Server を実行しているサーバーと併置されている Standard Edition サーバーに配置する必要があります。 監視サーバーと アーカイブ サーバーは、SQL Server データベースを持つスタンドアロン サーバーを使用します。

