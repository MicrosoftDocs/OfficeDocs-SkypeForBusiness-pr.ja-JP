---
title: 監視ノードの構成とインストール
TOCTitle: 監視ノードの構成とインストール
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48272306
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 監視ノードの構成とインストール

 

_**トピックの最終更新日:** 2015-03-09_

監視ノードは、Lync Server 代理トランザクションを定期的に実行するコンピューターです。代理トランザクションは、重要なエンド ユーザー シナリオ (システムへのサインインやインスタント メッセージの交換など) が予想どおりに動作することを検証する Windows PowerShell コマンドレットです。Lync Server 2013 では、System Center Operations Manager は、次の表に示す代理トランザクションを実行できます。代理トランザクションには、表に示す 3 つの種類があります。

  - **既定**。監視ノードが既定で実行する代理トランザクションです。新しい監視ノードを作成するときに、そのノードが実行する代理トランザクションを指定できます (これが **New-CsWatcherNodeConfiguration** コマンドレットで使用される Tests パラメーターの目的です)。監視ノードの作成時に Tests パラメーターを使用しない場合は、すべての既定の代理トランザクションが実行され、既定以外の代理トランザクションはまったく実行されません。これは、監視ノードがたとえば Test-CsAddressBookService テストは実行するが、Test-CsExumConnectivity テストは実行しないように構成されることを意味します。

  - **既定以外**。名前が意味するように、既定以外の代理トランザクションは、監視ノードが既定で実行しないテストです。ただし、監視ノードは、任意の既定以外の代理トランザクションを実行するように設定できます。これは、**New-CsWatcherNodeConfiguration** コマンドレットを使用して監視ノードを作成するとき、または作成後の任意の時点で実行できます。既定以外の代理トランザクションの多くは、追加のセットアップ手順を実行する必要があります。詳しくは、「[代理トランザクションの特別なセットアップ指示](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)」をご覧ください。

  - **拡張**。拡張テストは、特別な種類の既定以外の代理トランザクションです。他の代理トランザクションとは異なり、拡張テストは、1 回のパスで複数回実行できます。これは、プールに対する複数の公衆交換電話網 (PSTN) 音声ルートなどの動作を検証するときに便利です。これは、拡張テストの複数のインスタンスを監視ノードに追加するだけで構成できます。

監視ノードに他の代理トランザクションを追加する方法については、「[監視ノードの管理](lync-server-2013-managing-watcher-nodes.md)」をご覧ください。Lync Server 管理シェル を使用して監視ノードから代理トランザクションを削除することもできます。

監視ノードで使用できる代理トランザクションは以下のとおりです。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>コマンドレット名 (テスト名)</th>
<th>説明</th>
<th>代理トランザクションの種類</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Test-CsAddressBookService (ABS)</p></td>
<td><p>ユーザーが各自の連絡先リストに含まれていないユーザーを検索できることを確認します。</p></td>
<td><p>既定</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAddressBookWebQuery (ABWQ)</p></td>
<td><p>ユーザーが各自の連絡先リストに含まれていないユーザーを HTTP 経由で検索できることを確認します。</p></td>
<td><p>既定</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsIM (IM)</p></td>
<td><p>ユーザーがピアツーピア インスタント メッセージを送信できることを確認します。</p></td>
<td><p>既定</p></td>
</tr>
<tr class="even">
<td><p>Test-CsP2PAV (P2PAV)</p></td>
<td><p>ユーザーがピアツーピア音声通話を開始できることを確認します (シグナリングのみ)。</p></td>
<td><p>既定</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsPresence (Presence)</p></td>
<td><p>ユーザーが他のユーザーのプレゼンスを表示できることを確認します。</p></td>
<td><p>既定</p></td>
</tr>
<tr class="even">
<td><p>Test-CsRegistration (Registration)</p></td>
<td><p>ユーザーが Lync にサインインできることを確認します。</p></td>
<td><p>既定</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAudioConferencingProvider (ACP)</p></td>
<td><p>Lync Server 2013 の社内版では使用されません。</p></td>
<td><p>拡張</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPstnPeerToPeerCall (PSTN)</p></td>
<td><p>ユーザーが企業の外部のユーザー (PSTN 番号) と通話できることを確認します。</p></td>
<td><p>既定以外、拡張</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAVConference (AvConference)</p></td>
<td><p>ユーザーが音声/ビデオ会議で作成と参加が可能なことを確認します。</p></td>
<td><p>既定</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</p></td>
<td><p>音声ビデオ エッジ サーバーがピアツーピア通話と会議通話を行うための接続を受け入れることができることを確認します。</p></td>
<td><p>既定以外</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsDataConference (DataConference)</p></td>
<td><p>ユーザーが、データ グループ作業電話会議 (ホワイトボードや投票などのアクティビティが含まれるオンライン会議) に参加できることを確認します。</p></td>
<td><p>既定以外</p></td>
</tr>
<tr class="even">
<td><p>Test-CsExumConnectivity (ExumConnectivity)</p></td>
<td><p>ユーザーが Exchange ユニファイド メッセージング (UM)に接続できることを確認します。</p></td>
<td><p>既定以外</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsGroupIM (GroupIM)</p></td>
<td><p>ユーザーが会議中にインスタント メッセージを送信でき、3 人以上のユーザーとインスタント メッセージでの会話に参加できることを確認します。</p></td>
<td><p>既定</p></td>
</tr>
<tr class="even">
<td><p>Test-CsGroupIM ?TestJoinLauncher (JoinLauncher)</p></td>
<td><p>ユーザーがミーティングを作成でき、予定されたミーティングに Web アドレス リンクを介して参加できることを確認します。</p></td>
<td><p>既定以外</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsMCXP2PIM (MCXP2PIM)</p></td>
<td><p>モバイル デバイス ユーザーがインスタント メッセージの登録と送信を実行できることを確認します。</p></td>
<td><p>既定以外</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPersistentChatMessage (PersistentChatMessage)</p></td>
<td><p>ユーザーが常設チャット サービスを使用してメッセージを交換できることを確認します。</p></td>
<td><p>既定以外</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsUnifiedContactStore (UnifiedContactStore)</p></td>
<td><p>統合連絡先ストアを通じてユーザーの連絡先にアクセスできることを確認します。統合連絡先ストアにより、Lync 2013、Outlook、および Outlook Web Access を使用してアクセスできる単一の連絡先セットを保持できます。</p></td>
<td><p>既定以外</p></td>
</tr>
<tr class="even">
<td><p>Test-CsXmppIM (XmppIM)</p></td>
<td><p>インスタント メッセージを XMPP (Extensible Messaging and Presence Protocol) ゲートウェイ経由で送信できることを確認します。</p></td>
<td><p>既定以外</p></td>
</tr>
</tbody>
</table>


System Center Operations Manager を使用するために監視ノードをインストールする必要はありません。これらのノードをインストールしなかった場合でも、問題が発生したときに Lync Server 2013 コンポーネントからリアルタイムの通知を取得できます (Component and User Management Pack は監視ノードを使用しません)。ただし、エンドツーエンド シナリオを Active Monitoring Management Pack を使用して監視する場合は、監視ノードが必要です。

> [!NOTE]
> 管理者は、Operations Manager を使用したり、それをインストールすることなく、代理トランザクションを手動で実行することもできます。さまざまな Test-Cs コマンドレットについて詳しくは、「<a href="https://docs.microsoft.com/en-us/powershell/module/skype/?view=skype-ps">Lync Server 2013 のコマンドレットのインデックス</a>」をご覧ください。


展開の規模によっては、代理トランザクションがコンピューター メモリを大量に使用し、プロセッサを長時間使用する場合があります。このため、監視ノードとして動作する専用コンピューターを使用することをお勧めします。たとえば、フロント エンド サーバーは監視ノードとして構成しないでください。監視ノードは、以下のハードウェア仕様を満たす必要があります。

> [!NOTE]
> レガシー Microsoft Lync Server 2010 監視ノードは、Lync Server 2013 監視ノードと同じコンピューターに併置することはできません。これは、Lync Server 2010 および Lync Server 2013 用のコア システム ファイルを同じコンピューターにインストールできないためです。<br />
> ただし、Lync Server 2013 監視ノードは、Lync Server 2013 および Lync Server 2010 の両方を同時に監視できます。既定の代理トランザクションは、両方のバージョンの製品でサポートされます。


Lync Server 2013 監視ノードは、社内または社外に展開して、以下を検証できます。

  - 社内ユーザー用プールへの接続。

  - 社外で働くリモート ユーザー用の境界ネットワーク経由の接続。

  - ブランチ オフィス アプライアンスへの接続。

  - 社内の Lync Server 2010 への境界ネットワーク経由の接続。

管理を容易にするため、社内および社外用の異なる認証オプションがあります。詳しくは、「[代理トランザクションを実行する監視ノードの構成](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md)」をご覧ください。

監視ノードとして動作するようにコンピューターを構成するには、System Center Operations Manager をインストールし、Lync Server 2013 管理パックをインポートした後、次の手順を完了する必要があります。

Lync Server 2013 コア ファイルおよび System Center エージェント ファイルをインストールする前に、監視ノードに使用するコンピューターが Lync Server 2013 をインストールするためのすべての前提条件を満たしていることも確認する必要があります。さらに、監視ノード コンピューターには、次の項目がインストールされている必要があります。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ハードウェア コンポーネント</th>
<th>最小要件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>次のいずれかの要件:</p>
<ul>
<li><p>2.33 GHz またはそれ以上の 64 ビット プロセッサ、クアッド コア</p></li>
<li><p>64 ビット 2 ウェイ プロセッサ、デュアル コア、2.33 GHz 以上</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>メモリ</p></td>
<td><p>8 GB</p></td>
</tr>
<tr class="odd">
<td><p>ネットワーク オペレーティング システム</p></td>
<td><ul>
<li><p>1 つのネットワーク アダプター (1 Gbps)</p></li>
<li><p>Windows Server 2008 R2、Windows Server 2012、または</p>
<p>Windows Server 2012 R2</p></li>
</ul></td>
</tr>
</tbody>
</table>


  - 製品版の .NET Framework 4.5。

  - Windows Identity Foundation。

  - Windows PowerShell 3.0。

これらの前提条件がすべて満たされた後、次を行うことで監視ノードを構成できます。

  - 監視ノード コンピューターへの Lync Server 2013 コア ファイルのインストール。

  - 監視ノード コンピューターへの System Center Operations Manager エージェントのインストール。

  - Watchernode.msi 実行可能ファイルの実行。

  - **CsWatcherNodeConfiguration** コマンドレットによる監視ノードで使用されるテスト ユーザーの構成。

