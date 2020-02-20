---
title: 'Lync Server 2013: 監視ノードのインストールと構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing and configuring watcher nodes
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48184284
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cd57e3b78e3e16ac9d640536771cf2b5b90773a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a>Lync Server 2013 での監視ノードのインストールと構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-11-07_

*監視ノード*は、定期的に Lync Server 代理トランザクションを実行するコンピューターです。 *代理トランザクション*は Windows PowerShell コマンドレットで、システムにサインインする機能、またはインスタントメッセージを交換できるかどうかなど、主要なエンドユーザーシナリオが想定どおりに動作していることを確認します。 Lync Server 2013 の場合、System Center Operations Manager は、次の表に示す代理トランザクションを実行できます。 代理トランザクションには、表に示す 3 つの種類があります。

  - **既定値**です。 既定では、監視ノードが実行する代理トランザクションです。 新しい監視ノードを作成するときに、そのノードが実行する代理トランザクションを指定するオプションがあります。 (これは、 **set-cswatchernodeconfiguration**コマンドレットで使用される Tests パラメーターの目的です。)監視ノードの作成時に Tests パラメーターを使用しない場合、既定の代理トランザクションがすべて自動的に実行され、既定以外の代理トランザクションは実行されません。 これは、たとえば、監視ノードが Test-CsAddressBookService テストを実行するように構成されていますが、テスト-CsExumConnectivity テストを実行するように構成されていないことを意味します。

  - **既定値ではない**。 名前が意味するように、既定以外の代理トランザクションは、監視ノードが既定で実行しないテストです。 ただし、監視ノードは、任意の既定以外の代理トランザクションを実行するように設定できます。 これは、**New-CsWatcherNodeConfiguration** コマンドレットを使用して監視ノードを作成するとき、または作成後の任意の時点で実行できます。 既定以外の代理トランザクションの多くは、追加のセットアップ手順を実行する必要があります。 詳細については、「 [Lync Server 2013 の代理トランザクションの特別なセットアップ手順](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)」を参照してください。

  - **拡張**。 拡張テストは、特別な種類の既定以外の代理トランザクションです。 他の代理トランザクションとは異なり、拡張テストは、1 回のパスで複数回実行できます。 これは、プールに対する複数の公衆交換電話網 (PSTN) 音声ルートなどの動作を検証するときに便利です。 これは、拡張テストの複数のインスタンスを監視ノードに追加するだけで構成できます。

他の代理トランザクションを監視ノードに追加するプロセスの詳細については、「 [Lync Server 2013 の監視ノードの管理](lync-server-2013-managing-watcher-nodes.md)」を参照してください。 Lync Server 管理シェルを使用して、監視ノードから代理トランザクションを削除することができます。

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
<td><p>既定値</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAddressBookWebQuery (ABWQ)</p></td>
<td><p>ユーザーが各自の連絡先リストに含まれていないユーザーを HTTP 経由で検索できることを確認します。</p></td>
<td><p>既定値</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsIM (IM)</p></td>
<td><p>ユーザーがピアツーピア インスタント メッセージを送信できることを確認します。</p></td>
<td><p>既定値</p></td>
</tr>
<tr class="even">
<td><p>Test-csp2pav (P2PAV)</p></td>
<td><p>ユーザーがピアツーピア音声通話を開始できることを確認します (シグナリングのみ)。</p></td>
<td><p>既定値</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsPresence (Presence)</p></td>
<td><p>ユーザーが他のユーザーのプレゼンスを表示できることを確認します。</p></td>
<td><p>既定値</p></td>
</tr>
<tr class="even">
<td><p>Test-CsRegistration (Registration)</p></td>
<td><p>ユーザーが Lync にサインインできることを確認します。</p></td>
<td><p>既定値</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAudioConferencingProvider (ACP)</p></td>
<td><p>社内バージョンの Lync Server 2013 では使用されません。</p></td>
<td><p>拡張</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPstnPeerToPeerCall (PSTN)</p></td>
<td><p>ユーザーが企業の外部のユーザー (PSTN 番号) と通話できることを確認します。</p></td>
<td><p>既定以外、拡張</p></td>
</tr>
<tr class="odd">
<td><p>テスト-CsAVConference (AvConference)</p></td>
<td><p>ユーザーが音声/ビデオ会議で作成と参加が可能なことを確認します。</p></td>
<td><p>既定値</p></td>
</tr>
<tr class="even">
<td><p>Test-csavedgeconnectivity (AVEdgeConnectivity)</p></td>
<td><p>音声ビデオ エッジ サーバーがピアツーピア通話と会議通話を行うための接続を受け入れることができることを確認します。</p></td>
<td><p>既定以外</p></td>
</tr>
<tr class="odd">
<td><p>Test-csdataconference (DataConference)</p></td>
<td><p>ユーザーが、データ グループ作業電話会議 (ホワイトボードや投票などのアクティビティが含まれるオンライン ミーティング) に参加できることを確認します。</p></td>
<td><p>既定以外</p></td>
</tr>
<tr class="even">
<td><p>テスト-CsExumConnectivity (ExumConnectivity)</p></td>
<td><p>ユーザーが Exchange ユニファイドメッセージング (UM) に接続できることを確認します。</p></td>
<td><p>既定以外</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsGroupIM (GroupIM)</p></td>
<td><p>ユーザーが会議中にインスタント メッセージを送信でき、3 人以上のユーザーとインスタント メッセージでの会話に参加できることを確認します。</p></td>
<td><p>既定値</p></td>
</tr>
<tr class="even">
<td><p>Test-CsGroupIM – TestJoinLauncher (Joinラウンチャー)</p></td>
<td><p>ユーザーがミーティングを作成でき、予定されたミーティングに Web アドレス リンクを介して参加できることを確認します。</p></td>
<td><p>既定以外</p></td>
</tr>
<tr class="odd">
<td><p>Test-csmcxp2pim (MCXP2PIM)</p></td>
<td><p>モバイル デバイス ユーザーがインスタント メッセージの登録と送信を実行できることを確認します。</p></td>
<td><p>既定以外</p></td>
</tr>
<tr class="even">
<td><p>Test-cspersistentchatmessage (PersistentChatMessage)</p></td>
<td><p>ユーザーが常設チャットサービスを使用してメッセージを交換できることを確認します。</p></td>
<td><p>既定以外</p></td>
</tr>
<tr class="odd">
<td><p>Test-csunifiedcontactstore (UnifiedContactStore)</p></td>
<td><p>統合連絡先ストアを通じてユーザーの連絡先にアクセスできることを確認します。 統合連絡先ストアは、Lync 2013、Outlook、または Outlook Web Access を使用してアクセスできる単一の連絡先セットを管理する方法をユーザーに提供します。</p></td>
<td><p>既定以外</p></td>
</tr>
<tr class="even">
<td><p>テスト-CsXmppIM (XmppIM)</p></td>
<td><p>インスタント メッセージを XMPP (Extensible Messaging and Presence Protocol) ゲートウェイ経由で送信できることを確認します。</p></td>
<td><p>既定以外</p></td>
</tr>
</tbody>
</table>


System Center Operations Manager を使用するために監視ノードをインストールする必要はありません。 これらのノードをインストールしていない場合でも、問題が発生したときに Lync Server 2013 コンポーネントからリアルタイム通知を受け取ることができます。 (コンポーネントおよびユーザー管理パックでは、監視ノードは使用されません)。ただし、アクティブな監視管理パックを使用してエンドツーエンドのシナリオを監視する場合は、監視ノードが必要です。

<div>


> [!NOTE]  
> 管理者は、Operations Manager を使用したり、それをインストールすることなく、代理トランザクションを手動で実行することもできます。 さまざまなテスト用コマンドレットの詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 コマンドレットのインデックス</A>」を参照してください。



</div>

展開の規模によっては、代理トランザクションがコンピューター メモリを大量に使用し、プロセッサを長時間使用する場合があります。 このため、監視ノードとして動作する専用コンピューターを使用することをお勧めします。 たとえば、監視ノードとして動作するようにフロントエンドサーバーを構成する必要はありません。 監視ノードは、次のハードウェア仕様を満たしている必要があります。

<div>


> [!NOTE]  
> 従来の Microsoft Lync Server 2010 監視ノードを、Lync Server 2013 監視ノードと同じコンピューターに併置することはできません。 これは、Lync Server 2010 および Lync Server 2013 のコアシステムファイルを同じコンピューターにインストールできないためです。<BR>ただし、Lync server 2013 監視ノードは、Lync Server 2013 と Lync Server 2010 の両方を同時に監視できます。 既定の代理トランザクションは、両方のバージョンの製品でサポートされます。



</div>

Lync Server 2013 監視ノードはエンタープライズの内部または外部に展開され、次の点を確認できます。

  - <span></span>  
    社内ユーザー用プールへの接続。

  - <span></span>  
    社外で働くリモート ユーザー用の境界ネットワーク経由の接続。

  - <span></span>  
    ブランチ オフィス アプライアンスへの接続。

  - <span></span>  
    企業内および境界ネットワークを介した Lync Server 2010 への接続。

管理を容易にするため、社内および社外用の異なる認証オプションがあります。 詳細については、「 [Lync Server 2013 で代理トランザクションを実行する監視ノードの構成](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md)」を参照してください。

監視ノードとして動作するようにコンピューターを構成するには、System Center Operations Manager をインストールして Lync Server 2013 管理パックをインポートした後、次の手順を実行する必要があります。

Lync Server 2013 コアファイルおよび System Center エージェントファイルをインストールする前に、監視ノードコンピューターが Lync Server 2013 をインストールするための前提条件をすべて満たしていることを確認する必要があります。 さらに、監視ノード コンピューターには、次の項目がインストールされている必要があります。


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
<li><p>64ビットプロセッサ、クアッドコア、2.33 GHz またはそれ以上</p></li>
<li><p>64ビット2ウェイプロセッサ、デュアルコア、2.33 GHz またはそれ以上</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>メモリ</p></td>
<td><p>8 GB</p></td>
</tr>
<tr class="odd">
<td><p>ネットワークオペレーティングシステム</p></td>
<td><ul>
<li><p>1ネットワークアダプター 1 Gbps</p></li>
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

  - 監視ノードコンピューターに Lync Server 2013 コアファイルをインストールします。

  - 監視ノードコンピューターに System Center Operations Manager エージェントをインストールしています。

  - Watchernode.msi 実行可能ファイルの実行。

  - **CsWatcherNodeConfiguration** コマンドレットによる監視ノードで使用されるテスト ユーザーの構成。

</div>

<span> </span>

</div>

</div>

</div>

