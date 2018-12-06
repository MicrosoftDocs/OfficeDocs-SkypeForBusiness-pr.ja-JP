---
title: 'Lync Server 2013: フロントエンド プールの DNS 要件'
TOCTitle: フロントエンド プールの DNS 要件
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48271092
ms.date: 12/17/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のフロントエンド プールの DNS 要件

 

_**トピックの最終更新日:** 2016-12-15_

この手順を正常に完了するには、最低限でも Domain Admins グループまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンしている必要があります。

トポロジ ビルダーでトポロジを公開する前に、必要なドメイン ネーム システム (DNS) レコードを構成する必要があります。 また、Lync Server 2013 の展開の構成で使用される完全修飾ドメイン名 (FQDN) の一部は、論理的で、かつ物理サーバーの FQDN ではないものです。したがって、公開前に追加の DNS 構成が必要です。


> [!WARNING]
> Lync Server 2013 は、単一ラベルのドメインをサポートしません。たとえば、ルート ドメイン名が <STRONG>contoso.local</STRONG> であるフォレストはサポートされますが、<STRONG>local</STRONG> という名前のルート ドメインはサポートされません。詳細については、マイクロソフト サポート技術情報の記事 300684「単一ラベル DNS 名を使用して Active Directory のドメインを構成する」(<A class=uri href="http://support.microsoft.com/kb/300684/ja-jp">http://support.microsoft.com/kb/300684/ja-jp</A>) を参照してください。




> [!IMPORTANT]
> 指定する名前が、サーバーに構成されているコンピューター名と同じである必要があります。既定では、ドメインに参加していないコンピューターのコンピューター名は、FQDN ではなく短い名前です。トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。Lync Server、エッジ サーバー、およびプールを実行するサーバーの FQDN を割り当てる場合に使用できる文字は、<STRONG>標準文字のみ</STRONG> (A ～ Z、a ～ z、0 ～ 9、およびハイフン) です。Unicode 文字およびアンダースコアは使用しないでください。一般に、外部 DNS および公的証明機関 (CA) では、FQDN に非標準文字はサポートされていません (証明書で FQDN を SN に割り当てる必要がある場合)。



展開されたトポロジを運用する前に、(特定の機能で指示された場合) 次の Active Directory レコードと DNS レコードが作成されていることを確認します。

  - トポロジ内に存在する各サーバーの役割は、Active Directory オブジェクトとして公開されます (コンピューターがドメインに参加すると実行されます)。

  - DNS A レコードはサーバーごとに存在します。

  - \_sipinternaltls\_tcp.*SIP ドメイン*の形式のクライアントで自動ログオンを使用予定の場合、DNS SRV レコードは SIP ドメインごとに存在します。クライアントに手動構成を使用する場合、このレコードは不要です。

  - 構成済みの簡易 URL のそれぞれの DNS A レコードには、通常 meet、dialin、lwa、scheduler の 4 つがあります。また、Lync Server 2013 コントロール パネル へのアクセス用の特別な URL である簡単な管理 URL があります。

  - SQL Server を実行するサーバーは、ドメインに参加しており、トポロジ ビルダーを公開するコンピューターから到達可能である必要があります。

表は、「計画」セクションの参照アーキテクチャに従っています。詳細については、「計画」のドキュメントの「[Lync Server 2013 の外部ユーザー アクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」を参照してください。

### フロント エンド プールで必要な DNS レコード

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
<td><p>Pool01 (DNS 負荷分散)。プール内にある各 フロント エンド サーバーの IP アドレス用の DNS A レコード (プールの FQDN へのマッピング) が必要。</p></td>
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
<td><p>Pool01 フロント エンド サーバー (ノード 1)。</p>
<p>Pool01 フロント エンド サーバー (ノード 2)。</p>
<p>Pool01 フロント エンド サーバー (ノード 3)。</p>
<p>…</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>fe02.contoso.net</p></td>
<td><p>Pool01 フロント エンド サーバー (ノード 2)。</p></td>
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
<td><p>SQL Server 2008 R2 を実行する Pool01 バック エンド サーバー。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Lync Phone Edition、または DNS SRV レコードを持たないクライアントの自動ログオン、および厳密なドメインの照合に必要です。すべての場合に必要なわけではありません。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>sip.fabrikam.com</p></td>
<td><p>2 番目の SIP ドメインを前提とします。Lync Phone Edition、DNS SRV レコードを持たないクライアントの自動ログオン、および厳密なドメインの照合に必要です。すべての場合に必要なわけではありません。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>内部で公開されるダイヤルイン会議の簡易 URL - フロント エンド サーバー (またはインストールされている場合は ディレクター) が簡易 URL のクエリに応答します。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>内部で公開される電話会議の簡易 URL - フロント エンド サーバー (またはインストールされている場合は ディレクター) が簡易 URL のクエリに応答します。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>admin.contoso.com</p>
<p>admin</p></td>
<td><p>オプションのレコード、内部で公開される Lync Server 2013 コントロール パネルの簡易 URL - フロント エンド サーバー (またはインストールされている場合は ディレクター) が簡易 URL のクエリに応答します。ホスト名のみ (ドメイン名なし) にすることをお勧めします。</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> VIP = ロード バランサー機器の仮想 IP アドレス


## フロント エンド プールの DNS SRV レコード


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
<td><p>_sipinternaltls._tcp.contoso.com</p></td>
<td><p>pool01.contoso.com</p></td>
<td><p>5061</p></td>
<td><p>Lync 2013 クライアントの自動構成が内部で動作するために必要。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls._tcp.fabrikam.com</p></td>
<td><p>pool01.fabrikam.com</p></td>
<td><p>5061</p></td>
<td><p>Lync 2013 クライアントの自動構成が内部で動作するために必要。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_ntp._udp.contoso.com</p></td>
<td><p>dc01.contoso.com</p></td>
<td><p>123</p></td>
<td><p>Lync Phone Edition を実行するデバイスに必要なネットワーク タイム プロトコル (NTP) ソース。内部では、ドメイン コントローラーを指している必要があります。ドメイン コントローラーが定義されていない場合は、NTP サーバー time.windows.com の使用を試みます。</p></td>
</tr>
</tbody>
</table>

