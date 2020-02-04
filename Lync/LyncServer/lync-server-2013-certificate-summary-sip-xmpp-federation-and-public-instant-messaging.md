---
title: 証明書の概要-SIP、XMPP フェデレーション、パブリックインスタントメッセージ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49105659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fc3b7a1745d045954fb06403dbb3359fb699a29
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>証明書の概要-Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-15_

Microsoft Lync Server 2013、Lync Server 2010、および Office Communications Server とのフェデレーションに必要な証明書は、通常、エッジサーバーに対して構成、要求、および割り当てる証明書によって満たされます。

拡張メッセージングとプレゼンスプロトコル (XMPP) パートナーとの通信を有効にして確立するための証明書要件は、お使いの XMPP ドメインのエントリを追加する必要があります。 サブジェクトの代替名 (SAN) として証明書に含まれているレコードは、XMPP 通信に参加できるドメインです。 ドメイン全体で XMPP を有効にする場合や、ユーザーのサブセットに対して XMPP を有効にしている場合は、ドメインのルートレベルのドメイン (たとえば、contoso.com) にすることができます (例: corp.contoso.com)。

パブリックインスタントメッセージング接続用の証明書を構成するには、America Online (AOL) には証明書または証明書が必要であることを除いて、他の SIP フェデレーションタイプまたは標準エッジサーバーの証明書とはまったく異なるものがあることに注意してください。エッジプールの場合は、クライアント EKU も含まれます。 クライアント EKU は証明書に追加されたものであり、エッジサーバーに割り当てられている外部公開証明書の一部です。

エッジサーバーの展開に必要な証明書の要件を満たしていることを確認するには、 **「関連**項目」のセクションに記載されているトピックを確認してください。

<div>



<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>コンポーネント</th>
<th>サブジェクト名</th>
<th>サブジェクトの代替名 (SAN)</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部/アクセスエッジ</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>contoso.com</p>



> [!NOTE]
> Contoso.com XMPP 名前空間をサポートするには


<p>sip.fabrikam.com</p>



> [!NOTE]
> Fabrikam.com SIP 名前空間をサポートするには


<p>fabrikam.com</p>



> [!NOTE]
> Fabrikam.com XMPP 名前空間をサポートするには

</td>
<td><p>証明書はパブリック CA からである必要があります。また、AOL とのパブリック IM 接続を展開する場合は、サーバーの EKU とクライアントの EKU を持っている必要があります。 証明書は、次のための外部エッジサーバーインターフェイスに割り当てられます。</p>
<ul>
<li><p>アクセス エッジ サービス</p></li>
<li><p>Web 会議エッジ サービス</p></li>
<li><p>音声ビデオ エッジ サービス</p></li>
</ul>



> [!NOTE]
> 技術的には、証明書は A/V Edge に割り当てられません。 セキュリティで保護された通信と認証は、メディアリレー認証サービス (MRAS) を通じて管理されます。 MRAS では、エッジサーバーの内部インターフェイスに割り当てられている証明書が使用されます。


<p>San は、トポロジビルダーの定義に基づいて、自動的に証明書に追加されることに注意してください。 必要に応じて、必要に応じて SAN エントリを追加します。これには、サポートが必要な追加の SIP ドメインや他のエントリも含まれます。 サブジェクト名は SAN でレプリケートされ、正しい操作のために存在している必要があります。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での XMPP 構成の例  - Google Talk との XMPP フェデレーション](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Lync Server 2013 でエッジ サーバー証明書を計画する](lync-server-2013-plan-for-edge-server-certificates.md)  
[証明書の概要 - Lync Server 2013 内の NAT を使用したプライベート IP アドレスを持つ単一統合エッジ](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[証明書の概要 - Lync Server 2013 のパブリック IP アドレスを使用する単一の統合エッジ](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[証明書の概要 - Lync Server 2013 での拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[Lync Server 2013 の証明書の概要 - 拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[証明書の概要 - Lync Server 2013 の拡張統合エッジ (ロード バランサー機器を使用)](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

