---
title: 'Lync Server 2013: スキーマの属性と説明'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1c8259312e3ba4e939bd784e189f5aae495605d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a>Lync Server 2013 のスキーマの属性と説明

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-06_

このセクションでは、Lync Server 2013 で使用されるすべてのスキーマ属性について説明します。 属性に関連付けられたクラスについては、「 [Lync Server 2013 のクラス別のスキーマ属性](lync-server-2013-schema-attributes-by-class.md)」を参照してください。 Lync Server 2013 で新しく追加されたクラスと属性の一覧については、「 [Lync server 2013 のスキーマの変更点](lync-server-2013-schema-changes-in-lync-server-2013.md)」を参照してください。

リンクされたペアの属性は、前方リンクまたは後方リンクとして指定されます。 別のオブジェクトを参照する属性は、前方リンクです。最初のオブジェクトを参照する other オブジェクトの属性は、後方リンクです。 前方リンクは更新可能で、後方リンクは読み取り専用です。

一部の属性にはビットマスク値があります。 これらの属性の場合、各設定はビットで表され、表示される10進値はビット位置を表します。 ビット位置はビット0で始まります。 たとえば、1 (バイナリ) はビット0セットで、1万 (バイナリ) はビット4セットです。 各ビットはプロパティを表します。 以下はその例です。

  - 1万 (バイナリ) の10進値は16です (つまり、ビット4が設定されます)。

  - 1億 (バイナリ) の10進値は256です (つまり、ビット8が設定されます)。

  - 1100 (バイナリ) の10進値は12です (つまり、ビット2と3が設定され、両方のビットで表されるプロパティが有効になります)。

  - 1111000001 (バイナリ) の10進値は961です (つまり、ビット0、6、7、8、9が設定され、これらの各ビットのプロパティが有効になります)。

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a>Lync Server 2013 のスキーマの属性

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
<td><p><strong>MsRTCSIP</strong>と msRTCSIP の両方の<strong>サーバー</strong>クラスに関連付けられた、Active Directory ドメインサービスの既存の属性。 この属性は、プールまたは監視サーバーの完全修飾ドメイン名 (FQDN) を指定します。</p>
<p>各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</p></td>
<td><p>Microsoft Office Live Communications Server 2005 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msds-sourceobjectdn</p></td>
<td><p>この属性には、このオブジェクトに対応する別のフォレスト内のオブジェクトの識別名 (DN) の文字列表現が含まれています。 この属性は、配布グループの展開および自動出席に使用されます。 この属性は、Windows Server 2003 R2 用の既定の Active Directory スキーマで定義されています。</p>
<p>AD DS を Windows Server 2003 R2 にアップグレードしなくて済むように、Active Directory スキーマの準備により、Windows Server 2003 スキーマがこの属性定義で拡張されます。</p></td>
<td><p>Microsoft Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msExchUCVoiceMailSettings</p></td>
<td><p>この複数値属性は、ボイスメール設定を保持します。 この属性は、Exchange ユニファイドメッセージング (UM) と共有されます。</p></td>
<td><p>Microsoft Lync Server 2010 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>この複数値の属性には、ユーザーに適用される保持ポリシーの識別子が保持されます。 この保持の間は、ユーザーのメールボックス アイテムが保持ポリシーに保存されます。 この属性は、Exchange 2013 と共有されます。</p></td>
<td><p>Lync Server 2013 の新。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-AcpInfo</p></td>
<td><p>この属性は、ユーザーの電話会議プロバイダーの情報を格納します。</p></td>
<td><p>Lync Server 2010 の新。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationDestination</p></td>
<td><p>この属性は、アプリケーションの連絡先の信頼済みサービスエントリを指します。</p></td>
<td><p>Microsoft Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationList</p></td>
<td><p>この属性には、アプリケーションサーバー上のホストされているアプリケーションの一覧が含まれています。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationOptions</p></td>
<td><p>この属性は、アプリケーションの連絡先のオプションを指定します。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationPrimaryLanguage</p></td>
<td><p>この属性には、アプリケーションの連絡先の第1言語が含まれています。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationSecondaryLanguages</p></td>
<td><p>この複数値の属性には、アプリケーションの連絡先の第2言語が含まれています。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerBL</p></td>
<td><p>この属性には、このプールに属するアプリケーションサーバーの一覧が含まれています。 この後方リンク属性への対応する転送リンクは、 <strong>MsRTCSIP Serverpoollink</strong>です。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerPoolLink</p></td>
<td><p>この属性は、このアプリケーションサーバーが属するプールを指します。 これは、前方リンクです。 対応する後方リンクは、 <strong>MsRTCSIP Serverbl</strong>です。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-アーカイブ既定 (現在不使用)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2005 の新しいもの。</p>
<p>Office Communications Server 2007 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-アーカイブ Defaultflags (現在不使用)</p></td>
<td><p>この属性は、すべてのユーザー通信をアーカイブするためのフォレスト境界内でのグローバルな既定値を指定します。 これは、アーカイブエージェントレイヤーによって適用されます。 この属性の値の範囲は次のとおりです。</p>
<ul>
<li><p><strong>TRUE</strong>: すべてのユーザーをアーカイブする</p></li>
<li><p><strong>FALSE</strong>: すべてのユーザーをアーカイブしない</p></li>
</ul>
<p>この属性は、内部ネットワーク内でのユーザー通信のアーカイブ方法をフォレスト境界内でグローバルに制御します。</p>
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
<li><p>1-2: アーカイブ Internalcommunications</p></li>
<li><p>3-4: ArchiveFederatedCommunications</p></li>
<li><p>5: RecordPresenceRegistrations</p></li>
<li><p>6: RecordIMCallDetails</p></li>
<li><p>7: RecordGroupIMCallDetails</p></li>
<li><p>8: RecordFileTransferInstances</p></li>
<li><p>9: RecordAudioCallDetails</p></li>
<li><p>10: RecordVideoCallDetails</p></li>
<li><p>11: RecordRemoteAssistanceCallDetails</p></li>
<li><p>12: RecordApplicationSharingDetails</p></li>
<li><p>13: レコードの会議のインスタンス化</p></li>
<li><p>14: レコード会議の結合</p></li>
<li><p>15: RecordDataJoins</p></li>
<li><p>16: RecordAVJoins</p></li>
</ul></td>
<td><p>Live Communications Server 2005 の新しいもの。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Msrtcsip-archivefederationdefault (現在不使用)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2005 の新しいもの。</p>
<p>Office Communications Server 2007 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Msrtcsip-archivefederationdefaultflags (現在不使用)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2005 の新しいもの。</p>
<p>Office Communications Server 2007 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingEnabled</p></td>
<td><p>この属性は、1人のユーザーの通信をアーカイブするかどうかを制御するためのビットフィールドとして使用される整数です。 このコントロールは、アーカイブエージェントレイヤーによって適用されます。 グローバルカタログレプリケーションのマークが付いています。</p>
<p>この属性のスコープは、1人のユーザーまたは連絡先に固有です。 Lync Server での有効な値 (および関連するビット位置) は次のとおりです。</p>
<ul>
<li><p>0: アーカイブしない (ビットセットなし)</p></li>
<li><p>1: 廃止 (ビット位置 0)</p></li>
<li><p>2: 廃止 (ビット位置 1)</p></li>
<li><p>4: 内部通信のアーカイブ (ビット位置 2)</p></li>
<li><p>8: フェデレーション通信のアーカイブ (ビット位置 3)</p></li>
</ul>
<p>Live Communications Server 2005 の以前の有効な値は次のとおりです。</p>
<ul>
<li><p>0: <strong>msRTCSIP</strong>によって定義されている既定値<strong>を使用</strong>します。既定値は、この優先順位に従っています。</p>
<ul>
<li><p>1: アーカイブ</p></li>
<li><p>2: アーカイブしない</p></li>
<li><p>3: メッセージ本文を含まないアーカイブ</p></li>
</ul></li>
</ul></td>
<td><p>Live Communications Server 2005 の新しいもの。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Msrtcsip-archivingserverdata (現在不使用)</p></td>
<td><p>この属性は、今後の使用のために予約されています。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Msrtcsip-archivingserverversion (現在不使用)</p></td>
<td><p>この属性は、アーカイブサービスのバージョンを定義します。 この属性は、公式の製品リリースごとにインクリメントする monotonously 増加整数型です。 有効な値は次のとおりです。</p>
<ul>
<li><p>Undefined: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 with SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
</ul></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-BackEndServer</p></td>
<td><p>この属性は、プールのバックエンドサーバーの FQDN を指定します。 プールごとに1つのバックエンドサーバーしか存在できないため、これは単一値の属性です。</p>
<p>各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は255文字です。</p></td>
<td><p>Live Communications Server 2005 の新しいもの。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryHomePool</p></td>
<td><p>この属性には、会議ディレクトリをホストするプールの識別子が含まれます。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectoryId</p></td>
<td><p>この属性には、会議ディレクトリの識別子が含まれています。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryTargetPool</p></td>
<td><p>この属性には、会議ディレクトリの移動先のプールの識別子が含まれます。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-既定値</p></td>
<td><p>このブール値属性は、電話の使用法が既定の使用方法であるかどうかを定義します。 この属性が<strong>TRUE</strong>に設定されている場合、電話使用法は既定の使用方法であり、管理者が削除することはできません。 この属性が<strong>FALSE</strong>に設定されている場合は、使用法を削除できます。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWAExternalURL</p></td>
<td><p>この属性は、組織外のユーザーの Communicator Web Access URL を識別します。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultCWAInternalURL</p></td>
<td><p>この属性は、組織内のユーザーの Communicator Web Access URL を識別します。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultLocationProfileLink (現在不使用)</p></td>
<td><p>この単一値属性には、割り当てられている場所プロファイルクラスオブジェクトの識別名 (DN) が含まれています。</p>
<p>前方リンク:<strong>リンク ID 11036</strong></p>
<p>対応する後方リンクは、 <strong>msRTCSIP-ServerReferenceBL</strong>です。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultPolicy (現在不使用)</p></td>
<td><p>このブール属性は、ポリシーが既定のポリシーであるかどうかを指定します。 ポリシーは、 <strong>TRUE</strong>に設定されている場合の既定のポリシーです。</p></td>
<td><p>Office Communications Server 2007 の新製品</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Msrtcsip-defaultroutetoedgeproxy (現在不使用)</p></td>
<td><p>この属性は、アクセスエッジサービスを実行しているエッジサーバーの FQDN、アクセス可能な場合は、アクセスエッジサービスを実行しているサーバーのプールのハードウェアロードバランサーの FQDN を指定します。 アクセスエッジサービスを実行しているサーバーが1つまたは複数のディレクターを介してのみアクセスできる場合は、この属性によって、ディレクターの FQDN、およびオプションとして、ディレクタープールを提供するディレクターまたはハードウェアロードバランサーのポート番号が指定されます。</p>
<p>各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は255文字です。</p></td>
<td><p>Live Communications Server 2005 の新しいもの。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Msrtcsip-defaultroutetoedgeproxyport (現在不使用)</p></td>
<td><p>この属性は、アクセスエッジサービスを実行しているサーバーに接続するために使用されるポート番号を表します。</p>
<p>有効な値は、使用するポートを指定する整数型 (integer) の値です。 既定値は 5061 です。</p></td>
<td><p>Live Communications Server 2005 の新しいもの。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Msrtcsip-defpresencesubscriptiontimeout (現在不使用)</p></td>
<td><p>既定のプレゼンスサブスクリプションタイムアウト期間を表す属性です。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefRegistrationTimeout (obsolete)</p></td>
<td><p>既定の登録タイムアウト期間を表す属性です。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Msrtcsip-defroamingdatasubscriptiontimeout (現在不使用)</p></td>
<td><p>既定の移動データサブスクリプションタイムアウト期間を表す属性です。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DeploymentLocator</p></td>
<td><p>この属性は、分割ドメイントポロジで使用され、完全修飾ドメイン名 (FQDN) を含みます。</p></td>
<td><p>Lync Server 2010 の新。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Description (現在不使用)</p></td>
<td><p>この電話ルートまたは正規化ルールのわかりやすい説明を含む単一値の UNICODE 文字列属性です。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DomainData</p></td>
<td><p>この属性は、今後の使用のために予約されています。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DomainName</p></td>
<td><p>レジストラーに対して構成されたドメインを表す属性です。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EdgeProxyData</p></td>
<td><p>この属性は、今後の使用のために予約されています。</p></td>
<td><p>Live Communications Server 2005 の新しいもの。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxyFQDN</p></td>
<td><p>この属性は、アクセスエッジサービスを実行しているサーバーの FQDN を指定します。</p>
<p>各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は255文字です。</p></td>
<td><p>Live Communications Server 2005 の新しいもの。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Msrtcsip-enablebesteffortnotify (現在不使用)</p></td>
<td><p>この属性は、クライアントからのサブスクライブ要求に対する応答として、サーバーが NOTIFY 要求ではなく、Best エフォート NOTIFY (BENOTIFY) 要求を生成するかどうかを制御します。 BENOTIFY は、定期的な NOTIFY 要求ではなく、サーバーが BENOTIFY 要求を生成するサブスクライブ通知ハンドシェイクに対して、パフォーマンスが強化された拡張機能です。 パフォーマンス上の利点として、NOTIFY 要求と同様に、BENOTIFY 要求でクライアントから 200 OK 応答が要求されないことが挙げられます。</p>
<p>有効な値は、 <strong>TRUE</strong>または<strong>FALSE</strong>です。</p>
<div>

> [!NOTE]  
> Live Communications Server 2003 は、BENOTIFY 要求をサポートしていません。 Live Communications Server 2005 およびサードパーティ製サーバーで実行されている Live Communications Server 2003 サーバー API を使用して記述されたサーバーアプリケーションと相互運用するには、BENOTIFY 要求の値を<STRONG>FALSE</STRONG>に設定することで無効にすることができます。 現時点では、BENOTIFY は、IETF (インターネットエンジニアリングのタスクフォース) SIP 標準化プロセスの一部ではありません。


</div></td>
<td><p>Live Communications Server 2005 の新しいもの。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnableFederation (現在不使用)</p></td>
<td><p>この属性は、ユーザーが他の組織のユーザーとの通信を許可されているかどうかを構成するために IT 管理者が使用するグローバルスイッチです。 これにより、管理者は個々のユーザーの<strong>FederationEnabled</strong>属性を上書きすることができます。 この属性は、ワーム、ウイルス、または社内への攻撃によって発生する可能性があるインターネット攻撃から内部ネットワークを保護するのに役立ちます。</p>
<p>有効な値 (および関連するビット位置) は次のとおりです。</p>
<ul>
<li><p>1: パブリック IM 接続が有効 (ビット位置 0)</p></li>
<li><p>2: 予約済み (ビット位置 1)</p></li>
<li><p>4: 予約済み (ビット位置 2)</p></li>
<li><p>8: 予約済み (ビット位置 3)</p></li>
<li><p>16: リモート通話コントロールが有効 [テレフォニー] (ビット位置 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (ユーザーが匿名ユーザーを会議に招待できるようにする (ビット位置 6)</p></li>
<li><p>128: UCEnabled (ユーザーに対して統合コミュニケーションを有効にする) (ビット位置 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (ユーザーに対してパブリック IM 接続を有効にする) (ビット位置 8)</p></li>
<li><p>512: RemoteCallControlDualMode (ビット位置 9)</p></li>
</ul></td>
<td><p>Live Communications Server 2005 の新しいもの。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServices</p></td>
<td><p>この属性は、指定されたサーバーにエンタープライズサービスが読み込まれているかどうかを示します。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ExtensionData</p></td>
<td><p>この属性は、今後の使用のために予約されています。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ExternalAccessCode</p></td>
<td><p>外部アクセスのダイヤルコードを含む属性です。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-FederationEnabled</p></td>
<td><p>この属性は、1人のユーザーがフェデレーションを有効にするかどうかを制御します。 エンタープライズサービス層によって適用されます。 グローバルカタログレプリケーションのマークが付いています。</p>
<p>有効な値は、 <strong>TRUE</strong>または<strong>FALSE</strong>です。</p></td>
<td><p>Live Communications Server 2005 の新しいもの。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-FrontEndServers</p></td>
<td><p>この属性は、プールに関連付けられているすべての Enterprise Edition サーバーのドメイン名の複数値を持つリストです。</p>
<p>後方リンク:<strong>リンク ID 11023</strong></p>
<p>この後方リンクへの対応する転送リンクは、 <strong>msRTCSIP-PoolAddress</strong>です。</p></td>
<td><p>Live Communications Server 2005 の新しいもの。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ゲートウェイ (obsolete)</p></td>
<td><p>ゲートウェイとポート (ゲートウェイごと) の一覧を含む複数値の文字列属性です。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalSettingsData (現在不使用)</p></td>
<td><p>この属性には、名前と値のペアが格納されます。 既に定義されている名前: 値のペアは、<strong>プレゼンス設定のポーリングを許可</strong>するためのものです。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GroupingID</p></td>
<td><p>この属性は、アドレス帳のエントリをグループ化するために使用されるグループの一意の識別子です。</p></td>
<td><p>Lync Server 2010 の新。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Msrtcsip-homeserver (現在不使用)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003 (使用されていません) の新。</p>
<p>現在、Live Communications Server 2005 では使用されていません。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Msrtcsip-homeserverstring (現在不使用)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003 の新しいもの。</p>
<p>現在、Live Communications Server 2005 では使用されていません。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ホームユーザー (現在不使用)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003 (使用されていません) の新。</p>
<p>現在、Live Communications Server 2005 では使用されていません。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-InternetAccessEnabled</p></td>
<td><p>この属性は、単一のユーザーが外部ユーザーアクセスを有効にしているかどうかを制御します。 エンタープライズサービス層によって適用されます。 グローバルカタログレプリケーションのマークが付いています。</p>
<p>有効な値は、 <strong>TRUE</strong>または<strong>FALSE</strong>です。</p></td>
<td><p>Live Communications Server 2005 の新しいもの。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-IsMaster (現在不使用)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server の新サービス2003</p>
<p>現在、Live Communications Server 2005 では使用されていません。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP</p></td>
<td><p>この単一値の属性には、テレフォニーで Lync で使用されるデバイス ID (SIP URI またはユーザーが制御する電話の TEL URI) が含まれています。 この属性は、グローバルカタログレプリケーションのマークが付いており、インデックスが作成されます。 ユーザーがエンタープライズ Voip に対して有効になっている場合、この属性はユーザーの電話番号の e.164 正規化されたバージョンを格納します。</p></td>
<td><p>Microsoft Office Live Communications Server 2005 SP1 の新技術情報</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP</p></td>
<td><p>CSTA-SIP ゲートウェイサーバーの SIP URI を含む単一値の属性です。 この属性には、グローバルカタログレプリケーションのマークが付いていますが、インデックスは作成されません。</p></td>
<td><p>Microsoft Office Live Communications Server 2005 SP1 の新技術情報</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationData (現在不使用)</p></td>
<td><p>この属性は、今後の使用のために予約されています。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalizationLinks (現在不使用)</p></td>
<td><p>この複数値属性には、この場所プロファイルに関連付けられているローカル正規化識別名 (DN) の一覧が含まれています。 この属性の型は、DN binary です。 場所プロファイルとローカル正規化ルールの間には、一対多の関係があります。 ローカル正規化 DNs の一覧の順序は、管理者によって指定された順序で維持される必要があります。 順序の保持は、DN binary の2進部分によって維持されます。これにより、注文インデックスが指定されます。</p>
<p>前方リンク:<strong>リンク ID 11034</strong></p>
<p>この転送リンク属性への対応する後方リンクは、 <strong>msRTCSIP-LocationProfileBL</strong>です。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationOptions</p></td>
<td><p>この属性には、正規化ルールのオプションの一覧が含まれています。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationName (現在不使用)</p></td>
<td><p>この単一値の属性には、このプロファイルが表す場所を示す場所のプロファイルのフレンドリ名が含まれています。 複数の場所プロファイルが存在する可能性があるため、管理者は異なるプロファイルを区別するための方法が必要です。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-locationProfileBL (obsolete)</p></td>
<td><p>この複数値属性には、場所プロファイル識別名の一覧が含まれています。 この属性は、1つ以上の場所プロファイルへの後方リンクを指定します。</p>
<p>後方リンク:<strong>リンク ID 11035</strong></p>
<p>この属性は、前方リンク<strong>msRTCSIP-LocalNormalizationLinks</strong>に対応しています。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfileData (現在不使用)</p></td>
<td><p>この属性は、今後の使用のために予約されています。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfileOptions</p></td>
<td><p>この属性には、場所のプロファイルのオプションが含まれています。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MappingContact</p></td>
<td><p>この複数値属性は、アプリケーションの連絡先のリストを保持します。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MappingLocation</p></td>
<td><p>この複数値属性は、場所のプロファイルの一覧を保持します。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Maxnumoutingsearchperserver (現在不使用)</p></td>
<td><p>この属性は、サーバーごとの未処理の検索要求の最大数を表します。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxNumSubscriptionsPerUser (現在不使用)</p></td>
<td><p>ユーザーごとのサブスクリプションの最大数を表す属性です。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Msrtcsip-maxpresencesubscriptiontimeout (現在不使用)</p></td>
<td><p>サブスクリプションタイムアウト期間の最大値を表す属性です。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Msrtcsip-maxregistrationstimeout (現在不使用)</p></td>
<td><p>この属性は、最大登録タイムアウト時間枠を表します。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Msrtcsip-maxroamingdatasubscriptiontimeout (現在不使用)</p></td>
<td><p>この属性は、[移動データサブスクリプションの最大タイムアウト] ウィンドウを表します。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUData</p></td>
<td><p>この属性は、今後の使用のために予約されています。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Msrtcsip-mcufactoryaddress です</p></td>
<td><p>この属性は、属している multipoint control unit (MCU) ファクトリへのリンクを指定するコンピュータークラス下のサービスコントロールポイント属性です。 このサービスコントロールポイントと属性は、Microsoft MCU ごとに作成されます。 各 Microsoft MCU は、プールレベルの設定を取得するために、属しているプールのバックエンドサーバーを検索する必要があります。</p>
<p>この属性の値は、MCU ファクトリの識別名 (DN) です。 これは単一値の属性で、グローバルカタログレプリケーションのマークが付けられています。</p>
<p>前方リンク:<strong>リンク ID 11026</strong></p>
<p>この転送リンク属性への対応する後方リンクは、 <strong>msRTCSIP</strong>ともなります。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryData</p></td>
<td><p>これは複数文字列の予約済み属性です。 この属性に格納されている設定は、名前 = 値のペアとして表されます。 現在定義されている名前 = 値のペアは次のとおりです。</p>
<ul>
<li><p>FactoryURL = &lt;URL&gt;</p></li>
</ul></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Msrtcsip-mcufactorypath</p></td>
<td><p>これは、プールに関連付けられた1つの MCU ファクトリの識別名 (DN) を含む単一値の属性です。</p>
<p>前方リンク:<strong>リンク ID 11024</strong></p>
<p>この転送リンク属性への対応する後方リンクは、 <strong>MsRTCSIP アドレス</strong>です。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryProviderID</p></td>
<td><p>この属性は、MCU ファクトリプロバイダーの GUID を指定する単一値の文字列です。 この GUID 値に基づいて、MCU ファクトリプロセスは、この MCU の種類をサービスするかどうかを決定します。 GUID 値が<strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>の場合、MCU ファクトリプロセス (Lync Server では既定で利用可能) によって処理されます。 その他の GUID 値の場合、MCU ファクトリプロセスは MCU の種類をサービスしません。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUServers ユーザー</p></td>
<td><p>この属性は、複数値を持つ識別名 (DN) のリストです。 この属性には、この MCU ファクトリに関連付けられている同じ種類およびベンダーのすべての MCU サーバーの一覧が含まれています。 各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は255文字です。</p>
<p>後方リンク: リンク ID 11027</p>
<p>この後方リンクへの対応する転送リンクは、 <strong>msRTCSIP-msrtcsip-mcufactoryaddress です</strong>です。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUType</p></td>
<td><p>この属性は、MCU が処理できるメディアを指定する単一値の文字列です。</p>
<p>サポートされている有効な種類は次のとおりです。</p>
<ul>
<li><p>定期的</p></li>
<li><p>音声ビデオ</p></li>
<li><p>チャット</p></li>
<li><p>電話-conf</p></li>
</ul></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUVendor</p></td>
<td><p>この属性は、MCU ベンダーの名前を指定する単一値の文字列です。 すべての Microsoft Mcu は、この属性を<strong>Microsoft Corporation</strong>に指定します。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-会議フラグ (不使用)</p></td>
<td><p>この属性は、すべてのユーザーまたは連絡先オブジェクトに対してグローバルに有効になる、さまざまな会議オプションを定義します。 この属性は、整数型のビットマスク値です。</p>
<p>有効な値 (および関連するビット位置) は次のとおりです。</p>
<ul>
<li><p>0: AllowOrganizeMeetingWithAnonymousParticipants が None (会議への匿名ユーザーの招待をユーザーに許可しない) (ビットが設定されていない)</p></li>
<li><p>4: AllowOrganizeMeetingWithAnonymousParticipants はすべてのユーザー (すべてのユーザーが、会議への匿名ユーザーの招待を許可する) (ビット位置 2)</p></li>
<li><p>8: AllowOrganizeMeetingWithAnonymousParticipants が UsePerUserSetting (ユーザーごとの設定に基づいてユーザーに匿名ユーザーの会議への招待を許可する) (ビット位置 3)</p></li>
<li><p>16: Userperusermeeting Policy (ユーザーごとに会議ポリシーが定義されます) (ビット位置 4)</p></li>
</ul></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-会議ポリシー (不使用)</p></td>
<td><p>この属性は、管理者がこのユーザーに割り当てたポリシーの識別名 (DN) を単一値属性として指定します。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Msrtcsip-minpresencesubscriptiontimeout (現在不使用)</p></td>
<td><p>この属性は、最小プレゼンスサブスクリプションタイムアウト期間を表します。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MinRegistrationTimeout (obsolete)</p></td>
<td><p>この属性は、最小登録タイムアウト時間枠を表します。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Msrtcsip-minroamingdatasubscriptiontimeout (現在不使用)</p></td>
<td><p>この属性は、移動データサブスクリプションタイムアウト期間の最小値を表します。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>この属性は、フロントエンドプールで使用されるミラーリングされた SQL Server バックエンドを格納するために使用されます。</p></td>
<td><p>Lync Server 2013 の新。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MobilityFlags</p></td>
<td><p>この属性には、モビリティ設定を定義するオプションとフラグが含まれています。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MobilityPolicy</p></td>
<td><p>モビリティポリシーオブジェクトの DN を含む属性です。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Msrtcsip-numdevicesperuser (現在不使用)</p></td>
<td><p>ユーザーが SIP コミュニケーション用に登録し、プレゼンスにサブスクライブできるデバイスの許容数を表す属性です。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OptionFlags</p></td>
<td><p>この属性は、ユーザーまたは連絡先オブジェクトに対して有効になっているオプションを指定します。 この属性は、integer 型のビットマスク値です。 各オプションはビットで表されます。 この属性には、グローバルカタログレプリケーションのマークが付いています。</p>
<p>有効な値 (および関連するビット位置) は次のとおりです。</p>
<ul>
<li><p>1: パブリックインスタントメッセージング (IM) 接続が有効 (ビット位置 0)</p></li>
<li><p>2: 予約済み (ビット位置 1)</p></li>
<li><p>4: 予約済み (ビット位置 2)</p></li>
<li><p>8: 予約済み (ビット位置 3)</p></li>
<li><p>16: リモート通話コントロールが有効 [テレフォニー] (ビット位置 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (ユーザーが匿名ユーザーを会議に招待できるようにする (ビット位置 6)</p></li>
<li><p>128: UCEnabled (UC に対してユーザーを有効にする) (ビット位置 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (ユーザーに対してパブリック IM 接続を有効にする) (ビット位置 8)</p></li>
<li><p>512: RemoteCallControlDualMode (ビット位置 9)</p></li>
</ul></td>
<td><p>Live Communications Server 2005 SP1 で導入されています。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-の場合は、Sid</p></td>
<td><p>この属性は、ユーザーの ObjectSID が Windows NT Server プリンシパルアカウントから、リソースまたは中央フォレスト内の対応するユーザーまたは連絡先オブジェクトの属性にコピーされるときにシングルサインオンを有効にするために、リソースおよび中央フォレストのトポロジで使用されます。 Communicator Web Access は、この属性またはユーザーの ObjectSID を使用して、AD DS 内のユーザーを検索します。 この属性には、グローバルカタログレプリケーションのマークが付いています。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OwnerUrn</p></td>
<td><p>この属性は、アプリケーション連絡先の所有者の Uniform Resource Name (URN) です。</p></td>
<td><p>Lync Server 2010 の新。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-パターン (obsolete)</p></td>
<td><p>この単一値の文字列属性には、ダイヤル番号を e.164 形式に一致させるために使用するパターンが含まれています。 ダイヤル番号がこのパターンと一致する場合は、ダイヤル番号に変換が適用されます。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Msrtcsip-phoneroutebl です (現在不使用)</p></td>
<td><p>この複数値属性には、電話ルート識別名 (DN) の一覧が含まれています。 この属性は、1つまたは複数の電話ルートへの後方リンクを指定します。</p>
<p>後方リンク:<strong>リンク ID 11033</strong></p>
<p>この属性は、Msrtcsip-routeusagelinks の前方リンク<strong>msRTCSIP</strong>に対応します。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Msrtcsip-phoneroutedata (現在不使用)</p></td>
<td><p>この属性は、今後の使用のために予約されています。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Msrtcsip-phoneroutename (現在不使用)</p></td>
<td><p>この単一値の UNICODE 文字列属性は、電話ルートのフレンドリ名を指定します。これにより、管理者が簡単に参照できるようになります。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-電話での使用データ (obsolete)</p></td>
<td><p>この属性は、今後の使用のために予約されています。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyContent (現在不使用)</p></td>
<td><p>この属性は、単一の値を持つ Unicode 文字列です。 この文字列属性には、ポリシー定義が XML 形式で含まれています。 XML スキーマ定義はさまざまなポリシーの種類に共通していますが、ポリシーの種類ごとに設定のみが異なります。</p>
<p>XML スキーマ定義 (XSD) は次のように定義されています。</p>
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
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PolicyData (現在不使用)</p></td>
<td><p>この属性は、今後の使用のために予約されています。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Msrtcsip-policytype (現在不使用)</p></td>
<td><p>この単一値の Unicode 文字列属性には、ポリシーの種類が含まれています。 有効なポリシーの種類は次のとおりです。</p>
<ul>
<li><p>定期的</p></li>
<li><p>網</p></li>
</ul></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolAddress</p></td>
<td><p>この属性は、コンピューターが属するプールに戻るリンクを指定します。 この属性は、コンピューターでの Lync Server の Standard Edition または Enterprise Edition のどちらが実行されているかに関係なく設定されます。 この属性には、グローバルカタログレプリケーションのマークが付いています。</p>
<p>有効な値はプールのドメイン名です。</p>
<p>前方リンク:<strong>リンク ID 11022</strong></p>
<p>この転送リンク属性への対応する後方リンクは、 <strong>msRTCSIP-FrontEndServers</strong>です。</p></td>
<td><p>Live Communications Server 2005 の新しいもの。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolAddresses</p></td>
<td><p>これは、MCU ファクトリが関連付けられているプールの識別名 (DN) のリストを含む複数値の属性です。</p>
<p>後方リンク:<strong>リンク ID 11025</strong></p>
<p>この後方リンクへの対応する転送リンクは、 <strong>msRTCSIP-msrtcsip-mcufactorypath</strong>です。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolData</p></td>
<td><p>この属性は、今後の使用のために予約されています。</p></td>
<td><p>Live Communications Server 2005 SP1 で導入されています。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolDisplayName</p></td>
<td><p>この属性は、管理コンソールによって表示されるプールの任意の名前を指定します。 この名前は、管理者が変更できます。</p>
<p>有効な値は、プールの名前を表す文字列です。</p></td>
<td><p>Live Communications Server 2005 の新しいもの。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolDomainFQDN</p></td>
<td><p>この属性は、単一値の文字列型 (string) の値です。 この属性の値は、フロントエンドプールが作成された Active Directory ドメイン構造 (SIP など) に準拠していない FQDN を持つフロントエンドプールを管理者が作成する場合に、プールのドメイン FQDN を表します。名前空間はドメインネームシステム (DNS) 名前空間から分離しています。</p>
<p>プールが存在する Active Directory ドメインとして、フロントエンドプールのドメイン FQDN をドメイン名部分にマップすることをお勧めします。 そのため、この属性に値が指定されていない場合、フロントエンドプールの FQDN は、 <strong>dnsHostName</strong>属性によって示される Active Directory ドメイン名構造に既定で設定されます。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolFunctionality</p></td>
<td><p>プールに関連付けられたすべての Lync Server、Enterprise Edition サーバーのドメイン名の複数値リスト。 Integer 型の属性は、プールがインスタントメッセージング (IM) とプレゼンス、および会議をサポートするかどうかを定義します。</p>
<p>有効な値の種類は次のとおりです。</p>
<ul>
<li><p>未定義: IM およびプレゼンスサービス (Live Communications Server 2005 および 2003)</p></li>
<li><p>1: IM およびプレゼンスサービス (Lync Server)</p></li>
<li><p>2: IM とプレゼンスおよび会議サービス (Lync Server)</p></li>
</ul></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolType</p></td>
<td><p>この属性は、サーバープールで Standard Edition サーバーまたは Enterprise Edition サーバーが実行されているかどうかを指定します。 この属性は、integer 型のビットマスク値です。 各オプションはビットで表されます。</p>
<p>有効な値 (および関連するビット位置) は次のとおりです。</p>
<ul>
<li><p>1: Standard Edition サーバー、ユーザーをホストする (ビット位置 0)</p></li>
<li><p>2: Enterprise Edition サーバー、ユーザーをホストする (ビット位置 1)</p></li>
<li><p>4: Standard Edition サーバー、ホストアプリケーション (ビット位置 2)</p></li>
<li><p>8: Enterprise Edition サーバー、ホストアプリケーション (ビット位置 3)</p></li>
</ul>
<p>Lync Server はアプリケーションのみをホストするプールをサポートしていないため、有効な値は次のとおりです。</p>
<ul>
<li><p>5: Standard Edition サーバー、ユーザーとアプリケーションをホストする (ビット位置0および 2)</p></li>
<li><p>10: Enterprise Edition サーバー、ユーザーとアプリケーションをホストする (ビット位置1および 3)</p></li>
</ul></td>
<td><p>Live Communications Server 2005 の新しいもの。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolVersion</p></td>
<td><p>プールバージョンを定義する属性です。 これは、主な製品リリースごとにインクリメントされる整数型です。</p>
<p>有効な値の種類は次のとおりです。</p>
<ul>
<li><p>0: Live Communications Server 2003</p></li>
<li><p>1: Live Communications Server 2005</p></li>
<li><p>2: Live Communications Server 2005 SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
</ul></td>
<td><p>Live Communications Server 2005 SP1</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PresenceFlags</p></td>
<td><p>この属性には、プレゼンス設定を定義するオプションとフラグが含まれます。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PresencePolicy</p></td>
<td><p>この属性には、プレゼンスポリシーオブジェクトの DN が含まれています。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Msrtcsip-primaryhomeserver</p></td>
<td><p>この属性は、SIP メッセージングのユーザーまたは連絡先を有効にします。 中央フォレストトポロジでは、ユーザーオブジェクトではなく連絡先オブジェクトが SIP が有効になっているため、連絡先クラスに追加されます。</p>
<p>有効な値は、ユーザーが所属する Standard Edition サーバーまたは Enterprise Edition フロントエンドプールの DN です。</p></td>
<td><p>Live Communications Server 2005 の新しいもの。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>この属性には、指定されたユーザーの SIP アドレスが含まれます。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrivateLine</p></td>
<td><p>プライベート回線デバイスのデバイス ID を含む属性です。</p></td>
<td><p>Lync Server 2010 の新。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP ルーティング可能</p></td>
<td><p>この属性は、Lync Server が GRUU アドレスを使用してこのサービスにルーティングすることを承認されているかどうかを判断するために使用されるブール型の属性です。 この値が<strong>TRUE</strong>に設定されている場合、Lync Server はこのサービスへのルーティングを承認されています。 この値が<strong>FALSE</strong>に設定されている場合、Lync Server はこのサービスへのルーティングを承認されていません。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Msrtcsip-routeusageattribute (現在不使用)</p></td>
<td><p>この単一値の UNICODE 文字列属性は、電話ルートの使用を限定する属性を定義します。 電話ルートの選択は、2つの要素、つまり、電話ルートに割り当てられる usage 属性と、発信者に許可されているポリシー使用法属性に基づいて決定されます。 発信者の許可された使用法に一致する使用法属性を持つ最初の電話ルートが選択されています。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Msrtcsip-routeusagelinks (現在不使用)</p></td>
<td><p>この複数値の識別名 (DN) 属性には、ルート使用法の識別名の一覧が含まれています。</p>
<p>前方リンク:<strong>リンク ID 11032</strong></p>
<p>この属性は、対応する後方リンク<strong>msRTCSIP-msrtcsip-phoneroutebl です</strong>への転送リンクです。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RoutingPoolDN</p></td>
<td><p>この MCU または信頼済みサービス宛てのすべての SIP トラフィックが通過する必要のあるプールを指す DN を含む属性です。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RuleName (現在不使用)</p></td>
<td><p>正規化ルールのフレンドリ名を指定する単一値の UNICODE 文字列属性は、管理者が簡単に参照できるようにします。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SchemaVersion</p></td>
<td><p>この属性は、組織に現在展開されているスキーマのバージョンを表します。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SearchMaxRequests (obsolete)</p></td>
<td><p>ユーザーが Communicator を使用して連絡先を検索するときにディレクトリ検索から返される検索結果の数を制限する属性です。 この属性は、クライアントによって指定された値より優先されます。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SearchMaxResults (現在不使用)</p></td>
<td><p>この属性は、返される検索要求の数を制限します。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerBL</p></td>
<td><p>この複数値属性は、識別名 (DN) の一覧を含む後方リンクです。 これらの DNs は、プールまたは<strong>Trustedservice</strong>オブジェクトを指します。</p>
<p>この属性は、Msrtcsip-trustedservicelinks ですの前方リンク<strong>msRTCSIP</strong>に対応します。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerData</p></td>
<td><p>この属性は、今後の使用のために予約されています。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerReferenceBL (obsolete)</p></td>
<td><p>この複数値属性には、識別名の一覧が含まれています。 これらの識別名は、既定の場所のプロファイルを割り当てることができる他のサーバーオブジェクトを参照する後方リンクです。</p>
<p>後方リンク:<strong>リンク ID 11037</strong></p>
<p>この後方リンクへの対応する転送リンクは<strong>msRTCSIP-DefaultLocationProfileLink</strong>です。</p>
<p>この後方リンク属性は、プールと仲介サーバーのみを参照します。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerVersion</p></td>
<td><p>この属性は、サーバーのバージョン情報を定義します。 このバージョン番号は、すべてのサーバーの役割に適用されます。 これは、公式の製品リリースごとに増加する、monotonously の整数です。</p>
<p>有効な値は次のとおりです。</p>
<ul>
<li><p>Undefined: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 with SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
</ul></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SourceObjectType</p></td>
<td><p>次に示すように、integer 型のこの単一値属性は、 <strong>msds-sourceobjectdn</strong>が指すオブジェクトの種類を指定します。</p>
<ul>
<li><p>null |0x00000001: 別のフォレストの Windows NT Server プリンシパルユーザーオブジェクトを表します。</p></li>
<li><p>次の属性は、配布グループ拡張のための別のフォレストのグループの種類を表します。</p>
<ul>
<li><p>0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</p></li>
<li><p>0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</p></li>
<li><p>0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</p></li>
<li><p>0x90000000: 同じフォレストまたは別のフォレストからの自動応答またはサブスクライバーアクセスオブジェクトを表します。</p></li>
</ul></li>
</ul></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SubscriptionAuthRequired (obsolete)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003 の新しいもの。</p>
<p>現在、Live Communications Server 2005 では使用されていません。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Targethoの場合</p></td>
<td><p>この属性を使用すると、1つの Lync Server プールから別のユーザーまたは連絡先オブジェクトを移動することができます。 この属性は contact クラスに追加されます。中央フォレストのトポロジでは、ユーザーオブジェクトではなく連絡先オブジェクトが SIP が有効になっているためです。</p>
<p>有効な値は、ユーザーの移動先の Standard Edition サーバーまたはフロントエンドプールの DN です。</p></td>
<td><p>Live Communications Server 2005 の新しいもの。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Msrtcsip-targetphonenumber (現在不使用)</p></td>
<td><p><strong>MsRTCSIP</strong>で定義されている特定のゲートウェイにルーティングする電話番号のパターンまたは範囲を含む単一値の文字列属性です。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetUserPolicies</p></td>
<td><p>この属性は、Lync Server ユーザーのターゲットポリシーの名前と値のペアを格納します。</p></td>
<td><p>Lync Server 2010 の新。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TenantId</p></td>
<td><p>テナントの一意識別子を格納する属性です。</p></td>
<td><p>Lync Server 2010 の新。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-変換 (現在不使用)</p></td>
<td><p>この属性は、Lync Server の音声機能によって使用され、一致が見つかった場合にダイヤル番号に適用する変換文字列を格納します。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCUData</p></td>
<td><p>この属性は、今後の使用のために予約されています。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUFQDN</p></td>
<td><p>この属性は、MCU の FQDN を含む文字列型 (string) の値です。 これは単一値の属性です。 各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は255文字です。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxyData</p></td>
<td><p>この属性は、今後の使用のために予約されています。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxyFQDN</p></td>
<td><p>この属性は、プロキシサーバーを実行しているサーバーの FQDN を含む文字列型 (string) の値です。 この属性は単一値です。 各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は255文字です。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerData</p></td>
<td><p>この属性は、今後の使用のために予約されています。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServerFQDN</p></td>
<td><p>この属性は、信頼済みサーバーの FQDN を表す単一値の属性です。</p></td>
<td><p>Live Communications Server 2005 の新しいもの。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerVersion</p></td>
<td><p>この属性は、信頼済みサーバーの一覧のサーバーのバージョン番号を指定します。</p>
<p>有効な値は次のとおりです。</p>
<ul>
<li><p>NULL: Live Communications Server 2003</p></li>
<li><p>2: Live Communications Server 2005</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
</ul></td>
<td><p>Live Communications Server 2005 の新しいもの。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServiceFlags</p></td>
<td><p>この属性は、信頼済みサービスに対して有効になるオプションを定義します。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Msrtcsip-trustedservicelinks です</p></td>
<td><p>この複数値属性には、メディアリレー認証サービスなど、信頼されたサービスオブジェクトを参照する識別名 (DN) の一覧が含まれています。 メディアリレー認証サービス (音声ビデオ会議サービスを実行しているエッジサーバーに物理的に併置されている) は、リモートユーザーのオーディオシナリオをサポートするために、プールに関連付けられている必要があります。</p>
<p>この転送リンク属性への対応する後方リンクは、 <strong>msRTCSIP-ServerBL</strong>です。</p></td>
<td><p>UC</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServicePort</p></td>
<td><p>この GRUU サービスへの接続に使用するポート番号を定義する整数の属性です。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceType</p></td>
<td><p>この属性は、それが表す GRUU サービスの種類を定義する文字列型 (string) の値です。</p>
<p>有効な GRUU サービスの種類は次のとおりです。</p>
<ul>
<li><p>MediationServer</p></li>
<li><p>ゲートウェイ</p></li>
<li><p>メディアリレー認証サービス (MRAS)</p></li>
<li><p>QoSM</p></li>
<li><p>msRTCSIP-UserExtension NM-CWA-NO-VERSION</p></li>
</ul></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Trustedwebコンポーネント Serverdata</p></td>
<td><p>この属性は、今後の使用のために予約されています。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Trustedwebコンポーネント Serverfqdn</p></td>
<td><p>この属性は、Lync Server Web サービスを実行している IIS の FQDN を含む文字列型 (string) の値です。 これは単一値の属性です。 各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は255文字です。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UCFlags (obsolete)</p></td>
<td><p>この属性は、すべてのユーザーオブジェクトまたは連絡先オブジェクトに対してグローバルに有効になっているさまざまな UC オプションを定義します。 この属性は、整数型のビットマスク値です。 各オプションは、ビットがあるかどうかで表されます。</p>
<p>有効な値 (および関連するビット位置) は次のとおりです。</p>
<ul>
<li><p>4: UsePerUserUCPolicy (ビット位置 2)</p></li>
</ul>
<p>このビットが設定されている場合、UC ポリシーはユーザーごとに定義されます。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UCPolicy (現在不使用)</p></td>
<td><p>この単一値の属性には、管理者がこのユーザーに対して割り当てた UC ポリシーの識別名 (DN) が含まれています。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserDomainList (obsolete)</p></td>
<td><p>この属性は、SIP が有効なユーザーをホストするフォレスト内のすべてのドメインの一覧を提供します。 既定値は空のリストで、フォレスト内のすべてのドメインの SIP が有効になっていることを示します。</p>
<p>有効な値は、個々のドメインのドメイン名を表す複数の文字列です。</p></td>
<td><p>Live Communications Server 2005 の新しいもの。</p>
<p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserEnabled</p></td>
<td><p>この属性は、ユーザーが Lync Server に対して現在有効になっているかどうかを決定します。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserExtension</p></td>
<td><p>Name = value の&quot;形式の名前と値のペアの一覧を含む複数値の属性です。&quot;この属性には、グローバルカタログレプリケーションのマークが付いています。</p></td>
<td><p>Live Communications Server 2005 SP1 で導入されています。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserLocationProfile</p></td>
<td><p>この属性には、場所のプロファイルオブジェクトを指す識別名 (DN) が含まれています。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserPolicies</p></td>
<td><p>この属性は、ユーザーポリシーの名前と値のペアを格納します。</p></td>
<td><p>Lync Server 2010 の新。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserPolicy</p></td>
<td><p>これは、異なる種類のグローバルユーザーポリシーをポイントするバイナリ (DN_WITH_BINARY) を含む複数値の属性です。 Binary 部分は、DN 部分が指すポリシーの種類を示します。</p>
<p>有効なバイナリ値は次のとおりです。</p>
<ul>
<li><p>0x00000001: 会議ポリシー</p></li>
<li><p>0x00000002: UC ポリシー</p></li>
<li><p>0x00000005: プレゼンスポリシー</p></li>
</ul></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>SIP ルーティング グループ ID。同じグループのユーザーは、同じフロントエンド サーバーに登録します。</p></td>
<td><p>Lync Server 2013 の新。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Webコンポーネントデータ</p></td>
<td><p>これは複数値の属性です。 この属性は、今後の使用のために予約されています。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Msrtcsip-webcomponentspooladdress</p></td>
<td><p>Web コンポーネントが属するプールまたは Standard Edition サーバーを示す単一値の属性です。</p>
<p>前方リンク:<strong>リンク ID 11028</strong></p>
<p>この転送リンク属性への対応する後方リンクは、 <strong>msRTCSIP-Webコンポーネントサーバー</strong>です。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Webコンポーネントサーバー</p></td>
<td><p>この属性は、複数値を持つ識別名の一覧です。 この属性には、このプールに関連付けられているすべての Web サーバーの一覧が含まれています。</p>
<p>後方リンク:<strong>リンク ID 11029</strong></p>
<p>この後方リンクへの対応する転送リンクは、 <strong>msRTCSIP-msrtcsip-webcomponentspooladdress</strong>です。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP (現在不使用)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003 の新しいもの。</p>
<p>現在、Live Communications Server 2005 では使用されていません。</p></td>
</tr>
<tr class="odd">
<td><p>OtherIPPhone</p></td>
<td><p>この既存の Active Directory 属性は、テレフォニーが電話の代替 TCP/IP アドレスの一覧を指定するために使用されます。</p></td>
<td><p>Windows Server 2008 オペレーティングシステムの新機能。</p></td>
</tr>
<tr class="even">
<td><p>電話電話 (その他)</p></td>
<td><p>この既存の Active Directory 属性は、Lync Server の音声コンポーネントによって使用されます。連絡先オブジェクトの場合は、ユニファイドメッセージングの自動応答およびサブスクライバーアクセス番号への呼び出しをルーティングすることを目的としています。 無条件着信転送アドレスは、この複数値属性に格納されます。 このアカウントは、自動応答およびサブスクライバーアクセスの特定の目的のために作成されます。 このアカウントの属性は、管理者が変更することはできません。</p></td>
<td><p>Windows 2000 オペレーティングシステムの新機能。</p></td>
</tr>
<tr class="odd">
<td><p>ProxyAddresses</p></td>
<td><p>この既存の Active Directory 複数値属性は、Windows 2000 で導入された base Active Directory スキーマの一部です。 この属性には、ユーザーの電子メールのさまざまな X400、X500、および SMTP アドレスが含まれています。 Live Communications Server 2003 以降では、 &quot;sip:&quot;タグを使用して、ユーザーの sip URI がこのリストに追加されます。</p>
<p>次のアプリケーションは、この属性からユーザーの SIP URI を検索します。</p>
<ul>
<li><p>Microsoft Office Outlook 2003 メッセージングおよびコラボレーションクライアント</p></li>
<li><p>Microsoft Office SharePoint Server 2007</p></li>
</ul></td>
<td><p>Windows 2000 オペレーティングシステムの新機能。</p></td>
</tr>
<tr class="even">
<td><p>TelephoneNumber</p></td>
<td><p>この既存の Active Directory 属性には、ユーザーの電話番号が含まれています。</p></td>
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

