---
title: 'Lync Server 2013: SIP フェデレーション、XMPP フェデレーションおよびパブリック インスタント メッセージングの構成 '
TOCTitle: SIP フェデレーション、XMPP フェデレーションおよびパブリック インスタント メッセージングの構成
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48273193
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での SIP フェデレーション、XMPP フェデレーションおよびパブリック インスタント メッセージングの構成

 

_**トピックの最終更新日:** 2015-03-09_

フェデレーション、パブリック インスタント メッセージング接続、および XMPP (Extensible Messaging and Presence Protocol) は、別の外部ユーザー クラス、すなわちフェデレーション ユーザーを定義します。 Lync Server のフェデレーション展開、または XMPP のフェデレーション展開のユーザーは、サービスのうち限られた一部にアクセスでき、外部展開によって認証されます。リモート ユーザーは、 Lync Server 展開のメンバーであり、展開によって提供されるすべてのサービスにアクセスできます。


> [!NOTE]
> AOL と Yahoo! のサービス終了日は 2014 年 6 月と発表されています。詳しくは、「 <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリック インスタント メッセンジャーの接続のサポート</a>」をご覧ください。


パブリック インスタント メッセージング接続は、フェデレーションの特殊な種類で、Lync Server クライアントが Lync 2013 を使用して、構成されたパブリック インスタント メッセージング パートナーにアクセスできます。現時点のパブリック インスタント メッセージング接続パートナーは次のとおりです。

  - America Online

  - Windows Live

  - Yahoo\!

パブリック インスタント メッセージング接続を構成すると、Lync ユーザーは次の方法でパブリック インスタント メッセージング接続ユーザーにアクセスできます。

  - IM とプレゼンス

  - パブリック インスタント メッセージング接続の連絡先を Lync クライアント内に表示

  - 連絡先との 1 対 1 の IM 会話

  - Windows Live ユーザーとの音声およびビデオ通話

Lync Server フェデレーションは、Lync Server の展開と他の Office Communications Server 2007 R2 または Lync Server の展開との間の合意を定義します。Lync Server フェデレーションを構成すると、Lync ユーザーは次の方法でフェデレーション ユーザーにアクセスできます。

  - IM とプレゼンス

  - フェデレーションの連絡先を Lync クライアントに作成

XMPP フェデレーションは、XMPP (eXtensible Messaging and Presence Protocol) に基づく外部展開を定義します。XMPP を構成すると、Lync ユーザーは許可された XMPP ドメイン ユーザーに次の方法でアクセスできます。

  - IM とプレゼンス - 1 対 1 のみ

  - XMPP フェデレーションからの連絡先を Lync クライアントに作成


> [!IMPORTANT]
> Lync Server 2013 の XMPP 機能は、Google Talk とのインスタント メッセージングのフェデレーションについては Microsoft によってテストとサポートが行われています。その他の XMPP システムについては、Lync Server 2013 とのフェデレーションのサポートや、展開またはトラブルシューティングの推奨事項に関して、サード パーティ ベンダーに問い合わせて確認してください。



## エッジ サーバー外部フェデレーション、パブリック インスタント メッセージング接続、および XMPP ユーザーの展開プロセス


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>フェーズ</th>
<th>ステップ</th>
<th>アクセス許可</th>
<th>ドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>既存のエッジ展開に追加するオプションを決める</p></td>
<td><p>トポロジ ビルダーを実行して、エッジ サーバーの設定を編集し、トポロジを公開します。既存のエッジ トポロジは、 中央管理ストアからエッジ サーバーに変更内容を複製します。</p></td>
<td><p>Domain Admins グループおよび RTCUniversalServerAdmins グループ。</p>

> [!NOTE]
> ローカル ユーザー グループのメンバーであるアカウントを使用してトポロジを編集できますが、トポロジを公開するには Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーであるアカウントが必要です。

</div></td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Lync Server 2013 でのエッジおよびディレクターのトポロジの作成</a></p></td>
</tr>
<tr class="even">
<td><p>セットアップの準備をする</p></td>
<td><ol>
<li><p>システムの前提条件が適合していることを確認します。</p></li>
<li><p>内部および外部 DNS レコードを構成して、パブリック インスタント メッセージング接続、Lync フェデレーション、および XMPP フェデレーションをサポートします。</p></li>
<li><p>ファイアウォールのポートとプロトコルを構成して、展開するフェデレーションの種類をサポートします。</p></li>
<li><p>パブリック証明書を取得してインストールします。証明書の取得に必要な時間は、どの証明機関 (CA) が証明書を発行するかによって異なります。この時点で、この手順を必ずしも実行する必要はありません。この手順を実行しない場合は、エッジ サーバーの構成時に実行する必要があります。 証明書を取得しないと、エッジ サーバー サービスを開始できません。</p></li>
</ol>
<p></p></td>
<td><p>組織に応じる (一般に、これらの役割は多数のワーク グループと切り離されるため)</p></td>
<td><p><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Lync Server 2013 での SIP、XMPP フェデレーション、パブリック インスタント メッセージングの計画</a></p></td>
</tr>
<tr class="odd">
<td><p>フェデレーション シナリオ用にエッジ サーバーを設定する</p></td>
<td><ol>
<li><p>エクスポートされたトポロジ構成ファイルを各エッジ サーバーにトランスポートするか、レプリケーションを完了できるようにします。</p></li>
<li><p>展開ウィザードを再実行して、フェデレーション用にサポートされているコンポーネントをインストールします。</p></li>
<li><p>エッジ サーバーを構成します。</p></li>
<li><p>各エッジ サーバー用の証明書を要求してインストールします。</p></li>
<li><p>エッジ サーバー サービスを再起動します。</p></li>
</ol></td>
<td><p>Administrators グループ</p></td>
<td><p><a href="lync-server-2013-setting-up-lync-federation.md">Lync Server 2013 での Lync フェデレーションのセットアップ</a></p>
<p><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Lync Server 2013 でのパブリック インスタント メッセージング接続の設定</a></p>
<p><a href="lync-server-2013-setting-up-xmpp-federation.md">Lync Server 2013 XMPP フェデレーションのセットアップ</a></p></td>
</tr>
<tr class="even">
<td><p>外部ユーザー アクセスのサポートの構成</p></td>
<td><ol>
<li><p>Lync Server コントロール パネルの [外部ユーザー アクセス] を使用します。</p></li>
<li><p>外部アクセス ポリシーを構成して、フェデレーション ユーザーやパブリック ユーザーとの通信を有効します。</p></li>
<li><p>SIP フェデレーション ドメインを構成して、ドメインを許可または禁止します。</p></li>
<li><p>パブリック インスタント メッセージング接続プロバイダーに対して SIP フェデレーション プロバイダーを有効にします。</p></li>
<li><p>XMPP ドメインごとに XMPP フェデレーション パートナーを構成します。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins グループ、または CSAdministrator の役割に割り当てられているユーザー アカウント</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Lync Server 2013 での外部ユーザー アクセスのサポートの構成</a></p>
<p><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Lync Server 2013 での公開プロバイダーに対するメディアの暗号化の構成</a></p></td>
</tr>
<tr class="odd">
<td><p>エッジ サーバー構成を確認します。</p></td>
<td><p>内部サーバーからのサーバー接続および構成データのレプリケーションを確認します。</p></td>
<td><p>レプリケーションの確認には、RTCUniversalServerAdmins グループ、または CSAdministrator の役割に割り当てられているユーザー アカウントが必要。ユーザー接続の確認には、フェデレーション ユーザーの種類ごとにユーザーが必要。</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Lync Server 2013 でのエッジの展開の検証</a></p>
<p><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Lync Server 2013 での XMPP 構成の例 - Google Talk との XMPP フェデレーション</a></p></td>
</tr>
</tbody>
</table>

