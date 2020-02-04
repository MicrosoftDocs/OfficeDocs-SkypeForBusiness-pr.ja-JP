---
title: 'Lync Server 2013: TLS と MTLS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TLS and MTLS for Lync Server 2013
ms:assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481133(v=OCS.15)
ms:contentKeyID: 59893873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06938cfb6c37a84de5256feb6e4b370eb36f3702
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tls-and-mtls-for-lync-server-2013"></a>Lync Server 2013 の TLS と MTLS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-11-07_

TLS プロトコルと MTLS プロトコルにより、インターネット上での通信の暗号化とエンドポイント認証機能が提供されます。 Microsoft Lync Server 2013 は、これら2つのプロトコルを使って、信頼されたサーバーのネットワークを作成し、そのネットワーク上のすべての通信を暗号化します。 サーバー間のすべての SIP 通信は MTLS により行われます。 クライアントからサーバーへの SIP 通信は TLS により行われます。

TLS は、ユーザーがクライアントソフトウェアを通じて、接続先の Lync Server 2013 サーバーを認証できるようにします。 TLS 接続では、クライアントはサーバーから有効な証明書を要求します。 証明書が有効であると見なされるためには、証明書の発行元の CA がクライアントからも信頼されていること、およびサーバーの DNS 名が証明書の DNS 名に一致していることが必要です。 証明書が有効な場合、クライアントは証明書内の公開キーを使用して、通信に使う対称暗号化キーを暗号化し、証明書の最初の所有者だけが、その秘密キーを使用して通信の内容を暗号化することができます。 この接続は信頼済みと見なされ、それ以降は他の信頼されたサーバーやクライアントからチャレンジされません。 このような意味合いで、Web サービスで使用される SSL (Secure Sockets Layer) は TLS ベースであるということができます。

サーバー間接続は、相互認証に MTLS を利用します。 MTLS 接続では、サーバーが発信したメッセージをサーバーが受信すると、相互に信頼できる CA からの証明書を交換します。 証明書は、各サーバーの ID を他のサーバーに証明します。 Lync Server 2013 の展開では、エンタープライズ CA によって発行された証明書が有効期間中に公開 CA によって失効されていなくても、Active Directory ドメインのすべてのメンバーによって、すべての内部クライアントとサーバーで有効と見なされます。そのドメインのエンタープライズ CA を信頼します。 フェデレーションシナリオでは、発行 CA は両方のフェデレーションパートナーによって信頼されている必要があります。 各パートナーは、必要に応じて異なる CA を使用できます。その CA は、他のパートナーによっても信頼されている必要があります。 この信頼は、エッジサーバーが信頼されたルート ca でパートナーのルート CA 証明書を持っているか、または両方の当事者が信頼しているサードパーティ CA を使用して、最も簡単に実現できます。

TLS と MTLS は、盗聴および中間者 (man-in-the-middle) 攻撃の両方を防ぐのに役立ちます。 中間者 (man-in-the-middle) 攻撃では、攻撃者は 2 つのネットワーク エンティティ間の通信を、双方に気付かれることなく、攻撃者のコンピューターを経由して再ルーティングします。 TLS および Lync Server 2013 の信頼されたサーバー (Topology Builder で指定されたもののみ) の仕様は、公開キーの暗号化を使用して調整されたエンドツーエンドの暗号化を使用することで、アプリケーションレイヤー上の一部の中間攻撃のリスクを軽減します。2つのエンドポイント間で、攻撃者は、対応する秘密キーを持つ有効な信頼できる証明書と、クライアントが通信して通信を解読するサービスの名前に発行する必要があります。 とはいえ、結局は、現在のネットワーク インフラストラクチャ (このケースでは社内 DNS) でのセキュリティのベスト プラクティスに従う必要があります。 Lync Server 2013 は、ドメインコントローラーとグローバルカタログが信頼されているのと同じ方法で DNS サーバーが信頼されていることを前提としていますが、DNS は、攻撃者のサーバーが正常に応答できないようにすることで、dns ハイジャック攻撃に対する保護レベルを提供します。スプーフィングされた名前を要求します。

次の図は、Lync Server 2013 で MTLS を使用して信頼されたサーバーのネットワークを作成する方法を示しています。

**Lync Server ネットワークの信頼された接続**

![437749da-c372-4f・・・・・・・・・・・・・・・・ナイン](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f・・・・・・・・・・・・・・・・ナイン")

</div>

<span> </span>

</div>

</div>

</div>

