---
title: 'Lync Server 2013: 負荷分散のためのドメインネームシステム設定の検証'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc91b9f3c4ce28946830f6d91bd8cb90dd0544ce
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42116710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a>Lync Server 2013 での負荷分散のドメインネームシステム設定の検証

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-05-02_

DNS 負荷分散で使用される FQDN をサポートするには、プールの FQDN (pool01.contoso.com など) をプール内のすべてのサーバーの IP アドレス (192.168.1.1、192.168.1.2 など) に解決するように DNS をプロビジョニングする必要があります。現在展開されているサーバーの IP アドレスのみ含めるようにしてください。

また、エッジプールに DNS 負荷分散を使用している場合は、次の DNS エントリが必要です。

  - Lync Server アクセスエッジサービスの場合は、プール内のサーバーごとに1つのエントリが必要です。 各エントリは、Lync Server アクセスエッジサービス (たとえば、sip.contoso.com) の FQDN を、プール内のいずれかのエッジサーバー上の Lync Server アクセスエッジサービスの IP アドレスに解決する必要があります。

  - Lync Server Web 会議エッジサービスでは、プール内のサーバーごとに1つのエントリが必要です。 各エントリは、Lync Server Web 会議エッジサービスの FQDN (webconf.contoso.com など) を、プール内のいずれかのエッジサーバー上の Lync Server Web 会議エッジサービスの IP アドレスに解決する必要があります。

  - Lync Server 音声ビデオエッジサービスの場合は、プール内のサーバーごとに1つのエントリが必要です。 各エントリは、Lync Server 音声ビデオエッジサービス (たとえば、av.contoso.com) の FQDN を、プール内のいずれかのエッジサーバー上の Lync Server 音声ビデオエッジサービスの IP アドレスに解決する必要があります。

  - エッジプールの内部インターフェイスで DNS 負荷分散を使用する場合は、1つの DNS レコードを追加する必要があります。これにより、エッジプールの内部 FQDN がプール内の各サーバーの IP アドレスに解決されます。

DNS が DNS 負荷分散の正しい値を返すことを確認するには、nslookup ツールを使用する必要があります。 Nslookup を使用して DNS レコードのすべての値を返すには、次のコマンドを実行する必要があります。

`nslookup <FQDN >`

Dns 負荷分散構成で使用されているすべての FQDN に対してこのコマンドを実行し、DNS 負荷分散のすべてのレコードセットが正しいエントリをすべて返すようにします。

</div>

<span> </span>

</div>

</div>

</div>

