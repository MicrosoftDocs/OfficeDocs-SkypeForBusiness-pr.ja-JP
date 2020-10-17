---
title: 証明書の概要-SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング
description: 証明書の概要-SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング。
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
ms.openlocfilehash: 565d3b935d304aa09588688bd8d71948b1b3ec3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572143"
---
# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>証明書の概要-Lync Server 2013 の SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-15_

Microsoft Lync Server 2013、Lync Server 2010、および Office Communications Server とのフェデレーションに必要な証明書は、通常、構成した証明書、およびエッジサーバーの要求と割り当てによって満たされます。

拡張可能なメッセージングおよびプレゼンスプロトコル (XMPP) パートナーとの通信を有効または確立するための証明書の要件は、XMPP ドメインのエントリを追加する必要があります。 サブジェクトの別名 (SAN) として証明書に含まれているレコードは、XMPP 通信に参加できるドメインになります。 ドメイン全体に対して XMPP を有効にする場合はドメインをルートレベル ドメイン (例: contoso.com) とし、ユーザーのサブセットに対して XMPP を有効にする場合は子ドメイン (例: corp.contoso.com、finance.contoso.com) を選択できます。

パブリックインスタントメッセージング接続の証明書を構成するには、他の SIP フェデレーションタイプまたは標準エッジサーバー証明書には何も存在しないことに注意してください。ただし、America Online (AOL) には、クライアント EKU を含む証明書または証明書 (エッジプールの場合) が必要です。 クライアント EKU は証明書に追加され、エッジサーバーに割り当てられている外部公開証明書の一部です。

エッジサーバーの展開について正しい証明書要件を満たしていることを確認するには、 **「関連**項目」のセクションに記載されているトピックを確認してください。

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
<th>サブジェクト名の別名 (SAN)</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部/アクセス エッジ</p></td>
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
<td><p>証明書は、パブリック CA からのものである必要があり、AOL とのパブリック IM 接続を展開する場合は、サーバー EKU とクライアント EKU を持っている必要があります。 証明書は、次のような外部エッジサーバーインターフェイスに割り当てられます。</p>
<ul>
<li><p>アクセス エッジ サービス</p></li>
<li><p>Web 会議エッジ サービス</p></li>
<li><p>音声ビデオ エッジ サービス</p></li>
</ul>



> [!NOTE]
> 技術的には、音声ビデオエッジに証明書が割り当てられることはありません。 セキュリティで保護された通信と認証は、メディアリレー認証サービス (MRAS) を通じて管理されます。 MRAS は、エッジサーバーの内部インターフェイスに割り当てられた証明書を使用します。


<p>SAN は、トポロジ ビルダーの定義に基づいて自動的に証明書に追加されます。追加の SIP ドメインで必要な SAN エントリや、サポートする必要がある他のエントリを追加します。SAN にはサブジェクト名がレプリケートされるため、正常に動作するためにはサブジェクト名が存在している必要があります。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の XMPP 構成の例-Google Talk との XMPP フェデレーション](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Lync Server 2013 でエッジサーバー証明書を計画する](lync-server-2013-plan-for-edge-server-certificates.md)  
[証明書の概要-Lync Server 2013 で NAT を使用するプライベート IP アドレスを持つ単一統合エッジ](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[証明書の概要-Lync Server 2013 のパブリック IP アドレスを使用する単一統合エッジ](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[証明書の概要-Lync Server 2013 での NAT を使用したプライベート IP アドレスを使用した拡張統合エッジ、DNS 負荷分散](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[証明書の概要-Lync Server 2013 での拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[証明書の概要-Lync Server 2013 でのハードウェアロードバランサーを使用した拡張統合エッジ](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

