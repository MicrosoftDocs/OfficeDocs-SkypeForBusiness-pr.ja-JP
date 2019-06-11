---
title: 'Lync Server 2013: トランク構成設定の新しいコレクションを作成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a new collection of trunk configuration settings
ms:assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688054(v=OCS.15)
ms:contentKeyID: 49733647
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4c578fd670661413df0a8fb81cb1ce0316db13f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-collection-of-trunk-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 で、トランク構成設定の新しいコレクションを作成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

SIP トランク構成設定は、仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイ、IP パブリックブランチ交換 (PBX)、またはサービスプロバイダのセッションボーダーコントローラー (SBC) 間の関係と機能を定義します。 たとえば、次の設定ができます。

  - トランクでメディア バイパスを有効化するか。

  - リアルタイム伝送制御プロトコル (RTCP) パケットを送信する条件。

  - 各トランクで、セキュリティで保護されたリアルタイムプロトコル (SRTP) 暗号化が必要かどうかを示します。

Microsoft Lync Server 2013 をインストールすると、SIP トランク構成設定のグローバルコレクションが作成されます。 また、管理者はサイト スコープまたはサービス スコープ (PSTN ゲートウェイ サービスの場合のみ) でカスタム設定のコレクションを作成することができます。

Lync Server コントロールパネルを使用して SIP トランクの構成設定を作成する場合は、次のオプションを利用できます。


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
<td><p>ID</p></td>
<td><p>コレクションの一意の識別子。このプロパティは読み取り専用です。トランク構成設定のコレクションの Identity は変更できません。</p></td>
</tr>
<tr class="even">
<td><p>説明</p></td>
<td><p>説明</p></td>
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
<td><p>仲介サーバーと、サービス プロバイダーの PSTN ゲートウェイ、IP-PBX、または SBC 間のメディア トラフィックを保護するためのサポート レベルを示します。 メディア バイパスの場合、この値はメディア構成の EncryptionLevel 設定と互換性を持つ必要があります。 メディア構成は、 <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">CsMediaConfiguration</a>コマンドレットと<a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">CsMediaConfiguration</a>コマンドレットを使用して設定されます。</p>
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
<p>[<strong>サードパーティ通話コントロールを使用する参照を有効にする</strong>] に設定すると、3PCC プロトコルを使用して転送される通話がホストされたサイトをバイパスできるようにすることを示します。 3pcc はサードパーティコントロール&quot;&quot;とも呼ばれ、サードパーティが1組の発信者に接続するために使用される場合 (たとえば、ユーザー a からメンバー B に電話をかけているオペレーターなど) に発生します。</p></td>
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
<td><p>通話履歴の情報をトランク経由で転送するかどうかを指定します。</p></td>
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
<td><p>N/A</p></td>
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
<td><p>N/A</p></td>
<td><p>変換ルールの臨時テストを行うために使用できる電話番号です。</p></td>
</tr>
<tr class="odd">
<td><p>発信者番号</p></td>
<td><p>N/A</p></td>
<td><p>テストする電話番号が発信者の電話番号であることを示します。</p></td>
</tr>
<tr class="even">
<td><p>着信者番号</p></td>
<td><p>該当なし</p></td>
<td><p>テストする電話番号が着信者の電話番号であることを示します。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Lync Server の Set-cstrunkconfiguration コマンドレットでは、Lync Server コントロールパネルに表示されない追加のプロパティがサポートされています。 詳細については、 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">set-cstrunkconfiguration</A>コマンドレットのヘルプトピックを参照してください。



</div>

<div>

## <a name="to-create-new-trunk-configuration-settings-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用して新しいトランク構成設定を作成するには

1.  Lync Server コントロールパネルで、[**音声ルーティング**] をクリックし、[ **Trunk 構成**] をクリックします。

2.  [**トランク構成**] タブで [**新規作成**] をクリックします。新しい設定をサイト スコープで作成する場合は [**サイト トランク**] をクリックし、サービス スコープで作成する場合は [**プール トランク**] をクリックします。

3.  [**サイトの選択**] または [**サービスの選択**] ダイアログ ボックスで (表示されるダイアログ ボックスは、サイト スコープとサービス スコープのどちらの設定を作成するかによって異なります)、新しい構成設定の場所を選択し、[**OK**] をクリックします。ダイアログ ボックスが空白の場合は、新しい設定を作成する場所がないことを意味します。たとえば、[**サイトの選択**] ダイアログ ボックスが空白の場合、すべてのサイトにトランク構成サイトのコレクションが既に割り当てられており、各サイト (および各サービス) でホストできるのは該当のコレクションだけであることを示しています。この場合、既存のコレクションを削除して新しいコレクションを作成することも、既存のコレクションを変更することもできます。

4.  [**新規トランク構成**] ダイアログで、適切な選択を行って [**OK**] をクリックします。

5.  コレクションの [**状態**] プロパティが、[**コミットされていません**] に変わります。変更をコミットし、コレクションを削除するには、[**コミット**] をクリックした後、[**すべてコミット**] をクリックします。

6.  [**コミットされていない音声構成設定**] ダイアログ ボックスで、[**OK**] をクリックします。

7.  [ **Microsoft Lync Server 2013 コントロールパネル**] ダイアログボックスで、[ **OK**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

