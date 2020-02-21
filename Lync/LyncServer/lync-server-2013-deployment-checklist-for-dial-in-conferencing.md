---
title: Lync Server 2013 ダイヤルイン会議の展開チェックリスト
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 084686c33482e4828378db76c2a5ca1c834bacf3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205853"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a>Lync Server 2013 でのダイヤルイン会議の展開チェックリスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-10-03_

ダイヤルイン会議に必要なコンポーネントは、会議ワークロードを展開すると展開されます。 ダイヤルイン会議を構成する前に、エンタープライズ Voip または仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイのどちらかを展開する必要があります。

ユーザーが PSTN からダイヤルインして音声ビデオ会議に参加するには、次の表のすべての手順を実行する必要があります。

<div>


> [!NOTE]  
> Office Communications Server 2007 R2 から移行する場合は、ダイヤルイン会議を展開する前に、Office Communications Server 2007 R2 環境に最新の更新プログラムを適用する必要があります。



</div>

### <a name="dial-in-conferencing-deployment-process"></a>ダイヤルイン会議の展開プロセス

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
<th>手順</th>
<th>アクセス許可</th>
<th>展開のドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>仲介サーバーと PSTN ゲートウェイを含む、会議ワークロードを含むトポロジを作成し、フロントエンドプールまたは Standard Edition サーバーを展開します。</strong></p></td>
<td><ol>
<li><p>トポロジビルダーを実行してトポロジを構成します。 トポロジの構成時に、ダイヤルイン会議オプションを選択します。</p></li>
<li><p>トポロジを公開し、フロントエンドプールまたは Standard Edition サーバーを展開します。</p></li>
<li><p>必要に応じて、スタンドアロンの仲介サーバーを作成し、PSTN ゲートウェイに関連付けます。</p>
<div>

> [!NOTE]  
> この手順は、エンタープライズ Voip を展開せず、仲介サーバーをエンタープライズ EditionFront エンドサーバーまたは Standard Edition サーバーと併置しない場合にのみ必要です。 エンタープライズ Voip を展開する場合は、エンタープライズ Voip 展開の一部として、仲介サーバーと PSTN ゲートウェイをインストールして構成します。 仲介サーバーを併置する場合は、仲介サーバーをフロントエンドプールまたは Standard Edition サーバー展開の一部としてインストールして構成します。


</div></li>
</ol></td>
<td><p>Domain Admins</p>
<p>RTCUniversalServerAdmins</p>
<p>管理者</p></td>
<td><ul>
<li><p><a href="lync-server-2013-deploying-lync-server.md">Lync Server 2013 の展開 </a></p></li>
<li><p>スタンドアロンの仲介サーバープールを作成するには:<a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">仲介サーバーの展開と Lync server 2013 でのピアの定義</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>ダイヤル プランを構成する</strong></p></td>
<td><p>ダイヤルプランとは、電話の承認と通話のルーティングを目的として、特定の場所から1つの標準 (e.164) 形式にダイヤルする電話番号を変換する一連の電話番号正規化ルールのことです。 異なる場所からダイヤルされた同じ電話番号は、それぞれの場所に応じて、それぞれのダイヤルプランに基づいて異なる e.164 番号に解決できます。 エンタープライズ Voip を展開する場合は、ダイヤルプランをその展開の一部として設定し、ダイヤルプランがダイヤルイン会議にも対応していることを確認する必要があります。 エンタープライズ Voip を展開しない場合は、ダイヤルイン会議のダイヤルプランを設定する必要があります。</p>
<p>Lync Server 2013 コントロールパネルまたは Lync Server 管理シェルを使用して、ダイヤルプランを次のように設定します。</p>
<ol>
<li><p>ダイヤルイン アクセスの電話番号をルーティングするための、1 つまたは複数のダイヤル プランを作成します。</p></li>
<li><p>各プールに既定のダイヤル プランを割り当てます。 ダイヤル プランを適用する地理的場所に [<strong>ダイヤルイン会議の地域</strong>] を設定します。 地域がダイヤルイン アクセス番号が設定されたダイヤル プランに関連付けられます。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Lync Server 2013 でダイヤルイン会議のダイヤルプランを構成する</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>ダイヤルプランに地域が割り当てられていることを確認する</strong></p></td>
<td><p><strong>Get-csdialplan</strong>および<strong>get-csdialplan</strong>コマンドレットを実行して、すべてのダイヤルプランに地域が割り当てられていることを確認します。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">ダイヤルプラン Lync Server 2013 に地域が割り当てられていることを確認する</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(オプション) ユーザーの暗証番号 (PIN) 要件を確認または変更する</strong></p></td>
<td><p>Lync Server 2013 コントロールパネルまたは Lync Server 管理シェルを使用して、会議<strong>PIN ポリシー</strong>を表示または変更します。 最小 PIN サイズ、最大ログオン試行回数、PIN の有効期限、およびよくあるパターンを許可するかどうかを指定できます。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-pin-policy-settings.md">オプションLync Server 2013 での PIN ポリシー設定の確認</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>ダイヤルイン会議をサポートするように会議ポリシーを構成する</strong></p></td>
<td><p>Lync Server 2013 コントロールパネルまたは Lync Server 管理シェルを使用して、<strong>会議ポリシー</strong>の設定を構成します。 次のことを指定します。</p>
<ul>
<li><p>PSTN 会議ダイヤルインを有効にするかどうか。</p></li>
<li><p>ユーザーが匿名参加者を招待できるようにするかどうか。</p></li>
<li><p>認証されていないユーザーがダイヤルアウト番号を使用して会議に参加できるようにするかどうか。 会議サーバーはダイヤルアウト番号を使用してユーザーを呼び出し、ユーザーはその電話に応答し、会議に参加します。</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Lync Server 2013 でのダイヤルインの会議ポリシーの構成</a></p></td>
</tr>
<tr class="even">
<td><p><strong>ダイヤルイン アクセス番号を構成する</strong></p></td>
<td><p>Lync Server 2013 コントロールパネルまたは Lync Server 管理シェルを使用して、ユーザーが電話会議にダイヤルインするためにダイヤルインアクセス番号を設定し、アクセス番号を適切なダイヤルプランに関連付ける地域を指定します。 開催者のダイヤル プランで指定されている地域の最初の 3 つのアクセス番号が会議開催通知に含まれます。 すべてのアクセス番号は、[ダイヤルイン会議の設定] ページで利用できます。</p>
<div>

> [!NOTE]  
> ダイヤルインアクセス番号を作成した後は、 <STRONG>get-csdialinconferencingaccessnumber</STRONG>コマンドレットを使用して、Active Directory 連絡先オブジェクトの表示名を変更し、ユーザーが正しいアクセス番号を容易に識別できるようにすることができます。


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
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">オプションLync Server 2013 でダイヤルイン会議の設定を確認する</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(オプション) DTMF コマンドの主要なマッピングを変更する</strong></p></td>
<td><p><strong>Set-CsDialinConferencingDtmfConfiguration</strong> コマンドレットを使用して、デュアルトーン多重周波数 (DTMF) コマンドで使用される、参加者が会議設定 (ミュートとミュート解除、ロックとロック解除など) を制御するために使用するキーを変更します。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">オプションLync Server 2013 での DTMF コマンドのキーマッピングの変更</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>(オプション) 会議の参加時と退席時のアナウンス動作を変更する</strong></p></td>
<td><p><strong>Set-CsDialinConferencingConfiguration</strong> を使用して、参加者が会議に参加および退席する際のアナウンス動作を変更します。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">オプションLync Server 2013 での会議の参加と脱退のアナウンスを有効または無効にする</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(オプション) ダイヤルイン会議の検証</strong></p></td>
<td><p><strong>Test-CsDialInConferencing</strong> コマンドレットを使用して、指定のプールのアクセス番号が正しく機能するかどうかをテストします。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">オプションLync Server 2013 でのダイヤルイン会議の確認</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Lync 2013 用オンライン ミーティング アドインの展開</strong></p></td>
<td><p>ユーザーがダイヤルイン会議をサポートする会議をスケジュール設定できるように、Lync 2013 用のオンラインミーティングアドインを展開します。 Lync 2013 をインストールすると、Lync 2013 用のオンラインミーティングアドインが自動的にインストールされます。</p></td>
<td><p>管理者</p></td>
<td><p><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Lync 2013 用オンライン ミーティング アドインの展開</a></p></td>
</tr>
<tr class="even">
<td><p><strong>ユーザー アカウント設定の構成</strong></p></td>
<td><p>Lync Server 2013 コントロールパネルまたは Lync Server 管理シェルを使用して、テレフォニー<strong>回線 URI</strong>を正規化された一意の電話番号 (たとえば、tel: + 14255550200) として構成します。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsAdministrator</p>
<p>CsUserAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-user-account-settings.md">Lync Server 2013 でユーザーアカウント設定を構成する</a></p></td>
</tr>
<tr class="odd">
<td><p>勧め会議ディレクトリを構成する</p></td>
<td><p><strong>Get-csconferencedirectory</strong>コマンドレットを使用して、プール内の999ユーザーごとに1つの会議ディレクトリを作成します。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013 でのダイヤルイン会議の要件</a> <a href="recommended-create-conference-directories.md">(推奨) 電話会議ディレクトリを作成する</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(オプション) ユーザーにダイヤルイン会議を案内して最初の PIN を設定する</strong></p></td>
<td><p><strong>Set-cspinsendcawelcomemail</strong>スクリプトを使用して、ユーザーの初期 pin を設定し、初期 Pin およびダイヤルイン会議の設定ページへのリンクを含む開始メールを送信します。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">オプションLync Server 2013 でのダイヤルイン会議へのユーザーのようこそ</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

