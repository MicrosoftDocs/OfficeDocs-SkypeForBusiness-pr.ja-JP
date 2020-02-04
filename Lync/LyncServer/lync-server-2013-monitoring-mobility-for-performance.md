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
ms.openlocfilehash: 53bd9c3450617d4fd1db54b52efe0b0938c84c8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a>Lync Server 2013 でのモバイルパフォーマンスの監視

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-14_

Lync Server Mobility Service (Mcx) とユニファイドコミュニケーション Web API (UCWA) では、フロントエンドサーバーとフロントエンドプールの負荷が高くなります。 モバイルアプリケーションが最小化されている場合でもサーバーへの接続を維持するモバイルデバイス (lync 2010 Mobile を実行している Android や Nokia デバイス、Lync 2013 Mobile を実行している Android および Apple デバイスなど) には、高負荷の負荷がかかることがあります。モバイルアプリケーションが最小化されているときに、サーバーとの接続を終了します。 モバイル使用の増加に応じて、容量を増やす必要があるタイミングを判断するために、モビリティのパフォーマンスを監視する必要があります。

モビリティのパフォーマンスに影響を与えるいくつかの制限値があります。

  - 使用可能なメモリ

  - 要求キューの制限

  - 同時接続数

  - IIS キューの長さ

モビリティのパフォーマンスに影響を与える可能性のあるサーバーの制限は、最大12個の同時サインイン、認証、セッションの更新、終了です。 ただし、ほとんどの展開でこれらの最大値を変更する必要はありません。

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 でのサーバーメモリ容量の上限を監視する](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [Lync Server 2013 でのモビリティサービスと UCWA の使用状況の監視](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [Lync Server 2013 での高パフォーマンスのモビリティサービスの構成](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [Lync Server 2013 で IIS 要求トレースのログファイルを監視する](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [Lync Server 2013 のモバイルパフォーマンスカウンター](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

