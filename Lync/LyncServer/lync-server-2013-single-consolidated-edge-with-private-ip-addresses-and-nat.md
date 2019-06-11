---
title: 'Lync Server 2013: プライベート IP アドレスと NAT を用いた単一統合エッジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Single consolidated edge with private IP addresses and NAT
ms:assetid: e1e5189e-f17d-45e9-b177-e0e6f97f8951
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399001(v=OCS.15)
ms:contentKeyID: 48185691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f37395f840e8811d343f11f6ee2a84bd4fcfbf82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="single-consolidated-edge-with-private-ip-addresses-and-nat-in-lync-server-2013"></a>Lync Server 2013 におけるプライベート IP アドレスと NAT を用いた単一統合エッジ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-08_

組織で、15000アクセスエッジサービスクライアント接続、1000アクティブな Lync Server Web 会議サービスクライアント接続、および500の同時 A/V Edge セッションのサポートが必要な場合、エッジサーバーの高可用性は使用できません。重要: このトポロジは、ハードウェアコストの削減と展開の簡素化という利点を提供します。 容量を増やす必要がある場合、または高可用性が必要な場合は、スケーリングされた統合エッジサーバートポロジを展開する必要があります。 詳細については、次のいずれかを参照してください。

  - <span></span>  
    [Lync Server 2013 における拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [Lync Server 2013 での拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [Lync Server 2013 のハードウェア ロード バランサーによる拡張統合エッジ](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

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

**単一の統合エッジトポロジ**

![d9b889c1-587c-4732-9b68-841186ccff78](images/Gg399001.d9b889c1-587c-4732-9b68-841186ccff78(OCS.15).jpg "d9b889c1-587c-4732-9b68-841186ccff78")

<div>


> [!IMPORTANT]  
> 通話受付制御 (CAC) を使用している場合でも、エッジサーバーの内部インターフェイスに IPv4 アドレスを割り当てる必要があります。 CAC は IPv4 アドレスを使用し、操作には使用できるようにする必要があります。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [証明書の概要 - Lync Server 2013 内の NAT を使用したプライベート IP アドレスを持つ単一統合エッジ](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [ポートの概要 - Lync Server 2013 の NAT を使用したプライベート IP アドレスを含む単一統合エッジ](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [DNS の概要 - Lync Server 2013 の単一統合エッジ (NAT によるプライベート IP アドレスを使用)](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

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

