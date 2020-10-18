---
title: 'Lync Server 2013: フロントエンドプールの DNS 要件'
description: 'Lync Server 2013: フロントエンドプールの DNS 要件。'
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
ms.openlocfilehash: bfce90eccb8c8dff94d4122c96c4ca68ea9150f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574333"
---
# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a>Lync Server 2013 のフロントエンドプールの DNS 要件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-07_

この手順を正常に完了するには、最低限でも Domain Admins グループまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンしている必要があります。

トポロジビルダーでトポロジを公開する前に、必要なドメインネームシステム (DNS) レコードを構成する必要があります。 さらに、Lync Server 2013 の展開の構成で使用されている完全修飾ドメイン名 (Fqdn) の一部は論理的で、物理サーバーの Fqdn ではないため、公開する前に追加の DNS 構成が必要になります。

<div>


> [!WARNING]  
> Lync Server 2013 は、単一ラベルのドメインをサポートしていません。 たとえば、ルート ドメイン名が <STRONG>contoso.local</STRONG> であるフォレストはサポートされますが、<STRONG>local</STRONG> という名前のルート ドメインはサポートされません。 詳細については、「Microsoft サポート技術情報の記事300684」を参照してください。「単一ラベル DNS 名を使用してドメインに Windows を構成する」の「at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp ; kbid = 300684</A>」を参照してください。



</div>

<div>


> [!IMPORTANT]  
> 指定する名前が、サーバーに構成されているコンピューター名と同じである必要があります。 既定では、ドメインに参加していないコンピューターのコンピューター名は、FQDN ではなく短い名前です。 トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。 Lync Server、エッジサーバー、およびプールを実行しているサーバーの Fqdn を割り当てるときは、標準文字 (A ~ Z、a ~ z、0 ~ 9、およびハイフン)<STRONG>のみを使用</STRONG>します。 Unicode 文字およびアンダースコアは使用しないでください。 一般に、外部 DNS および公的証明機関 (CA) では、FQDN に非標準文字はサポートされていません (証明書で FQDN を SN に割り当てる必要がある場合)。



</div>

トポロジを展開した後でトポロジを運用する前に、次の Active Directory と DNS レコードが作成されていることを確認してください (特定の機能の決定に必要な場合)。

  - トポロジ内に存在する各サーバーの役割は、Active Directory オブジェクトとして公開されます (コンピューターをドメインに参加させることでこれを実現できます)。

  - DNS A レコードはサーバーごとに存在します。

  - \_Sipinternaltls tcp の形式でクライアントの自動ログオンを使用することを計画している場合は、SIP ドメインごとに DNS SRV レコードが存在します。 \_ \<SIP domain\> クライアントに手動構成を使用する場合、このレコードは不要です。

  - 構成済みの簡易 URL のそれぞれの DNS A レコードには、通常 meet、dialin、lwa、scheduler の 4 つがあります。 さらに、管理者の簡易 URL は、Lync Server 2013 コントロールパネルにアクセスするための特別な URL です。

  - SQL Server を実行しているサーバーは、ドメインに参加している必要があります。また、トポロジビルダーが公開しているコンピューターから到達可能である必要があります。

表は、「計画」セクションの参照アーキテクチャに従っています。 詳細については、「計画」のドキュメントの「 [Lync Server 2013 の外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md) 」を参照してください。

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
<th>マッピング先/コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (DNS 負荷分散)。 プールの FQDN へのマッピングで、プール内の各フロントエンドサーバーの IP アドレスの DNS A レコードが必要です。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (ロード バランサー機器の仮想 IP (VIP))。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>fe01.contoso.net</p>
<p>fe02.contoso.net</p>
<p>fe03.contoso.net</p>
<p>…</p></td>
<td><p>Pool01 フロントエンドサーバー (ノード 1)。</p>
<p>Pool01 フロントエンドサーバー (ノード 2)。</p>
<p>Pool01 フロントエンドサーバー (ノード 3)。</p>
<p>…</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>fe02.contoso.net</p></td>
<td><p>Pool01 フロントエンドサーバー (ノード 2)。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>lsweb.contoso.net</p></td>
<td><p>クライアントとサーバー間の Web トラフィック用の Pool01 (VIP)。</p></td>
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
<td><p>Lync Phone Edition の場合、または DNS SRV レコードのないクライアントの自動ログオン、および厳密なドメイン照合の場合に必須です。 すべての場合に必要なわけではありません。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>sip.fabrikam.com</p></td>
<td><p>2 番目の SIP ドメインを前提とします。 Lync Phone Edition、DNS SRV レコードのないクライアントの自動ログオン、および厳密なドメイン照合に必要です。 すべての場合に必要なわけではありません。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>内部で公開されたダイヤルイン会議の簡単な URL-フロントエンドサーバー (またはディレクターがインストールされている場合はディレクター) が簡単な URL クエリに応答します。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>内部で公開された電話会議の簡単な URL-フロントエンドサーバー (またはディレクターがインストールされている場合はディレクター) が簡単な URL クエリに応答します。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>admin.contoso.com</p>
<p>同期</p></td>
<td><p>(省略可能) Lync Server 2013 コントロールパネルの内部公開-フロントエンドサーバー (またはディレクターがインストールされている場合) は、簡易 URL クエリに応答します。 ホスト名のみ (ドメイン名なし) にすることをお勧めします。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> VIP = ロード バランサー機器の仮想 IP アドレス



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
<th>対象 FQDN</th>
<th>ポート</th>
<th>マッピング先/コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls _sipinternaltls._tcp</p></td>
<td><p>pool01.contoso.com</p></td>
<td><p>5061</p></td>
<td><p>Lync 2013 クライアントを内部で動作するように自動構成するために必要です。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls _sipinternaltls._tcp</p></td>
<td><p>pool01.fabrikam.com</p></td>
<td><p>5061</p></td>
<td><p>Lync 2013 クライアントを内部で動作するように自動構成するために必要です。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_ntp _ntp._udp</p></td>
<td><p>dc01.contoso.com</p></td>
<td><p>123</p></td>
<td><p>Lync Phone Edition を実行しているデバイスには、ネットワークタイムプロトコル (NTP) ソースが必要です。 内部では、ドメイン コントローラーを指している必要があります。 ドメイン コントローラーが定義されていない場合は、NTP サーバー time.windows.com の使用を試みます。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

