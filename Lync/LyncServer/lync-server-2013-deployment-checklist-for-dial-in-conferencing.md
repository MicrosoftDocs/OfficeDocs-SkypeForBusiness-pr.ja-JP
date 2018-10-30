---
title: 'Lync Server 2013: ダイヤルイン会議の展開チェックリスト'
TOCTitle: ダイヤルイン会議の展開チェックリスト
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48272983
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のダイヤルイン会議の展開チェックリスト

 

_**トピックの最終更新日:** 2015-03-09_

ダイヤルイン会議に必要なコンポーネントは、会議ワークロードを展開すると展開されます。ダイヤルイン会議を構成する前に、 エンタープライズ VoIP または 仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイのいずれかを展開する必要があります。

ユーザーが PSTN からダイヤルインして音声ビデオ会議に参加するには、次の表のすべての手順を実行する必要があります。


> [!NOTE]
> Office Communications Server 2007 R2 から移行している場合は、ダイヤルイン会議を展開する前に、 Office Communications Server 2007 R2 環境に最新の更新プログラムを適用する必要があります。


### ダイヤルイン会議の展開プロセス

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>フェーズ</th>
<th>ステップ</th>
<th>アクセス許可</th>
<th>「展開」のドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>仲介サーバーや PSTN ゲートウェイなどの会議ワークロードが含まれるトポロジを作成し、フロント エンド プールまたは Standard Edition サーバーを展開する</strong></p></td>
<td><ol>
<li><p>トポロジ ビルダーを実行してトポロジを構成します。トポロジの構成時に、ダイヤルイン会議オプションを選択します。</p></li>
<li><p>トポロジを公開し、 フロント エンド プールまたは Standard Edition サーバーを展開します。</p></li>
<li><p>必要に応じて、スタンドアロンの 仲介サーバーを作成し、PSTN ゲートウェイに関連付けます。</p>

> [!NOTE]
> この手順は、エンタープライズ VoIP を展開せず、仲介サーバー を Enterprise Editionフロント エンド サーバー または Standard Edition サーバー と併置しない場合にのみ必要です。エンタープライズ VoIP を展開する場合、仲介サーバー および PSTN ゲートウェイを エンタープライズ VoIP 展開の一部としてインストールし、構成します。仲介サーバー を併置する場合、仲介サーバー を フロント エンド プール または Standard Edition サーバー 展開の一部としてインストールし、構成します。

</div></li>
</ol></td>
<td><p>Domain Admins</p>
<p>RTCUniversalServerAdmins</p>
<p>管理者</p></td>
<td><ul>
<li><p><a href="lync-server-2013-deploying-lync-server.md">Lync Server 2013 の展開</a></p></li>
<li><p>スタンドアロンの 仲介サーバー プールを作成するには: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Lync Server 2013 での仲介サーバーの展開とピアの定義</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>ダイヤル プランを構成する</strong></p></td>
<td><p>ダイヤル プランは、電話の認証と通話のルーティングのために、特定の場所からダイヤルされた電話番号を 1 つの標準 (E.164) 形式に変換する、電話番号の正規化ルールのセットです。同一の電話番号であっても異なる場所からダイヤルされる場合は、それぞれのダイヤル プランに基づいて、各場所に応じた別々の E.164 番号に変換できます。エンタープライズ VoIP を展開する場合、ダイヤル プランをその展開の一部として設定します。また、そのダイヤル プランがダイヤルイン会議にも対応するようにする必要があります。エンタープライズ VoIP を展開しない場合、ダイヤルイン会議のためにダイヤル プランを設定する必要があります。</p>
<p>Lync Server 2013 コントロール パネルまたは Lync Server 管理シェルを使用して、次のようにダイヤル プランを設定します。</p>
<ol>
<li><p>ダイヤルイン アクセスの電話番号をルーティングするための、1 つまたは複数のダイヤル プランを作成します。</p></li>
<li><p>各プールに既定のダイヤル プランを割り当てます。ダイヤル プランを適用する地理的場所に [<strong>ダイヤルイン会議の地域</strong>] を設定します。地域がダイヤルイン アクセス番号が設定されたダイヤル プランに関連付けられます。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Lync Server 2013 でのダイヤルイン会議のダイヤル プランの構成</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>ダイヤル プランが地域に割り当てられていることを確認する</strong></p></td>
<td><p><strong>Get-CsDialPlan</strong> コマンドレットと <strong>Set-CsDialPlan</strong> コマンドレットを実行して、すべてのダイヤル プランに地域が割り当てられていることを確認します。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Lync Server 2013 で、ダイヤル プランに地域が割り当てられていることの確認</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(オプション) ユーザーの暗証番号 (PIN) 要件を確認または変更する</strong></p></td>
<td><p>Lync Server 2013 コントロール パネルまたは Lync Server 管理シェルを使用して、会議の [<strong>PIN ポリシー</strong>] を表示または変更します。最小 PIN サイズ、最大ログオン試行回数、PIN の有効期限、およびよくあるパターンを許可するかどうかを指定できます。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(オプション) Lync Server 2013 での PIN ポリシー設定の確認</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>ダイヤルイン会議をサポートするように会議ポリシーを構成する</strong></p></td>
<td><p>Lync Server 2013 コントロール パネルまたは Lync Server 管理シェルを使用して、[<strong>会議ポリシー</strong>] 設定を構成します。次のことを指定します。</p>
<ul>
<li><p>PSTN 会議ダイヤルインを有効にするかどうか。</p></li>
<li><p>ユーザーが匿名参加者を招待できるようにするかどうか。</p></li>
<li><p>認証されていないユーザーがダイヤルアウト番号を使用して会議に参加できるようにするかどうか。会議サーバーはダイヤルアウト番号を使用してユーザーを呼び出し、ユーザーはその電話に応答し、会議に参加します。</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Lync Server 2013 でダイヤルインの会議ポリシーを構成する</a></p></td>
</tr>
<tr class="even">
<td><p><strong>ダイヤルイン アクセス番号を構成する</strong></p></td>
<td><p>Lync Server 2013 コントロール パネルまたは Lync Server 管理シェルを使用して、ユーザーが会議にダイヤルインするために呼び出すダイヤルイン アクセス番号を設定し、そのアクセス番号を適切なダイヤル プランに関連付ける地域を指定します。開催者のダイヤル プランで指定されている地域の最初の 3 つのアクセス番号が会議開催通知に含まれます。すべてのアクセス番号が ダイヤルイン会議の設定ページに表示されます。</p>

> [!NOTE]
> ダイヤルイン アクセス番号を作成したら、 <strong>Set-CsDialInConferencingAccessNumber</strong> コマンドレットを使用して、ユーザーが正しいアクセス番号を容易に確認できるよう、 Active Directory の連絡先オブジェクトの表示名を変更できます。

</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Lync Server 2013 でのダイヤルイン会議アクセス番号の構成</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>(オプション) ダイヤルイン会議の設定の検証</strong></p></td>
<td><p><strong>Get-CsDialinConferencingAccessNumber</strong> コマンドレットを使用して、地域が割り当てられていないすべてのアクセス番号に関して使用されるダイヤルイン会議の地域が設定されたダイヤル プランを検索します。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p>
<p>CsHelpDesk</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(オプション) Lync Server 2013 でのダイヤルイン会議の設定の検証</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(オプション) DTMF コマンドの主要なマッピングを変更する</strong></p></td>
<td><p><strong>Set-CsDialinConferencingDtmfConfiguration</strong> コマンドレットを使用して、デュアルトーン多重周波数 (DTMF) コマンドで使用される、参加者が会議設定 (ミュートとミュート解除、ロックとロック解除など) を制御するために使用するキーを変更します。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(オプション) Lync Server 2013 で DTMF コマンドの主要なマッピングを変更する</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>(オプション) 会議の参加時と退席時のアナウンス動作を変更する</strong></p></td>
<td><p><strong>Set-CsDialinConferencingConfiguration</strong> を使用して、参加者が会議に参加および退席する際のアナウンス動作を変更します。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(オプション) Lync Server 2013 での会議への入退出のアナウンスの有効化および無効化</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(オプション) ダイヤルイン会議の検証</strong></p></td>
<td><p><strong>Test-CsDialInConferencing</strong> コマンドレットを使用して、指定のプールのアクセス番号が正しく機能するかどうかをテストします。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(オプション) Lync Server 2013 でのダイヤルイン会議の検証</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Lync 2013 用オンライン ミーティング アドインを展開する</strong></p></td>
<td><p>ダイヤルイン会議をサポートする会議をユーザーがスケジュールできるよう、 Lync 2013 用オンライン ミーティング アドインを展開します。 Lync 2013 用オンライン ミーティング アドインは、 Lync 2013 をインストールすると自動的にインストールされます。</p></td>
<td><p>管理者</p></td>
<td><p><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Lync 2013 用オンライン会議アドインの展開</a></p></td>
</tr>
<tr class="even">
<td><p><strong>ユーザー アカウント設定の構成</strong></p></td>
<td><p>Lync Server 2013 コントロール パネルまたは Lync Server 管理シェルを使用して、テレフォニーの [<strong>回線 URI</strong>] を一意の正規化された電話番号 (たとえば、tel:+14255550200) として構成します。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsAdministrator</p>
<p>CsUserAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-user-account-settings.md">Lync Server 2013 でのユーザー アカウント設定の構成</a></p></td>
</tr>
<tr class="odd">
<td><p>(推奨) 会議ディレクトリを構成する</p></td>
<td><p><strong>New-CsConferenceDirectory</strong> コマンドレットを使用して、プールに含まれる 999 ユーザーごとに会議ディレクトリを 1 つ作成します。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013 でのダイヤルイン会議の要件</a> <a href="recommended-create-conference-directories.md">(推奨) 会議ディレクトリを作成する</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(オプション) ユーザーにダイヤルイン会議を案内して最初の PIN を設定する</strong></p></td>
<td><p><strong>Set-CsPinSendCAWelcomeMail</strong> スクリプトを使用して、ユーザーの最初の PIN を設定し、最初の PIN および ダイヤルイン会議の設定ページへのリンクが含まれた案内メールを送信します。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(オプション) Lync Server 2013 でのダイヤルイン会議へのユーザーの受け入れ</a></p></td>
</tr>
</tbody>
</table>

