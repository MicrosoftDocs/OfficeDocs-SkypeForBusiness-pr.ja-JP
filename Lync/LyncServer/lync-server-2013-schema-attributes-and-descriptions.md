---
title: 'Lync Server 2013: スキーマの属性と説明'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc18b4b074302ba3c233670f21fd8479bbd0b0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a>Lync Server 2013 でのスキーマの属性と説明

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-06_

このセクションでは、Lync Server 2013 で使用されるすべてのスキーマ属性について説明します。 属性に関連付けられているクラスについては、「 [Lync Server 2013 のクラス別のスキーマ属性](lync-server-2013-schema-attributes-by-class.md)」をご覧ください。 Lync Server 2013 で新しく追加されたクラスと属性の一覧については、「 [Lync server 2013 でのスキーマの変更](lync-server-2013-schema-changes-in-lync-server-2013.md)」を参照してください。

リンクペアの属性は、転送リンクまたは戻るリンクとして指定します。 別のオブジェクトを参照する属性は、転送リンクです。最初のオブジェクトを参照する他のオブジェクトの属性は、[戻る] リンクです。 前方リンクは更新可能で、戻るリンクは読み取り専用です。

一部の属性にはビットマスク値があります。 これらの属性の場合、各設定は1ビットで表され、表示される10進値はビット位置を表します。 ビット位置はビット0から始まります。 たとえば、1 (binary) はビット0に設定され、1万 (binary) はビット4で設定されています。 各ビットはプロパティを表します。 次に例を示します。

  - 1万 (binary) の10進数は16です (つまり、ビット4が設定されています)。

  - 1億 (binary) の小数点以下の値は 256 (ビット8が設定されている) です。

  - 1100 (binary) の10進数の値は12です (つまり、ビット2と3は設定され、両方のビットで表されるプロパティは有効です)。

  - 1111000001 (binary) には、10進数の 961 (ビット0、6、7、8、および9の値が設定されています。これらの各ビットのプロパティは有効です)。

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a>Lync Server 2013 のスキーマ属性

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
<td><p><strong>Msrtcsip-userenabled true</strong>と<strong>msrtcsip-userenabled true の</strong>両方のサーバークラスに関連付けられている、Active Directory ドメインサービス内の既存の属性。 この属性は、プールまたは監視サーバーの完全修飾ドメイン名 (FQDN) を指定します。</p>
<p>各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</p></td>
<td><p>Microsoft Office Live Communications Server 2005 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>SourceObjectDN</p></td>
<td><p>この属性には、このオブジェクトに対応する別のフォレストのオブジェクトの識別名 (DN) の文字列表現が含まれます。 この属性は、配布グループの展開と自動参加に使用されます。 この属性は、Windows Server 2003 R2 の既定の Active Directory スキーマで定義されています。</p>
<p>AD DS から Windows Server 2003 R2 へのアップグレードを必要としないように、Active Directory スキーマの準備では、Windows Server 2003 スキーマがこの属性定義で拡張されます。</p></td>
<td><p>Microsoft Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msExchUCVoiceMailSettings</p></td>
<td><p>この複数値属性はボイスメールの設定を保持します。 この属性は、Exchange ユニファイドメッセージング (UM) と共有されます。</p></td>
<td><p>Microsoft Lync Server 2010 の新製品です。</p></td>
</tr>
<tr class="even">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>このマルチバリュー属性は、ユーザーに適用される保留ポリシーの識別子を保持します。 保留ポリシーは、保留中のユーザーのメールボックスアイテムを保持します。 この属性は Exchange 2013 と共有されます。</p></td>
<td><p>Lync Server 2013 の新サービスです。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-AcpInfo</p></td>
<td><p>この属性は、ユーザーに対して電話会議プロバイダーの情報を格納します。</p></td>
<td><p>Lync Server 2010 の新サービスです。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-ApplicationDestination</p></td>
<td><p>この属性は、アプリケーションの連絡先に対して信頼されているサービスエントリを指します。</p></td>
<td><p>Microsoft Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-ApplicationList</p></td>
<td><p>この属性には、アプリケーションサーバー上でホストされているアプリケーションの一覧が含まれます。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-ApplicationOptions</p></td>
<td><p>この属性は、アプリケーションの連絡先のオプションを指定します。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-ApplicationPrimaryLanguage</p></td>
<td><p>この属性には、アプリケーションの連絡先の第一言語が含まれます。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-ApplicationSecondaryLanguages</p></td>
<td><p>この複数の値の属性には、アプリケーションの連絡先のセカンダリ言語が含まれています。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-ApplicationServerBL</p></td>
<td><p>この属性には、このプールに属しているアプリケーションサーバーの一覧が含まれます。 このバックリンク属性への対応する前方リンクは<strong>Msrtcsip-userenabled true Serverpoollink</strong>です。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-ApplicationServerPoolLink</p></td>
<td><p>この属性は、このアプリケーションサーバーが属しているプールを指します。 これは、転送リンクです。 対応する後方リンクは、 <strong>Msrtcsip-userenabled true Serverbl</strong>です。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-アーカイブの既定値 (廃止)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2005 の新サービスです。</p>
<p>Office Communications Server 2007 で廃止されます。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-アーカイブ Defaultflags (廃止)</p></td>
<td><p>この属性は、すべてのユーザーの通信をアーカイブするために、フォレストの境界内でグローバルな既定値を指定します。 これは、アーカイブエージェントレイヤーによって適用されます。 この属性の値の範囲は、次のようになります。</p>
<ul>
<li><p><strong>TRUE</strong>: すべてのユーザーをアーカイブする</p></li>
<li><p><strong>FALSE</strong>: すべてのユーザーをアーカイブしない</p></li>
</ul>
<p>この属性は、フォレストの境界内でのグローバルコントロールであり、内部ネットワーク内でのユーザーの通信はどのようにアーカイブされますか。</p>
<p><strong>Live Communications Server 2005 の動作 (現在は廃止)</strong></p>
<p>この属性の値の範囲は、次のようになります。</p>
<ul>
<li><p>0: メッセージ本文をアーカイブする [ビット 0]</p></li>
<li><p>1: メッセージ本文をアーカイブしない [ビット 0]</p></li>
</ul>
<p><strong>Office Communications Server 2007 の動作</strong></p>
<p>この属性の値の範囲は、次のようになります。</p>
<ul>
<li><p>0: ArchiveFederationDefaultWithoutBody (廃止)</p></li>
<li><p>1-2: アーカイブ内部通信</p></li>
<li><p>3-4: ArchiveFederatedCommunications</p></li>
<li><p>5: RecordPresenceRegistrations</p></li>
<li><p>6: RecordIMCallDetails</p></li>
<li><p>7: RecordGroupIMCallDetails</p></li>
<li><p>8: RecordFileTransferInstances</p></li>
<li><p>9: RecordAudioCallDetails</p></li>
<li><p>10: RecordVideoCallDetails</p></li>
<li><p>11: RecordRemoteAssistanceCallDetails</p></li>
<li><p>12: RecordApplicationSharingDetails</p></li>
<li><p>13: Record会議のインスタンス化</p></li>
<li><p>14: Record会議の結合</p></li>
<li><p>15: RecordDataJoins</p></li>
<li><p>16: RecordAVJoins</p></li>
</ul></td>
<td><p>Live Communications Server 2005 の新サービスです。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-ArchiveFederationDefault (廃止)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2005 の新サービスです。</p>
<p>Office Communications Server 2007 で廃止されます。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-ArchiveFederationDefaultFlags (廃止)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2005 の新サービスです。</p>
<p>Office Communications Server 2007 で廃止されます。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-ArchivingEnabled</p></td>
<td><p>この属性は、1人のユーザーの通信がアーカイブされるかどうかを制御するためのビットフィールドとして使用される整数です。 このコントロールは、アーカイブエージェントレイヤーによって適用されます。 グローバルカタログのレプリケーション用にマークされています。</p>
<p>この属性の範囲は、1人のユーザーまたは連絡先によって異なります。 Lync Server の有効な値 (および関連するビット位置) は、次のとおりです。</p>
<ul>
<li><p>0: アーカイブしない (ビットセットなし)</p></li>
<li><p>1: 廃止 (ビット位置 0)</p></li>
<li><p>2: 廃止 (ビット位置 1)</p></li>
<li><p>4: 内部通信をアーカイブする (ビット位置 2)</p></li>
<li><p>8: フェデレーション通信をアーカイブする (ビット位置 3)</p></li>
</ul>
<p>Live Communications Server 2005 で以前に有効になっていた値は、次のようになります。</p>
<ul>
<li><p>0: Msrtcsip-userenabled true によって定義された既定値を使用します。これは、次の優先順位で、<strong>アーカイブの既定</strong>と<strong>msrtcsip-userenabled true フェデレーション</strong>によって定義されます。</p>
<ul>
<li><p>1: アーカイブ</p></li>
<li><p>2: アーカイブしない</p></li>
<li><p>3: メッセージ本文を含まないアーカイブ</p></li>
</ul></li>
</ul></td>
<td><p>Live Communications Server 2005 の新サービスです。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-ArchivingServerData (廃止)</p></td>
<td><p>この属性は将来使用するために予約されています。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-ArchivingServerVersion (廃止)</p></td>
<td><p>この属性は、アーカイブサービスのバージョンを定義します。 この属性は、各公式の製品リリースによってインクリメントされる monotonously の増加整数型です。 有効な値は、次のとおりです。</p>
<ul>
<li><p>未定義: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
</ul></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-BackEndServer</p></td>
<td><p>この属性は、プールのバックエンドサーバーの FQDN を指定します。 バックエンドサーバーは1つのプールにつき1つしか存在できないため、これは単一値の属性です。</p>
<p>各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</p></td>
<td><p>Live Communications Server 2005 の新サービスです。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-ConferenceDirectoryHomePool</p></td>
<td><p>この属性には、会議ディレクトリをホストするプールの識別子が含まれます。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-ConferenceDirectoryId</p></td>
<td><p>この属性には、会議ディレクトリの識別子が含まれます。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-ConferenceDirectoryTargetPool</p></td>
<td><p>この属性には、会議ディレクトリの移動先のプールの識別子が含まれています。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-既定値</p></td>
<td><p>このブール値の属性は、電話の使用状況が既定で使用されているかどうかを定義します。 この属性が<strong>TRUE</strong>に設定されている場合、電話の使用状況は既定で使用されているため、管理者は削除できません。 この属性が<strong>FALSE</strong>に設定されている場合、使用法は削除できます。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-DefaultCWAExternalURL</p></td>
<td><p>この属性は、組織外のユーザーの Communicator Web Access URL を識別します。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-DefaultCWAInternalURL</p></td>
<td><p>この属性は、組織内のユーザーの Communicator Web Access URL を識別します。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-DefaultLocationProfileLink (廃止)</p></td>
<td><p>この単一値の属性には、割り当てられた位置情報プロファイルクラスオブジェクトの識別名 (DN) が含まれます。</p>
<p>転送リンク:<strong>リンク ID 11036</strong></p>
<p>対応する後方リンクは、 <strong>msrtcsip-userenabled true-ServerReferenceBL</strong>です。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-DefaultPolicy (廃止)</p></td>
<td><p>このブール属性は、ポリシーが既定のポリシーであるかどうかを指定します。 ポリシーは、 <strong>TRUE</strong>に設定されている場合の既定のポリシーです。</p></td>
<td><p>Office Communications Server 2007 の新製品</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-DefaultRouteToEdgeProxy (廃止)</p></td>
<td><p>この属性は、アクセスエッジサービスを実行しているエッジサーバーの FQDN (access edge サービスを実行しているサーバーのプールに直接アクセスできるか、またはハードウェアロードバランサー) を指定します。 アクセスエッジサービスを実行しているサーバーが1つ以上のディレクターを介してのみアクセスできる場合、この属性は、ディレクタープールを提供するディレクターまたはハードウェアロードバランサーのポート番号を指定します。</p>
<p>各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</p></td>
<td><p>Live Communications Server 2005 の新サービスです。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-DefaultRouteToEdgeProxyPort (廃止)</p></td>
<td><p>この属性は、アクセスエッジサービスを実行しているサーバーへの接続に使用するポート番号を表します。</p>
<p>有効な値は、使用するポートを指定する整数値です。 既定値は5061です。</p></td>
<td><p>Live Communications Server 2005 の新サービスです。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-DefPresenceSubscriptionTimeout (廃止)</p></td>
<td><p>この属性は、既定のプレゼンスサブスクリプションのタイムアウト期間を表します。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-DefRegistrationTimeout (廃止)</p></td>
<td><p>この属性は、既定の登録タイムアウトウィンドウを表します。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-DefRoamingDataSubscriptionTimeout (廃止)</p></td>
<td><p>この属性は、既定のローミングデータサブスクリプションのタイムアウトウィンドウを表します。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DeploymentLocator</p></td>
<td><p>この属性は、分割ドメイントポロジで使用され、完全修飾ドメイン名 (FQDN) が含まれます。</p></td>
<td><p>Lync Server 2010 の新サービスです。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-Description (廃止)</p></td>
<td><p>この単一値の UNICODE 文字列属性には、この電話ルートまたは正規化ルールのわかりやすい説明が含まれています。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-DomainData</p></td>
<td><p>この属性は将来使用するために予約されています。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-ドメイン名</p></td>
<td><p>この属性は、レジストラー用に構成されているドメインを表します。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-EdgeProxyData</p></td>
<td><p>この属性は将来使用するために予約されています。</p></td>
<td><p>Live Communications Server 2005 の新サービスです。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-EdgeProxyFQDN</p></td>
<td><p>この属性は、Access Edge サービスを実行しているサーバーの FQDN を指定します。</p>
<p>各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</p></td>
<td><p>Live Communications Server 2005 の新サービスです。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-EnableBestEffortNotify (廃止)</p></td>
<td><p>この属性は、クライアントからの SUBSCRIBE 要求に応じて、サーバーが NOTIFY 要求ではなく、ベストエフォート通知 (BENOTIFY) 要求を生成するかどうかを制御します。 BENOTIFY は、通常の通知要求の代わりにサーバーが BENOTIFY 要求を生成する、サブスクライブ通知ハンドシェイクのパフォーマンス強化された拡張機能です。 パフォーマンスの利点は、通知要求によって、BENOTIFY 要求でクライアントから 200 OK 応答が要求されないことです。</p>
<p>有効な値は、 <strong>TRUE</strong>または<strong>FALSE</strong>です。</p>
<div>

> [!NOTE]  
> Live Communications Server 2003 は BENOTIFY 要求をサポートしていません。 Live communications server の2005とサードパーティのサーバーで実行されている Live Communications Server 2003 server API で記述されたサーバーアプリケーションと相互運用するには、BENOTIFY 要求の値を<STRONG>FALSE</STRONG>に設定して無効にすることができます。 現在、BENOTIFY は IETF (インターネットエンジニアリングタスクフォース) SIP 標準化プロセスの一部ではありません。


</div></td>
<td><p>Live Communications Server 2005 の新サービスです。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-EnableFederation (廃止)</p></td>
<td><p>この属性は、IT 管理者が他の組織のユーザーとの通信を許可するかどうかを構成するために使用するグローバルスイッチです。 管理者が個々のユーザーの<strong>FederationEnabled</strong>属性を上書きできるようにします。 この属性は、ワーム、ウイルス、または企業の標的となる攻撃によって発生する可能性があるインターネット攻撃から内部ネットワークを保護するために役立ちます。</p>
<p>有効な値 (および関連するビット位置) は、次のようになります。</p>
<ul>
<li><p>1: パブリック IM 接続を有効にする (ビット位置 0)</p></li>
<li><p>2: 予約済み (ビット位置 1)</p></li>
<li><p>4: 予約済み (ビット位置 2)</p></li>
<li><p>8: 予約済み (ビット位置 3)</p></li>
<li><p>16: リモート通話コントロールが有効になっている [Telephony] (ビット位置 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (ユーザーが会議に匿名ユーザーを招待することを許可する (ビット位置 6)</p></li>
<li><p>128: UCEnabled (ユニファイドコミュニケーションのためのユーザーの有効化) (ビット位置 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (ユーザーにパブリック IM 接続を有効にする) (ビット位置 8)</p></li>
<li><p>512: RemoteCallControlDualMode (ビット位置 9)</p></li>
</ul></td>
<td><p>Live Communications Server 2005 の新サービスです。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-EnterpriseServices</p></td>
<td><p>この属性は、エンタープライズサービスが指定されたサーバーに読み込まれているかどうかを示します。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-ExtensionData</p></td>
<td><p>この属性は将来使用するために予約されています。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-ExternalAccessCode</p></td>
<td><p>この属性には、外部アクセスのダイヤルコードが含まれています。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-FederationEnabled</p></td>
<td><p>この属性は、1人のユーザーがフェデレーションを有効にしているかどうかを制御します。 エンタープライズサービスレイヤーによって適用されます。 グローバルカタログのレプリケーション用にマークされています。</p>
<p>有効な値は、 <strong>TRUE</strong>または<strong>FALSE</strong>です。</p></td>
<td><p>Live Communications Server 2005 の新サービスです。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-FrontEndServers</p></td>
<td><p>この属性は、プールに関連付けられたすべての Enterprise Edition サーバーのドメイン名の複数値を持つ一覧です。</p>
<p>戻るリンク:<strong>リンク ID 11023</strong></p>
<p>この戻るリンクへの対応する前方リンクは<strong>msrtcsip-userenabled true の住所</strong>です。</p></td>
<td><p>Live Communications Server 2005 の新サービスです。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-ゲートウェイ (廃止)</p></td>
<td><p>この複数値文字列属性には、ゲートウェイとポート (ゲートウェイごと) の一覧が含まれています。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-GlobalSettingsData (廃止)</p></td>
<td><p>この属性には、名前と値のペアが格納されます。 既に定義された名前: 値のペアは、プレゼンス設定の [<strong>ポーリングを許可</strong>する] に対応しています。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-GroupingID</p></td>
<td><p>この属性は、アドレス帳のエントリをグループ化するために使用されるグループの一意の識別子です。</p></td>
<td><p>Lync Server 2010 の新サービスです。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-HomeServer (廃止)</p></td>
<td><p>-</p></td>
<td><p>最新のライブ通信サーバー 2003 (使用されていません)。</p>
<p>現在、ライブ通信サーバー2005で廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-HomeServerString (廃止)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003 の新サービスです。</p>
<p>現在、ライブ通信サーバー2005で廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-ホームユーザー (廃止)</p></td>
<td><p>-</p></td>
<td><p>最新のライブ通信サーバー 2003 (使用されていません)。</p>
<p>現在、ライブ通信サーバー2005で廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-InternetAccessEnabled</p></td>
<td><p>この属性は、1人のユーザーが外部ユーザーアクセスを有効にしているかどうかを制御します。 エンタープライズサービスレイヤーによって適用されます。 グローバルカタログのレプリケーション用にマークされています。</p>
<p>有効な値は、 <strong>TRUE</strong>または<strong>FALSE</strong>です。</p></td>
<td><p>Live Communications Server 2005 の新サービスです。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-IsMaster (廃止)</p></td>
<td><p>-</p></td>
<td><p>最新のライブコミュニケーションサーバー2003</p>
<p>現在、ライブ通信サーバー2005で廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true ライン</p></td>
<td><p>この単一値の属性には、Lync for telephony によって使用されるデバイス ID (SIP URI またはユーザーが制御する電話の TEL URI のいずれか) が含まれます。 この属性はグローバルカタログのレプリケーション用にマークされ、インデックスが作成されます。 ユーザーがエンタープライズ Voip を有効にしている場合、この属性には、ユーザーの電話番号の E.i 正規化されたバージョンが格納されます。</p></td>
<td><p>Microsoft Office Live Communications Server 2005 SP1 の新製品</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true</p></td>
<td><p>この単一値属性には、CSTA-SIP ゲートウェイサーバーの SIP URI が含まれています。 この属性はグローバルカタログのレプリケーション用にマークされていますが、インデックスは作成されません。</p></td>
<td><p>Microsoft Office Live Communications Server 2005 SP1 の新製品</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-LocalNormalizationData (廃止)</p></td>
<td><p>この属性は将来使用するために予約されています。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-Localnormallinks (廃止)</p></td>
<td><p>この複数値属性には、この場所プロファイルに関連付けられたローカル正規化識別名 (DN) の一覧が含まれています。 この属性の型は、DN バイナリです。 位置情報プロファイルとローカル正規化ルールの間には一対多のリレーションシップがあります。 ローカル正規化 DNs の一覧の順序は、管理者が指定した順序で維持する必要があります。 順序の保持は、DN バイナリのバイナリ部分によって管理されます。これにより、注文インデックスが指定されます。</p>
<p>転送リンク:<strong>リンク ID 11034</strong></p>
<p>この転送リンク属性への対応する "戻る" リンクは、 <strong>msrtcsip-userenabled true (プロファイル Ebl)</strong>です。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-LocalNormalizationOptions</p></td>
<td><p>この属性には、正規化ルールのオプションの一覧が含まれています。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-LocationName (廃止)</p></td>
<td><p>この単一値の属性には、このプロファイルが表す場所を示す場所プロファイルのフレンドリ名が含まれています。 複数の場所プロファイルが存在する可能性があるため、管理者はさまざまなプロファイルを区別するための方法が必要です。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-locationProfileBL (廃止)</p></td>
<td><p>この複数値属性には、場所プロファイルの識別名の一覧が含まれています。 この属性は、1つ以上の位置情報プロファイルへの戻るリンクを指定します。</p>
<p>戻るリンク:<strong>リンク ID 11035</strong></p>
<p>この属性は、forward link <strong>msrtcsip-userenabled true-Localnormalのリンク</strong>に対応します。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-LocationProfileData (廃止)</p></td>
<td><p>この属性は将来使用するために予約されています。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-LocationProfileOptions</p></td>
<td><p>この属性には、位置情報プロファイルのオプションが含まれています。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-MappingContact</p></td>
<td><p>この複数値属性は、アプリケーションの連絡先の一覧を保持します。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-MappingLocation</p></td>
<td><p>この複数値属性は、位置情報プロファイルの一覧を保持します。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-Maxnumoutスタンド Ingsearchperserver (廃止)</p></td>
<td><p>この属性は、サーバーあたりの未処理の検索要求の最大数を表します。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-MaxNumSubscriptionsPerUser (廃止)</p></td>
<td><p>この属性は、ユーザーごとのサブスクリプションの最大数を表します。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-MaxPresenceSubscriptionTimeout (廃止)</p></td>
<td><p>この属性は、サブスクリプションの最大タイムアウトウィンドウを表します。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-MaxRegistrationsTimeout (廃止)</p></td>
<td><p>この属性は、登録の最大タイムアウトウィンドウを表します。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-MaxRoamingDataSubscriptionTimeout (廃止)</p></td>
<td><p>この属性は、最大ローミングデータサブスクリプションのタイムアウトウィンドウを表します。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-MCUData</p></td>
<td><p>この属性は将来使用するために予約されています。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-MCUFactoryAddress</p></td>
<td><p>この属性は、属している multipoint control unit (MCU) ファクトリへのリンクを指定するコンピュータークラスの下のサービス制御ポイント属性です。 このサービス制御ポイントと属性は、Microsoft MCU ごとに作成されます。 各 Microsoft MCU は、プールレベルの設定を取得するために、所属するプールのバックエンドサーバーを見つける必要があります。</p>
<p>この属性の値は、MCU ファクトリの識別名 (DN) です。 これは単一値の属性であり、グローバルカタログのレプリケーション用にマークされています。</p>
<p>転送リンク:<strong>リンク ID 11026</strong></p>
<p>この転送リンク属性への対応する "戻る" リンクは、 <strong>Msrtcsip-userenabled true MCUServers</strong>です。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-MCUFactoryData</p></td>
<td><p>これは、複数の文字列で予約された属性です。 この属性に格納される設定は、name = value のペアとして表されます。 現在定義されている name = value のペア:</p>
<ul>
<li><p>FactoryURL = &lt;URL&gt;</p></li>
</ul></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-MCUFactoryPath</p></td>
<td><p>これは、プールに関連付けられた単一の MCU ファクトリの識別名 (DN) を含む単一値の属性です。</p>
<p>転送リンク:<strong>リンク ID 11024</strong></p>
<p>この転送リンク属性への対応する "戻る" リンクは<strong>msrtcsip-userenabled true の住所</strong>です。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-MCUFactoryProviderID</p></td>
<td><p>この属性は、MCU ファクトリプロバイダーの GUID を指定する単一値の文字列です。 MCU ファクトリプロセスは、GUID 値に基づいて、この MCU 型をサービスするかどうかを決定します。 GUID 値が<strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>の場合は、MCU ファクトリプロセス (既定では Lync Server で利用可能) によって処理されます。 他の GUID 値の場合、MCU ファクトリプロセスは MCU の種類を処理しません。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msrtcsip-userenabled true-mcuser</p></td>
<td><p>この属性は、複数値を持つ識別名 (DN) の一覧です。 この属性には、この MCU ファクトリに関連付けられている同じ種類とベンダーのすべての MCU サーバーの一覧が含まれます。 各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</p>
<p>戻るリンク: リンク ID 11027</p>
<p>この戻るリンクへの対応する前方リンクは<strong>Msrtcsip-userenabled true MCUFactoryAddress</strong>です。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-MCUType</p></td>
<td><p>この属性は、MCU が処理できる媒体を指定する単一値の文字列です。</p>
<p>サポートされている有効な形式は次のとおりです。</p>
<ul>
<li><p>会議</p></li>
<li><p>オーディオ-ビデオ</p></li>
<li><p>チャット</p></li>
<li><p>電話-conf</p></li>
</ul></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-MCUVendor</p></td>
<td><p>この属性は、MCU ベンダーの名前を指定する単一値の文字列です。 Microsoft のすべての Mcu は、この属性を<strong>Microsoft Corporation</strong>に指定します。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-会議フラグ (廃止)</p></td>
<td><p>この属性は、すべてのユーザーまたは連絡先オブジェクトでグローバルに有効になるさまざまな会議オプションを定義します。 この属性は、整数型のビットマスク値です。</p>
<p>有効な値 (および関連するビット位置) は、次のようになります。</p>
<ul>
<li><p>0: AllowOrganizeMeetingWithAnonymousParticipants が None (ユーザーが会議に匿名ユーザーを招待することを許可しない) (bits は設定されません)</p></li>
<li><p>4: AllowOrganizeMeetingWithAnonymousParticipants はすべてのユーザー (すべてのユーザーが会議に匿名ユーザーを招待することを許可します) (ビット位置 2)</p></li>
<li><p>8: AllowOrganizeMeetingWithAnonymousParticipants は UsePerUserSetting (ユーザーごとの設定に基づいてユーザーが会議に匿名ユーザーを招待できるようにします) (ビット位置 3)</p></li>
<li><p>16: Userperuser会議ポリシー (会議ポリシーはユーザーごとに定義されます) (ビット位置 4)</p></li>
</ul></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-会議ポリシー (廃止)</p></td>
<td><p>この属性は、管理者がこのユーザーに割り当てたポリシーの識別名 (DN) を単一値の属性として指定します。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-MinPresenceSubscriptionTimeout (廃止)</p></td>
<td><p>この属性は、最小プレゼンスサブスクリプションのタイムアウトウィンドウを表します。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-MinRegistrationTimeout (廃止)</p></td>
<td><p>この属性は、最小登録タイムアウトウィンドウを表します。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-MinRoamingDataSubscriptionTimeout (廃止)</p></td>
<td><p>この属性は、最小のローミングデータサブスクリプションのタイムアウトウィンドウを表します。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-MirrorBackEndServer</p></td>
<td><p>この属性は、フロントエンドプールによって使用されるミラー化された SQL Server バックエンドを格納するために使用されます。</p></td>
<td><p>Lync Server 2013 の新サービスです。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-MobilityFlags</p></td>
<td><p>この属性には、モビリティー設定を定義するオプションとフラグが含まれています。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-MobilityPolicy</p></td>
<td><p>この属性には、モビリティーポリシーオブジェクトの DN が含まれます。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-NumDevicesPerUser (廃止)</p></td>
<td><p>この属性は、ユーザーが SIP コミュニケーションに登録してプレゼンスをサブスクライブできるデバイスの許可された数を表します。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-OptionFlags</p></td>
<td><p>この属性は、ユーザーまたは連絡先オブジェクトに対して有効になるオプションを指定します。 この属性は、integer 型のビットマスク値です。 各オプションは1ビットで表されます。 この属性は、グローバルカタログのレプリケーション用にマークされます。</p>
<p>有効な値 (および関連するビット位置) は、次のようになります。</p>
<ul>
<li><p>1: パブリックインスタントメッセージング (IM) 接続を有効にします (ビット位置 0)。</p></li>
<li><p>2: 予約済み (ビット位置 1)</p></li>
<li><p>4: 予約済み (ビット位置 2)</p></li>
<li><p>8: 予約済み (ビット位置 3)</p></li>
<li><p>16: リモート通話コントロールが有効になっている [Telephony] (ビット位置 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (ユーザーが会議に匿名ユーザーを招待することを許可する (ビット位置 6)</p></li>
<li><p>128: UCEnabled (UC でのユーザーの有効化) (ビット位置 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (ユーザーにパブリック IM 接続を有効にする) (ビット位置 8)</p></li>
<li><p>512: RemoteCallControlDualMode (ビット位置 9)</p></li>
</ul></td>
<td><p>SP1 での最新のライブ通信サーバー2005。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-OriginatorSID</p></td>
<td><p>この属性は、リソースおよび中央フォレストトポロジで使用され、Windows NT Server プリンシパルアカウントからのユーザーの ObjectSID が、リソースまたは中央フォレストの対応するユーザーまたは連絡先オブジェクトのこの属性にコピーされた場合に、シングルサインオンを有効にします。 Communicator Web Access は、この属性またはユーザーの ObjectSID を使用して、AD DS 内のユーザーを検索します。 この属性は、グローバルカタログのレプリケーション用にマークされます。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-OwnerUrn</p></td>
<td><p>この属性は、アプリケーションの連絡先の所有者の Uniform Resource Name (URN) です。</p></td>
<td><p>Lync Server 2010 の新サービスです。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-Pattern (廃止)</p></td>
<td><p>この単一値文字列属性には、ダイヤル番号を E.i 形式に一致させるために使われるパターンが含まれています。 ダイヤル番号がこのパターンと一致する場合、翻訳はダイヤルされた番号に適用されます。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-PhoneRouteBL (廃止)</p></td>
<td><p>この複数値属性には、電話ルートの識別名 (DN) の一覧が含まれます。 この属性は、1つ以上の電話ルートへの戻るリンクを指定します。</p>
<p>戻るリンク:<strong>リンク ID 11033</strong></p>
<p>この属性は、 <strong>msrtcsip-userenabled true-RouteUsageLinks</strong>の前方リンクに対応しています。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-PhoneRouteData (廃止)</p></td>
<td><p>この属性は将来使用するために予約されています。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-PhoneRouteName (廃止)</p></td>
<td><p>この単一の値の UNICODE 文字列属性は、電話ルートのフレンドリ名を指定するため、管理者が簡単に参照できます。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-電話の使用データ (廃止)</p></td>
<td><p>この属性は将来使用するために予約されています。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-ポリシーのコンテンツ (廃止)</p></td>
<td><p>この属性は、単一の値を持つ Unicode 文字列です。 この文字列属性には、XML 形式のポリシー定義が含まれています。 XML スキーマ定義は、ポリシーの種類によって共通していますが、ポリシーの種類によって設定は異なります。</p>
<p>XML スキーマ定義 (XSD) は、次のように定義されます。</p>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;xs:schema id=&quot;instance&quot; xmlns=&quot;&quot; xmlns:xs=&quot;http://www.w3.org/2001/XMLSchema&quot; xmlns:msdata=&quot;urn:schemas-microsoft-com:xml-msdata&quot;&gt;
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
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-ポリシーデータ (廃止)</p></td>
<td><p>この属性は将来使用するために予約されています。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-PolicyType (廃止)</p></td>
<td><p>この単一値の Unicode 文字列属性には、ポリシー型が含まれています。 有効なポリシーの種類は次のとおりです。</p>
<ul>
<li><p>会議</p></li>
<li><p>電話</p></li>
</ul></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-PoolAddress</p></td>
<td><p>この属性は、コンピューターが属しているプールへのリンクを指定します。 この属性は、コンピューターで実行されているのが標準エディションであるか、エンタープライズ版の Lync Server であるかに関係なく設定されます。 この属性は、グローバルカタログのレプリケーション用にマークされます。</p>
<p>有効な値は、プールのドメイン名です。</p>
<p>転送リンク:<strong>リンク ID 11022</strong></p>
<p>この転送リンク属性への対応する "戻る" リンクは、 <strong>msrtcsip-userenabled true-FrontEndServers</strong>です。</p></td>
<td><p>Live Communications Server 2005 の新サービスです。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-PoolAddresses</p></td>
<td><p>これは、MCU ファクトリが関連付けられているプールの識別名 (DN) の一覧を含む複数値の属性です。</p>
<p>戻るリンク:<strong>リンク ID 11025</strong></p>
<p>この戻るリンクへの対応する前方リンクは<strong>Msrtcsip-userenabled true MCUFactoryPath</strong>です。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-PoolData</p></td>
<td><p>この属性は将来使用するために予約されています。</p></td>
<td><p>SP1 での最新のライブ通信サーバー2005。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-PoolDisplayName</p></td>
<td><p>この属性は、管理コンソールによって表示されるプールの任意の名前を指定します。 この名前は管理者が変更できます。</p>
<p>有効な値は、プールの名前を表す文字列です。</p></td>
<td><p>Live Communications Server 2005 の新サービスです。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-Pooldomaqdn</p></td>
<td><p>この属性は単一値文字列値です。 この属性の値が指定されている場合、管理者がフロントエンドプールを作成する Active Directory ドメイン構造に準拠していない FQDN (たとえば、SIP) を使っている場合、プールのドメイン FQDN が示されます。ドメインネームシステム (DNS) 名前空間からの名前空間の分離。</p>
<p>プールが存在する Active Directory ドメインとして、フロントエンドプールドメイン FQDN をドメイン名部分にマッピングすることをお勧めします。 そのため、この属性に値が含まれていない場合、フロントエンドプールの FQDN は、 <strong>dnsHostName</strong>属性で示される Active Directory ドメイン名の構造体に既定値として設定されます。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-PoolFunctionality</p></td>
<td><p>プールに関連付けられたすべての Lync Server Enterprise Edition サーバーのドメイン名の複数値を持つリスト。 Integer 型の属性は、プールがインスタントメッセージング (IM) とプレゼンス、会議に対応しているかどうかを定義します。</p>
<p>有効な値の型は、次のようになります。</p>
<ul>
<li><p>未定義: IM とプレゼンスサービス (Live Communications Server 2005 および 2003)</p></li>
<li><p>1: IM とプレゼンスサービス (Lync Server)</p></li>
<li><p>2: IM、プレゼンス、会議サービス (Lync Server)</p></li>
</ul></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-PoolType</p></td>
<td><p>この属性は、サーバープールで Standard Edition server または Enterprise Edition server が実行されているかどうかを指定します。 この属性は、integer 型のビットマスク値です。 各オプションは1ビットで表されます。</p>
<p>有効な値 (および関連するビット位置) は、次のようになります。</p>
<ul>
<li><p>1: Standard Edition server、ホストユーザー (ビット位置 0)</p></li>
<li><p>2: Enterprise Edition server、hosts ユーザー (ビット位置 1)</p></li>
<li><p>4: 標準エディションサーバー、ホストアプリケーション (ビット位置 2)</p></li>
<li><p>8: Enterprise Edition server、ホストアプリケーション (ビット位置 3)</p></li>
</ul>
<p>Lync Server はアプリケーションのみをホストするプールをサポートしていないため、有効な値は次のとおりです。</p>
<ul>
<li><p>5: 標準エディションサーバー、ホストユーザーとアプリケーション (ビット位置0、2)</p></li>
<li><p>10: Enterprise Edition server、ホストユーザーとアプリケーション (ビット位置1と 3)</p></li>
</ul></td>
<td><p>Live Communications Server 2005 の新サービスです。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-PoolVersion</p></td>
<td><p>この属性はプールのバージョンを定義します。 これは、主要製品のリリースごとにインクリメントされる整数型です。</p>
<p>有効な値の型は、次のようになります。</p>
<ul>
<li><p>0: Live Communications Server 2003</p></li>
<li><p>1: Live Communications Server 2005</p></li>
<li><p>2: SP1 での Live Communications Server 2005</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
</ul></td>
<td><p>Live Communications Server 2005 SP1</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-PresenceFlags</p></td>
<td><p>この属性には、プレゼンス設定を定義するオプションとフラグが含まれます。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-PresencePolicy</p></td>
<td><p>この属性には、プレゼンスポリシーオブジェクトの DN が含まれます。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-PrimaryHomeServer</p></td>
<td><p>この属性によって、SIP メッセージングのユーザーまたは連絡先が有効になります。 この機能は、中央フォレストのトポロジでは、ユーザーオブジェクトではなく SIP 対応の連絡先オブジェクトであるため、連絡先クラスに追加されます。</p>
<p>有効な値は、ユーザーが所属する Standard Edition server または Enterprise Edition のフロントエンドプールの DN です。</p></td>
<td><p>Live Communications Server 2005 の新サービスです。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>この属性には、特定のユーザーの SIP アドレスが含まれます。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-PrivateLine</p></td>
<td><p>この属性には、プライベート回線デバイスのデバイス ID が含まれます。</p></td>
<td><p>Lync Server 2010 の新サービスです。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-ルーティング可能</p></td>
<td><p>この属性は、Lync Server がその GRUU アドレスを使ってこのサービスにルーティングすることを許可するかどうかを決定するために使用されるブール型の属性です。 この値が<strong>TRUE</strong>に設定されている場合、Lync Server はこのサービスにルーティングすることを許可されています。 この値が<strong>FALSE</strong>に設定されている場合、Lync Server はこのサービスにルーティングする権限がありません。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-RouteUsageAttribute (廃止)</p></td>
<td><p>この単一値の UNICODE 文字列属性は、電話ルートの使用を限定する属性を定義します。 電話ルートの選択は、電話ルートに割り当てられる利用属性と、発信者に許可されているポリシー使用属性の2つの要素に基づいて決定されます。 呼び出し元の使用が許可されている使用法属性を持つ最初の電話ルートが選択されています。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-RouteUsageLinks (廃止)</p></td>
<td><p>この複数値識別名 (DN) 属性には、ルートの使用の識別名の一覧が含まれています。</p>
<p>転送リンク:<strong>リンク ID 11032</strong></p>
<p>この属性は、対応する back link <strong>msrtcsip-userenabled true-PhoneRouteBL</strong>への転送リンクです。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-RoutingPoolDN</p></td>
<td><p>この属性には、この MCU または信頼されたサービスに宛てたすべての SIP トラフィックが通過する必要があるプールを指す DN が含まれています。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-RuleName (廃止)</p></td>
<td><p>この単一値の UNICODE 文字列属性は、正規化ルールのフレンドリ名を指定するため、管理者が簡単に参照できます。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-SchemaVersion</p></td>
<td><p>この属性は、組織に現在展開されているスキーマバージョンを表します。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-SearchMaxRequests (廃止)</p></td>
<td><p>この属性は、ユーザーが Communicator を使って連絡先を検索するときに、ディレクトリ検索から返される検索結果の数を制限します。 この属性は、クライアントによって指定された値を上書きします。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-SearchMaxResults (廃止)</p></td>
<td><p>この属性は、返される検索要求の数を制限します。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-ServerBL</p></td>
<td><p>この複数値属性は、識別名 (DN) の一覧を含む戻るリンクです。 これらの DNs はプールまたは<strong>Trustedservice</strong>オブジェクトを参照します。</p>
<p>この属性は、 <strong>msrtcsip-userenabled true-TrustedServiceLinks</strong>の前方リンクに対応しています。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-ServerData</p></td>
<td><p>この属性は将来使用するために予約されています。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-ServerReferenceBL (廃止)</p></td>
<td><p>この複数値属性には、識別名のリストが含まれています。 これらの識別名は、既定の場所プロファイルを割り当てることができる他のサーバーオブジェクトを参照する戻るリンクです。</p>
<p>戻るリンク:<strong>リンク ID 11037</strong></p>
<p>この戻るリンクへの対応する前方リンクは<strong>msrtcsip-userenabled true-DefaultLocationProfileLink</strong>です。</p>
<p>この back link 属性は、プールおよび仲介サーバーのみを参照します。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-ServerVersion</p></td>
<td><p>この属性は、サーバーのバージョン情報を定義します。 このバージョン番号は、すべてのサーバーの役割に適用されます。 これは、各公式の製品リリースによって増加する monotonously 整数です。</p>
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
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-SourceObjectType</p></td>
<td><p>Integer 型の単一値属性は、次のように、 <strong>SourceObjectDN</strong>が指すオブジェクトの型を指定します。</p>
<ul>
<li><p>null |0x00000001: 別のフォレストから Windows NT Server プリンシパルユーザーオブジェクトを表します。</p></li>
<li><p>次の属性は、配布グループの展開用に別のフォレストからのグループの種類を表します。</p>
<ul>
<li><p>0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</p></li>
<li><p>0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</p></li>
<li><p>0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</p></li>
<li><p>0x90000000: 同じフォレストまたは別のフォレストからの自動応答またはサブスクライバーのアクセスオブジェクトを表します。</p></li>
</ul></li>
</ul></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-SubscriptionAuthRequired (廃止)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003 の新サービスです。</p>
<p>現在、ライブ通信サーバー2005で廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-Targethoのメッセージ</p></td>
<td><p>この属性によって、ユーザーまたは連絡先オブジェクトを、Lync Server プール間で移動することができます。 この属性は、中央フォレストのトポロジでは、ユーザーオブジェクトではなく、SIP が有効になるため、contact クラスに追加されます。</p>
<p>有効な値は、ユーザーが移動するターゲットの Standard Edition サーバーまたはフロントエンドプールの DN です。</p></td>
<td><p>Live Communications Server 2005 の新サービスです。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-TargetPhoneNumber (廃止)</p></td>
<td><p>この単一値文字列属性には、 <strong>msrtcsip-userenabled true</strong>で定義されたゲートウェイにルーティングするための電話番号のパターンまたは範囲が含まれます。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-TargetUserPolicies</p></td>
<td><p>この属性は、Lync Server ユーザーのターゲットポリシーの名前と値のペアを格納します。</p></td>
<td><p>Lync Server 2010 の新サービスです。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-TenantId</p></td>
<td><p>この属性には、テナントの一意の識別子が格納されます。</p></td>
<td><p>Lync Server 2010 の新サービスです。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-翻訳 (廃止)</p></td>
<td><p>この属性は、Lync Server の音声機能によって使用され、一致が見つかった場合は、ダイヤルした番号に適用する翻訳文字列が含まれます。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-TrustedMCUData</p></td>
<td><p>この属性は将来使用するために予約されています。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-TrustedMCUFQDN</p></td>
<td><p>この属性は、MCU の FQDN を含む文字列値です。 これは単一値の属性です。 各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-TrustedProxyData</p></td>
<td><p>この属性は将来使用するために予約されています。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-TrustedProxyFQDN</p></td>
<td><p>この属性は、プロキシサーバーを実行しているサーバーの FQDN を含む文字列値です。 この属性は単一値になります。 各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-TrustedServerData</p></td>
<td><p>この属性は将来使用するために予約されています。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-TrustedServerFQDN</p></td>
<td><p>この属性は、信頼されたサーバーの FQDN を表す単一値属性です。</p></td>
<td><p>Live Communications Server 2005 の新サービスです。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-TrustedServerVersion</p></td>
<td><p>この属性は、信頼されたサーバーの一覧にあるサーバーのバージョン番号を指定します。</p>
<p>有効な値は次のとおりです。</p>
<ul>
<li><p>NULL: Live Communications Server 2003</p></li>
<li><p>2: Live Communications Server 2005</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
</ul></td>
<td><p>Live Communications Server 2005 の新サービスです。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-TrustedServiceFlags</p></td>
<td><p>この属性は、信頼されたサービスに対して有効になるオプションを定義します。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-TrustedServiceLinks</p></td>
<td><p>この複数値属性には、メディアリレー認証サービスなどの信頼されたサービスオブジェクトを参照する識別名 (DN) の一覧が含まれています。 リモートユーザー向けのオーディオシナリオをサポートするには、メディアリレー認証サービス (A/V 会議サービスを実行しているエッジサーバーに物理的に併置されているサービス) がプールに関連付けられている必要があります。</p>
<p>この転送リンク属性への対応する [戻る] リンクは、 <strong>msrtcsip-userenabled true-ServerBL</strong>です。</p></td>
<td><p>コミュニケーション</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-TrustedServicePort</p></td>
<td><p>この属性は、この GRUU サービスへの接続に使用するポート番号を定義する整数です。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-TrustedServiceType</p></td>
<td><p>この属性は、GRUU サービスの型を定義する文字列値です。</p>
<p>有効な GRUU サービスの種類は次のとおりです。</p>
<ul>
<li><p>MediationServer</p></li>
<li><p>ゲートウェイ</p></li>
<li><p>メディアリレー認証サービス (MRAS)</p></li>
<li><p>QoSM</p></li>
<li><p>Msrtcsip-userenabled true-UserExtension CWA</p></li>
</ul></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-TrustedWebComponentsServerData</p></td>
<td><p>この属性は将来使用するために予約されています。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-TrustedWebComponentsServerFQDN</p></td>
<td><p>この属性は、Lync Server Web サービスが実行されている IIS の FQDN を含む文字列値です。 これは単一値の属性です。 各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-UCFlags (廃止)</p></td>
<td><p>この属性は、すべてのユーザーオブジェクトまたは連絡先オブジェクトでグローバルに有効になるさまざまな UC オプションを定義します。 この属性は、整数型のビットマスク値です。 各オプションはビットが存在することで表されます。</p>
<p>有効な値 (および関連するビット位置) は、次のようになります。</p>
<ul>
<li><p>4: Peruserucpolicy (ビット位置 2)</p></li>
</ul>
<p>このビットが設定されると、ユーザーごとに UC ポリシーが定義されます。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-UCPolicy (廃止)</p></td>
<td><p>この単一値属性には、管理者がこのユーザーに割り当てた UC ポリシーの識別名 (DN) が含まれます。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-UserDomainList (廃止)</p></td>
<td><p>この属性は、SIP 対応ユーザーをホストしているフォレスト内のすべてのドメインの一覧を提供します。 既定値は空の一覧で、フォレスト内のすべてのドメインが SIP 対応であることを示します。</p>
<p>有効な値は、個々のドメインのドメイン名を表す複数の文字列です。</p></td>
<td><p>Live Communications Server 2005 の新サービスです。</p>
<p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-UserEnabled</p></td>
<td><p>この属性は、ユーザーが Lync Server で現在有効になっているかどうかを決定します。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-UserExtension</p></td>
<td><p>この複数値を持つ属性には、name = value の&quot;形式の名前と値のペアの一覧が含まれています。&quot;この属性は、グローバルカタログのレプリケーション用にマークされます。</p></td>
<td><p>SP1 での最新のライブ通信サーバー2005。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-UserLocationProfile</p></td>
<td><p>この属性には、場所プロファイルオブジェクトを参照する識別名 (DN) が含まれます。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-UserPolicies</p></td>
<td><p>この属性は、ユーザーポリシーの名前と値のペアを格納します。</p></td>
<td><p>Lync Server 2010 の新サービスです。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-UserPolicy</p></td>
<td><p>これは、さまざまな種類のグローバルユーザーポリシーを指定するバイナリ (DN_WITH_BINARY) の識別名のリストを含む複数値の属性です。 バイナリ部分は、DN の部分が指しているポリシーの種類を示します。</p>
<p>有効なバイナリ値は、次のとおりです。</p>
<ul>
<li><p>0x00000001: 会議のポリシー</p></li>
<li><p>0x00000002: UC ポリシー</p></li>
<li><p>0x00000005: プレゼンスポリシー</p></li>
</ul></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-UserRoutingGroupId</p></td>
<td><p>これは、SIP ルーティンググループの ID です。 同じグループ内のユーザーは、同じフロントエンドサーバーに登録されます。</p></td>
<td><p>Lync Server 2013 の新サービスです。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-Webcontacts データ</p></td>
<td><p>これは複数値の属性です。 この属性は将来使用するために予約されています。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-WebComponentsPoolAddress</p></td>
<td><p>この単一値の属性は、web コンポーネントが属しているプールまたは Standard Edition サーバーを指します。</p>
<p>転送リンク:<strong>リンク ID 11028</strong></p>
<p>この転送リンク属性への対応する "戻る" リンクは、 <strong>Msrtcsip-userenabled true Webservers サーバー</strong>です。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-Webservers サーバー</p></td>
<td><p>この属性は、複数値を持つ識別名の一覧です。 この属性には、このプールに関連付けられているすべての Web サーバーの一覧が含まれます。</p>
<p>戻るリンク:<strong>リンク ID 11029</strong></p>
<p>この戻るリンクへの対応する前方リンクは<strong>Msrtcsip-userenabled true WebComponentsPoolAddress</strong>です。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true の形式の Instanceid (廃止)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003 の新サービスです。</p>
<p>現在、ライブ通信サーバー2005で廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>他の Ip電話</p></td>
<td><p>この既存の Active Directory 属性は、電話の代替 TCP/IP アドレスの一覧を指定するためにテレフォニーで使用されます。</p></td>
<td><p>Windows Server 2008 オペレーティングシステムの新機能。</p></td>
</tr>
<tr class="even">
<td><p>他の電話帳</p></td>
<td><p>この既存の Active Directory 属性は、ユニファイドメッセージングの自動応答とサブスクライバーアクセス番号の呼び出しをルーティングすることを目的として、Lync Server のボイスコンポーネントに対してのみ使用されます。 無条件着信転送アドレスがこの複数値属性に保存されています。 このアカウントは、自動応答とサブスクライバーアクセスの特定の目的で作成されます。 このアカウントの属性は、管理者が変更することはできません。</p></td>
<td><p>Windows 2000 オペレーティングシステムの新機能。</p></td>
</tr>
<tr class="odd">
<td><p>ProxyAddresses</p></td>
<td><p>この既存の Active Directory マルチバリュー属性は、Windows 2000 で導入されたベース Active Directory スキーマの一部です。 この属性には、ユーザーのメールのさまざまな X400、X500、および SMTP アドレスが含まれています。 Live Communications Server 2003 以降では、 &quot;sip:&quot;タグを使用して、ユーザーの sip URI がこのリストに追加されます。</p>
<p>次のアプリケーションは、この属性によってユーザーの SIP URI を検索します。</p>
<ul>
<li><p>Microsoft Office Outlook 2003 メッセージングおよびコラボレーションクライアント</p></li>
<li><p>Microsoft Office SharePoint Server 2007</p></li>
</ul></td>
<td><p>Windows 2000 オペレーティングシステムの新機能。</p></td>
</tr>
<tr class="even">
<td><p>TelephoneNumber</p></td>
<td><p>この既存の Active Directory の属性には、ユーザーの電話番号が含まれています。</p></td>
<td><p>Windows 2000 オペレーティングシステムの新機能。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

