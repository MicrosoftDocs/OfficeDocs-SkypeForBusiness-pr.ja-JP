---
title: 'Lync Server 2013: リバース プロキシ サーバーの DNS レコードの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create DNS records for reverse proxy servers
ms:assetid: b3513339-e49b-4665-80f1-b5a1c81a0e2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429719(v=OCS.15)
ms:contentKeyID: 48185181
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f85b222688dcefd45030f2c05f7b59ce45ec0ae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a>Lync Server 2013 でのリバース プロキシ サーバーの DNS レコードの作成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-29_

外部 DNS の作成 Microsoft インターネットセキュリティとアクセラレータ (ISA) サーバー 2006 SP1、Forefront Threat Management Gateway 2010 Server、または Internet Information Server アプリケーション要求ルーティングのパブリック外部インターフェイスを指すレコード。詳細については、「 [Lync Server 2013 での Microsoft edge サポートの DNS の構成](lync-server-2013-configure-dns-for-edge-support.md)」を参照してください。 各プール、ディレクター (またはディレクタープール)、および各シンプル URL について、外部 Web サービス Fqdn 用の DNS レコードが必要です。

リバースプロキシに対するクライアントの解決に関する最小の DNS レコードは、次のレコードを作成する必要があります。

  - ディレクターおよびディレクタープールに対して公開された外部 web サービスを定義する Host (A) レコード ( **webdirext.contoso.com**など)

  - 任意のフロントエンドプールおよび Standard Edition サーバーの役割 (たとえば、 **webext.contoso.com**) でホストされている外部 web サービスに対して公開されている外部 web サービスを定義する Host (A) レコード

  - 単純な Url (たとえば、 **dialin.contoso.com**や**meet.contoso.com**) のホスト (A) レコード

  - Lync Discover 外部レコードのホスト (A) レコード。また、Lync Web App、scheduler、モビリティなどのすべての Web アプリ (たとえば、 **lyncdiscover.contoso.com**) の自動検出へのポインターが表示されます。

  - Office Web Apps サーバーの URL のホスト (A) レコード (たとえば、 **officewebapp01.contoso.com**)

詳細については、「 [DNS の概要-Lync Server 2013 のリバースプロキシ](lync-server-2013-dns-summary-reverse-proxy.md)」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

