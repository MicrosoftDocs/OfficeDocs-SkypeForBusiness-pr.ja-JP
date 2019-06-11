---
title: 'Lync Server 2013: ダイヤルイン会議の展開チェックリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44591676d69b5fb4ac3d66ce0e18718389a0c189
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a>Lync Server 2013 のダイヤルイン会議の展開チェックリスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-10-03_

会議のワークロードを展開すると、ダイヤルイン会議に必要なコンポーネントが展開されます。 ダイヤルイン会議を構成する前に、エンタープライズボイスまたは仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイを展開する必要があります。

次の表のすべての手順を実行して、ユーザーが PSTN から電話会議に参加するようにする必要があります。

<div>


> [!NOTE]  
> Office Communications Server 2007 R2 から移行する場合は、ダイヤルイン会議を展開する前に、Office Communications Server 2007 R2 の環境に最新の更新プログラムを適用する必要があります。



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
<th>段階</th>
<th>ステップ</th>
<th>アクセス許可</th>
<th>「展開」のドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>仲介サーバーと PSTN ゲートウェイなどの会議のワークロードを含むトポロジを作成して、フロントエンドプールまたは Standard Edition サーバーを展開する</strong></p></td>
<td><ol>
<li><p>トポロジビルダーを実行してトポロジを構成します。 トポロジの構成時に、ダイヤルイン会議オプションを選択します。</p></li>
<li><p>トポロジを公開し、フロントエンドプールまたは Standard Edition サーバーを展開します。</p></li>
<li><p>必要に応じて、スタンドアロンの仲介サーバーを作成して、PSTN ゲートウェイに関連付けます。</p>
<div>

> [!NOTE]  
> この手順が必要になるのは、エンタープライズボイスを展開せず、エンタープライズ EditionFront エンドサーバーまたは Standard Edition サーバーで仲介サーバーを検索しない場合のみです。 エンタープライズ Voip を展開する場合は、エンタープライズ Voip 展開の一部として、仲介サーバーと PSTN ゲートウェイをインストールして構成します。 仲介サーバーを検索する場合は、フロントエンドプールまたは Standard Edition サーバーの展開の一部として、仲介サーバーをインストールして構成します。


</div></li>
</ol></td>
<td><p>Domain Admins</p>
<p>RTCUniversalServerAdmins</p>
<p>Administrator</p></td>
<td><ul>
<li><p><a href="lync-server-2013-deploying-lync-server.md">Lync Server 2013 の展開</a></p></li>
<li><p>スタンドアロンの仲介サーバープールを作成するには、「 <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Lync server 2013 での仲介サーバーの展開とピアの定義」</a>をご覧ください。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Configure dial plans</strong></p></td>
<td><p>ダイヤルプランとは、特定の場所からダイヤルされた電話番号を、電話の認証と通話ルーティングの目的に合わせて1つの標準 (E.i) 形式に変換する、一連の電話番号の正規化ルールです。 異なる場所からダイヤルされた同じ電話番号は、それぞれのダイヤルプランに基づいて、それぞれの場所に応じて異なる E.i 番号に解決することができます。 エンタープライズ Voip を展開する場合は、その展開の一環としてダイヤルプランを設定する必要があります。また、ダイヤルプランがダイヤルイン会議にも対応していることを確認する必要があります。 エンタープライズ Voip を展開しない場合は、ダイヤルイン会議のダイヤルプランをセットアップする必要があります。</p>
<p>Lync Server 2013 コントロールパネルまたは Lync Server 管理シェルを使用して、次のようにダイヤルプランを設定します。</p>
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
<td><p><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">「ダイヤルプラン Lync Server 2013 に地域が割り当てられていることを確認する」</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(オプション) ユーザーの暗証番号 (PIN) 要件を確認または変更する</strong></p></td>
<td><p>Lync Server 2013 コントロールパネルまたは Lync Server 管理シェルを使用して、会議<strong>ピンポリシー</strong>を表示または変更します。 最小 PIN サイズ、最大ログオン試行回数、PIN の有効期限、およびよくあるパターンを許可するかどうかを指定できます。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(オプション) Lync Server 2013 での PIN ポリシー設定の確認</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>ダイヤルイン会議をサポートするように会議ポリシーを構成する</strong></p></td>
<td><p>Lync Server 2013 コントロールパネルまたは Lync Server Management Shell を使って、<strong>会議のポリシー</strong>設定を構成します。 次のことを指定します。</p>
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
<td><p><strong>Configure dial-in access numbers</strong></p></td>
<td><p>Lync Server 2013 コントロールパネルまたは Lync Server Management Shell を使用して、ユーザーが電話会議にダイヤルインするためにダイヤルインアクセス番号を設定し、アクセス番号を適切なダイヤルプランに関連付ける地域を指定します。 開催者のダイヤル プランで指定されている地域の最初の 3 つのアクセス番号が会議開催通知に含まれます。 [ダイヤルイン会議の設定] ページでは、すべてのアクセス番号を利用できます。</p>
<div>

> [!NOTE]  
> ダイヤルインアクセス番号を作成したら、 <STRONG>CsDialInConferencingAccessNumber</STRONG>コマンドレットを使用して Active Directory の連絡先オブジェクトの表示名を変更し、ユーザーが正しいアクセス番号を簡単に識別できるようにすることができます。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Lync Server 2013 でのダイヤルイン会議アクセス番号の構成</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>(オプション) ダイヤルイン会議の設定の検証</strong></p></td>
<td><p><strong>Get-CsDialinConferencingAccessNumber</strong> コマンドレットを使用して、どのアクセス番号でも使用されていないダイヤルイン会議の地域が設定されたダイヤル プランと、どの地域も割り当てられていないアクセス番号を検索します。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p>
<p>CsHelpDesk</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(オプション) Lync Server 2013 でのダイヤルイン会議の設定の検証</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(オプション) DTMF コマンドの主要なマッピングを変更する</strong></p></td>
<td><p><strong>CsDialinConferencingDtmfConfiguration</strong>コマンドレットを使用して、2トーン (DTMF) コマンドで使用されるキーを変更します。参加者は、会議の設定 (ミュート、ミュート解除、ロックとロック解除など) を制御するために使用できます。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(オプション) Lync Server 2013 で DTMF コマンドの主要なマッピングを変更する</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>(オプション) 電話会議の参加時と退席時のアナウンス動作を変更する</strong></p></td>
<td><p><strong>Set-CsDialinConferencingConfiguration</strong> を使用して、参加者が電話会議に参加および退席する際のアナウンス動作を変更します。</p></td>
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
<td><p><strong>Lync 2013 用オンライン会議アドインの展開</strong></p></td>
<td><p>Lync 2013 用のオンライン会議アドインを展開して、ユーザーがダイヤルイン会議をサポートする会議をスケジュールできるようにします。 Lync 2013 をインストールすると、Lync 2013 用のオンライン会議アドインが自動的にインストールされます。</p></td>
<td><p>管理者</p></td>
<td><p><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Lync 2013 用オンライン会議アドインの展開</a></p></td>
</tr>
<tr class="even">
<td><p><strong>ユーザー アカウント設定の構成</strong></p></td>
<td><p>Lync Server 2013 コントロールパネルまたは Lync Server Management Shell を使って、一意の正規化された電話番号としてテレフォニーの<strong>ライン URI</strong>を構成します (たとえば、tel: + 14255550200)。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsAdministrator</p>
<p>CsUserAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-user-account-settings.md">Lync Server 2013 でのユーザー アカウント設定の構成</a></p></td>
</tr>
<tr class="odd">
<td><p>(推奨) 電話会議ディレクトリを構成する</p></td>
<td><p><strong>New-CsConferenceDirectory</strong> コマンドレットを使用して、プールに含まれる 999 ユーザーごとに電話会議ディレクトリを 1 つ作成します。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013 でのダイヤルイン会議の要件</a><a href="recommended-create-conference-directories.md">(推奨) 会議ディレクトリを作成する</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(オプション) ユーザーにダイヤルイン会議を案内して最初の PIN を設定する</strong></p></td>
<td><p><strong>CsPinSendCAWelcomeMail</strong>スクリプトを使用して、ユーザーの初期 pin を設定し、初期 Pin とダイヤルイン会議の設定ページへのリンクを含むようこそメールを送信します。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(オプション) Lync Server 2013 でのダイヤルイン会議へのユーザーの受け入れ</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

