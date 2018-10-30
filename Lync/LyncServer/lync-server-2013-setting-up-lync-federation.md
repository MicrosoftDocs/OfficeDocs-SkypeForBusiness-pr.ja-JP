---
title: 'Lync Server 2013: Lync フェデレーションのセットアップ'
TOCTitle: Lync フェデレーションのセットアップ
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48271758
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Lync フェデレーションのセットアップ

 

_**トピックの最終更新日:** 2015-03-09_

エッジ サーバーが既に展開されている場合、フェデレーション シナリオ機能は簡単に追加できます。エッジ サーバーがまだセットアップされていない場合は、これを最初に行う必要があります。詳細については、「計画」ドキュメントの「[Lync Server 2013 の外部ユーザー アクセスの計画](lync-server-2013-planning-for-external-user-access.md)」、展開ドキュメントの「[Lync Server 2013 での外部ユーザー アクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。

> [!NOTE]
> XMPP フェデレーション、Lync フェデレーション、またはパブリック インスタント メッセージング接続を組み合わせてセットアップする場合、これらを同時に展開することもできれば、1 つずつ展開することもできます。トポロジ ビルダーと Lync Server 管理シェルを通じてオプションを構成し、1 つ、2 つ、または 3 つすべてのフェデレーションの種類のオプションを構成した後でエッジ サーバーで展開ウィザードを実行すると、必要な手順の数が少なくてすみます。


## トポロジ ビルダーと展開ウィザードで Lync フェデレーションをセットアップする

1.  フロントエンド サーバーでトポロジ ビルダーを開きます。エッジ プールを展開し、エッジ サーバーまたはエッジ サーバー プールを右クリックします。\[プロパティの編集\] をクリックします。

2.  \[全般\] の下の \[プロパティの編集\] で、\[このエッジ プールのフェデレーションの有効化 (ポート 5061)\] を選択します。\[OK\] をクリックします。

3.  \[アクション\] をクリックし、\[トポロジ\]、\[公開\] の順にクリックします。トポロジの公開を確認するプロンプトが表示されたら、\[次へ\] をクリックします。公開が完了したら、\[完了\] をクリックします。

4.  エッジ サーバーで、Lync Server 展開ウィザードを開きます。\[Lync Server システムのインストールまたは更新\] をクリックして、\[Lync Server コンポーネントのセットアップまたは削除\] をクリックします。\[再実行\] をクリックします。

5.  \[Lync Server コンポーネントのセットアップ\] で、\[次へ\] をクリックします。概要画面に、実行された処理が表示されます。展開が完了したら、\[ログの表示\] をクリックして、利用可能なログ ファイルを表示します。\[完了\] をクリックして、展開を完了します。
    

    > [!IMPORTANT]
    > このオプションを選ぶことは可能ですが、組織内の 1 つのエッジ プールまたはエッジ サーバーのみ、フェデレーション用に外部に公開できます。パブリック インスタント メッセージング (IM) ユーザーを含め、フェデレーション ユーザーによるすべてのアクセスが同じエッジ プールまたは単一エッジサーバーを通過します。たとえば、ニューヨークとロンドンにそれぞれ展開されているエッジ プールまたは単一エッジ サーバーが展開に含まれている場合、ニューヨークのエッジ プールまたは単一エッジ サーバーでフェデレーション サポートを有効にすると、フェデレーション ユーザーの信号トラフィックはニューヨークのエッジ プールまたは単一エッジ サーバーを通過します。これは、ロンドンのユーザーとの通信の場合でも同じです。ただし、ロンドンの内部ユーザーがロンドンのフェデレーション ユーザーを呼び出す場合は、音声ビデオ トラフィックにロンドンのプールまたはエッジ サーバーを使用します。



## パートナーとのフェデレーションを構成する

1.  他の Microsoft Lync Server 2013、Lync Server 2010、Office Communications Server 2007 R2、または Office Communicator 2007 とのフェデレーションをセットアップに適切に行うには、以下の表からフェデレーションの種類を選択し、DNS SRV レコードと DNS ホスト (A、または IPv6 では AAAA) を定義します。次に、フェデレーションの種類に該当するポリシーを構成します。
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>フェデレーションの種類</th>
    <th>DNS レコード</th>
    <th>ポリシー定義</th>
    <th>メモ</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>検出済みのパートナー ドメイン</p></td>
    <td><p>_sipfederationtls._tcp.&lt;外部ドメイン ネーム&gt;の形式で SRV レコードを構成します。ここで、SRV レコードのポート値は TCP 5061 で、[ <strong>このサービスを提供しているホスト</strong>] は sip として定義されます。&lt;外部ドメイン ネーム&gt; - アクセス エッジ サービスの FQDN。SRV レコードの作成の詳細については、「<a href="lync-server-2013-configure-dns-for-edge-support.md">Lync Server 2013 でのエッジ サポートの DNS の構成</a>」を参照してください。</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</a></p></li>
    <li><p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Lync Server 2013 でのフェデレーション パートナーの検出の有効化または無効化</a></p></li>
    </ul></td>
    <td><p>以前のバージョンでは、このフェデレーションの種類は、<strong>オープン拡張フェデレーション</strong>と呼ばれていました。この種類のフェデレーションでは、SRV レコードの作成が必要です。その他のパートナーがフェデレーションを検出できるようにします。</p></td>
    </tr>
    <tr class="even">
    <td><p>許可されたパートナー ドメイン</p></td>
    <td><p>_sipfederationtls._tcp.&lt;外部ドメイン ネーム&gt;の形式で SRV レコードを構成します。ここで、SRV レコードのポート値は TCP 5061 で、[ <strong>このサービスを提供しているホスト</strong>] は sip として定義されます。&lt;外部ドメイン ネーム&gt; - アクセス エッジ サービスの FQDN。SRV レコードの作成の詳細については、「<a href="lync-server-2013-configure-dns-for-edge-support.md">Lync Server 2013 でのエッジ サポートの DNS の構成</a>」を参照してください。</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</a></p></li>
    </ul></td>
    <td><p>以前のバージョンでは、このフェデレーションの種類は、<strong>拡張フェデレーション</strong>と呼ばれていました。この種類のフェデレーションでは、SRV レコードの作成は省略可です。その他のパートナーがフェデレーションを検出できるようにします。この場合は、<strong>オープン拡張フェデレーション</strong>、または <strong>検出済みのパートナー ドメイン</strong>になります。</p></td>
    </tr>
    <tr class="odd">
    <td><p>許可されたパートナー サーバー</p></td>
    <td><p>ポリシーでフェデレーション パートナーとして、SIP ドメイン名とパートナー エッジ サーバー FQDN を構成します。</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Lync Server 2013 での、許可された外部ドメイン向けサポートの構成</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Lync Server 2013 での禁止された外部ドメイン向けサポートの構成</a></p></li>
    </ul></td>
    <td><p>このフェデレーションの種類は 1 対 1 の関係の定義です。その他のフェデレーション パートナーの検出は許可されません。各フェデレーション パートナーは明示的に構成されます。以前のバージョンでは、これは <strong>直接フェデレーション</strong>と呼ばれていました。</p></td>
    </tr>
    <tr class="even">
    <td><p>ホスティング プロバイダーとパブリック IM プロバイダー</p></td>
    <td><p>このフェデレーションの種類では、特定の DNS 要件は定義されていません。</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Lync Server 2013 での公開 SIP フェデレーション プロバイダーの作成または編集</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Lync Server 2013 でのホスト SIP フェデレーション プロバイダーの作成または編集</a></p></li>
    </ul></td>
    <td><p>このフェデレーションの種類は、ユーザーに対して構成するサービスおよびホスティング プロバイダーを定義します。一般的な使用法としては、Windows Live Messenger、Yahoo!、AOL のような公開 IM プロバイダーの構成、また Lync Online と Office 365 のようなホスティング プロバイダーの構成が含まれます。</p>
    <div>

    > [!IMPORTANT]
    > <UL>
    > <LI>
    > <P>2012 年 9 月 1 日の時点で、Microsoft Lync パブリック IM 接続のユーザー サブスクリプション ライセンス ("PIC USL") を新規または更新契約において購入することができなくなりました。アクティブなライセンスをお持ちのお客様は、サービスの停止日まで Yahoo! Messenger とのフェデレーションを引き続きご利用いただけます。AOL と Yahoo! に関しては、2014 年 6 月の終了日が発表されています。詳細については、「<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリック インスタント メッセンジャーの接続のサポート</A>」を参照してください。</P>
    > <LI>
    > <P>PIC USL は、ユーザー単位および月単位のサブスクリプション ライセンスであり、Lync Server または Office Communications Server と Yahoo! Messenger とのフェデレーションを行うにはこのライセンスが必要です。Microsoft がこのサービスを提供できるのは、Yahoo! からのサポートを条件とするものでしたが、その基盤となる契約の終了が近づいてきました。</P>
    > <LI>
    > <P>Lync は組織間を接続したり世界中のユーザーと接続したりするための、これまで以上の強力なツールとなります。Windows Live Messenger とのフェデレーションを行うのに、Lync Standard CAL を超えてユーザー/デバイス ライセンスを追加する必要はありません。Skype フェデレーションがこのリストに追加されることで、Lync ユーザーは IM および音声を使用して数億のユーザーにアクセスできます。</P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  すべての必要な DNS ホスト (A、または IPv6 では AAAA) と DNS SRV レコードを定義して、構成します。

3.  Lync Server コントロール パネルまたは Lync Server 管理シェルと適切なコマンドレットを使用して、すべてのポリシーを定義して構成します。 Lync Server 管理シェル コマンドレットの詳細は、「[Lync Server 2013 でのフェデレーションおよび外部アクセスのコマンドレット](https://docs.microsoft.com/en-us/powershell/module/skype/)」を参照してください。
    
    > [!NOTE]  
    > Lync Room System (LRS) の [参加] ボタンは、その会議を送信した開催者が Lync のフェデレーション パートナーの場合には表示されません。会議に参加するリンクを LRS に表示するには、送信側が次のコマンドレットを使って TNEF を有効にする必要があります。<br />
    > <br />
    > <code>New-RemoteDomain -DomainName Contoso.com -Name Contoso</code><br />
    > <code>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</code><br />
    > これは LRS に固有の問題ではありません。Outlook と Lync でも MAPI プロパティが転送されないため、このような場合は [参加] のリンクが表示されません。ただし、Outlook の場合は、ユーザーが会議の招待を開いてその会議の URL をクリックできます。TNEFEnabled が TRUE に設定されると、Exchange 2013 は OnlineMeetingExternalLink などの MAPI プロパティを削除しないため、アラームに [参加] ボタンが表示されます。

## 関連項目

#### その他のリソース

[Lync Server 2013 での SIP、XMPP フェデレーション、パブリック インスタント メッセージングの計画](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[Lync Server 2013 へのフェデレーションおよび外部アクセスの管理](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)

