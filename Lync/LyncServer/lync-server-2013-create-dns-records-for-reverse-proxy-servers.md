---
title: 'Lync Server 2013: リバースプロキシサーバーの DNS レコードの作成'
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
ms.openlocfilehash: 51af1c3179d8101a7e2f9942e15553b5831bce95
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532214"
---
# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a>Lync Server 2013 でリバースプロキシサーバーの DNS レコードを作成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-29_

「 [Lync server 2013 での DNS の構成](lync-server-2013-configure-dns-for-edge-support.md)」で説明されているように、Microsoft インターネットセキュリティとアクセラレータ (ISA) サーバー 2006 SP1、Forefront Threat Management Gateway 2010 server、または Internet Information Server アプリケーション要求ルーティングのパブリック外部インターフェイスをポイントする外部 DNS A レコードを作成します。 各プール、ディレクター (またはディレクタープール)、および各簡易 URL に対して、外部 Web サービス Fqdn の DNS レコードが必要です。

リバースプロキシへのクライアント解決用の最小 DNS レコードは、次のレコードを作成する必要があります。

  - ディレクターおよびディレクタープール用に公開された外部 web サービスを定義するホスト (A) レコード (たとえば、 **webdirext.contoso.com**)

  - 任意のフロントエンドプールおよび Standard Edition サーバーの役割でホストされている外部 web サービスに対して発行された外部 web サービスを定義するホスト (A) レコード (たとえば、 **webext.contoso.com**)

  - 簡易 Url のホスト (A) レコード (たとえば、 **dialin.contoso.com** および **meet.contoso.com**)

  - Lync discovery External record のホスト (A) レコード。また、Lync Web App、scheduler、モビリティ (たとえば、 **lyncdiscover.contoso.com**) を含むすべての web アプリの自動検出へのポインターも提供します。

  - Office Web Apps サーバーの URL のホスト (A) レコード (たとえば **officewebapp01.contoso.com**)

詳細については、「 [DNS の概要-Lync Server 2013 のリバースプロキシ](lync-server-2013-dns-summary-reverse-proxy.md)」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

