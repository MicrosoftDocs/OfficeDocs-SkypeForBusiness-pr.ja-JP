---
title: Lync Server 2013 でのスキーマの属性と説明
TOCTitle: Lync Server 2013 でのスキーマの属性と説明
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48273278
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのスキーマの属性と説明

 

_**トピックの最終更新日:** 2015-03-09_

このセクションでは、Lync Server 2013 で使用するすべてのスキーマ属性について説明します。属性に関連するクラスについては、「[Lync Server 2013 でのクラスごとのスキーマの属性](lync-server-2013-schema-attributes-by-class.md)」を参照してください。Lync Server 2013 で導入されたクラスおよび属性の一覧については、「[Lync Server 2013 のスキーマの変更](lync-server-2013-schema-changes-in-lync-server-2013.md)」を参照してください。

リンクされたペアである属性は、前方リンクまたは後方リンクとして指定されます。別のオブジェクトを参照する属性を前方リンクと呼びます。他のオブジェクトから逆に最初のオブジェクトを参照する属性を後方リンクと呼びます。前方リンクは更新できますが、後方リンクは読み取り専用です。

一部の属性にはビット マスク値があります。これらの属性では、それぞれの設定がビットで表され、表示される 10 進値はビット位置を表します。ビット位置は 0 で始まります。たとえば、1 (バイナリ) はビット 0 が設定され、10000 (バイナリ) はビット 4 が設定されます。各ビットはプロパティを表します。いくつかの例を次に示します。

  - 10000 (バイナリ) の 10 進値は 16 です (つまり、ビット 4 が設定されます)。

  - 100000000 (バイナリ) の 10 進値は 256 です (つまり、ビット 8 が設定されます)。

  - 1100 (バイナリ) の 10 進値は 12 です (つまり、ビット 2 と 3 が設定され、この両方のビットで表されるプロパティが有効です)。

  - 1111000001 (バイナリ) の 10 進値は 961 です (つまり、ビット 0、6、7、8、9 が設定され、これらの各ビットのプロパティが有効です)。

### Lync Server 2013 のスキーマ属性

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>属性</th>
<th>説明</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dnsHostName</p></td>
<td><p>Active Directory ドメイン サービス の既存の属性です。<strong>msRTCSIP-Pool</strong> および <strong>msRTCSIP-MonitoringServer</strong> のクラスに関連付けられています。この属性は、プールまたは監視サーバーの完全修飾ドメイン名 (FQDN) を指定します。</p>
<p>各セグメントの有効な値は 63 文字、FQDN 全体では 255 文字です。</p></td>
<td><p>Microsoft Office Live Communications Server 2005 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msDS-SourceObjectDN</p></td>
<td><p>このオブジェクトに対応する別のフォレストのオブジェクトの識別名 (DN) の文字列表現を含む属性です。配布グループ拡張と自動応答のために使用されます。この属性は、Windows Server 2003 R2 の既定の Active Directory スキーマで定義されています。</p>
<p>AD DS を Windows 2003 R2 にアップグレードしなくても済むように、Active Directory のスキーマの準備により、Windows 2003 のスキーマがこの属性定義で拡張されます。</p></td>
<td><p>Microsoft Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msExchUCVoiceMailSettings</p></td>
<td><p>ボイス メールの設定が含まれる複数値の属性です。この属性は、Exchange ユニファイド メッセージング (UM) と共有されています。</p></td>
<td><p>Microsoft Lync Server 2010 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>この複数値の属性には、ユーザーに適用される保持ポリシーの識別子が保持されます。この保持の間は、ユーザーのメールボックス アイテムが保持ポリシーに保存されます。この属性は、Exchange 2013 と共有されます。</p></td>
<td><p>New in Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-AcpInfo</p></td>
<td><p>ユーザーの電話会議プロバイダー情報を格納する属性です。</p></td>
<td><p>Lync Server 2010 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationDestination</p></td>
<td><p>アプリケーションの連絡先の信頼済みサービス エントリを指す属性です。</p></td>
<td><p>Microsoft Office Communications Server 2007 R2 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationList</p></td>
<td><p>アプリケーション サーバーでホストされているアプリケーションの一覧を含む属性です。</p></td>
<td><p>Office Communications Server 2007 R2 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationOptions</p></td>
<td><p>アプリケーションの連絡先のオプションを指定する属性です。</p></td>
<td><p>Office Communications Server 2007 R2 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationPrimaryLanguage</p></td>
<td><p>アプリケーションの連絡先の第 1 言語を含む属性です。</p></td>
<td><p>Office Communications Server 2007 R2 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationSecondaryLanguages</p></td>
<td><p>アプリケーションの連絡先の第 2 言語を含む複数値の属性です。</p></td>
<td><p>Office Communications Server 2007 R2 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerBL</p></td>
<td><p>このプールに所属するアプリケーション サーバーの一覧を含む属性です。この後方リンク属性に対応する前方リンクは <strong>msRTCSIP-ApplicationServerPoolLink</strong> です。</p></td>
<td><p>Office Communications Server 2007 R2 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerPoolLink</p></td>
<td><p>このアプリケーション サーバーが所属するプールを指す属性です。これは前方リンクです。対応する後方リンクは <strong>msRTCSIP-ApplicationServerBL</strong> です。</p></td>
<td><p>Office Communications Server 2007 R2 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveDefault (廃止)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2005 で導入。</p>
<p>Office Communications Server 2007 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveDefaultFlags (廃止)</p></td>
<td><p>すべてのユーザーの通信をアーカイブするかどうかについて、フォレスト境界内のグローバルな既定値を指定する属性です。この設定はアーカイブ エージェント レイヤーによって適用されます。この属性の値の範囲は次のとおりです。</p>
<ul>
<li><p><strong>TRUE</strong>: すべてのユーザーをアーカイブする</p></li>
<li><p><strong>FALSE</strong>: すべてのユーザーをアーカイブしない</p></li>
</ul>
<p>この属性は、内部ネットワーク内のユーザーによる通信のアーカイブ方法をフォレスト境界内でグローバルに制御します。</p>
<p><strong>Live Communications Server 2005 の動作 (現在は廃止)</strong></p>
<p>この属性の値の範囲は次のとおりです。</p>
<ul>
<li><p>0: メッセージ本文をアーカイブする [ビット 0]</p></li>
<li><p>1: メッセージ本文をアーカイブしない [ビット 0]</p></li>
</ul>
<p><strong>Office Communications Server 2007 の動作</strong></p>
<p>この属性の値の範囲は次のとおりです。</p>
<ul>
<li><p>0: ArchiveFederationDefaultWithoutBody (廃止)</p></li>
<li><p>1-2: ArchiveInternalCommunications</p></li>
<li><p>3-4: ArchiveFederatedCommunications</p></li>
<li><p>5: RecordPresenceRegistrations</p></li>
<li><p>6: RecordIMCallDetails</p></li>
<li><p>7: RecordGroupIMCallDetails</p></li>
<li><p>8: RecordFileTransferInstances</p></li>
<li><p>9: RecordAudioCallDetails</p></li>
<li><p>10: RecordVideoCallDetails</p></li>
<li><p>11: RecordRemoteAssistanceCallDetails</p></li>
<li><p>12: RecordApplicationSharingDetails</p></li>
<li><p>13: RecordMeetingInstantiations</p></li>
<li><p>14: RecordMeetingJoins</p></li>
<li><p>15: RecordDataJoins</p></li>
<li><p>16: RecordAVJoins</p></li>
</ul></td>
<td><p>Live Communications Server 2005 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveFederationDefault (廃止)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2005 で導入。</p>
<p>Office Communications Server 2007 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveFederationDefaultFlags (廃止)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2005 で導入。</p>
<p>Office Communications Server 2007 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingEnabled</p></td>
<td><p>この属性は、1 人のユーザーの通信をアーカイブするかどうかを制御するビット フィールドとして使用される整数です。この制御はアーカイブ エージェント レイヤーによって適用されます。この属性には、グローバル カタログ レプリケーションのマークが付いています。</p>
<p>この属性のスコープは、1 人のユーザーまたは連絡先に限定されています。Lync Server の有効な値 (および関連するビット位置) は次のとおりです。</p>
<ul>
<li><p>0: アーカイブしない (ビットは設定されません)</p></li>
<li><p>1: 廃止 (ビット位置 0)</p></li>
<li><p>2: 廃止 (ビット位置 1)</p></li>
<li><p>4: 内部通信のアーカイブ (ビット位置 2)</p></li>
<li><p>8: フェデレーション通信のアーカイブ (ビット位置 3)</p></li>
</ul>
<p>Live Communications Server 2005 で有効だった値は次のとおりです。</p>
<ul>
<li><p>0: <strong>msRTCSIP-ArchiveDefault</strong> および <strong>msRTCSIP-ArchiveFederation</strong> で定義されている既定値をこの順番で使用する</p>
<ul>
<li><p>1: アーカイブする</p></li>
<li><p>2: アーカイブしない</p></li>
<li><p>3: メッセージ本文を除いてアーカイブする</p></li>
</ul></li>
</ul></td>
<td><p>Live Communications Server 2005 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchivingServerData (廃止)</p></td>
<td><p>この属性は将来の使用のために予約されています。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServerVersion (廃止)</p></td>
<td><p>アーカイブ サービスのバージョンを定義する属性です。製品が正式にリリースされるたびにインクリメントされる単調増加の整数型です。有効な値は次のとおりです。</p>
<ul>
<li><p>未定義: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
</ul></td>
<td><p>Office Communications Server 2007 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-BackEndServer</p></td>
<td><p>プールのバック エンド サーバーの FQDN を指定する属性です。バック エンド サーバーは各プールに 1 つしかないので、この属性は単一値の属性です。</p>
<p>各セグメントの有効な値は 63 文字、FQDN 全体では 255 文字です。</p></td>
<td><p>Live Communications Server 2005 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryHomePool</p></td>
<td><p>会議ディレクトリをホストしているプールの識別子を含む属性です。</p></td>
<td><p>Office Communications Server 2007 R2 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectoryId</p></td>
<td><p>会議ディレクトリの識別子を含む属性です。</p></td>
<td><p>Office Communications Server 2007 R2 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryTargetPool</p></td>
<td><p>会議ディレクトリの移動先のプールの識別子を含む属性です。</p></td>
<td><p>Office Communications Server 2007 R2 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Default</p></td>
<td><p>電話使用法が既定の使用法かどうかを定義するブール値の属性です。この属性が <strong>TRUE</strong> に設定されている場合、その電話使用法は既定の使用法であり、管理者が削除することはできません。この属性が <strong>FALSE</strong> に設定されている場合は削除できます。</p></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWAExternalURL</p></td>
<td><p>組織の外部に存在するユーザーの Communicator Web Access URL を識別する属性です。</p></td>
<td><p>Office Communications Server 2007 R2 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultCWAInternalURL</p></td>
<td><p>組織の内部に存在するユーザーの Communicator Web Access URL を識別する属性です。</p></td>
<td><p>Office Communications Server 2007 R2 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultLocationProfileLink (廃止)</p></td>
<td><p>場所のプロファイルのクラス オブジェクトに割り当てられた識別名 (DN) を含む単一値の属性です。</p>
<p>前方リンク: <strong>リンク ID 11036</strong></p>
<p>対応する後方リンクは <strong>msRTCSIP-ServerReferenceBL</strong> です。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultPolicy (廃止)</p></td>
<td><p>ポリシーが既定のポリシーかどうかを指定するブール値の属性です。<strong>TRUE</strong> に設定されている場合は既定のポリシーです。</p></td>
<td><p>Office Communications Server 2007 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultRouteToEdgeProxy (廃止)</p></td>
<td><p>直接アクセスできる場合は、アクセス エッジ サービスを実行しているエッジ サーバーの FQDN、またはアクセス エッジ サービスを実行しているサーバーのプールのロード バランサー機器の FQDN を指定する属性です。アクセス エッジ サービスを実行しているサーバーに 1 つ以上のディレクターを通じてしかアクセスできない場合、この属性は、ディレクターの FQDN およびポート番号 (オプション)、またはディレクターのプールが使用するロード バランサー機器の FQDN およびポート番号 (オプション) を指定します。</p>
<p>各セグメントの有効な値は 63 文字、FQDN 全体では 255 文字です。</p></td>
<td><p>Live Communications Server 2005 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultRouteToEdgeProxyPort (廃止)</p></td>
<td><p>アクセス エッジ サービスを実行するサーバーへの接続に使用するポート番号を表す属性です。</p>
<p>有効な値は、使用するポートを指定する整数値です。既定値は 5061 です。</p></td>
<td><p>Live Communications Server 2005 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefPresenceSubscriptionTimeout (廃止)</p></td>
<td><p>既定のプレゼンス サブスクリプション タイムアウト期間を表す属性です。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefRegistrationTimeout (廃止)</p></td>
<td><p>既定の登録タイムアウト期間を表す属性です。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefRoamingDataSubscriptionTimeout (廃止)</p></td>
<td><p>既定の移動データ サブスクリプション タイムアウト期間を表す属性です。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DeploymentLocator</p></td>
<td><p>分割ドメインのトポロジで使用する属性で、完全修飾ドメイン名 (FQDN) が含まれます。</p></td>
<td><p>Lync Server 2010 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Description (廃止)</p></td>
<td><p>この電話ルートまたは正規化ルールのわかりやすい説明を含む単一値の UNICODE 文字列属性です。</p></td>
<td><p>Office Communications Server 2007 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DomainData</p></td>
<td><p>この属性は将来の使用のために予約されています。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DomainName</p></td>
<td><p>レジストラー用に構成されたドメインを表す属性です。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EdgeProxyData</p></td>
<td><p>この属性は将来の使用のために予約されています。</p></td>
<td><p>Live Communications Server 2005 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxyFQDN</p></td>
<td><p>アクセス エッジ サービスを実行しているサーバーの FQDN を指定する属性です。</p>
<p>各セグメントの有効な値は 63 文字、FQDN 全体では 255 文字です。</p></td>
<td><p>Live Communications Server 2005 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnableBestEffortNotify (廃止)</p></td>
<td><p>クライアントから SUBSCRIBE 要求を受けた場合に、サーバーで NOTIFY 要求の代わりに BENOTIFY (Best Effort NOTIFY) 要求を生成するかどうかを制御する属性です。BENOTIFY は、サブスクライブ通知のハンドシェイクのパフォーマンスを強化する拡張機能で、サーバーで標準の NOTIFY 要求の代わりに BENOTIFY 要求が生成されます。BENOTIFY 要求は、NOTIFY 要求のようにクライアントからの 200 OK 応答を必要としないので、パフォーマンス上のメリットがあります。</p>
<p>有効な値は、<strong>TRUE</strong> または <strong>FALSE</strong> です。</p>

> [!NOTE]
> Live Communications Server 2003 では BENOTIFY 要求はサポートされていません。Live Communications Server 2003 のサーバー API で作成され、Live Communications Server 2005 やサードパーティのサーバーで実行されるサーバー アプリケーションとの相互運用性を確保するには、この属性の値を <strong>FALSE</strong> に設定して BENOTIFY 要求を無効にします。現時点では、BENOTIFY は IETF (インターネット技術標準化委員会) の SIP の標準化プロセスに含まれていません。

</div></td>
<td><p>Live Communications Server 2005 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnableFederation (廃止)</p></td>
<td><p>ユーザーが他の組織のユーザーと通信できるようにするかどうかを構成するためのグローバル スイッチとして IT 管理者が使用する属性です。これにより管理者は、個々のユーザーの <strong>FederationEnabled</strong> 属性を上書きすることができます。ワーム、ウイルス、または会社を標的にした攻撃によって引き起こされるインターネット攻撃から内部ネットワークを保護するために使用できます。</p>
<p>有効な値 (および関連するビット位置) は次のとおりです。</p>
<ul>
<li><p>1: パブリック IM 接続が有効 (ビット位置 0)</p></li>
<li><p>2: 予約済み (ビット位置 1)</p></li>
<li><p>4: 予約済み (ビット位置 2)</p></li>
<li><p>8: 予約済み (ビット位置 3)</p></li>
<li><p>16: リモート通話コントロールが有効 [テレフォニー] (ビット位置 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (会議への匿名ユーザーの招待を許可する) (ビット位置 6)</p></li>
<li><p>128: UCEnabled (ユーザーに対して統合コミュニケーションを有効にする) (ビット位置 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (ユーザーに対してパブリック IM 接続を有効にする) (ビット位置 8)</p></li>
<li><p>512: RemoteCallControlDualMode (ビット位置 9)</p></li>
</ul></td>
<td><p>Live Communications Server 2005 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServices</p></td>
<td><p>特定のサーバーにエンタープライズ サービスを読み込むかどうかを指定する属性です。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ExtensionData</p></td>
<td><p>この属性は将来の使用のために予約されています。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ExternalAccessCode</p></td>
<td><p>外部アクセスのダイヤル コードを含む属性です。</p></td>
<td><p>Office Communications Server 2007 R2 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-FederationEnabled</p></td>
<td><p>1 人のユーザーをフェデレーションに対して有効にするかどうかを制御する属性です。この制御はエンタープライズ サービス レイヤーによって適用されます。この属性には、グローバル カタログ レプリケーションのマークが付いています。</p>
<p>有効な値は、<strong>TRUE</strong> または <strong>FALSE</strong> です。</p></td>
<td><p>Live Communications Server 2005 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-FrontEndServers</p></td>
<td><p>プールに関連付けられているすべての Enterprise Edition サーバーのドメイン名の一覧を含む複数値の属性です。</p>
<p>後方リンク: <strong>リンク ID 11023</strong></p>
<p>この後方リンクに対応する前方リンクは <strong>msRTCSIP-PoolAddress</strong> です。</p></td>
<td><p>Live Communications Server 2005 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Gateways (廃止)</p></td>
<td><p>ゲートウェイとポート (ゲートウェイごとのポート) の一覧を含む複数値の文字列属性です。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalSettingsData (廃止)</p></td>
<td><p>名前と値のペアを格納する属性です。既に定義されている名前と値のペアは、<strong>&quot;プレゼンスのポーリングを許可する&quot;</strong> の設定に使用されます。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GroupingID</p></td>
<td><p>この属性は、アドレス帳のエントリをグループ化するために使用する、グループの一意の識別子です。</p></td>
<td><p>Lync Server 2010 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeServer (廃止)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003 で導入 (未使用)。</p>
<p>Live Communications Server 2005 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-HomeServerString (廃止)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003 で導入。</p>
<p>Live Communications Server 2005 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeUsers (廃止)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003 で導入 (未使用)。</p>
<p>Live Communications Server 2005 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-InternetAccessEnabled</p></td>
<td><p>1 人のユーザーを外部ユーザー アクセスに対して有効にするかどうかを制御する属性です。この制御はエンタープライズ サービス レイヤーによって適用されます。この属性には、グローバル カタログ レプリケーションのマークが付いています。</p>
<p>有効な値は、<strong>TRUE</strong> または <strong>FALSE</strong> です。</p></td>
<td><p>Live Communications Server 2005 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-IsMaster (廃止)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003 で導入。</p>
<p>Live Communications Server 2005 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Line</p></td>
<td><p>Lync がテレフォニーのために使用するデバイス ID (SIP URI またはユーザーがコントロールする電話の電話 URI) を含む単一値の属性です。この属性には、グローバル カタログ レプリケーションのマークとインデックスが付いています。ユーザーがエンタープライズ VoIP に対して有効な場合は、この属性は E.164 に正規化されたユーザーの電話番号を格納します。</p></td>
<td><p>Microsoft Office Live Communications Server 2005 SP1 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LineServer</p></td>
<td><p>CSTA-SIP ゲートウェイ サーバーの SIP URI を含む単一値の属性です。この属性には、グローバル カタログ レプリケーションのマークは付いていますが、インデックスは付いていません。</p></td>
<td><p>Microsoft Office Live Communications Server 2005 SP1 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationData (廃止)</p></td>
<td><p>この属性は将来の使用のために予約されています。</p></td>
<td><p>Office Communications Server 2007 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalizationLinks (廃止)</p></td>
<td><p>この場所のプロファイルに関連付けられているローカル正規化の識別名 (DN) の一覧を含む複数値の属性です。この属性の種類は DN Binary です。場所のプロファイルとローカル正規化ルールの間には一対多の関係があります。ローカル正規化の DN の一覧は、管理者が指定した順序で維持される必要があります。この順序は、DN Binary のバイナリ部 (順序のインデックスを指定します) によって維持されます。</p>
<p>前方リンク: <strong>リンク ID 11034</strong></p>
<p>この前方リンク属性に対応する後方リンクは <strong>msRTCSIP-LocationProfileBL</strong> です。</p></td>
<td><p>Office Communications Server 2007 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationOptions</p></td>
<td><p>正規化ルールに関するオプションの一覧を含む属性です。</p></td>
<td><p>Office Communications Server 2007 R2 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationName (廃止)</p></td>
<td><p>場所のプロファイルのフレンドリ名を含む単一値の属性です。この名前は、このプロファイルが表す場所を示します。場所のプロファイルは複数存在する可能性があるため、管理者には、それらを区別するための手段が必要です。</p></td>
<td><p>Office Communications Server 2007 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-locationProfileBL (廃止)</p></td>
<td><p>場所のプロファイルの識別名の一覧を含む複数値の属性です。この属性は、1 つ以上の場所のプロファイルへの後方リンクを指定します。</p>
<p>後方リンク: <strong>リンク ID 11035</strong></p>
<p>対応する前方リンクは <strong>msRTCSIP-LocalNormalizationLinks</strong> です。</p></td>
<td><p>Office Communications Server 2007 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfileData (廃止)</p></td>
<td><p>この属性は将来の使用のために予約されています。</p></td>
<td><p>Office Communications Server 2007 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfileOptions</p></td>
<td><p>場所のプロファイルのオプションを含む属性です。</p></td>
<td><p>Office Communications Server 2007 R2 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MappingContact</p></td>
<td><p>アプリケーションの連絡先の一覧を保持する複数値の属性です。</p></td>
<td><p>Office Communications Server 2007 R2 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MappingLocation</p></td>
<td><p>場所のプロファイルの一覧を保持する複数値の属性です。</p></td>
<td><p>Office Communications Server 2007 R2 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxNumOutstandingSearchPerServer (廃止)</p></td>
<td><p>サーバーごとの同時に処理できる検索要求の最大数を表す属性です。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxNumSubscriptionsPerUser (廃止)</p></td>
<td><p>ユーザーごとのサブスクリプションの最大数を表す属性です。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxPresenceSubscriptionTimeout (廃止)</p></td>
<td><p>サブスクリプション タイムアウト期間の最大値を表す属性です。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxRegistrationsTimeout (廃止)</p></td>
<td><p>登録タイムアウト期間の最大値を表す属性です。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxRoamingDataSubscriptionTimeout (廃止)</p></td>
<td><p>移動データ サブスクリプション タイムアウト期間の最大値を表す属性です。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUData</p></td>
<td><p>この属性は将来の使用のために予約されています。</p></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryAddress</p></td>
<td><p>コンピューター クラスのサービス制御ポイント属性です。所属する Multipoint Control Unit (MCU) ファクトリへのリンクを指定します。このサービス制御ポイント属性は、すべての Microsoft MCU に対して作成されます。各 Microsoft MCU では、プール レベルの設定を取得するために、所属するプールのバック エンド サーバーを見つける必要があります。</p>
<p>この属性の値は MCU ファクトリの識別名 (DN) です。この属性は単一値の属性で、グローバル カタログ レプリケーションのマークが付いています。</p>
<p>前方リンク: <strong>リンク ID 11026</strong></p>
<p>この前方リンク属性に対応する後方リンクは <strong>msRTCSIP-MCUServers</strong> です。</p></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryData</p></td>
<td><p>予約されている複数値の文字列属性です。この属性に格納される設定は、名前 = 値のペアとして表されます。現在定義されている名前 = 値のペアは次のとおりです。</p>
<ul>
<li><p>FactoryURL = &lt;URL&gt;</p></li>
</ul></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryPath</p></td>
<td><p>プールに関連付けられている 1 つの MCU ファクトリの識別名 (DN) を含む単一値の属性です。</p>
<p>前方リンク: <strong>リンク ID 11024</strong></p>
<p>この前方リンク属性に対応する後方リンクは <strong>msRTCSIP-PoolAddresses</strong> です。</p></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryProviderID</p></td>
<td><p>MCU ファクトリ プロバイダーの GUID を指定する単一値の文字列属性です。MCU ファクトリ プロセスは、この GUID 値に基づいて、その MCU の種類を処理するかどうかを決定します。GUID 値が <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong> の場合、MCU ファクトリ プロセス (Lync Server で既定で利用可能なプロセス) はその MCU の種類を処理します。その他の GUID 値の場合は処理しません。</p></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUServers</p></td>
<td><p>識別名 (DN) の一覧を含む複数値の属性です。この MCU ファクトリに関連付けられている同じ種類およびベンダーのすべての MCU サーバーの一覧が含まれています。各セグメントの有効な値は 63 文字、FQDN 全体では 255 文字です。</p>
<p>後方リンク: リンク ID 11027</p>
<p>この後方リンクに対応する前方リンクは、<strong>msRTCSIP-MCUFactoryAddress</strong> です。</p></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUType</p></td>
<td><p>MCU で処理できるメディアを指定する単一値の文字列属性です。</p>
<p>サポートされる有効な種類は次のとおりです。</p>
<ul>
<li><p>meeting</p></li>
<li><p>audio-video</p></li>
<li><p>chat</p></li>
<li><p>phone-conf</p></li>
</ul></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUVendor</p></td>
<td><p>MCU ベンダーの名前を指定する単一値の文字列属性です。すべての Microsoft MCU は、この属性を <strong>&quot;Microsoft Corporation&quot;</strong> に指定します。</p></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MeetingFlags (廃止)</p></td>
<td><p>すべてのユーザー オブジェクトや連絡先オブジェクトに対してグローバルに有効になるさまざまな会議オプションを定義する属性です。この属性は整数型のビット マスク値です。</p>
<p>有効な値 (および関連するビット位置) は次のとおりです。</p>
<ul>
<li><p>0: AllowOrganizeMeetingWithAnonymousParticipants が None (会議への匿名ユーザーの招待を許可しない) (ビットは設定されません)</p></li>
<li><p>4: AllowOrganizeMeetingWithAnonymousParticipants が Everyone (ユーザー全員に、会議への匿名ユーザーの招待を許可する) (ビット位置 2)</p></li>
<li><p>8: AllowOrganizeMeetingWithAnonymousParticipants が UsePerUserSetting (ユーザーごとの設定に基づいて、会議への匿名ユーザーの招待を許可する) (ビット位置 3)</p></li>
<li><p>16: UserPerUserMeetingPolicy (ユーザーごとに会議ポリシーが定義される) (ビット位置 4)</p></li>
</ul></td>
<td><p>Office Communications Server 2007 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MeetingPolicy (廃止)</p></td>
<td><p>管理者がこのユーザーに割り当てたポリシーの識別名 (DN) を単一値属性として指定する属性です。</p></td>
<td><p>Office Communications Server 2007 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinPresenceSubscriptionTimeout (廃止)</p></td>
<td><p>プレゼンス サブスクリプション タイムアウト期間の最小値を表す属性です。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MinRegistrationTimeout (廃止)</p></td>
<td><p>登録タイムアウト期間の最小値を表す属性です。</p></td>
<td><p>Office Communications Server 2007 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinRoamingDataSubscriptionTimeout (廃止)</p></td>
<td><p>移動データ サブスクリプション タイムアウト期間の最小値を表す属性です。</p></td>
<td><p>Office Communications Server 2007 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>この属性は、フロント エンド プールが使用するミラーリングされた SQL Server バックエンドを格納するために使用します。</p></td>
<td><p>New in Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MobilityFlags</p></td>
<td><p>モビリティの設定を定義するオプションやフラグを含む属性です。</p></td>
<td><p>Office Communications Server 2007 R2 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MobilityPolicy</p></td>
<td><p>モビリティ ポリシー オブジェクトの DN を含む属性です。</p></td>
<td><p>Office Communications Server 2007 R2 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-NumDevicesPerUser (廃止)</p></td>
<td><p>ユーザーが SIP コミュニケーション用に登録してプレゼンスにサブスクライブできるデバイスの数を表す属性です。</p></td>
<td><p>Office Communications Server 2007 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OptionFlags</p></td>
<td><p>ユーザー オブジェクトや連絡先オブジェクトに対して有効になるオプションを指定する属性です。この属性は整数型のビット マスク値です。各オプションはビットで表されます。この属性には、グローバル カタログ レプリケーションのマークが付いています。</p>
<p>有効な値 (および関連するビット位置) は次のとおりです。</p>
<ul>
<li><p>1: パブリック インスタント メッセージング (IM) 接続が有効 (ビット位置 0)</p></li>
<li><p>2: 予約済み (ビット位置 1)</p></li>
<li><p>4: 予約済み (ビット位置 2)</p></li>
<li><p>8: 予約済み (ビット位置 3)</p></li>
<li><p>16: リモート通話コントロールが有効 [テレフォニー] (ビット位置 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (会議への匿名ユーザーの招待を許可する) (ビット位置 6)</p></li>
<li><p>128: UCEnabled (ユーザーに対して UC を有効にする) (ビット位置 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (ユーザーに対してパブリック IM 接続を有効にする) (ビット位置 8)</p></li>
<li><p>512: RemoteCallControlDualMode (ビット位置 9)</p></li>
</ul></td>
<td><p>Live Communications Server 2005 SP1 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-OriginatorSID</p></td>
<td><p>リソース フォレストと中央フォレストのトポロジで、シングル サインオンを有効にするために使用される属性です。ユーザーの ObjectSID が、Windows NT Server プリンシパル アカウントから、リソース フォレストまたは中央フォレストの対応するユーザー オブジェクトまたは連絡先オブジェクトのこの属性にコピーされている場合に、シングル サインオンが有効になります。Communicator Web Access は、この属性またはユーザーの ObjectSID を使用して、ユーザーを AD DS で検索します。この属性には、グローバル カタログ レプリケーションのマークが付いています。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OwnerUrn</p></td>
<td><p>この属性は、アプリケーション連絡先の所有者の Uniform Resource Name (URN) です。</p></td>
<td><p>Lync Server 2010 で導入。</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Pattern (廃止)</p></td>
<td><p>電話番号を E.164 形式に一致させるために使用されるパターンを含む単一値の文字列属性です。電話番号がこのパターンに一致した場合は、ダイヤルされた番号に変換が適用されます。</p></td>
<td><p>Office Communications Server 2007 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteBL (廃止)</p></td>
<td><p>電話ルートの識別名 (DN) のリストを含む複数値の属性です。この属性は、1 つ以上の電話ルートへの後方リンクを指定します。</p>
<p>後方リンク: <strong>リンク ID 11033</strong></p>
<p>対応する前方リンクは <strong>msRTCSIP-RouteUsageLinks</strong> です。</p></td>
<td><p>Office Communications Server 2007 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRouteData (廃止)</p></td>
<td><p>この属性は将来の使用のために予約されています。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteName (廃止)</p></td>
<td><p>電話ルートのフレンドリ名を指定して、管理者が簡単に参照できるようにする単一値の UNICODE 文字列属性です。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneUsageData (廃止)</p></td>
<td><p>この属性は将来の使用のために予約されています。</p></td>
<td><p>Office Communications Server 2007 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyContent (廃止)</p></td>
<td><p>単一値の Unicode 文字列属性です。XML 形式のポリシー定義を含む文字列属性です。XML スキーマ定義はさまざまな種類のポリシーの間で共通です。ポリシーの種類ごとに異なるのはその設定だけです。</p>
<p>この XML スキーマ定義 (XSD) は次のように定義されています。</p>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;xs:schema id=&quot;instance&quot;  xmlns=&quot;&quot; xmlns:xs=&quot;http://www.w3.org/2001/XMLSchema&quot; xmlns:msdata=&quot;urn:schemas-microsoft-com:xml-msdata&quot;&gt;
  &lt;xs:element name=&quot;instance&quot; msdata:IsDataSet=&quot;true&quot;&gt;
    &lt;xs:complexType&gt;
      &lt;xs:choice maxOccurs=&quot;unbounded&quot;&gt;
        &lt;xs:element name=&quot;property&quot; nillable=&quot;true&quot;&gt;
          &lt;xs:complexType&gt;
            &lt;xs:simpleContent msdata:ColumnName=&quot;property_Text&quot; msdata:Ordinal=&quot;1&quot;&gt;
              &lt;xs:extension base=&quot;xs:string&quot;&gt;
                &lt;xs:attribute name=&quot;name&quot; type=&quot;xs:string&quot; /&gt;
              &lt;/xs:extension&gt;
            &lt;/xs:simpleContent&gt;
          &lt;/xs:complexType&gt;
        &lt;/xs:element&gt;
      &lt;/xs:choice&gt;
    &lt;/xs:complexType&gt;
  &lt;/xs:element&gt;
&lt;/xs:schema&gt;</code></pre></td>
<td><p>Office Communications Server 2007 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PolicyData (廃止)</p></td>
<td><p>この属性は将来の使用のために予約されています。</p></td>
<td><p>Office Communications Server 2007 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyType (廃止)</p></td>
<td><p>ポリシーの種類を含む単一値の Unicode 文字列属性です。有効なポリシーの種類は次のとおりです。</p>
<ul>
<li><p>meeting</p></li>
<li><p>telephony</p></li>
</ul></td>
<td><p>Office Communications Server 2007 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolAddress</p></td>
<td><p>コンピューターが所属するプールへのリンクを指定する属性です。この属性は、コンピューターで Standard Edition と Enterprise Edition のどちらの Lync Server が実行されているかに関係なく設定されます。この属性には、グローバル カタログ レプリケーションのマークが付いています。</p>
<p>有効な値はプールのドメイン名です。</p>
<p>前方リンク: <strong>リンク ID 11022</strong></p>
<p>この前方リンク属性に対応する後方リンクは <strong>msRTCSIP-FrontEndServers</strong> です。</p></td>
<td><p>Live Communications Server 2005 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolAddresses</p></td>
<td><p>MCU ファクトリが関連付けられているプールの識別名 (DN) のリストを含む複数値の属性です。</p>
<p>後方リンク: <strong>リンク ID 11025</strong></p>
<p>この後方リンクに対応する前方リンクは <strong>msRTCSIP-MCUFactoryPath</strong> です。</p></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolData</p></td>
<td><p>この属性は将来の使用のために予約されています。</p></td>
<td><p>Live Communications Server 2005 SP1 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolDisplayName</p></td>
<td><p>管理コンソールに表示されるプールの任意の名前を指定する属性です。この名前は管理者が変更できます。</p>
<p>有効な値は、プールの名前を表す文字列です。</p></td>
<td><p>Live Communications Server 2005 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolDomainFQDN</p></td>
<td><p>単一値の文字列属性です。この属性値は、フロントエンド プールを Active Directory ドメインのドメイン構造に準拠しない FQDN で作成する場合 (ドメイン ネーム システム (DNS) 名前空間から分離した SIP 名前空間など) に使用され、値が存在する場合は、そのプールのドメインの FQDN を表します。</p>
<p>フロントエンド プールのドメインの FQDN は、そのプールが存在する Active Directory ドメインのドメイン名の部分にマップすることをお勧めします。したがって、この属性の値が存在しない場合は、フロントエンド プールの FQDN の既定値が Active Directory ドメインのドメイン名構造 (<strong>dnsHostName</strong> 属性の値) になります。</p></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolFunctionality</p></td>
<td><p>プールに関連付けられているすべての Lync Server Enterprise Edition サーバーのドメイン名の複数値の一覧です。この整数型の属性は、プールがインスタント メッセージング (IM) とプレゼンス、および会議に対応しているかどうかを定義します。</p>
<p>有効な値の種類は次のとおりです。</p>
<ul>
<li><p>未定義: IM とプレゼンスのサービス (Live Communications Server 2005 および 2003)</p></li>
<li><p>1: IM とプレゼンスのサービス (Lync Server)</p></li>
<li><p>2: IM とプレゼンスおよび会議のサービス (Lync Server)</p></li>
</ul></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolType</p></td>
<td><p>サーバー プールで実行されているのは、Standard Edition または Enterprise Edition のどちらのサーバーなのかを指定する属性です。この属性は整数型のビット マスク値です。各オプションはビットで表されます。</p>
<p>有効な値 (および関連するビット位置) は次のとおりです。</p>
<ul>
<li><p>1: Standard Edition サーバー、ユーザーをホスト (ビット位置 0)</p></li>
<li><p>2: Enterprise Edition サーバー、ユーザーをホスト (ビット位置 1)</p></li>
<li><p>4: Standard Edition サーバー、アプリケーションをホスト (ビット位置 2)</p></li>
<li><p>8: Enterprise Edition サーバー、アプリケーションをホスト (ビット位置 3)</p></li>
</ul>
<p>Lync Server は、アプリケーションのみをホストするプールをサポートしていないので、有効なのは次の値だけです。</p>
<ul>
<li><p>5: Standard Edition サーバー、ユーザーとアプリケーションをホスト (ビット位置 0 および 2)</p></li>
<li><p>10: Enterprise Edition サーバー、ユーザーとアプリケーションをホスト (ビット位置 1 および 3)</p></li>
</ul></td>
<td><p>Live Communications Server 2005 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolVersion</p></td>
<td><p>プールのバージョンを定義する属性です。製品のメジャー リリースごとにインクリメントされる整数型です。</p>
<p>有効な値の種類は次のとおりです。</p>
<ul>
<li><p>0: Live Communications Server 2003</p></li>
<li><p>1: Live Communications Server 2005</p></li>
<li><p>2: Live Communications Server 2005 SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
</ul></td>
<td><p>Live Communications Server 2005 SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PresenceFlags</p></td>
<td><p>プレゼンスの設定を定義するオプションやフラグを含む属性です。</p></td>
<td><p>Office Communications Server 2007 R2 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PresencePolicy</p></td>
<td><p>プレゼンス ポリシー オブジェクトの DN を含む属性です。</p></td>
<td><p>Office Communications Server 2007 R2 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrimaryHomeServer</p></td>
<td><p>ユーザーまたは連絡先を SIP メッセージングに対して有効にする属性です。中央フォレスト トポロジで SIP が有効なのは、ユーザー オブジェクトではなく、連絡先オブジェクトです。このため、この属性は連絡先クラスに追加されています。</p>
<p>有効な値は、ユーザーのホームになる Standard Edition サーバーまたは Enterprise Edition フロントエンド プールの DN です。</p></td>
<td><p>Live Communications Server 2005 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>特定のユーザーの SIP アドレスを含む属性です。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrivateLine</p></td>
<td><p>プライベート番号デバイスのデバイス ID を含む属性です。</p></td>
<td><p>Lync Server 2010 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Routable</p></td>
<td><p>Lync Server が、GRUU アドレスを使用したこのサービスへのルーティングを承認されているかどうかを判断するために使用されるブール値の属性です。この値が <strong>TRUE</strong> に設定されている場合、Lync Server はこのサービスへのルーティングを承認されています。この値が <strong>FALSE</strong> に設定されている場合、Lync Server はこのサービスへのルーティングを承認されていません。</p></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsageAttribute (廃止)</p></td>
<td><p>電話ルート使用法を修飾する属性を定義する単一値の UNICODE 文字列属性です。電話ルートの選択は、2 つの要素に基づいて行われます。電話ルートに割り当てられた使用法属性と、発信者の許可されたポリシー使用法属性です。発信者の許可された使用法と一致する使用法属性を持つ最初の電話ルートが選択されます。</p></td>
<td><p>Office Communications Server 2007 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsageLinks (廃止)</p></td>
<td><p>ルート使用法の識別名 (DN) の一覧を含む複数値の属性です。</p>
<p>前方リンク: <strong>リンク ID 11032</strong></p>
<p>この前方リンク属性に対応する後方リンクは <strong>msRTCSIP-PhoneRouteBL</strong> です。</p></td>
<td><p>Lync Server 2010 で廃止。</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RoutingPoolDN</p></td>
<td><p>この MCU または信頼済みサービス宛てのすべての SIP トラフィックが通過する必要のあるプールを指す DN を含む属性です。</p></td>
<td><p>Office Communications Server 2007 R2 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RuleName (廃止)</p></td>
<td><p>正規化ルールのフレンドリ名を指定して、管理者が簡単に参照できるようにする単一値の UNICODE 文字列属性です。</p></td>
<td><p>Office Communications Server 2007 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SchemaVersion</p></td>
<td><p>現在組織に展開されているスキーマのバージョンを表す属性です。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SearchMaxRequests (廃止)</p></td>
<td><p>ユーザーが Communicator を使用して連絡先を検索したときに、ディレクトリ検索から返される検索結果の数を制限する属性です。この属性は、クライアントによって指定された値より優先されます。</p></td>
<td><p>Lync Server 2010 で廃止。</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SearchMaxResults (廃止)</p></td>
<td><p>返される検索要求の数を制限する属性です。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerBL</p></td>
<td><p>識別名 (DN) の一覧を含む複数値の属性です。この属性は後方リンクです。これらの DN は、プール オブジェクトまたは <strong>TrustedService</strong> オブジェクトを参照します。</p>
<p>対応する前方リンクは <strong>msRTCSIP-TrustedServiceLinks</strong> です。</p></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerData</p></td>
<td><p>この属性は将来の使用のために予約されています。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerReferenceBL (廃止)</p></td>
<td><p>識別名の一覧を含む複数値の属性です。これらの識別名は、既定の場所のプロファイルを割り当てることができる他のサーバー オブジェクトを参照する後方リンクです。</p>
<p>後方リンク: <strong>リンク ID 11037</strong></p>
<p>この後方リンクに対応する前方リンクは <strong>msRTCSIP-DefaultLocationProfileLink</strong> です。</p>
<p>この後方リンク属性が参照するのはプールと仲介サーバーだけです。</p></td>
<td><p>Office Communications Server 2007 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerVersion</p></td>
<td><p>サーバーのバージョン情報を定義する属性です。このバージョン番号は、すべてのサーバーの役割に適用されます。この属性は、製品が正式にリリースされるたびにインクリメントされる単調増加の整数型です。</p>
<p>有効な値は次のとおりです。</p>
<ul>
<li><p>未定義: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
</ul></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SourceObjectType</p></td>
<td><p><strong>msDS-SourceObjectDN</strong> が参照するオブジェクトの種類を指定する整数型の単一値属性です。値は次のとおりです。</p>
<ul>
<li><p>null | 0x00000001: 別のフォレストの Windows NT Server プリンシパル ユーザー オブジェクトを表します。</p></li>
<li><p>以下の属性は、配布グループ拡張のための別のフォレストのグループの種類を表します。</p>
<ul>
<li><p>0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</p></li>
<li><p>0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</p></li>
<li><p>0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</p></li>
<li><p>0x90000000: 同じフォレストまたは別のフォレストの自動応答オブジェクト、またはサブスクライバー アクセス オブジェクトを表します。</p></li>
</ul></li>
</ul></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SubscriptionAuthRequired (廃止)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003 で導入。</p>
<p>Live Communications Server 2005 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetHomeServer</p></td>
<td><p>ユーザーや連絡先を、Lync Server プールの間で移動できるようにする属性です。中央フォレスト トポロジで SIP が有効なのは、ユーザー オブジェクトではなく、連絡先オブジェクトです。このため、この属性は連絡先クラスに追加されています。</p>
<p>有効な値は、ユーザーの移動先となる Standard Edition サーバーまたはフロントエンド プールの DN です。</p></td>
<td><p>Live Communications Server 2005 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TargetPhoneNumber (廃止)</p></td>
<td><p><strong>msRTCSIP-Gateways</strong> で定義されている特定のゲートウェイにルーティングする電話番号のパターンまたは範囲を含む単一値の文字列属性です。</p></td>
<td><p>Lync Server 2010 で廃止。</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetUserPolicies</p></td>
<td><p>Lync Server のユーザーを対象とするポリシーのために、名前と値のペアを格納する属性です。</p></td>
<td><p>Lync Server 2010 で導入。</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TenantId</p></td>
<td><p>テナントの一意の識別子を格納する属性です。</p></td>
<td><p>Lync Server 2010 で導入。</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Translation (廃止)</p></td>
<td><p>Lync Server の音声機能によって使用される属性で、ダイヤルされた番号に (番号が一致した場合に) 適用される変換文字列が含まれています。</p></td>
<td><p>Office Communications Server 2007 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCUData</p></td>
<td><p>この属性は将来の使用のために予約されています。</p></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUFQDN</p></td>
<td><p>MCU の FQDN を含む文字列値の属性です。この属性は単一値の属性です。各セグメントの有効な値は 63 文字、FQDN 全体では 255 文字です。</p></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxyData</p></td>
<td><p>この属性は将来の使用のために予約されています。</p></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxyFQDN</p></td>
<td><p>プロキシ サーバーを実行しているサーバーの FQDN を含む文字列値の属性です。この属性は単一値の属性です。各セグメントの有効な値は 63 文字、FQDN 全体では 255 文字です。</p></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerData</p></td>
<td><p>この属性は将来の使用のために予約されています。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServerFQDN</p></td>
<td><p>信頼済みサーバーの FQDN を表す単一値の属性です。</p></td>
<td><p>Live Communications Server 2005 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerVersion</p></td>
<td><p>信頼済みサーバーの一覧のサーバーのバージョン番号を指定する属性です。</p>
<p>有効な値は次のとおりです。</p>
<ul>
<li><p>NULL: Live Communications Server 2003</p></li>
<li><p>2: Live Communications Server 2005</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
</ul></td>
<td><p>Live Communications Server 2005 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServiceFlags</p></td>
<td><p>信頼済みサービスに対して有効になるオプションを定義する属性です。</p></td>
<td><p>Office Communications Server 2007 R2 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceLinks</p></td>
<td><p>信頼済みサービス オブジェクト (メディア リレー認証サービスなど) を参照する識別名 (DN) の一覧を含む複数値の属性です。リモート ユーザーのオーディオのシナリオをサポートするには、メディア リレー認証サービス (物理的には音声ビデオ会議サービスを実行しているエッジ サーバー上に併置されている) がプールに関連付けられている必要があります。</p>
<p>この前方リンク属性に対応する後方リンクは <strong>msRTCSIP-ServerBL</strong> です。</p></td>
<td><p>UC</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServicePort</p></td>
<td><p>この GRUU サービスに接続するために使用されるポート番号を定義する整数の属性です。</p></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceType</p></td>
<td><p>クラスが表す GRUU サービスの種類を定義する文字列値の属性です。</p>
<p>有効な GRUU サービスの種類は次のとおりです。</p>
<ul>
<li><p>MediationServer</p></li>
<li><p>Gateway</p></li>
<li><p>メディア リレー認証サービス (MRAS)</p></li>
<li><p>QoSM</p></li>
<li><p>msRTCSIP-UserExtension CWA</p></li>
</ul></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServerData</p></td>
<td><p>この属性は将来の使用のために予約されています。</p></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServerFQDN</p></td>
<td><p>Lync Server Web サービスを実行している IIS の FQDN を含む文字列値の属性です。この属性は単一値の属性です。各セグメントの有効な値は 63 文字、FQDN 全体では 255 文字です。</p></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UCFlags (廃止)</p></td>
<td><p>すべてのユーザー オブジェクトや連絡先オブジェクトに対してグローバルに有効になるさまざまな UC のオプションを定義する属性です。この属性は整数型のビット マスク値です。各オプションはビットの存在によって表されます。</p>
<p>有効な値 (および関連するビット位置) は次のとおりです。</p>
<ul>
<li><p>4: UsePerUserUCPolicy (ビット位置 2)</p></li>
</ul>
<p>このビットが設定されている場合は、UC ポリシーがユーザーごとに定義されます。</p></td>
<td><p>Lync Server 2010 で廃止。</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UCPolicy (廃止)</p></td>
<td><p>管理者がこのユーザーに対して割り当てた UC ポリシーの識別名 (DN) を含む単一値の属性です。</p></td>
<td><p>Lync Server 2010 で廃止。</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserDomainList (廃止)</p></td>
<td><p>SIP 対応のユーザーをホストするフォレスト内のすべてのドメインの一覧を指定する属性です。既定値は空の一覧です。これは、フォレスト内のすべてのドメインが SIP 対応であることを示します。</p>
<p>有効な値は、個々のドメインのドメイン名を表す複数の文字列です。</p></td>
<td><p>Live Communications Server 2005 で導入。</p>
<p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserEnabled</p></td>
<td><p>Lync Server に対して有効になっているかどうかを決定する属性です。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserExtension</p></td>
<td><p>&quot;name=value&quot; という形式の名前と値のペアの一覧を含む複数値の属性です。この属性には、グローバル カタログ レプリケーションのマークが付いています。</p></td>
<td><p>Live Communications Server 2005 SP1 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserLocationProfile</p></td>
<td><p>場所のプロファイル オブジェクトを指す識別名 (DN) を含む属性です。</p></td>
<td><p>Office Communications Server 2007 R2 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserPolicies</p></td>
<td><p>ユーザー ポリシーのために、名前と値のペアを格納する属性です。</p></td>
<td><p>Lync Server 2010 で導入。</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserPolicy</p></td>
<td><p>複数値の属性です。さまざまな種類のグローバル ユーザー ポリシーを参照する、バイナリを含む識別名 (DN_WITH_BINARY) の一覧が含まれています。バイナリ部は、DN 部が参照するポリシーの種類を示します。</p>
<p>有効なバイナリ値は次のとおりです。</p>
<ul>
<li><p>0x00000001: 会議ポリシー</p></li>
<li><p>0x00000002: UC ポリシー</p></li>
<li><p>0x00000005: プレゼンス ポリシー</p></li>
</ul></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>SIP ルーティング グループ ID。同じグループのユーザーは、同じフロントエンド サーバーに登録します。</p></td>
<td><p>Lync Server 2013 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsData</p></td>
<td><p>複数値の属性です。この属性は将来の使用のために予約されています。</p></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsPoolAddress</p></td>
<td><p>Web コンポーネントが所属するプールまたは Standard Edition サーバーを参照する単一値の属性です。</p>
<p>前方リンク: <strong>リンク ID 11028</strong></p>
<p>この前方リンク属性に対応する後方リンクは <strong>msRTCSIP-WebComponentsServers</strong> です。</p></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsServers</p></td>
<td><p>識別名の一覧を含む複数値の属性です。このプールに関連付けられているすべての Web サーバーの一覧が含まれています。</p>
<p>後方リンク: <strong>リンク ID 11029</strong></p>
<p>この後方リンクに対応する前方リンクは <strong>msRTCSIP-WebComponentsPoolAddress</strong> です。</p></td>
<td><p>Office Communications Server 2007 で導入。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WMIInstanceId (廃止)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003 で導入。</p>
<p>Live Communications Server 2005 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>OtherIPPhone</p></td>
<td><p>Active Directory の既存の属性です。テレフォニーが電話の代替 TCP/IP アドレスの一覧を指定するときに使用されます。</p></td>
<td><p>Windows Server 2008 オペレーティング システムで導入。</p></td>
</tr>
<tr class="even">
<td><p>PhoneOfficeOther</p></td>
<td><p>Lync Server の音声コンポーネントによって使用される、Active Directory の既存の属性です。呼び出しをユニファイド メッセージングの自動応答およびサブスクライバー アクセスの番号にルーティングするために、連絡先オブジェクトに対してのみ使用されます。無条件着信転送アドレスは、この複数値の属性に格納されます。このアカウントは、自動応答およびサブスクライバ アクセスのために特別に作成されるアカウントです。このアカウントの属性を変更しないでください。</p></td>
<td><p>Windows 2000 オペレーティング システムで導入。</p></td>
</tr>
<tr class="odd">
<td><p>ProxyAddresses</p></td>
<td><p>Windows 2000 で導入された基本 Active Directory スキーマの一部である、Active Directory の既存の複数値属性で、X400、X500、SMTP など、ユーザーの電子メールのさまざまなアドレスが含まれています。Live Communications Server 2003 以降では、このリストにユーザーの SIP URI が追加されています (&quot;sip:&quot; タグが使用されます)。</p>
<p>以下のアプリケーションは、この属性でユーザーの SIP URI を検索します。</p>
<ul>
<li><p>Microsoft Office Outlook 2003 メッセージングおよびコラボレーション クライアント</p></li>
<li><p>Microsoft Office SharePoint Server 2007</p></li>
</ul></td>
<td><p>Windows 2000 オペレーティング システムで導入。</p></td>
</tr>
<tr class="even">
<td><p>TelephoneNumber</p></td>
<td><p>ユーザーの電話番号が含まれる、Active Directory の既存の属性です。</p></td>
<td><p>Windows 2000 オペレーティング システムで導入。</p></td>
</tr>
</tbody>
</table>

