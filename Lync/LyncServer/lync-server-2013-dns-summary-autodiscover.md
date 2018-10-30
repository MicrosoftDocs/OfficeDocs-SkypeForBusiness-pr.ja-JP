---
title: Lync Server 2013 での DNS 概要 - 自動検出
TOCTitle: Lync Server 2013 での DNS 概要 - 自動検出
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ945644(v=OCS.15)
ms:contentKeyID: 52056677
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での DNS 概要 - 自動検出

 

_**トピックの最終更新日:** 2015-03-09_

自動検出は、HTTP または HTTPS 経由の通信を受け入れる柔軟なサービスです。このためには、自動検出サービスをホストするサーバーによって使用されるドメイン ネーム システム (DNS) と証明書を正しく設定する必要があります。証明書要件については、「[証明書の概要 - 自動検出](lync-server-2013-certificate-summary-autodiscover.md)」で説明しています。


> [!IMPORTANT]
> Lync Server クライアントの DNS 参照ロジックでは、特定の順序で解決を使用します。DNS には、必ず lyncdiscoverinternal.&lt;domain&gt; と lyncdiscover.&lt;domain&gt; の両方を含める必要があります。lyncdiscoverinternal.&lt;domain&gt; レコードを除外すると、内部クライアントが目的のサービスに接続できなくなるか、自動検出サービスからの不適切な応答を受信します。



### 内部 DNS レコード

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>レコードの種類</th>
<th>ホスト名</th>
<th>解決先</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>Lyncdiscoverinternal.&lt;internal domain name&gt;</p></td>
<td><p>ディレクター プール (ディレクター プールがある場合) またはフロント エンド プール (ディレクターがない場合) の内部 Web サービス FQDN</p></td>
</tr>
<tr class="even">
<td><p>A (ホスト、IPv6 の場合は AAAA)</p></td>
<td><p>lyncdiscoverinternal.&lt;internal domain name&gt;</p></td>
<td><p>ディレクター プール (ディレクター プールがある場合) またはフロント エンド プール (ディレクターがない場合) の内部 Web サービス IP アドレス (ロード バランサーを使用する場合は仮想 IP (VIP) アドレス)</p></td>
</tr>
</tbody>
</table>


次の外部 DNS レコードの 1 つを作成する必要があります。

### 外部 DNS レコード

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>レコードの種類</th>
<th>ホスト名</th>
<th>解決先</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover.&lt;sipdomain&gt;</p></td>
<td><p>ディレクター プール (ディレクター プールがある場合) またはフロント エンド プール (ディレクターがない場合) の外部 Web サービス FQDN</p></td>
</tr>
<tr class="even">
<td><p>A (ホスト、IPv6 の場合は AAAA)</p></td>
<td><p>lyncdiscover.&lt;sipdomain&gt;</p></td>
<td><p>リバース プロキシの外部またはパブリック IP アドレス</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> 外部トラフィックはリバース プロキシを経由します。


> [!NOTE]
> モバイル デバイスのクライアントでは、異なるドメインからの複数の SSL (Secure Sockets Layer) 証明書がサポートされません。つまり、HTTPS では、異なるドメインへの CNAME のリダイレクトがサポートされません。たとえば、director.contoso.net のアドレスにリダイレクトされる lyncdiscover.contoso.com の DNS CNAME レコードは、HTTPS ではサポートされません。このようなトポロジでは、CNAME のリダイレクトが HTTP で解決されるように、モバイル デバイスのクライアントは、最初の要求に対して HTTP を使用する必要があります。その後、以降の要求については HTTPS を使用します。このシナリオをサポートするには、ポート 80 (HTTP) の Web 公開ルールを使用して、リバース プロキシを構成する必要があります。詳細については、「<a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 での、モビリティに合わせたリバース プロキシの構成</a>」の「ポート 80 の Web 公開ルールを作成するには」を参照してください。HTTPS では、同じドメインへの CNAME のリダイレクトはサポートされます。この場合、リダイレクト先のドメインの証明書で元のドメインがカバーされます。


## 関連項目

#### タスク

[Lync Server 2013 での、モビリティに合わせたリバース プロキシの構成](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  

#### 概念

[証明書の概要 - 自動検出](lync-server-2013-certificate-summary-autodiscover.md)

