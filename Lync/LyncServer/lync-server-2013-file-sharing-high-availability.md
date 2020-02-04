---
title: 'Lync Server 2013: ファイル共有の高可用性'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f67fc8cfffc0b5dbecaf6da212b3a8e5414b18ef
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a>Lync Server 2013 でのファイル共有の高可用性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-03-30_

1つのデータセンターで Lync Server ファイル共有の高可用性を確保するには、分散ファイルシステム (DFS) を使用できます。 DFS は、同一データ センター内の 1 台のファイル サーバーから別のファイル サーバーへのフェールオーバーをサポートします。 大規模展開に対しては、DFS を使用してペアにした専用ファイル サーバーを使用することをお勧めします。

使用しているネットワークのサイズと回復性の量に応じて、1組のサーバーを使用して、サイト内のすべてのファイル共有をホストするか、フロントエンドプールごとに1つのペアを使うことができます。

DFS はベスト エフォート型のファイル レプリケーション メカニズムで、目標復旧時間 (RTO) または目標復旧ポイント (RPO) は公表されていません。 DFS サーバー間のフェールオーバーはすぐに完了する必要がありますが、データレプリケーションの遅延によって、フェールオーバーの発生時に進行中の作業を続行することができなくなる場合があります。

Fileshare で DFS とデータストアを使用することが重要な場合は、ファイル共有を頻繁にバックアップする必要があります (たとえば、4 ~ 8 時間)。 1 つのファイル共有がダウンして、レプリケーションが最新ではない場合は、バックアップを使用して、障害が発生したサーバー上のコンテンツを、そのサーバーとペアになっている他のサーバーに復元できます。

</div>

<span> </span>

</div>

</div>

</div>

