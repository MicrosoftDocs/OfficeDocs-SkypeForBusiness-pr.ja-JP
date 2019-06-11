---
title: 障害回復のための拡張型の常設チャット サーバー プールの使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cced4904619fdbda87fecb29f35f11b40270c0ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013 における障害回復のための拡張型の常設チャット サーバー プールの使用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-06_

常設チャットサーバーの障害回復ソリューションは、拡張された常設チャットサーバープールを基盤としています。 これは、Lync Server 2010 のメトロポリタンサイトの回復性に似ています。ただし、ストレッチ仮想ローカルエリアネットワーク (VLAN) を使用する必要はありません。 常設チャットサーバープールを拡大することで、基本的にトポロジの1つのプールを論理的に構成することができますが、プール内にはサーバーを物理的に2つの異なるデータセンターに配置します。 データベースの SQL Server ミラーリングを同じように構成し、同じデータセンターにデータベースとミラーを展開します。 セカンダリ データ センターでは、(障害復旧時に高可用性を提供するためにオプションのミラーを使用して) バックアップ データベースを構成する必要があります。 これは、障害復旧時にフェールオーバー用に使用されるバックアップ データベースです。

高可用性のために SQL Server ミラーリングを構成する方法の詳細については、「 [Lync server 2013 での Sql server のミラーリング](lync-server-2013-sql-server-mirroring.md)」を参照してください。 障害回復のためのデータベースのフェイルオーバーについて詳しくは、「 [Lync server 2013 での常設チャットサーバーのプライマリデータベースの Sql Server ログの配布](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md)のセットアップ」と「[プライマリミラーとログ間の Sql server ログ配布のセットアップ」をご覧ください。Lync Server 2013 でのセカンダリデータベースの配布](lync-server-2013-setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database.md)。

</div>

<span> </span>

</div>

</div>

</div>

