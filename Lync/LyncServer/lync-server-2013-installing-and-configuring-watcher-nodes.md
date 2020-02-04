---
title: 'Lync Server 2013: ウォッチャーノードのインストールと構成'
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
ms.openlocfilehash: 89465227e351da3c69116201efe5ee4eab89eca4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a>Lync Server 2013 でのウォッチャーノードのインストールと構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-11-07_

*ウォッチャーノード*は、定期的に Lync Server の代理トランザクションを実行するコンピューターです。 *代理トランザクション*は、Windows PowerShell コマンドレットであり、システムへのサインイン機能や、インスタントメッセージの交換機能など、主要なエンドユーザーシナリオが期待どおりに機能していることを確認するための Windows PowerShell コマンドレットです。 Lync Server 2013 の場合、System Center Operations Manager は、次の表に示す代理トランザクションを実行できます。 テーブルには、次の3種類の代理トランザクションタイプが表示されます。

  - **既定値**。 これは、既定でウォッチャーノードが実行する代理トランザクションです。 新しいウォッチャーノードを作成するときに、ノードが実行する代理トランザクションを指定するオプションがあります。 (これは、 **CsWatcherNodeConfiguration**コマンドレットで使用されるテストパラメーターの目的です。)ウォッチャーノードが作成されたときに Tests パラメーターを使用しないと、既定のすべての合成トランザクションが自動的に実行され、既定以外の代理トランザクションは実行されません。 つまり、たとえば、watcher ノードは、CsAddressBookService のテストを実行するように構成されていますが、テスト-CsExumConnectivity テストを実行するように構成されていないことを意味します。

  - **既定以外の値**。 名前が示すように、既定以外の代理トランザクションは、既定ではウォッチャーノードが実行されないテストです。 ただし、ウォッチャーノードを有効にして、既定以外の代理トランザクションのいずれかを実行することができます。 これは、( **CsWatcherNodeConfiguration**コマンドレットを使用して) ウォッチャーノードを作成するとき、またはそれ以降の任意の時点で行うことができます。 既定以外の代理トランザクションの多くには、追加のセットアップ手順が必要です。 詳細については、「 [Lync Server 2013 での代理トランザクション用の特別なセットアップ手順](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)」を参照してください。

  - **拡張**します。 拡張テストは、特別な種類の既定以外の代理トランザクションです。 他の代理トランザクションとは異なり、拡張テストは、1 回のパスで複数回実行できます。 これは、複数の公衆交換電話網 (PSTN) のプールのボイスルーティングなどの動作を確認するときに役立ちます。 これは、1つの拡張テストの複数のインスタンスをウォッチャーノードに追加するだけで構成できます。

他の代理トランザクションをウォッチャーノードに追加するプロセスの詳細については、「 [Lync Server 2013 でウォッチャーノードを管理](lync-server-2013-managing-watcher-nodes.md)する」を参照してください。 Lync Server 管理シェルを使って、ウォッチャーノードから合成トランザクションを削除することができます。

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
<td><p>ユーザーが連絡先リストに含まれていないユーザーを検索できることを確認します。</p></td>
<td><p>既定</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAddressBookWebQuery (ABWQ)</p></td>
<td><p>ユーザーが、連絡先リストに含まれていないユーザーを HTTP 経由で検索できることを確認します。</p></td>
<td><p>既定</p></td>
</tr>
<tr class="odd">
<td><p>テスト-CsIM (IM)</p></td>
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
<td><p>CsAudioConferencingProvider (ACP)</p></td>
<td><p>Lync Server 2013 のオンプレミスバージョンでは使用されませんでした</p></td>
<td><p>拡張。</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPstnPeerToPeerCall (PSTN)</p></td>
<td><p>ユーザーが企業の外部のユーザー (PSTN 番号) と通話できることを確認します。</p></td>
<td><p>既定以外の拡張</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAVConference (AvConference)</p></td>
<td><p>ユーザーが音声/ビデオ会議で作成と参加が可能なことを確認します。</p></td>
<td><p>既定</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</p></td>
<td><p>A/V Edge サーバーが、ピアツーピア通話と電話会議への接続を受け入れることができることを確認します。</p></td>
<td><p>既定以外の場合</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsDataConference (DataConference)</p></td>
<td><p>ユーザーがデータコラボレーション会議 (ホワイトボードや投票などのアクティビティを含むオンライン会議) に参加できることを確認します。</p></td>
<td><p>既定以外の場合</p></td>
</tr>
<tr class="even">
<td><p>Test-CsExumConnectivity (ExumConnectivity)</p></td>
<td><p>ユーザーが Exchange ユニファイドメッセージング (UM) に接続できることを確認します。</p></td>
<td><p>既定以外の場合</p></td>
</tr>
<tr class="odd">
<td><p>テスト-CsGroupIM (GroupIM)</p></td>
<td><p>ユーザーが会議中にインスタント メッセージを送信でき、3 人以上のユーザーとインスタント メッセージでの会話に参加できることを確認します。</p></td>
<td><p>既定</p></td>
</tr>
<tr class="even">
<td><p>Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</p></td>
<td><p>ユーザーが、web アドレスリンク経由でスケジュールされた会議を作成して参加できることを確認します。</p></td>
<td><p>既定以外の場合</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsMCXP2PIM (MCXP2PIM)</p></td>
<td><p>モバイル デバイス ユーザーがインスタント メッセージの登録と送信を実行できることを確認します。</p></td>
<td><p>既定以外の場合</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPersistentChatMessage (PersistentChatMessage)</p></td>
<td><p>ユーザーが常設チャット サービスを使用してメッセージを交換できることを確認します。</p></td>
<td><p>既定以外の場合</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsUnifiedContactStore (UnifiedContactStore)</p></td>
<td><p>統合連絡先ストアを通じてユーザーの連絡先にアクセスできることを確認します。 統合連絡先ストアは、Lync 2013、Outlook、または Outlook Web Access を使用してアクセスできる単一の連絡先セットを管理するための手段を提供します。</p></td>
<td><p>既定以外の場合</p></td>
</tr>
<tr class="even">
<td><p>Test-CsXmppIM (XmppIM)</p></td>
<td><p>インスタントメッセージを XMPP (拡張メッセージングとプレゼンスプロトコル) ゲートウェイ間で送信できることを確認します。</p></td>
<td><p>既定以外の場合</p></td>
</tr>
</tbody>
</table>


System Center Operations Manager を使用するためには、監視ノードをインストールする必要はありません。 これらのノードをインストールしていない場合でも、問題が発生したときに Lync Server 2013 コンポーネントからリアルタイムの通知を受け取ることができます。 (コンポーネントとユーザー管理パックはウォッチャーノードを使用しません)。ただし、アクティブな監視管理パックを使用してエンドツーエンドのシナリオを監視する場合は、監視ノードが必要です。

<div>


> [!NOTE]  
> 管理者は、Operations Manager を使用したりインストールしたりすることなく、代理トランザクションを手動で実行することもできます。 さまざまなテスト用コマンドレットの詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 コマンドレットインデックス</A>」を参照してください。



</div>

展開のサイズによっては、合成トランザクションで大量のコンピューターメモリとプロセッサ時間を使うことがあります。 このため、専用のコンピューターをウォッチャーノードとして使用することをお勧めします。 たとえば、フロントエンドサーバーを監視ノードとして動作するように構成しないでください。 ウォッチャーノードは、次のハードウェア仕様を満たしている必要があります。

<div>


> [!NOTE]  
> 従来の Microsoft Lync Server 2010 ウォッチャーノードは、Lync Server 2013 ウォッチャーノードと同じコンピューター上にある必要があります。 これは、Lync Server 2010 と Lync Server 2013 のコアシステムファイルを同じコンピューターにインストールできないためです。<BR>ただし、lync server 2013 ウォッチャーノードでは、Lync Server 2013 と Lync Server 2010 の両方を同時に監視できます。 既定の代理トランザクションは、両方の製品バージョンでサポートされています。



</div>

Lync Server 2013 ウォッチャーノードは、次の点を確認するために企業内外に展開することができます。

  - <span></span>  
    社内ユーザー用プールへの接続。

  - <span></span>  
    組織外で作業しているリモートユーザーに対する境界ネットワーク経由の接続。

  - <span></span>  
    ブランチ オフィス アプライアンスへの接続。

  - <span></span>  
    企業内および境界ネットワーク経由での Lync Server 2010 への接続。

管理を簡略化するために、エンタープライズの内外でさまざまな認証オプションを利用できます。 詳細については、「 [Lync Server 2013 で代理トランザクションを実行するためのウォッチャーノードの構成](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md)」を参照してください。

ウォッチャーノードとして動作するようにコンピューターを構成するには、System Center Operations Manager をインストールして Lync Server 2013 管理パックをインポートした後、次の手順を完了する必要があります。

Lync Server 2013 コアファイルと System Center agent ファイルをインストールする前に、監視ノードコンピューターが Lync Server 2013 をインストールするための前提条件をすべて満たしていることを確認する必要があります。 また、ウォッチャーノードのコンピューターにも次の項目がインストールされている必要があります。


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
<td><p>ネットワークオペレーティングシステム</p></td>
<td><ul>
<li><p>1 Gbps のネットワークアダプタ 1 Gbps</p></li>
<li><p>Windows Server 2008 R2、Windows Server 2012、または</p>
<p>Windows Server 2012 R2</p></li>
</ul></td>
</tr>
</tbody>
</table>


  - .NET Framework 4.5 の完全バージョン。

  - Windows Identity Foundation。

  - Windows PowerShell 3.0

すべての前提条件が満たされたら、次の方法でウォッチャーノードを構成できます。

  - ウォッチャーノードコンピューターに Lync Server 2013 コアファイルをインストールします。

  - Watcher ノードコンピューターに System Center Operations Manager エージェントをインストールしています。

  - Watchernode 実行可能ファイルを実行します。

  - **CsWatcherNodeConfiguration**コマンドレットを使用して、ウォッチャーノードによって採用されるテストユーザーを構成します。

</div>

<span> </span>

</div>

</div>

</div>

