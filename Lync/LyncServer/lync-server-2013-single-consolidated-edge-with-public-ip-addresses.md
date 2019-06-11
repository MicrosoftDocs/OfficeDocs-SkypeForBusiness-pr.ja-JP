---
title: 'Lync Server 2013: パブリック IP アドレスを使用する単一統合エッジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Single consolidated edge with public IP addresses
ms:assetid: a92d1179-6a1f-4efe-908a-f8dfc5024f30
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205148(v=OCS.15)
ms:contentKeyID: 48185035
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bf6655c596be657d1779a404c6f1f5b108f3251
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Lync Server 2013 のパブリック IP アドレスを使用する単一統合エッジ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-08_

15000アクセスエッジサービスクライアント接続、1000アクティブな Lync Server Web 会議サービスクライアント接続、および500の同時 A/V Edge セッションのサポートが必要な場合、エッジサーバーの高可用性は重要ではありません。このトポロジでは、ハードウェアコストの削減と展開の簡素化という利点が提供されます。 容量を増やす必要がある場合、または高可用性が必要な場合は、スケーリングされた統合エッジサーバートポロジを展開する必要があります。

  - <span></span>  
    [Lync Server 2013 における拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [Lync Server 2013 での拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [Lync Server 2013 のハードウェア ロード バランサーによる拡張統合エッジ](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]  
> エッジサーバーでパブリック IP アドレスを使用している場合、エッジサーバー上の既定のゲートウェイは、ファイアウォールまたはルーターではなく、公開されている境界エッジのルーターまたはファイアウォールで、パブリックアドレスになります。 リバースプロキシは、外部境界ネットワークに関連付けられているルーターまたはファイアウォールを引き続き使用します。 リバースプロキシとパブリック IP アドレスを使ったエッジサーバーの違いは、リバースプロキシが依然として NAT を使用していて、エッジサーバーがルートリレーションシップを使用していることです。



</div>

この図には、エッジサーバーとフロントエンドプールまたはサーバー間の内部ネットワークに展開されたオプションのサーバー役割であるダイレクタは表示されません。 ディレクターのトポロジの詳細については、「 [Lync Server 2013 でディレクターに必要なコンポーネント](lync-server-2013-components-required-for-the-director.md)」を参照してください。 この図は、単一の逆プロキシを示しています。

<div>


> [!NOTE]  
> 次の図は、向きと IP アドレス指定の例を示していますが、正しい着信トラフィックと発信トラフィックでの実際の通信フローを示すものではありません。 この図は、可能なトラフィックの高レベルビューを示しています。 着信 (リッスンするポート) に関連するトラフィックフローと送信 (送信先サーバーまたはクライアント) は、各シナリオの [ポートの概要] ダイアグラムで表されます。 たとえば、TCP 443 は実際には (エッジまたは逆プロキシに対する) 受信のみであり、プロトコル (TCP) の観点からの双方向のフローにすぎません。 また、この図では、NAT (ネットワークアドレス変換) が発生したときのトラフィックの性質を示しています (宛先のアドレスが受信時に変更されると、送信時にソースアドレスが変更されます)。 外部および内部ファイアウォールの例とサーバーインターフェイスは、参照目的でのみ表示されます。 最後に、既定のゲートウェイとルートリレーションシップの例を示します (該当する場合)。 また、図では、リバースプロキシとエッジサーバーの両方の外部 DNS ゾーンを示すために<EM>.Com</EM> dns ゾーンを使用し、 <EM>.net</EM> DNS ゾーンは内部 dns ゾーンを参照していることにも注意してください。



</div>

Microsoft Lync Server 2013 の新機能は、IPv6 アドレス指定をサポートしています。 IPv4 アドレス指定と同じように、IPv6 アドレスは、割り当てられている IPv6 アドレス空間の一部であるため、アドレスを割り当てる必要があります。 このトピックの住所は、例としてのみ使用できます。 展開で機能する IPv6 アドレスを取得し、適切なスコープを指定して、内部および外部のアドレス指定と相互運用されるようにする必要があります。 Windows Server では、2つの*スタック*と呼ばれる、ipv6 操作と IPv4 から ipv6 への通信に重要な機能が提供されています。 デュアルスタックは、IPv4 と IPv6 のための独立した個別のネットワークスタックです。 デュアルスタックでは、IPv4 と IPv6 のアドレスを同時に割り当てることができます。また、要件に基づいてサーバーが他のホストやクライアントと通信できるようにします。

IPv6 アドレス指定に使用する一般的なアドレスの種類は、IPv6 のグローバルアドレス (パブリック IPv4 アドレスに似ています)、ipv6 固有のローカルアドレス (プライベート IPv4 アドレスの範囲に似ています)、IPv6 リンクローカルアドレス (自動プライベート IP に類似) です。IPv4 用 Windows Server のアドレス

IPv6 向けのネットワークアドレス変換技術 (NAT) が存在します。これにより、NAT IPv6 (通常は、NAT64 とも呼ばれます) と NAT IPv6 (通常は NAT66 と呼ばれます) を使用できます。 NAT 技術が存在することは、Lync Server Edge サーバーに対して提示された5つのシナリオが有効であることを意味します。

<div>


> [!WARNING]  
> IPv6 は複雑なトピックであり、ネットワークチームとインターネットプロバイダーによる慎重な計画を行う必要があります。これにより、Windows server レベルで割り当てるアドレスと Lync Server 2013 レベルで割り当てたアドレスが予期したとおりに動作するようになります。 IPv6 のアドレス指定と計画に関するその他のリソースについては、このトピックの最後にあるリンクを参照してください。



</div>

**パブリック IP アドレスのトポロジを使った単一の統合エッジ**

![2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d](images/JJ205148.2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d(OCS.15).jpg "2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d")

<div>


> [!IMPORTANT]  
> 通話受付制御 (CAC) を使用している場合でも、エッジサーバーの内部インターフェイスに IPv4 アドレスを割り当てる必要があります。 CAC は IPv4 アドレスを使用し、操作には使用できるようにする必要があります。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [証明書の概要 - Lync Server 2013 のパブリック IP アドレスを使用する単一の統合エッジ](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [ポートの概要 - Lync Server 2013 でパブリック IP アドレスを使用する単一の統合エッジ](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [DNS の概要 - Lync Server 2013 でパブリック IP アドレスを持つ単一統合エッジ](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[IP バージョン6アドレス体系](http://tools.ietf.org/html/rfc4291)  
[IPv6 グローバルユニキャストアドレス形式](http://tools.ietf.org/html/rfc3587)  
[一意のローカル IPv6 ユニキャストアドレス](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

