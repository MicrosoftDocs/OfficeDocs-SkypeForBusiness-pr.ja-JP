---
title: 'Lync Server 2013: ドメインネームシステム (DNS) の要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13fcb074ea5ce90bbe7097bf5c2f1f975de809c8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a>Lync Server 2013 のドメインネームシステム (DNS) の要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-18_

Lync Server を展開するには、クライアントとサーバーの検出を有効にするドメインネームシステム (DNS) レコードを作成する必要があります。また、必要に応じて、組織でサポートする必要がある場合に、自動クライアントサインインをサポートする必要があります。

Lync Server は、次の方法で DNS を使用します。

  - サーバー間通信用の内部のサーバーまたはプールを検出する。

  - クライアントが、さまざまな SIP トランザクションに使用されるフロントエンドプールまたは Standard Edition サーバーを検出できるようにします。

  - ログオンしていない統合コミュニケーション (UC) デバイスによる、デバイス更新 Web サービスを実行しているフロントエンドプールまたは Standard Edition サーバーの検出、更新プログラムの取得、およびログの送信を許可します。

  - 外部サーバーとクライアントが、インスタントメッセージング (IM) または会議用のエッジサーバーまたは HTTP リバースプロキシに接続できるようにします。

  - 外部 UC デバイスがエッジサーバーまたは HTTP リバースプロキシ経由でデバイス更新 Web サービスに接続できるようにするには、更新を取得します。

  - モバイル クライアントによる、ユーザーがデバイスの設定で URL を手動で入力する必要がない、Web サービス リソースの自動検出を許可する。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 の DNS 要件を決定する](lync-server-2013-determine-dns-requirements.md)

  - [Lync Server 2013 のフロントエンドプールの DNS 要件](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [Lync Server 2013 の Standard Edition サーバーの DNS 要件](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [Lync Server 2013 の簡易 Url の DNS 要件](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Lync Server 2013 での自動クライアントサインインの DNS 要件](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [Lync Server 2013 を使用したモビリティの DNS 要件](lync-server-2013-dns-requirements-for-mobility.md)

  - [Lync Server 2013 での DNS 負荷分散](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

