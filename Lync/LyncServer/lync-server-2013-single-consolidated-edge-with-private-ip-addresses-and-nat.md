---
title: 'Lync Server 2013: プライベート IP アドレスと NAT を使用する単一統合エッジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Single consolidated edge with private IP addresses and NAT
ms:assetid: e1e5189e-f17d-45e9-b177-e0e6f97f8951
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399001(v=OCS.15)
ms:contentKeyID: 48185691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60beb67ec6d2aca79210f06b9a4dabe8370649cb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="single-consolidated-edge-with-private-ip-addresses-and-nat-in-lync-server-2013"></a>Lync Server 2013 でのプライベート IP アドレスと NAT を使用する単一統合エッジ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-08_

組織で15000アクセスエッジサービスクライアント接続のサポートが必要な場合、1000アクティブな Lync Server Web 会議サービスクライアント接続、および500の同時音声ビデオエッジセッション、およびエッジサーバーの高可用性は重要ではないため、このトポロジでは、ハードウェアコストの削減と展開の簡素化という利点がありません。 より多くの容量が必要な場合、または高可用性が必要な場合は、拡張統合エッジサーバートポロジを展開する必要があります。 詳細については、以下を参照してください。

  - <span></span>  
    [Lync Server 2013 での拡張統合エッジ、NAT を使用したプライベート IP アドレスを使用した DNS 負荷分散](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [Lync Server 2013 の拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [Lync Server 2013 での拡張統合エッジとロードバランサー機器](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

この図は、エッジサーバーとフロントエンドプールまたはサーバーの間の内部ネットワークに展開されたオプションのサーバーの役割であるディレクターを示していません。 ディレクターのトポロジの詳細については、「 [Lync Server 2013 でのディレクターに必要なコンポーネント](lync-server-2013-components-required-for-the-director.md)」を参照してください。 この図は、単一のリバース プロキシを表しています。

<div>


> [!NOTE]  
> 以下の図には、方向と IP アドレス指定の例が示されていますが、正しい受信トラフィックと送信トラフィックを使用した実際の通信フローを表すことを目的としていません。 図は、可能なトラフィックの大まかなビューを示しています。 着信 (リッスン ポートへの) および発信 (宛先サーバーまたはクライアントへの) に関連するトラフィック フローの詳細は、各シナリオのポートの概要図に示されています。 たとえば、実際には TCP 443 は着信 (エッジ プロキシまたはリバース プロキシへの) のみで、プロトコル (TCP) の観点から見た場合のみ双方向のフローになります。 さらに、図は、ネットワーク アドレス変換 (NAT) が発生したとき (着信で宛先アドレスが変更され、発信で発信元アドレスが変更されます) に変化するトラフィックの特性を示しています。 外部および内部ファイアウォールの例とサーバー インターフェイスは、参考としてのみ示されています。 最後に、必要な場合のために、既定のゲートウェイとルートの関係の例が示されています。 また、図では、リバースプロキシとエッジサーバーの両方の外部 DNS ゾーンを表すために<EM>.Com</EM> dns ゾーンを使用しており、 <EM>.net</EM> DNS ゾーンは内部 DNS ゾーンを参照していることにも注意してください。



</div>

Microsoft Lync Server 2013 の新規作成では、IPv6 アドレスのサポートがサポートされています。 IPv4 アドレス指定と同じように、IPv6 アドレスを、割り当てられた IPv6 アドレス スペースの一部になるように割り当てる必要があります。 このトピックのアドレスは、例としてのみ使用されています。 展開で機能する IPv6 アドレスを取得して正しいスコープを指定し、内部および外部アドレスと相互運用する必要があります。 Windows Server では、二重化された IPv6 操作と IPv4 から IPv6 への通信にとって重要な機能が*デュアルスタック*と呼ばれています。 デュアル スタックは、IPv4 および IPv6 用の別個のネットワーク スタックです。 デュアル スタックを使用すると、IPv4 および IPv6 用のアドレスを同時に割り当て、要件に基づいて、サーバーが他のホストやクライアントと通信できるようになります。

IPv6 アドレス指定に使用する一般的なアドレスの種類は、IPv6 グローバルアドレス (パブリック IPv4 アドレスと類似)、IPv6 固有のローカルアドレス (プライベート IPv4 アドレスの範囲に類似)、IPv6 リンクローカルアドレス (自動プライベート IP に似ています) です。IPv4 用 Windows Server のアドレス)

IPv6 から IPv4 に変換 (一般に NAT64 と呼ばれます) したり、IPv6 から IPv6 に変換 (一般に NAT66 と呼ばれます) したりするネットワーク アドレス変換 (NAT) テクノロジが存在します。 NAT テクノロジが存在することは、Lync Server エッジサーバーに提示された5つのシナリオが引き続き有効であることを意味します。

<div>


> [!WARNING]  
> IPv6 は複雑なトピックで、Windows server レベルおよび Lync Server 2013 レベルで割り当てたアドレスが期待どおりに機能するように、ネットワークチームとインターネットプロバイダーについて慎重に計画する必要があります。 IPv6 アドレス指定および計画に関するその他のリソースについては、このトピックの最後にあるリンクを参照してください。



</div>

**単一統合エッジトポロジ**

![d9b889c1-587c-4732-9b68-841186ccff78](images/Gg399001.d9b889c1-587c-4732-9b68-841186ccff78(OCS.15).jpg "d9b889c1-587c-4732-9b68-841186ccff78")

<div>


> [!IMPORTANT]  
> 通話受付管理 (CAC) を使用している場合でも、エッジサーバーの内部インターフェイスに IPv4 アドレスを割り当てる必要があります。 CAC は IPv4 アドレスを使用しており、動作可能な IPv4 アドレスが存在する必要があります。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [証明書の概要-Lync Server 2013 で NAT を使用するプライベート IP アドレスを持つ単一統合エッジ](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [ポートの概要-Lync Server 2013 で NAT を使用するプライベート IP アドレスを持つ単一統合エッジ](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [DNS の概要-Lync Server 2013 で NAT を使用するプライベート IP アドレスを持つ単一統合エッジ](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

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

