---
title: 'Lync Server 2013: ハードウェアロードバランサーによる拡張統合エッジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled consolidated edge with hardware load balancers
ms:assetid: 6783e225-9677-415a-8731-0bf2e2c4cf8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398478(v=OCS.15)
ms:contentKeyID: 48184353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 125f9a598d2d768a7417489f1e2004a1cbb17cf8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511004"
---
# <a name="scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Lync Server 2013 での拡張統合エッジとロードバランサー機器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-21_

エッジプールトポロジでは、2つ以上のエッジサーバーが、データセンターの境界ネットワークの負荷分散プールとして展開されます。 ハードウェア負荷分散は、外部および内部エッジサーバーインターフェイスの両方へのトラフィックに使用されます。

組織で15000を超えるアクセスエッジサービスクライアント接続、1000アクティブ Web 会議エッジサービスクライアント接続、または500の同時音声ビデオエッジサービスセッションのサポートが必要であり、エッジサーバーの高可用性が重要な場合、このトポロジはスケーラビリティとフェールオーバーのサポートの利点を提供します。

この図は、エッジサーバーとフロントエンドプールまたはサーバーの間の内部ネットワークに展開されたオプションのサーバーの役割であるディレクターを示していません。 . ディレクターのトポロジの詳細については、「 [Lync Server 2013 でのディレクターに必要なコンポーネント](lync-server-2013-components-required-for-the-director.md)」を参照してください。

<div>


> [!NOTE]  
> 図は方向や IP アドレス指定の例を示すものであり、正確な着信および発信トラフィックがある実際の通信フローを表現することが目的ではありません。 図は、可能なトラフィックの大まかなビューを示しています。 リスニング ポートへの着信および宛先サーバーまたはクライアントへの発信に関連するトラフィック フローの詳細が、シナリオごとにポートの概要図で示されています。 たとえば、TCP 443 は実際には受信 (エッジサーバーまたはリバースプロキシ) のみであり、プロトコル (TCP) の観点からの双方向のフローに過ぎません。 さらに、図は、NAT (ネットワーク アドレス変換) の発生時に変更されるトラフィックの性質を示しています (宛先アドレスは受信時に変更され、ソース アドレスは送信時に変更されます)。 外部および内部ファイアウォールの例とサーバー インターフェイスは、参考としてのみ示されています。 最後に、必要な場合のために、既定のゲートウェイとルートの関係の例が示されています。 また、図では、リバースプロキシとエッジサーバーの両方の外部 DNS ゾーンを表すために <EM>.Com</EM> dns ゾーンを使用しており、 <EM>.net</EM> DNS ゾーンは内部 DNS ゾーンを参照していることにも注意してください。



</div>

Microsoft Lync Server 2013 の新規作成では、IPv6 アドレスのサポートがサポートされています。 IPv4 アドレス指定と同じように、IPv6 アドレスを、割り当てられた IPv6 アドレス スペースの一部になるように割り当てる必要があります。 このトピックのアドレスは、例としてのみ使用されています。 展開で機能する IPv6 アドレスを取得して正しいスコープを指定し、内部および外部アドレスと相互運用する必要があります。 Windows Server では、二重化された IPv6 操作と IPv4 から IPv6 への通信にとって重要な機能が *デュアルスタック*と呼ばれています。 デュアル スタックは、IPv4 および IPv6 用の別個のネットワーク スタックです。 デュアル スタックを使用すると、IPv4 および IPv6 用のアドレスを同時に割り当て、要件に基づいて、サーバーが他のホストやクライアントと通信できるようになります。

IPv6 アドレス指定に使用する一般的なアドレスの種類は、IPv6 グローバルアドレス (パブリック IPv4 アドレスと類似)、IPv6 の一意のローカルアドレス (プライベート IPv4 アドレスの範囲に似ている)、IPv6 リンクローカルアドレス (Windows Server の IPv4 では自動プライベート IP アドレスに似ています) です。

IPv6 から IPv4 に変換 (一般に NAT64 と呼ばれます) したり、IPv6 から IPv6 に変換 (一般に NAT66 と呼ばれます) したりするネットワーク アドレス変換 (NAT) テクノロジが存在します。 NAT テクノロジが存在することは、Lync Server エッジサーバーに提示された5つのシナリオが引き続き有効であることを意味します。

<div>


> [!WARNING]  
> IPv6 は複雑なトピックで、Windows server レベルおよび Lync Server 2013 レベルで割り当てたアドレスが期待どおりに機能するように、ネットワークチームとインターネットプロバイダーについて慎重に計画する必要があります。 IPv6 アドレス指定と計画に関するその他の技術情報については、このトピックの最後にあるリンクを参照してください。



</div>

**ハードウェア ロード バランサーの構成**

詳細については、「 [Lync Server 2013 の外部ユーザーアクセスに必要なコンポーネント](lync-server-2013-components-required-for-external-user-access.md)」の「音声ビデオエッジに対するハードウェアロードバランサーの要件」セクションを参照してください。

**拡張統合エッジ トポロジ (ハードウェア負荷分散)**

![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")

<div>


> [!IMPORTANT]  
> 通話受付管理 (CAC) を使用している場合でも、エッジサーバーの内部インターフェイスに IPv4 アドレスを割り当てる必要があります。 CAC は IPv4 アドレスを使用しており、動作可能な IPv4 アドレスが存在する必要があります。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [証明書の概要-Lync Server 2013 でのハードウェアロードバランサーを使用した拡張統合エッジ](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [ポートの概要-Lync Server 2013 の拡張統合エッジ (ロードバランサー機器を含む)](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [DNS の概要-Lync Server 2013 でのハードウェアロードバランサーを使用した拡張統合エッジ](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

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

