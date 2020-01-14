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
ms.openlocfilehash: 3ae23ed2d12548388cd1462aad653de4652633dc
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013 における障害回復のための拡張型の常設チャット サーバー プールの使用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-06_

常設チャットサーバーの障害回復ソリューションは、拡張された常設チャットサーバープールを基盤としています。 これは、Lync Server 2010 のメトロポリタンサイトの回復性に似ています。ただし、ストレッチ仮想ローカルエリアネットワーク (VLAN) を使用する必要はありません。 常設チャットサーバープールを拡大することで、基本的にトポロジの1つのプールを論理的に構成することができますが、プール内にはサーバーを物理的に2つの異なるデータセンターに配置します。 データベースの SQL Server ミラーリングを同じように構成し、同じデータセンターにデータベースとミラーを展開します。 セカンダリ データ センターでは、(障害復旧時に高可用性を提供するためにオプションのミラーを使用して) バックアップ データベースを構成する必要があります。 これは、障害復旧時にフェールオーバー用に使用されるバックアップ データベースです。

高可用性のために SQL Server ミラーリングを構成する方法の詳細については、「 [Lync server 2013 での Sql server のミラーリング](lync-server-2013-sql-server-mirroring.md)」を参照してください。 障害回復のためのデータベースのフェイルオーバーについて詳しくは、「 [Lync server 2013 での常設チャットサーバーのプライマリデータベースの sql Server ログの配布の設定](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md)」と「 [lync server 2013 のプライマリミラーとログ配布のセカンダリデータベースの間での Sql Server のログ配布](lync-server-2013-set-up-log-shipping-secondary-database.md)のセットアップ」をご覧ください。

</div>

<span> </span>

</div>

</div>

</div>

