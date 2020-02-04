---
title: 'Lync Server 2013: フロントエンド プールの DNS 要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 252bacd9818676155dcab0f84e3e1c5fcdb31b5d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a>Lync Server 2013 のフロントエンド プールの DNS 要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-07_

この手順を完了するには、ドメイン管理者グループのメンバー、または DnsAdmins グループのメンバーとして、サーバーまたはドメインに最低でもログオンしている必要があります。

トポロジビルダーでトポロジを公開する前に、必要なドメインネームシステム (DNS) レコードを構成する必要があります。 さらに、Lync Server 2013 の展開の構成で使用される完全修飾ドメイン名 (Fqdn) の一部は論理的であり、物理サーバーの Fqdn ではないため、公開前に追加の DNS 構成が必要になります。

<div>


> [!WARNING]  
> Lync Server 2013 では、単一ラベルのドメインはサポートされていません。 たとえば、 <STRONG>local</STRONG>という名前のルートドメインを持つフォレストはサポートされていますが、 <STRONG>local</STRONG>という名前のルートドメインはサポートされていません。 詳細については、「Microsoft サポート技術情報の記事300684」「単一ラベルの DNS 名を使用してドメイン用の Windows を構成する方法について」を参照してください。 "at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 300684</A>。



</div>

<div>


> [!IMPORTANT]  
> 指定する名前が、サーバーで構成されているコンピューター名と同じである必要があります。 既定では、ドメインに参加していないコンピューターのコンピューター名は、FQDN ではなく、短い名前です。 トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。 Lync Server、エッジサーバー、およびプールを実行しているサーバーの Fqdn を割り当てるときは、標準の文字 (-Z、a ~ z、0 ~ 9、ハイフンを含む)<STRONG>のみを使用</STRONG>します。 Unicode 文字およびアンダースコアは使用しないでください。 FQDN の非標準文字は、多くの場合、外部 DNS と公共の証明機関 (Ca) でサポートされていません (証明書の SN に FQDN を割り当てる必要があります)。



</div>

トポロジが展開された後にトポロジを操作する前に、次の Active Directory と DNS レコードが作成されていることを確認してください (具体的な機能の設定が必要な場合)。

  - トポロジに存在する各サーバーの役割は、Active Directory オブジェクトとして公開されます (コンピューターをドメインに参加させることによって、この操作を実行します)。

  - DNS A レコードが各サーバーに存在します。

  - Sipinternaltls \_\_tcp の形式でクライアントに自動ログオンを使用することを計画している場合は、各 SIP ドメインに対して DNS SRV レコードが存在します。\<SIP ドメイン\>。 クライアントに手動構成を使用する場合は、このレコードは必要ありません。

  - 構成された簡易 URL ごとに1つの DNS A レコード。通常は、会議、ダイヤルイン、lwa、スケジューラの4種類があります。 さらに、管理者の簡単な URL は、Lync Server 2013 コントロールパネルへのアクセスに使用する特別な URL です。

  - SQL Server が実行されているサーバーは、ドメインに参加し、トポロジビルダーが発行元のコンピューターからアクセスできる必要があります。

この表は、計画セクションに示されているリファレンスアーキテクチャを示しています。 詳細については、計画ドキュメントの「 [Lync Server 2013 での外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」を参照してください。

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a>フロントエンドプールに必要な DNS レコード

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>場所</th>
<th>型</th>
<th>FQDN</th>
<th>マップ先/コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (DNS ロードバランシング)。 プール内の各フロントエンドサーバーの IP アドレスに対して DNS A レコードが必要です。プールの FQDN にマッピングします。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (仮想 IP (VIP) (ハードウェアロードバランサー)。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>fe01.contoso.net</p>
<p>fe02.contoso.net</p>
<p>fe03.contoso.net</p>
<p>…</p></td>
<td><p>Pool01 フロントエンドサーバー (ノード 1)。</p>
<p>Pool01 フロントエンドサーバー (ノード 2)</p>
<p>Pool01 フロントエンドサーバー (ノード 3)</p>
<p>…</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>fe02.contoso.net</p></td>
<td><p>Pool01 フロントエンドサーバー (ノード 2)</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>lsweb.contoso.net</p></td>
<td><p>クライアントとサーバーの web トラフィックの Pool01 (VIP)。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>sqlbe.contoso.net</p></td>
<td><p>SQL Server 2008 R2 を実行している Pool01 バックエンドサーバー。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Lync Phone Edition の場合、または DNS SRV レコードのないクライアントの自動ログオン、および厳密なドメイン照合の場合に必須です。 すべてのケースで必須ではありません。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>sip.fabrikam.com</p></td>
<td><p>第2の SIP ドメインを仮定します。 Lync Phone Edition の場合は必須。 DNS SRV レコードがないクライアントの自動ログオン、および厳密なドメインの一致の場合。 すべてのケースで必須ではありません。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>内部で公開されたダイヤルイン会議の単純な URL –フロントエンドサーバー (またはインストールされている場合はディレクター) が単純な URL クエリに応答します。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>内部で公開された会議の単純な URL –フロントエンドサーバー (またはインストールされている場合はディレクター) が単純な URL クエリに応答します。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>admin.contoso.com</p>
<p>同期</p></td>
<td><p>省略可能なレコード。 Lync Server 2013 コントロールパネルが内部的に公開されている場合は、フロントエンドサーバー (またはディレクター (インストールされている場合はディレクター)) で簡単な URL クエリに応答します。 ホスト名のみ (ドメイン名は不要) をお勧めします。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> VIP = ハードウェアロードバランサーの仮想 IP アドレス



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a>フロントエンドプールの DNS SRV レコード


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>場所</th>
<th>型</th>
<th>FQDN</th>
<th>ターゲット FQDN</th>
<th>ポート</th>
<th>マップ先/コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls の _tcp</p></td>
<td><p>pool01.contoso.com</p></td>
<td><p>5061</p></td>
<td><p>Lync 2013 クライアントを内部で動作するように自動構成する場合に必要です。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls. .com _tcp</p></td>
<td><p>pool01.fabrikam.com</p></td>
<td><p>5061</p></td>
<td><p>Lync 2013 クライアントを内部で動作するように自動構成する場合に必要です。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_ntp._udp.contoso.com</p></td>
<td><p>dc01.contoso.com</p></td>
<td><p>123</p></td>
<td><p>Lync Phone Edition を実行しているデバイスに必要なネットワークタイムプロトコル (NTP) ソース。 内部では、これはドメインコントローラーを指している必要があります。 ドメインコントローラーが定義されていない場合は、NTP サーバー time.windows.com を使います。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

