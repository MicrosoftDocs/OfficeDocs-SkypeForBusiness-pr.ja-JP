---
title: 'Lync Server 2013: 負荷分散のためにドメインネームシステムの設定を検証する'
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
ms.openlocfilehash: 0178d179a9684cf07450cdee839af1c8c1ebc22d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a>Lync Server 2013 での負荷分散のためにドメインネームシステムの設定を検証する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-05-02_

DNS の負荷分散で使用される FQDN をサポートするには、DNS をプロビジョニングしてプールの FQDN (pool01.contoso.com など) を、プール内のすべてのサーバーの IP アドレス (たとえば、192.168.1.1、192.168.1.2 など) に解決する必要があります。 現在展開されているサーバーの IP アドレスのみを含める必要があります。

また、エッジプールで DNS の負荷分散を使用している場合は、次の DNS エントリが必要になります。

  - Lync Server Access Edge サービスの場合、プール内の各サーバーに対して1つのエントリが必要です。 各エントリでは、Lync Server アクセスエッジサービスの FQDN (sip.contoso.com など) を、プール内のいずれかのエッジサーバー上にある Lync Server アクセスエッジサービスの IP アドレスに解決する必要があります。

  - Lync Server Web 会議エッジサービスの場合、プール内の各サーバーに対して1つのエントリを用意する必要があります。 各エントリでは、Lync Server Web 会議エッジサービスの FQDN (webconf.contoso.com など) を、プール内のいずれかのエッジサーバー上にある Lync Server Web 会議エッジサービスの IP アドレスに解決する必要があります。

  - Lync Server の音声/ビデオエッジサービスの場合、プール内の各サーバーに対して1つのエントリが必要です。 各エントリは、Lync Server の音声/ビデオエッジサービス (av.contoso.com など) の FQDN を、プール内のエッジサーバーの1つである Lync Server オーディオ/ビデオエッジサービスの IP アドレスに解決する必要があります。

  - エッジプールの内部インターフェイスで DNS の負荷分散を使用する場合は、1つの DNS レコードを追加する必要があります。これにより、エッジプールの内部 FQDN がプール内の各サーバーの IP アドレスに解決されます。

DNS が DNS の負荷分散の正しい値を返していることを確認するには、nslookup ツールを使用する必要があります。 Nslookup を使用して DNS レコードのすべての値を返すには、次のコマンドを実行します。

`nslookup <FQDN >`

Dns ロードバランス構成で使用されているすべてのレコードセットで、すべての正しいエントリが返されたことを確認するために、このコマンドを実行します。

</div>

<span> </span>

</div>

</div>

</div>

