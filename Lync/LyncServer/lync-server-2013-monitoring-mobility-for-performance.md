---
title: 'Lync Server 2013: パフォーマンスのためのモビリティの監視'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e217e28545eea15a61bf4b4470472cc9944e9b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531824"
---
# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a>Lync Server 2013 でのパフォーマンスのためのモビリティの監視

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-14_

Lync Server Mobility Service (Mcx) と統合コミュニケーション Web API (UCWA) によって、フロントエンドサーバーおよびフロントエンドプールの負荷が増加します。 モバイルアプリケーションが最小化されている場合でも (Lync 2010 Mobile を実行している Android および Nokia デバイス、Lync 2013 Mobile を実行している Android や Apple デバイスなど)、モバイルアプリケーションが最小化されているときにサーバーへの接続を終了するデバイスよりも高い負荷が課せられます。 モビリティの使用量が増加するにつれて、モビリティのパフォーマンスを監視して、処理能力を高める必要があるかどうかを判断する必要があります。

モビリティのパフォーマンスに影響を与えるいくつかの制限値があります。

  - 使用可能なメモリ

  - 要求キューの制限

  - 同時接続数

  - IIS キューの長さ

モビリティのパフォーマンスに影響を与える可能性があるサーバーのその他の制限は、最大12個の同時サインイン、認証、セッション更新、および終了です。 ただし、ほとんどの展開でこれらの最大値を変更する必要はありません。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 でのサーバーのメモリ容量制限の監視](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [Lync Server 2013 でのモビリティサービスおよび UCWA の使用状況の監視](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [Lync Server 2013 での高パフォーマンスの Mobility Service の構成](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [Lync Server 2013 での IIS 要求トレースログファイルの監視](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [Lync Server 2013 のモビリティパフォーマンスカウンター](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

