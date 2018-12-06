---
title: 証明書の概要 - SIP、XMPP フェデレーション、パブリック インスタント メッセージング
TOCTitle: 証明書の概要 - SIP、XMPP フェデレーション、パブリック インスタント メッセージング
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49115231
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 証明書の概要 - SIP、XMPP フェデレーション、パブリック インスタント メッセージング

 

_**トピックの最終更新日:** 2015-03-09_

通常、Microsoft Lync Server 2013、Lync Server 2010、および Office Communications Server のフェデレーションで必要な証明書の要件は、エッジ サーバーに対して構成および要求し、割り当てる証明書によって満たされます。

Extensible Messaging and Presence Protocol (XMPP) パートナーとの通信を有効にして確立するための証明書要件では、XMPP ドメインの追加エントリが必要になります。サブジェクトの別名 (SAN) として証明書に含まれているレコードは、XMPP 通信に参加できるドメインになります。ドメイン全体に対して XMPP を有効にする場合はドメインをルートレベル ドメイン (例: contoso.com) とし、ユーザーのサブセットに対して XMPP を有効にする場合は子ドメイン (例: corp.contoso.com、finance.contoso.com) を選択できます。

パブリック インスタント メッセージング接続の証明書の構成は、America Online (AOL) では 1 つまたは複数 (エッジ プールの場合) の証明書にもクライアント EKU を含めることが必要な点を除いて、他の種類の SIP フェデレーションや標準のエッジ サーバー証明書とまったく同じです。クライアント EKU は証明書に対する追加であり、エッジ サーバーに関連付けられた外部公開証明書の一部です。

エッジ サーバーの展開に対応する証明書要件を満たしていることを確認するには、「**関連項目**」の一覧にあるトピックを参照してください。



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
<th>サブジェクトの別名 (SAN)</th>
<th>コメント</th>
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
> contoso.com XMPP 名前空間をサポートするため

</div>
<p>sip.fabrikam.com</p>

> [!NOTE]
> fabrikam.com SIP 名前空間をサポートするため

</div>
<p>fabrikam.com</p>

> [!NOTE]
> fabrikam.com XMPP 名前空間をサポートするため

</div></td>
<td><p>証明書は公的 CA のものである必要があります。また、AOL とのパブリック IM 接続を展開する場合は、サーバー EKU およびクライアント EKU が必要です。証明書は、次のエッジの外部 エッジ サーバー インターフェイスに割り当てられます。</p>
<ul>
<li><p>アクセス エッジ サービス</p></li>
<li><p>Web 会議エッジ サービス</p></li>
<li><p>音声ビデオ エッジ サービス</p></li>
</ul>

> [!NOTE]
> 技術的に、証明書は A/V エッジには割り当てられません。セキュリティで保護された通信と認証は、メディア リレー認証サービス (MRAS) によって管理されます。MRAS はエッジ サーバーの内部インターフェイスに割り当てられた証明書を使用します。

</div>
<p>SAN は、トポロジ ビルダーの定義に基づいて自動的に証明書に追加されます。追加の SIP ドメインで必要な SAN エントリや、サポートする必要がある他のエントリを追加します。SAN にはサブジェクト名がレプリケートされるため、正常に動作するためにはサブジェクト名が存在している必要があります。</p></td>
</tr>
</tbody>
</table>


## 関連項目

#### タスク

[Lync Server 2013 での XMPP 構成の例 - Google Talk との XMPP フェデレーション](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  

#### 概念

[Lync Server 2013 でエッジ サーバー証明書を計画する](lync-server-2013-plan-for-edge-server-certificates.md)  
[証明書の概要 - Lync Server 2013 内の NAT を使用したプライベート IP アドレスを持つ単一統合エッジ](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[証明書の概要 - Lync Server 2013 のパブリック IP アドレスを使用する単一の統合エッジ](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[証明書の概要 - Lync Server 2013 での拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)  
[Lync Server 2013 の証明書の概要 - 拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[証明書の概要 - Lync Server 2013 の拡張統合エッジ (ロード バランサー機器を使用)](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

