---
title: 'Lync Server 2013: 拡張統合エッジ、NAT を使用したプライベート IP アドレスによる DNS 負荷分散'
description: 'Lync Server 2013: 拡張統合エッジ、NAT を使用したプライベート IP アドレスによる DNS 負荷分散。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: c7ca4ca8-c639-4d93-86d7-8891170cacbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398823(v=OCS.15)
ms:contentKeyID: 48185369
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a1b668902059ef2680525b884d8b2c5e8486260
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577703"
---
# <a name="scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>Lync Server 2013 での拡張統合エッジ、NAT を使用したプライベート IP アドレスを使用した DNS 負荷分散

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-08_

エッジ サーバー プール トポロジでは、複数のエッジ サーバーがデータ センターの境界ネットワークに負荷分散プールとして展開されます。 ドメイン ネーム システム (DNS) 負荷分散は、外部と内部両方のエッジ インターフェイスへのトラフィックに適用されます。

組織で15000を超えるアクセスエッジサービスクライアント接続、1000アクティブ Lync Server Web 会議サービスクライアント接続、または500の同時音声ビデオエッジセッション、またはエッジサーバーの高可用性をサポートする必要がある場合、このトポロジはスケーラビリティとフェールオーバーのサポートの利点を提供します。

この図は、エッジサーバーとフロントエンドプールまたはサーバーの間の内部ネットワークに展開されたオプションのサーバーの役割であるディレクターを示していません。 ディレクターのトポロジの詳細については、「 [Lync Server 2013 でのディレクターに必要なコンポーネント](lync-server-2013-components-required-for-the-director.md)」を参照してください。 この図は、単一のリバース プロキシを表しています。

<div>


> [!NOTE]  
> 以下の図には、方向と IP アドレス指定の例が示されていますが、正しい受信トラフィックと送信トラフィックを使用した実際の通信フローを表すことを目的としていません。 図は、可能なトラフィックの大まかなビューを示しています。 着信 (リッスン ポートへの) および発信 (宛先サーバーまたはクライアントへの) に関連するトラフィック フローの詳細は、各シナリオのポートの概要図に示されています。 たとえば、実際には TCP 443 は着信 (エッジ プロキシまたはリバース プロキシへの) のみで、プロトコル (TCP) の観点から見た場合のみ双方向のフローになります。 さらに、図は、ネットワーク アドレス変換 (NAT) が発生したとき (着信で宛先アドレスが変更され、発信で発信元アドレスが変更されます) に変化するトラフィックの特性を示しています。 外部および内部ファイアウォールの例とサーバー インターフェイスは、参考としてのみ示されています。 最後に、必要な場合のために、既定のゲートウェイとルートの関係の例が示されています。 また、図では、リバースプロキシとエッジサーバーの両方の外部 DNS ゾーンを表すために <EM>.Com</EM> dns ゾーンを使用しており、 <EM>.net</EM> DNS ゾーンは内部 DNS ゾーンを参照していることにも注意してください。



</div>

Microsoft Lync Server 2013 の新規作成では、IPv6 アドレスのサポートがサポートされています。 IPv4 アドレス指定と同じように、IPv6 アドレスを、割り当てられた IPv6 アドレス スペースの一部になるように割り当てる必要があります。 このトピックのアドレスは、例としてのみ使用されています。 展開で機能する IPv6 アドレスを取得して正しいスコープを指定し、内部および外部アドレスと相互運用する必要があります。 Windows Server では、二重化された IPv6 操作と IPv4 から IPv6 への通信にとって重要な機能が *デュアルスタック*と呼ばれています。 デュアル スタックは、IPv4 および IPv6 用の別個のネットワーク スタックです。 デュアル スタックを使用すると、IPv4 および IPv6 用のアドレスを同時に割り当て、要件に基づいて、サーバーが他のホストやクライアントと通信できるようになります。

IPv6 アドレス指定に使用する一般的なアドレスの種類は、IPv6 グローバルアドレス (パブリック IPv4 アドレスと類似)、IPv6 の一意のローカルアドレス (プライベート IPv4 アドレスの範囲に似ている)、IPv6 リンクローカルアドレス (Windows Server の IPv4 では自動プライベート IP アドレスに似ています) です。

IPv6 から IPv4 に変換 (一般に NAT64 と呼ばれます) したり、IPv6 から IPv6 に変換 (一般に NAT66 と呼ばれます) したりするネットワーク アドレス変換 (NAT) テクノロジが存在します。 NAT テクノロジが存在することは、Lync Server エッジサーバーに提示された5つのシナリオが引き続き有効であることを意味します。

<div>


> [!WARNING]  
> IPv6 は複雑なトピックで、Windows server レベルおよび Lync Server 2013 レベルで割り当てたアドレスが期待どおりに機能するように、ネットワークチームとインターネットプロバイダーについて慎重に計画する必要があります。 IPv6 アドレス指定および計画に関するその他のリソースについては、このトピックの最後にあるリンクを参照してください。



</div>

![899546d4-2eef4-4d2-8317-51c5f699cd2a](images/Gg398823.899546d4-2eef-44d2-8317-51c5f699cd2a(OCS.15).jpg "899546d4-2eef4-4d2-8317-51c5f699cd2a")

<div>


> [!IMPORTANT]  
> 通話受付管理 (CAC) を使用している場合でも、エッジサーバーの内部インターフェイスに IPv4 アドレスを割り当てる必要があります。 CAC は IPv4 アドレスを使用しており、動作可能な IPv4 アドレスが存在する必要があります。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [証明書の概要-Lync Server 2013 での NAT を使用したプライベート IP アドレスを使用した拡張統合エッジ、DNS 負荷分散](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)

  - [ポートの概要-Lync Server 2013 での NAT を使用したプライベート IP アドレスを使用した拡張統合エッジ、DNS 負荷分散](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [DNS の概要-Lync Server 2013 での NAT を使用したプライベート IP アドレスを使用した拡張統合エッジ、DNS 負荷分散](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[IP バージョン6アドレス指定アーキテクチャ](https://tools.ietf.org/html/rfc4291)  
[IPv6 グローバルユニキャストアドレス形式](https://tools.ietf.org/html/rfc3587)  
[一意のローカル IPv6 ユニキャストアドレス](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

