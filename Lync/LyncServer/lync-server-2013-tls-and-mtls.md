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
ms.openlocfilehash: 39c3d9dbaeb4c630445b832ab8f220c209461837
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tls-and-mtls-for-lync-server-2013"></a>Lync Server 2013 の TLS と MTLS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-11-07_

トランスポート層セキュリティ (TLS) と相互トランスポート層セキュリティ (MTLS) プロトコルは、インターネット上で暗号化された通信とエンドポイント認証を提供します。 Microsoft Lync Server 2013 は、これら2つのプロトコルを使用して、信頼されたサーバーのネットワークを作成し、そのネットワーク上のすべての通信が暗号化されるようにします。 サーバー間のすべての SIP 通信は MTLS 経由で行われます。 クライアントからサーバーへの SIP 通信は TLS 経由で行われます。

TLS を使用すると、ユーザーはクライアントソフトウェアを使用して、接続先の Lync Server 2013 サーバーを認証できます。 TLS 接続の場合、クライアントはサーバーから有効な証明書を要求します。 有効にするには、証明書がクライアントによっても信頼された CA によって発行されていて、サーバーの DNS 名が証明書の DNS 名と一致している必要があります。 証明書が有効な場合、クライアントは証明書の公開キーを使用して、通信に使用される対称暗号化キーを暗号化します。そのため、証明書の元の所有者のみが秘密キーを使用して通信の内容を復号化できます。 その結果、接続は信頼され、その時点から、他の信頼されたサーバーまたはクライアントによるチャレンジは行われません。 このコンテキストでは、Web サービスで使用される Secure Sockets Layer (SSL) を TLS ベースとして関連付けることができます。

サーバー間接続は相互認証のために MTLS に依存します。 MTLS 接続では、メッセージを送信したサーバーとそれを受信するサーバーが、相互に信頼された CA からの証明書を交換します。 証明書によって、各サーバーの id が他のサーバーに対して証明されます。 Lync Server 2013 の展開では、エンタープライズ CA によって発行された証明書の有効期間中で、発行元 CA によって取り消されていないものは、Active Directory ドメインのすべてのメンバーが、すべての内部クライアントおよびサーバーで自動的に有効と見なされます。そのドメイン内のエンタープライズ CA を信頼します。 フェデレーションのシナリオでは、発行元の CA が両方のフェデレーションパートナーによって信頼されている必要があります。 各パートナーは、必要に応じて、その CA が他のパートナーによっても信頼されている場合は、異なる CA を使用できます。 この信頼は、エッジサーバーが信頼されたルート ca にパートナーのルート CA 証明書を持っているか、または両方の所有者によって信頼されているサードパーティの CA を使用することによって、最も簡単に実現できます。

TLS と MTLS は、盗聴と man-in-the-middle 攻撃の両方を防止するのに役立ちます。 Man-in-the-middle 攻撃では、攻撃者は2つのネットワークエンティティ間の通信を、いずれかの当事者を認識することなく、攻撃者のコンピューターを経由して再ルーティングします。 TLS および Lync Server 2013 の信頼済みサーバー (トポロジビルダーで指定されたもののみ) の仕様では、公開キー暗号化を使用して調整されたエンドツーエンドの暗号化を使用することによって、アプリケーション層で部分的に攻撃を受けるリスクを軽減します。2つのエンドポイント間、および攻撃者は、対応する秘密キーを持つ有効な信頼された証明書を持っており、クライアントが通信を暗号化するために通信するサービスの名前に発行される必要があります。 ただし、最終的には、ネットワークインフラストラクチャ (この場合は、企業 DNS) について、セキュリティに関するベストプラクティスに従う必要があります。 Lync Server 2013 は、ドメインコントローラーとグローバルカタログが信頼されているのと同じ方法で DNS サーバーが信頼されていると想定していますが、dns は、攻撃者のサーバーが正常に応答しないようにすることによって、dns ハイジャック攻撃に対する保護レベルを提供します。詐称された名前への要求。

次の図は、Lync Server 2013 が MTLS を使用して、信頼されたサーバーのネットワークを作成する方法の概要を示しています。

**Lync Server ネットワークの信頼された接続**

![437749da2-c372-4fkbs 2-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da2-c372-4fkbs 2-ac72-ccfd5191696b")

</div>

<span> </span>

</div>

</div>

</div>

