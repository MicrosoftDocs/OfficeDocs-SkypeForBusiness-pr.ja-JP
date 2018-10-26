---
title: 'Lync Server 2013: 外部ユーザー アクセスの展開チェックリスト'
TOCTitle: 外部ユーザー アクセスの展開チェックリスト
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48271867
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の外部ユーザー アクセスの展開チェックリスト

 

_**トピックの最終更新日:** 2015-03-09_

境界ネットワークを展開して外部ユーザーのサポートを実装する前に、フロント エンド プール、Standard Edition サーバーなどの Microsoft Lync Server 2013 内部サーバーを展開しておく必要があります。内部ネットワークにオプションの ディレクターを展開する予定がある場合は、エッジ サーバーを展開する前にそれらも展開する必要があります。ディレクターの展開プロセスの詳細については、「計画」のドキュメントの「[Lync Server 2013 のディレクターのシナリオ](lync-server-2013-scenarios-for-the-director.md)」を参照してください。

Microsoft Lync Server 2013 には、内部サーバーおよびエッジ サーバーの両方の計画と展開を容易にするためのツールが付属しています。トポロジが完成したら、作成したトポロジ定義を運用環境に公開します。これを行うためには、**Domain Admins** グループと **RTCUniversalServerAdmins** グループのメンバーである必要があります。

  - **計画ツール**Office Communications Server 2007 R2 には、トポロジ設計の手順を順に示す計画ツールとエッジ計画ツールが付属していました。Lync Server 2010 では、これら 2 つのツールは、計画ユーザー数、VoIP 要件、外部ユーザー アクセス タイプ、フェデレーション オプションの収集など、追加の機能を備えた 1 つの 計画ツールに統合されました。また、IP アドレス、ロード バランサー タイプ、その他境界ネットワークの考慮事項など、インフラストラクチャのネットワーク パラメーターを計画することもできます。

  - **トポロジ ビルダー**Lync Server 2013トポロジ ビルダーは、トポロジとコンポーネントを定義するのに役立ちます。トポロジ ビルダーは、Lync Server 2013 を実行するサーバーの展開に不可欠です。結果は、トポロジ ビルダーによって 中央管理ストアに公開され、組織内で Lync Server 2013 を実行するすべてのサーバーの構成に使用されます。トポロジ ビルダーを使用せずに Lync Server 2013 をサーバーにインストールすることはできません。

トポロジ ビルダーを実行してエッジ トポロジを定義するなど、計画プロセスでエッジ トポロジを設計した場合は、これらの結果を使用してエッジ サーバーの展開を開始できます。まだエッジ トポロジの構築が完了していない場合や、以前に指定した情報を変更する場合は、他の展開手順に進む前に トポロジ ビルダーの実行を完了しておく必要があります。トポロジの構築方法の詳細については、「[Lync Server 2013 の外部ユーザー アクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」を参照してください。

計画ツールおよびトポロジ ビルダーの詳細については、「計画」のドキュメントの「[Lync Server 2013 の計画プロセスの開始](lync-server-2013-beginning-the-planning-process.md)」を参照してください。

次の表に、エッジ サーバーの展開プロセスの概要を示します。外部ユーザー アクセスの展開前に決定する必要がある計画事項を確認するには、「[Lync Server 2013 の外部ユーザー アクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」を参照してください。


> [!WARNING]
> 次の表には、新規展開に関する情報を掲載しています。 Lync Server 2010、Office Communications Server 2007 R2、または Office Communications Server 2007 環境にエッジ サーバーを展開済みの場合、Lync Server 2013 への移行の詳細については、「<A href="migration.md">移行</A>」を参照してください。 Office Communications Server 2007 R2 より前のバージョン (Office Communications Server 2007、Live Communications Server 2005、Live Communications Server 2003 など) からの移行はサポートされていません。



エッジ サーバーのパフォーマンスとセキュリティを向上させ、展開作業を円滑に行うことができるようにするため、次のベスト プラクティスに従って境界ネットワークとエッジ サーバーを展開します。

  - エッジ サーバーの展開は、組織内で Lync Server 2013 の動作をテストおよび検証した後にのみ行います。

  - エッジ サーバーは、ドメインではなく、ワークグループに展開することをお勧めします。これにより、インストールが容易になり、Active Directory ドメイン サービス (AD DS) を境界ネットワークの外側に置くことができます。境界ネットワーク上に AD DS を配置すると、セキュリティ リスクが高くなる場合があります。

  - 全体が境界ネットワーク内にあるドメインへのエッジ サーバーの追加はサポートされていますが、お勧めしません。内部ドメインに属するエッジ サーバーは、インターネットは最も信頼性が低く、境界ネットワークはインターネットよりも信頼性が高く、内部ネットワークは最も信頼性が高いという信頼されたネットワークの境界の規則に違反します。内部ドメインのメンバーであるエッジ サーバーは自動的に最も信頼性の高いネットワークに属しますが、実際にはより信頼性の低いネットワーク (境界ネットワーク) に存在するからです。

## エッジ サーバーの展開プロセス


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
<td><p>適切なエッジ トポロジの作成および適切なコンポーネントの決定。</p></td>
<td><ul>
<li><p>トポロジ ビルダーを実行して、エッジ サーバーの設定を構成してトポロジを作成および公開し、Lync Server 管理シェルを使用してトポロジ構成ファイルをエクスポートします。</p></li>
</ul>
<p></p></td>
<td><p><strong>Domain Admins</strong> グループおよび <strong>RTCUniversalServerAdmins</strong> または <strong>CsAdmins</strong> グループ</p>

> [!NOTE]
> ローカル ユーザー グループのメンバーであるアカウントを使用してトポロジを定義することはできますが、トポロジを公開するには <strong>Domain Admins</strong> グループおよび <strong>RTCUniversalServerAdmins</strong> グループのメンバーであるアカウントが必要です。

<td><p>「展開」のドキュメントの「<a href="lync-server-2013-building-an-edge-and-director-topology.md">Lync Server 2013 でのエッジおよびディレクターのトポロジの作成</a>」</p></td>
</tr>
<tr class="even">
<td><p>セットアップの準備。</p></td>
<td><ol>
<li><p>システムの前提条件が適合していることを確認します。</p></li>
<li><p>各エッジ サーバーの、内部とパブリック側の両方のネットワーク インターフェイスの IP アドレス (IPv4 および IPv6 (使用されている場合)) を構成します。</p></li>
<li><p>内部および外部の DNS レコード (IPv4 および IPv6 の場合はホスト A および AAAA) を構成します。これにはエッジ サーバーとして展開されるコンピューターでの DNS サフィックスの構成も含まれます。</p></li>
<li><p>(オプション) パブリック証明書を作成してインストールします。証明書の取得に必要な時間は、証明書を発行する証明機関 (CA) によって異なります。現時点でこのステップを実行しない場合は、エッジ サーバーのインストール時に実行する必要があります。証明書を取得してインストールしないと、エッジ サーバー サービスを開始できません。</p></li>
<li><p>展開が Windows Live、AOL、または Yahoo! ユーザーとの通信をサポートする場合は、パブリック IM 接続のサポートをプロビジョニングします。</p>


> [!IMPORTANT]
> <UL>
> <LI>
> <P>2012 年 9 月 1 日の時点で、Microsoft Lync パブリック IM 接続のユーザー サブスクリプション ライセンス ("PIC USL") を新規または更新契約において購入することができなくなりました。アクティブなライセンスをお持ちのお客様は、サービスの停止日まで Yahoo! Messenger とのフェデレーションを引き続きご利用いただけます。AOL と Yahoo! に関しては、2014 年 6 月の終了日が発表されています。詳細については、「<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリック インスタント メッセンジャーの接続のサポート</A>」を参照してください。</P>
> <LI>
> <P>PIC USL は、ユーザー単位および月単位のサブスクリプション ライセンスであり、Lync Server または Office Communications Server と Yahoo! Messenger とのフェデレーションを行うにはこのライセンスが必要です。Microsoft がこのサービスを提供できるのは、Yahoo! からのサポートを条件とするものでしたが、その基盤となる契約の終了が近づいてきました。</P>
> <LI>
> <P>Lync は組織間を接続したり世界中のユーザーと接続したりするための、これまで以上の強力なツールとなります。Windows Live Messenger とのフェデレーションを行うのに、Lync Standard CAL を超えてユーザー/デバイス ライセンスを追加する必要はありません。Skype フェデレーションがこのリストに追加されることで、Lync ユーザーは IM および音声を使用して数億のユーザーにアクセスできます。</P></LI></UL>



<li><p>展開で使用する場合は、XMPP のサポートおよび Office Communications Server 2007、Office Communications Server 2007 R2、Lync Server 2010 パートナーのフェデレーション サポートをプロビジョニングします。</p></li>
<li><p>ファイアウォールの構成。</p></li>
</ol></td>
<td><p>組織に合わせて設定</p></td>
<td><p>「展開」のドキュメントの「<a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Lync Server 2013 の境界ネットワークへのサーバーのインストールの準備</a>」</p></td>
</tr>
<tr class="odd">
<td><p>リバース プロキシの設定。</p></td>
<td><ul>
<li><p>境界ネットワークでリバース プロキシ (Microsoft Forefront Threat Management Gateway 2010 用または Service Pack 1 を適用した Microsoft Internet Security and Acceleration (ISA) Server 用など) を設定し、必要なパブリック証明書を取得し、リバース プロキシ サーバーで Web 公開ルールを構成します。</p>
<p>モビリティの計画を行っており、フロントエンド プールまたは Standard Edition サーバーに Mobility Service を展開する場合は、Mobility Service 用のリバース プロキシを準備します。</p></li>
</ul></td>
<td><p><strong>Administrators</strong> グループまたはリバース プロキシの管理者</p></td>
<td><p></p>
<p>「展開」のドキュメントの「<a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync Server 2013 のリバース プロキシ サーバーの設定</a>」</p></td>
</tr>
<tr class="even">
<td><p>ディレクターのセットアップ (オプション)。</p></td>
<td><ul>
<li><p>(オプション) 内部ネットワークにディレクターを 1 つ以上インストールして構成します。</p></li>
</ul></td>
<td><p><strong>Administrators</strong> グループ</p></td>
<td><p>「展開」のドキュメントの「<a href="lync-server-2013-setting-up-the-director.md">Lync Server 2013 でのディレクターの設定</a>」</p></td>
</tr>
<tr class="odd">
<td><p>エッジ サーバーの設定。</p></td>
<td><ol>
<li><p>必要なソフトウェアをインストールします。</p></li>
<li><p>エクスポートされたトポロジ構成ファイルを各エッジ サーバーにトランスポートします。</p></li>
<li><p>各エッジ サーバーに Lync Server 2013 ソフトウェアをインストールします。</p></li>
<li><p>エッジ サーバーを構成します。</p></li>
<li><p>各エッジ サーバー用の証明書を要求してインストールします。</p></li>
<li><p>エッジ サーバー サービスを開始します。</p></li>
</ol></td>
<td><p><strong>Administrators</strong> グループ</p></td>
<td><p>「展開」のドキュメントの「<a href="lync-server-2013-setting-up-edge-servers.md">Lync Server 2013 でのエッジ サーバーの設定</a>」</p></td>
</tr>
<tr class="even">
<td><p>外部ユーザー アクセスの展開の構成。</p></td>
<td><ol>
<li><p>Lync Server コントロール パネルを使用して、以下の各項目のサポートを構成します (適用可能な場合)。</p>
<ul>
<li><p>メディア リレー</p></li>
<li><p>フェデレーション ルート</p></li>
<li><p>リモート ユーザー アクセス</p></li>
<li><p>Lync Server、Office Communications Server、および Live Communications Server とのフェデレーション</p></li>
<li><p>パブリック IM 接続</p></li>
<li><p>XMPP フェデレーション</p></li>
<li><p>匿名ユーザー</p></li>
</ul></li>
<li><p>(必要に応じて) リモート ユーザー アクセス、フェデレーション、パブリック IM 接続、XMPP、および匿名ユーザー サポート用のユーザー アカウントを構成します。</p></li>
</ol></td>
<td><p><strong>RTCUniversalServerAdmins</strong> グループ、または <strong>CSAdministrator</strong> の役割に割り当てられているユーザー アカウント</p>
<p></p></td>
<td><p>「展開」のドキュメントの「<a href="lync-server-2013-configuring-support-for-external-user-access.md">Lync Server 2013 での外部ユーザー アクセスのサポートの構成</a>」</p></td>
</tr>
<tr class="odd">
<td><p>エッジ サーバー構成の確認。</p></td>
<td><ol>
<li><p>内部サーバーからのサーバー接続および構成データのレプリケーションを確認します。</p></li>
<li><p>外部ユーザー (リモート ユーザー、フェデレーション ドメイン内のユーザー、パブリック IM ユーザー、および匿名ユーザーなど) が、必要に応じて展開に接続できることを確認します。</p></li>
<li><p>Lync Server Remote Connectivity Analyzer (<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a>) を使用して、構成と通信を確認します。</p></li>
<li><p>構成および通信の問題のトラブルシューティングを行います。</p></li>
</ol></td>
<td><p>レプリケーションの確認の場合は、<strong>RTCUniversalServerAdmins</strong> グループ、または <strong>CSAdministrator</strong> の役割に割り当てられているユーザー アカウント</p>
<p>ユーザー接続の確認の場合は、サポートしている外部ユーザー アクセスの各種ユーザー</p>
<p>リモート ユーザー</p></td>
<td><p>「展開」のドキュメントの「<a href="lync-server-2013-verifying-your-edge-deployment.md">Lync Server 2013 でのエッジの展開の検証</a>」</p></td>
</tr>
</tbody>
</table>

