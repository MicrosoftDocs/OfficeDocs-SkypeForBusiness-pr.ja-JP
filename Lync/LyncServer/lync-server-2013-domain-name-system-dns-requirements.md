---
title: 'Lync Server 2013: ドメインネームシステム (DNS) の要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 771bf78f8477008345422cc61f63202c58fcdd14
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a>Lync Server 2013 のドメインネームシステム (DNS) 要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-18_

Lync Server を展開するには、クライアントとサーバーの検出を有効にするドメインネームシステム (DNS) レコードを作成し、必要に応じて、組織でサポートが必要な場合は、自動クライアントサインインをサポートする必要があります。

Lync Server では、次のような方法で DNS を使用します。

  - 内部サーバーまたはサーバー間通信のプールを検出します。

  - クライアントが、さまざまな SIP トランザクションに使用されるフロントエンドプールまたは Standard Edition サーバーを検出できるようにするには、

  - ログオンしていないユニファイドコミュニケーション (UC) デバイスで、デバイス更新 Web サービスが実行されているフロントエンドプールまたは Standard Edition サーバーを検出し、更新プログラムを入手してログを送信できるようにするには、

  - 外部サーバーとクライアントが、エッジサーバーまたはインスタントメッセージング (IM) または会議の HTTP リバースプロキシに接続できるようにするには、こちらを参照してください。

  - 外部 UC デバイスがエッジサーバーまたは HTTP リバースプロキシ経由でデバイス更新 Web サービスに接続できるようにするには、[更新プログラムの取得] を選びます。

  - モバイルクライアントが、デバイス設定で Url を手動で入力する必要なく、Web サービスのリソースを自動的に検出できるようにする。

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 の DNS の要件を確認する](lync-server-2013-determine-dns-requirements.md)

  - [Lync Server 2013 のフロントエンドプールの DNS 要件](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [Lync Server 2013 での Standard Edition サーバーの DNS 要件](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [Lync Server 2013 の簡易 URL の DNS 要件](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Lync Server 2013 での自動クライアントサインインの DNS 要件](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [Lync Server 2013 を使ったモビリティの DNS 要件](lync-server-2013-dns-requirements-for-mobility.md)

  - [Lync Server 2013 での DNS の負荷分散](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

