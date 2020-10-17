---
title: 障害復旧用に拡張常設チャットサーバープールを使用する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c09231abfae7bbcc32083d7db72d8a4be79ecff
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535924"
---
# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013 での障害復旧のための拡張された常設チャットサーバープールの使用

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-06_

常設チャットサーバーの障害復旧ソリューションは、拡張された常設チャットサーバープール上に構築されています。 これは、Lync Server 2010 の大都市サイト復元に似ています。ただし、拡張された仮想ローカルエリアネットワーク (VLAN) は必要ありません。 常設チャットサーバープールをストレッチすることで、トポロジ内に論理的に1つのプールを構成することができますが、物理的には2つの異なるデータセンターにサーバーをプールに配置します。 データベースの SQL Server ミラーリングを同じ方法で構成し、データベースとミラーを同じデータセンターに展開します。 セカンダリデータセンターでバックアップデータベースを構成する必要があります (障害復旧時の高可用性を実現するためのオプションのミラーを備えています)。 これは、障害復旧時のフェールオーバーに使用されるバックアップデータベースです。

高可用性を確保するために SQL Server ミラーリングを構成する方法の詳細については、「 [Lync server 2013 の Sql server ミラーリング](lync-server-2013-sql-server-mirroring.md)」を参照してください。 障害復旧のためにデータベースをフェールオーバーする詳細については、「 [Lync server 2013 での常設チャットサーバーのプライマリデータベースの Sql Server ログ配布の設定](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) 」と「 [プライマリミラーとログ配布のセカンダリデータベース間での Sql server ログ配布のセットアップ (lync server 2013](lync-server-2013-set-up-log-shipping-secondary-database.md))」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

