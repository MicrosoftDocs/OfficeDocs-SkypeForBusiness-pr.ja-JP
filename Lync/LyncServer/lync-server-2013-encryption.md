---
title: Lync Server 2013 の暗号化
TOCTitle: Lync Server 2013 の暗号化
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59679290
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の暗号化

 

_**トピックの最終更新日:** 2016-12-08_

Microsoft Lync Server 2013 では、TLS と MTLS を使用してインスタント メッセージを暗号化します。トラフィックが内部ネットワークに限定されているか、内部ネットワークの境界を越えるかに関係なく、MTLS は、サーバー間のすべてのトラフィックに必要です。TLS はオプションですが、仲介サーバーとメディア ゲートウェイの間で使用することを強くお勧めします。この接続に TLS を構成する場合は MTLS も必要です。したがって、ゲートウェイは、仲介サーバーによって信頼される証明機関 (CA) から発行された証明書を使用して構成する必要があります。

クライアント間のトラフィックに対する要件は、そのトラフィックが内部の企業ファイアウォールを越えるかどうかによって異なります。厳密に言えば、内部のトラフィックでは、TLS を使うことも (インスタント メッセージが暗号化される)、TCP を使うことも (インスタント メッセージが暗号化されない) できます。

次の表に、各種トラフィックのプロトコル要件をまとめます。

### トラフィックの保護

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>トラフィックの種類</th>
<th>保護用プロトコル</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>サーバー間</p></td>
<td><p>MTLS</p></td>
</tr>
<tr class="even">
<td><p>クライアントからサーバー</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>インスタント メッセージングとプレゼンス</p></td>
<td><p>TLS (TLS 用に構成されている場合)</p></td>
</tr>
<tr class="even">
<td><p>オーディオとビデオ、メディアのデスクトップ共有など</p></td>
<td><p>SRTP</p></td>
</tr>
<tr class="odd">
<td><p>デスクトップ共有 (シグナリング)</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="even">
<td><p>Web 会議</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>会議コンテンツのダウンロード、アドレス帳のダウンロード、配布グループの拡張</p></td>
<td><p>HTTPS</p></td>
</tr>
</tbody>
</table>


## メディアの暗号化

メディア トラフィックは、Secure RTP (SRTP) を使用して暗号化されます。これは、秘密保持機能、認証、RTP トラフィックなどに対する再生攻撃からの保護機能を提供するリアルタイム転送プロトコル (RTP) のプロファイルです。SRTP では、(メディア参加者のために) サーバーの要求が正常に認証された結果としてメディア リレー認証サービスによって生成されるセッション キーを使用します。このセッション キーは、ネゴシエートされたユーザー名とパスワードによって保護されます。このユーザー名とパスワードは、フロント エンド サーバーによってメディア リレー認証サービスに対して提示され、TLS のセキュリティで保護された SIP チャネル経由で参加者に送信されます。このセッション キーは、ユーザー名とパスワードによってセキュリティで保護されます。また、このセッション キーは、メディア リレー サービスで使用され、参加者の TLS 証明書とセキュリティで保護された SIP チャネルによって提供されます。このセッション キーを復号化すると、参加者は SRTP ストリームを復号化できます。さらに、仲介サーバーと内部の次ホップの間で双方向に送信されるメディアも、SRTP を使用して暗号化されます。仲介サーバーとメディア ゲートウェイの間で双方向に送信されるメディアは暗号化されません。仲介サーバーは、メディア ゲートウェイに対して暗号化をサポートできますが、ゲートウェイは、MTLS と証明書の保管をサポートする必要があります。

> [!NOTE]
> 音声ビデオ (A/V) は、最新バージョンの Windows Live Messenger でサポートされます。Windows Live Messenger で音声ビデオ フェデレーションを実装する場合は、Lync Server の暗号化レベルを変更する必要もあります。既定では、暗号化レベルは &quot;必須&quot; です。Lync Server 管理シェルを使用して、この設定を &quot;サポート&quot; に変更する必要があります。詳しくは、展開のドキュメントの「<a href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013 での外部ユーザー アクセスの展開</a>」をご覧ください。


音声ビデオ メディア トラフィックは、Microsoft Lync 2013 と Windows Live クライアントの間では暗号化されません。

## FIPS

Windows Server オペレーティング システムが、システム暗号化に Federal Information Processing Standard (FIPS) 140-2 アルゴリズムを使用するように構成されている場合、Lync Server 2013 および Microsoft Exchange Server 2013 は FIPS 140-2 アルゴリズムをサポートして動作します。FIPS サポートを実装するには、Lync Server 2013 を実行する各サーバーで FIPS のサポートを構成する必要があります。FIPS 準拠のアルゴリズムの使用および FIPS サポートの実装方法について詳しくは、Microsoft サポート技術情報の記事 811833 「Windows XP 以降のバージョンの Windows で "システム暗号化: 暗号化、ハッシュ、署名に FIPS 準拠アルゴリズムを使用する" セキュリティ設定を有効にする効果 (英語)」([http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)) をご覧ください。Exchange 2010 における FIPS 140-2 のサポートと制限について詳しくは、「Exchange 2010 SP1 と FIPS 準拠アルゴリズムのサポート (英語)」([http://go.microsoft.com/fwlink/p/?LinkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335)) をご覧ください。

