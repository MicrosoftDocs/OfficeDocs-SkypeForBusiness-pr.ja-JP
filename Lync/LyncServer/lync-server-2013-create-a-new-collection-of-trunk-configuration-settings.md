---
title: トランク構成設定の新しいコレクションの作成
TOCTitle: トランク構成設定の新しいコレクションの作成
ms:assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688054(v=OCS.15)
ms:contentKeyID: 49886953
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# トランク構成設定の新しいコレクションの作成

 

_**トピックの最終更新日:** 2015-03-09_

SIP トランク構成設定では、仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイ、IP 構内交換機 (PBX)、またはサービス プロバイダーのセッション境界コントローラー (SBC) との間の関係と機能を定義します。これらの設定では以下を指定します。

  - トランクでメディアのバイパスを有効にする必要があるかどうか

  - リアルタイム転送制御プロトコル (RTCP) パケットを送信する条件

  - 各トランクでセキュア リアルタイム プロトコル (SRTP) 暗号化が必要かどうか

Microsoft Lync Server 2013 をインストールすると、SIP トランク構成設定のグローバル コレクションが作成されます。また、管理者は、サイト スコープまたはサービス スコープ (PSTN ゲートウェイ サービスの場合のみ) でカスタム設定コレクションを作成することもできます。

Lync Server コントロール パネルを使用して SIP トランク構成設定を作成する場合、次のオプションが用意されています。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>UI 設定</th>
<th>PowerShell パラメーター</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>名前</p></td>
<td><p>Identity</p></td>
<td><p>コレクションの一意の識別子です。このプロパティは読み取り専用です。トランク構成設定のコレクション ID を変更することはできません。</p></td>
</tr>
<tr class="even">
<td><p>説明</p></td>
<td><p>Description</p></td>
<td><p>管理者は、設定に関する追加情報 (トランク構成の目的など) を格納できます。</p></td>
</tr>
<tr class="odd">
<td><p>サポートされる最大初期ダイアログの数</p></td>
<td><p>MaxEarlyDialogs</p></td>
<td><p>PSTN ゲートウェイ、IP-PBX、またはサービス プロバイダーの SBC が、仲介サーバーに送信した INVITE に対して受信できる分岐応答の最大数です。</p></td>
</tr>
<tr class="even">
<td><p>暗号化サポート レベル</p></td>
<td><p>SRTPMode</p></td>
<td><p>仲介サーバーと PSTN ゲートウェイ、IP-PBX、またはサービス プロバイダーの SBC 間でのメディア トラフィックの保護のサポート レベルを指定します。メディア バイパスの場合、この値はメディア構成の EncryptionLevel 設定と互換性があることが必要です。メディア構成は、<a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> コマンドレットと <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> コマンドレットを使用して設定します。</p>
<p>有効な値は次のとおりです。</p>
<ul>
<li><p>Required: SRTP 暗号化を使用する必要があります。</p></li>
<li><p>Optional: ゲートウェイでサポートされている場合は、SRTP が使用されます。</p></li>
<li><p>NotSupported: SRTP 暗号化はサポートされていないため使用されません。</p></li>
</ul>
<p>SRTPMode は、ゲートウェイがトランスポート層セキュリティ (TLS) を使用するよう構成されている場合にのみ使用されます。ゲートウェイがトランスポートとして伝送制御プロトコル (TCP) を使用するように構成されている場合は、SRTPMode が内部で NotSupported に設定されます。</p></td>
</tr>
<tr class="odd">
<td><p>サポートの参照</p></td>
<td><p>Enable3pccRefer</p>
<p>EnableReferSupport</p></td>
<td><p>[<strong>ゲートウェイへの参照の送信を有効にする</strong>] に設定した場合は、トランクが仲介サーバーからの参照要求の受信をサポートすることを示します。</p>
<p>[<strong>サードパーティ通話コントロールを使用する参照を有効にする</strong>] に設定した場合は、3PCC プロトコルを使用して、転送された通話が、ホストされたサイトをバイパスできるようにすることを示します。3PCC は、&quot;三者間通話コントロール&quot; とも呼ばれ、第三者を使って二人の通話者を接続する場合 (オペレーターが人物 A から人物 B への通話を接続する場合など) に使用します。</p></td>
</tr>
<tr class="even">
<td><p>メディアのバイパスを有効にする</p></td>
<td><p>EnableBypass</p></td>
<td><p>このトランクのメディア バイパスを有効にするかどうかを指定します。メディアのバイパスを有効にできるのは、[<strong>集中メディア処理</strong>] が有効になっている場合に限られます。</p></td>
</tr>
<tr class="odd">
<td><p>集中メディア処理</p></td>
<td><p>ConcentratedTopology</p></td>
<td><p>既知のメディア終端ポイントがあるかどうかを指定します (既知のメディア終端ポイントの例として、メディア終端が信号終端と同じ IP を持つ PSTN ゲートウェイがあります)。</p></td>
</tr>
<tr class="even">
<td><p>RTP ラッチを有効にする</p></td>
<td><p>EnableRTPLatching</p></td>
<td><p>SIP トランクが RTP ラッチをサポートするかどうかを指定します。RTP ラッチは、NAT (ネットワーク アドレス変換) 装置またはファイアウォールを介した RTP/RTCP 接続を可能にする技術です。</p></td>
</tr>
<tr class="odd">
<td><p>着信転送履歴を有効にする</p></td>
<td><p>ForwardCallHistory</p></td>
<td><p>通話履歴の情報をトランク経由で転送するかどうかを指定します。</p></td>
</tr>
<tr class="even">
<td><p>P-Asserted-Identity データの転送を有効にする</p></td>
<td><p>ForwardPAI</p></td>
<td><p>P-Asserted-Identity (PAI) ヘッダーを通話と共に転送するかどうかを指定します。PAI ヘッダーがあれば、発信者 ID を確認できます。</p></td>
</tr>
<tr class="odd">
<td><p>送信ルーティング フェールオーバー タイマーを有効にする</p></td>
<td><p>EnableFastFailoverTimer</p></td>
<td><p>ゲートウェイから 10 秒以内に応答がない発信通話を使用可能な次のトランクにルーティングするかどうかを指定します。他のトランクがない場合、その通話は自動的に破棄されます。低速ネットワークとゲートウェイの応答を使用する組織では、通話が不必要に破棄される可能性があります。</p></td>
</tr>
<tr class="even">
<td><p>関連付けられている PSTN 使用法</p></td>
<td><p>PSTNUsages</p></td>
<td><p>トランクに割り当てられた PSTN 使用法のコレクションです。</p></td>
</tr>
<tr class="odd">
<td><p>テストする変換後の番号</p></td>
<td><p>該当なし</p></td>
<td><p>トランク構成設定のアドホック テストに使用できる電話番号です。</p></td>
</tr>
<tr class="even">
<td><p>関連付けられている変換ルール</p></td>
<td><p>OutboundTranslationRulesList</p></td>
<td><p>発信ルーティングによって処理される通話 (PBX または PSTN の宛先にルーティングされる通話) に適用される、電話番号変換ルールのコレクションです。</p></td>
</tr>
<tr class="odd">
<td><p>着信者番号の変換ルール</p></td>
<td><p>OutboundCallingNumberTranslationRulesList</p></td>
<td><p>トランクに割り当てられた発信電話番号の変換ルールのコレクションです。</p></td>
</tr>
<tr class="even">
<td><p>テストする電話番号</p></td>
<td><p>該当なし</p></td>
<td><p>変換ルールのアドホック テストに使用できる電話番号です。</p></td>
</tr>
<tr class="odd">
<td><p>発信者番号</p></td>
<td><p>該当なし</p></td>
<td><p>テストする電話番号が発信者の電話番号であることを指定します。</p></td>
</tr>
<tr class="even">
<td><p>着信者番号</p></td>
<td><p>該当なし</p></td>
<td><p>テストする電話番号が相手先の電話番号であることを指定します。</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> Lync Server の CsTrunkConfiguration コマンドレットは、Lync Server コントロール パネルに表示されないその他のプロパティをサポートします。詳細については、<a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrunkConfiguration">New-CsTrunkConfiguration</a> コマンドレットに関するヘルプ トピックを参照してください。


## Lync Server コントロール パネルを使用した新しいトランク構成設定の作成

1.  Lync Server コントロール パネルで、\[**音声のルーティング**\] をクリックし、\[**トランク構成**\] をクリックします。

2.  \[**トランク構成**\] タブで \[**新規作成**\] をクリックします。新しい設定をサイト スコープで作成する場合は \[**サイト トランク**\] をクリックし、サービス スコープで作成する場合は \[**プール トランク**\] をクリックします。

3.  \[**サイトの選択**\] または \[**サービスの選択**\] ダイアログ ボックスで (表示されるダイアログ ボックスは、サイト スコープとサービス スコープのどちらの設定を作成するかによって異なります)、新しい構成設定の場所を選択し、\[**OK**\] をクリックします。ダイアログ ボックスが空白の場合は、新しい設定を作成する場所がないことを意味します。たとえば、\[**サイトの選択**\] ダイアログ ボックスが空白の場合、すべてのサイトにトランク構成サイトのコレクションが既に割り当てられており、各サイト (および各サービス) でホストできるのは該当のコレクションだけであることを示しています。この場合、既存のコレクションを削除して新しいコレクションを作成することも、既存のコレクションを変更することもできます。

4.  \[**新規トランク構成**\] ダイアログで、適切な選択を行って \[**OK**\] をクリックします。

5.  コレクションの \[**状態**\] プロパティが \[**コミットされていません**\] に更新されます。変更をコミットし、コレクションを削除するには、\[**コミット**\]、\[**すべてコミット**\] の順にクリックします。

6.  \[**コミットされていない音声構成設定**\] ダイアログ ボックスで、\[**OK**\] をクリックします。

7.  \[**Microsoft Lync Server 2013 Control Panel**\] ダイアログ ボックスで、\[**OK**\] をクリックします。

