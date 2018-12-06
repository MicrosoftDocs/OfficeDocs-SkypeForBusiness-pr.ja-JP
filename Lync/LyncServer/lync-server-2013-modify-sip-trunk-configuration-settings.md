---
title: SIP トランク構成設定の変更
TOCTitle: SIP トランク構成設定の変更
ms:assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688104(v=OCS.15)
ms:contentKeyID: 49887014
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# SIP トランク構成設定の変更

 

_**トピックの最終更新日:** 2015-03-09_

SIP トランクの構成設定では、仲介サーバーと、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、またはサービス プロバイダーのセッション境界コントローラー (SBC) との間の関係および機能が定義されています。これらの設定は、以下を指定するために使用されます。

  - トランクでメディア バイパスを有効にする必要があるかどうか。

  - リアルタイム転送制御プロトコル (RTCP) パケットが送信される条件。

  - 各トランクでセキュア リアルタイム プロトコル (SRTP) 暗号化が必要かどうか。

Microsoft Lync Server 2013 をインストールすると、SIP トランクの構成設定のグローバル コレクションが自動的に作成されます。さらに、管理者はサイト スコープまたはサービス スコープ (PSTN ゲートウェイ サービスの場合のみ) でカスタム設定コレクションを作成できます。これらのコレクションはすべて、後で Lync Server コントロール パネルまたは Windows PowerShell を使用して変更できます。

Lync Server コントロール パネルを使用して SIP トランクの構成設定を変更するときは、次のオプションを使用できます。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>UI 設定</th>
<th>PowerShell のパラメーター</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>名前</p></td>
<td><p>Identity</p></td>
<td><p>コレクションの一意の識別子。このプロパティは読み取り専用です。トランク構成設定のコレクションの Identity は変更できません。</p></td>
</tr>
<tr class="even">
<td><p>説明</p></td>
<td><p>Description</p></td>
<td><p>管理者が、設定に関する追加情報を格納できます (たとえば、トランク構成の目的)。</p></td>
</tr>
<tr class="odd">
<td><p>サポートされる最大初期ダイアログの数</p></td>
<td><p>MaxEarlyDialogs</p></td>
<td><p>サービス プロバイダーの PSTN ゲートウェイ、IP-PBX、または SBC が、仲介サーバーに送信した INVITE に対して受信できる分岐応答の最大数です。</p></td>
</tr>
<tr class="even">
<td><p>暗号化サポート レベル</p></td>
<td><p>SRTPMode</p></td>
<td><p>仲介サーバーと、サービス プロバイダーの PSTN ゲートウェイ、IP-PBX、または SBC 間のメディア トラフィックを保護するためのサポート レベルを示します。メディア バイパスの場合、この値はメディア構成の EncryptionLevel 設定と互換性を持つ必要があります。メディア構成は、<a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> コマンドレットおよび <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> コマンドレットを使用して設定します。</p>
<p>有効な値は次のとおりです。</p>
<ul>
<li><p>Required: SRTP 暗号化を使用する必要があります。</p></li>
<li><p>Optional: ゲートウェイでサポートされている場合は、SRTP が使用されます。</p></li>
<li><p>Not Supported: SRTP 暗号化がサポートされていないので、使用されません。</p></li>
</ul>
<p>SRTPMode は、ゲートウェイがトランスポート層セキュリティ (TLS) プロトコルを使用するよう構成されている場合にのみ使用されます。ゲートウェイがトランスポートとして伝送制御プロトコル (TCP) を使用するように構成されている場合は、SRTPMode は内部で Not Supported に設定されます。</p></td>
</tr>
<tr class="odd">
<td><p>サポートの参照</p></td>
<td><p>Enable3pccRefer</p>
<p>EnableReferSupport</p></td>
<td><p>[<strong>ゲートウェイへの参照の送信を有効にする</strong>] に設定した場合、トランクが仲介サーバーからの REFER 要求の受信をサポートすることを示します。</p>
<p>[<strong>サードパーティ通話コントロールを使用する参照を有効にする</strong>] に設定すると、3PCC プロトコルを使用して転送される通話がホストされたサイトをバイパスできるようにすることを示します。3PCC は、「三者間通話コントロール」とも呼ばれ、第三者を使用して二人の通話者を接続するとき (たとえば、オペレーターが人物 A から人物 B への通話を接続するとき) に使用します。</p></td>
</tr>
<tr class="even">
<td><p>メディアのバイパスを有効にする</p></td>
<td><p>EnableBypass</p></td>
<td><p>メディア バイパスがこのトランクに対して有効かどうかを示します。メディア バイパスは、[<strong>集中メディア処理</strong>] も有効になっている場合にのみ有効にできます。</p></td>
</tr>
<tr class="odd">
<td><p>集中メディア処理</p></td>
<td><p>ConcentratedTopology</p></td>
<td><p>既知のメディア終端ポイントがあるかどうかを示します (既知のメディア終端ポイントの例として、メディア終端が信号終端と同じ IP を持つ PSTN ゲートウェイがあります)。</p></td>
</tr>
<tr class="even">
<td><p>RTP ラッチを有効にする</p></td>
<td><p>EnableRTPLatching</p></td>
<td><p>SIP トランクが RTP ラッチをサポートするかどうかを示します。RTP ラッチは、NAT (ネットワーク アドレス変換) 装置またはファイアウォールを経由した RTP/RTCP 接続を可能にする技術です。</p></td>
</tr>
<tr class="odd">
<td><p>着信転送履歴を有効にする</p></td>
<td><p>ForwardCallHistory</p></td>
<td><p>通話履歴の情報をトランク経由で転送するかどうかを示します。</p></td>
</tr>
<tr class="even">
<td><p>P-Asserted-Identity データの転送を有効にする</p></td>
<td><p>ForwardPAI</p></td>
<td><p>P-Asserted-Identity (PAI) ヘッダーを通話とともに転送するかどうかを示します。PAI ヘッダーがあれば、発信者 ID を確認できます。</p></td>
</tr>
<tr class="odd">
<td><p>送信ルーティング フェールオーバー タイマーを有効にする</p></td>
<td><p>EnableFastFailoverTimer</p></td>
<td><p>発信通話が 10 秒以内にゲートウェイによって応答されない場合に次に使用できるトランクにルーティングするかどうかを示します。他にトランクがない場合は、通話は自動的に破棄されます。ネットワークおよびゲートウェイの応答が遅い環境の場合、通話が不必要に破棄されるようになる可能性があります。</p></td>
</tr>
<tr class="even">
<td><p>関連付けられている PSTN 使用法</p></td>
<td><p>PSTNUsages</p></td>
<td><p>トランクに割り当てられた PSTN 使用法のコレクションです。</p></td>
</tr>
<tr class="odd">
<td><p>テストする変換後の番号</p></td>
<td><p>該当なし</p></td>
<td><p>トランクの構成設定の臨時テストを行うために使用できる電話番号です。</p></td>
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
<td><p>変換ルールの臨時テストを行うために使用できる電話番号です。</p></td>
</tr>
<tr class="odd">
<td><p>発信者番号</p></td>
<td><p>該当なし</p></td>
<td><p>テストする電話番号が発信者の電話番号であることを示します。</p></td>
</tr>
<tr class="even">
<td><p>着信者番号</p></td>
<td><p>該当なし</p></td>
<td><p>テストする電話番号が着信者の電話番号であることを示します。</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> Lync Server の CsTrunkConfiguration コマンドレットは、Lync Server コントロール パネルに表示されていない他のプロパティをサポートします。詳細については、<a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsTrunkConfiguration">Set-CsTrunkConfiguration</a> コマンドレットのヘルプ トピックを参照してください。


## Lync Server コントロール パネルを使用した SIP トランク構成設定の変更

1.  Lync Server コントロール パネルで、\[**音声のルーティング**\] をクリックし、\[**トランク構成**\] をクリックします。

2.  \[**トランク構成**\] タブで、変更するトランク構成の設定をダブルクリックします。編集できる設定のコレクションは一度に 1 つだけです。複数のコレクションで同じ変更を行う場合は、Windows PowerShell を使用してください。

3.  \[**トランク構成の編集**\] ダイアログ ボックスで、適切な選択を行った後、\[**OK**\] をクリックします。

4.  コレクションの \[**状態**\] プロパティが、\[**コミットされていません**\] に変わります。変更をコミットし、コレクションを削除するには、\[**コミット**\] をクリックした後、\[**すべてコミット**\] をクリックします。

5.  \[**コミットされていない音声構成設定**\] ダイアログ ボックスで、\[**OK**\] をクリックします。

6.  \[**Microsoft Lync Server 2013 コントロール パネル**\] ダイアログ ボックスで、\[**OK**\] をクリックします。

