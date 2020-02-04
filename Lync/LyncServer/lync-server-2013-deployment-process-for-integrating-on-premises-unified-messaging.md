---
title: オンプレミスのユニファイドメッセージングを統合する展開プロセス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76a45210fa90e5d2493885e54f07bb922f6d0495
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>内部設置型ユニファイド メッセージングと Lync Server 2013 を統合するための展開プロセス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-12-17_

Exchange ユニファイドメッセージング (UM) と Lync Server 2013 を統合する場合は、このトピックで説明するタスクを実行する必要があります。 また、「[オンプレミスのユニファイドメッセージングと Lync Server 2013 の統合に関するガイドライン](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)」で説明されている計画と展開のベストプラクティスを確認してください。 このトピックでは、お客は、併置された仲介サーバーと共に Lync server 2013 を展開しており、lync Server 2013 のユーザーを有効にしていることを前提としていますが、展開ドキュメントに「[エンタープライズ 2013 voip を導入](lync-server-2013-deploying-enterprise-voice.md)する」の説明に従って、エンタープライズ voip を有効にするための展開と構成の手順をすべて実行

<div>

## <a name="unified-messaging-integration-process"></a>ユニファイド メッセージング統合プロセス

<div>


> [!IMPORTANT]
> スムーズに問題なく統合できるように、組織の Exchange 管理者と協力して、各自が実施する作業を確認することが重要です。



</div>


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
<th>必要なグループおよび役割</th>
<th>「展開」のドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>次のいずれかを展開します。</p>
<ul>
<li><p>Microsoft Exchange Server 2007 Service Pack 1 (SP2) または最新の Service pack</p></li>
<li><p>Microsoft Exchange Server 2010 または最新の service pack</p></li>
<li><p>Microsoft Exchange Server 2013</p></li>
</ul></td>
<td><p>Microsoft Exchange Server 2013 を使用している場合は、次の Exchange Server の役割を同じフォレストまたは別のフォレストの Lync Server 2013 としてインストールします。</p>
<ul>
<li><p>クライアント アクセス</p></li>
<li><p>メールボックス</p></li>
</ul>
<p>Microsoft Exchange Server 2013 と Exchange ユニファイドメッセージング (UM) が異なるフォレストにインストールされている場合は、各 Exchange フォレストが Lync Server 2013 フォレストを信頼するように構成します。</p>
<p>Exchange 2010 を使用している場合は、次の Exchange Server の役割を同じフォレストまたは別のフォレストの Lync Server 2013 としてインストールします。</p>
<ul>
<li><p>ユニファイド メッセージング</p></li>
<li><p>ハブ トランスポート</p></li>
<li><p>クライアント アクセス</p></li>
<li><p>メールボックス</p></li>
</ul>
<p>Lync Server 2013 と Exchange ユニファイドメッセージング (UM) が異なるフォレストにインストールされている場合は、各 Exchange フォレストが Lync Server 2013 フォレストを信頼するように構成します。</p></td>
<td><p>エンタープライズ管理者 (これが組織内で最初の Exchange Server である場合)</p>
<p>- または -</p>
<p>Exchange 組織管理者 (これが組織内で最初の Exchange Server ではない場合)</p></td>
<td><p>お使いの Exchange Server のバージョンに適したドキュメントを参照してください。</p>
<dl>
<dt><span></span></dt>
<dd><p>Exchange Server 2007 展開に<a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>関するドキュメント</p>
</dd>
<dt><span></span></dt>
<dd><p>Exchange Server 2010 または最新の service pack の<a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>展開ドキュメント</p>
</dd>
<dt><span></span></dt>
<dd><p>Microsoft Exchange Server 2013 の計画と展開<a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>証明書をインストールします。</p></td>
<td><p>信頼されたルート証明機関 (CA) から各 Exchange UM サーバーの証明書をダウンロードしてインストールします。 証明書は、Exchange UM と Lync Server 2013 を実行しているサーバー間の相互トランスポートレベルセキュリティ (MTLS) に必要です。</p></td>
<td><p>管理者</p></td>
<td><p><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Microsoft Exchange Server ユニファイドメッセージングを実行しているサーバーで証明書を構成する</a></p></td>
</tr>
<tr class="odd">
<td><p>新しい Exchange UM SIP ダイヤルプランを作成して構成します。</p></td>
<td><p>Exchange UM サーバーで、組織の特定の展開要件に基づいて SIP ダイヤルプランを作成します。</p></td>
<td><p>Exchange 組織管理者</p></td>
<td><p>Exchange 2007 SP1 または最新の service pack に&quot;ついては、「ユニファイドメッセージング SIP URI&quot;ダイヤル<a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>プランを作成する方法」を参照してください。</p>
<p>Exchange 2010 または最新の service pack に&quot;ついては、「&quot; At <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>で UM ダイヤルプランを作成する」を参照してください。</p>
<p>Exchange 2013 については、の<a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>「ユニファイドメッセージング」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>Exchange UM SIP ダイヤルプランのセキュリティ設定を構成します。</p></td>
<td><p>エンタープライズボイストラフィックを暗号化するには、Sip がセキュリティで<strong>保護</strong>されている、またはセキュリティで<strong>保護</strong>されている場合に、Exchange UM SIP ダイヤルプランのセキュリティ設定を構成します。 これは、お客様の環境に Lync Phone Edition のデバイスを展開または展開する予定がある場合に特に重要です。 Exchange UM との統合が設定された環境で機能する Lync Phone Edition デバイスの場合、Lync Server の暗号化設定は、Exchange UM ダイヤルプランのセキュリティ設定に合わせる必要があります。 詳細については、「展開」のドキュメントを参照してください。</p></td>
<td><p>Exchange 組織管理者</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Lync Server 2013 向けの Microsoft Exchange でユニファイドメッセージングを構成する</a></p>
<p>Exchange 2007 SP1 または最新の service pack については、以下も参照してください。</p>
<p>&quot;ユニファイドメッセージングダイヤルプラン&quot;でセキュリティを構成する方法<a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>については、をご覧ください。</p>
<p>Exchange 2010 または最新 Service Pack の場合は、次のドキュメントも参照してください。</p>
<p>&quot;UM ダイヤルプラン&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>で VoIP セキュリティを構成します。</p>
<p>Exchange 2013 については、の<a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>「ユニファイドメッセージング」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>ユニファイドメッセージングサーバーを Exchange UM SIP ダイヤルプランに追加します。</p></td>
<td><p>新しくインストールされたユニファイド メッセージング サーバーを、着信通話に応答および着信通話を処理できるようにするには、ユニファイド メッセージング サーバーを UM ダイヤル プランに追加しなければなりません。 この場合は、Exchange UM SIP ダイヤルプランにサーバーを追加します。</p></td>
<td><p>管理者</p>
<p>Exchange Server 管理者</p></td>
<td><p>Exchange 2007 SP1 または最新の service pack に&quot;ついては、「のダイヤルプラン&quot;にユニファイド<a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>メッセージングサーバーを追加する方法」を参照してください。</p>
<p>Exchange 2010 または最新の service pack に&quot;ついては、「UM サーバー&quot;のプロパティを<a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>表示または構成する」を参照してください。</p>
<p>Exchange 2013 については、の<a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>「ユニファイドメッセージング」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>SIP アドレスでメールボックスを構成します。</p></td>
<td><p>Exchange UM 機能を使用するエンタープライズ Voip ユーザーのメールボックスに SIP アドレスを割り当てます。</p></td>
<td><p>Lync Server 2013 管理者</p>
<p>Exchange 受信者の管理者</p></td>
<td><p>Exchange 2007 SP1 または最新の service pack に&quot;ついては、「UM が有効なユーザー&quot;の SIP アドレスを追加、削除、 <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>変更する方法」を参照してください。</p>
<p>Exchange 2010 または最新の service pack に&quot;ついては、「UM が有効なユーザー&quot;の<a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>SIP アドレスを変更する」を参照してください。</p>
<p>Exchange 2013 については、の<a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>「ユニファイドメッセージング」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>exchucutil.ps1 スクリプトを実行します。</p></td>
<td><p>Exchange UM サービスを実行しているサーバーで、Exchange 管理シェルを開き、次の操作を実行する exchucutil というスクリプトを実行します。</p>
<ul>
<li><p>Exchange UM Active Directory ドメインサービスオブジェクト (具体的には、前のタスクで作成した SIP ダイヤルプラン) を読み取る Lync Server 2013 アクセス許可を付与します。</p></li>
<li><p>エンタープライズ Voip を有効にしているユーザーをホストする、Lync Server 2013 Enterprise Edition プールまたは Standard Edition server の Active Directory にユニファイドメッセージング IP ゲートウェイオブジェクトを作成します。</p></li>
<li><p>各ゲートウェイの Exchange UM ハントグループを作成します。 ハント グループのパイロット ID は、対応するゲートウェイに関連付けられたダイヤル プランの名前になります。 複数のダイヤル プランが存在する場合は、これらは 1 対 1 でマップされる必要があります。</p></li>
</ul></td>
<td><p>Exchange 組織管理者</p>
<p>Exchange 受信者の管理者</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Lync Server 2013 向けの Microsoft Exchange でユニファイドメッセージングを構成する</a></p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 ダイヤルプランを構成します。</p></td>
<td><p>Exchange 2007 SP1 または最新の service pack、または Exchange 2010 と統合する場合は、新しいエンタープライズボイスダイヤルプランを作成します。このプランには、Exchange UM dial plan の完全修飾ドメイン名 (FQDN) と一致する名前が付いています。</p>



> [!NOTE]
> これを UM ダイヤル プランごとに行う必要があります。


<p>Exchange 2010 SP1 と統合する場合は、適切なグローバル/サイトレベルまたはプールレベルのエンタープライズボイスダイヤルプランが構成されていることを確認します。</p>



> [!NOTE]
> Exchange 2010 SP1 と統合する場合、Lync Server のダイヤルプランと Exchange UM SIP ダイヤルプランの名前を一致させる必要はありません。

</td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-dial-plans.md">Lync Server 2013 でのダイヤル プランの構成</a></p></td>
</tr>
<tr class="odd">
<td><p>Exchange UM 統合ツールを実行します。</p></td>
<td><p>Lync Server 2013 で、次のように<strong>ocsumutil</strong>を実行します。</p>
<ul>
<li><p>サブスクライバー アクセスおよび自動応答連絡先オブジェクトを作成します。</p></li>
<li><p>Exchange UM ダイヤルプランの FQDN と一致する名前のエンタープライズボイスダイヤルプランがあることを検証します。 Exchange 2010 SP1 以降を実行している場合は、ダイヤルプラン名が一致している必要はありません。これに関するツールの警告は無視してかまいません。</p></li>
</ul>
<p>このツールは、Active Directory で Exchange UM 設定をスキャンし、Lync Server 2013 管理者が連絡先オブジェクトを表示、作成、編集できるようにすることで機能します。</p></td>
<td><p>RTCUniversalServerAdmins <em></em>および RTCUniversalUserAdmins</p>



> [!IMPORTANT]
> ocsumutil.exe を正常に実行するため、ユーザーはこれらのグループの両方に属していなければなりません。





> [!NOTE]
> 連絡先オブジェクトを作成するには、ocsumutil.exe を実行するユーザーが、新しい連絡先オブジェクトが保存される Active Directory 組織単位 (OU) への適切なアクセス許可を持たなければなりません。 このアクセス許可は、<STRONG>Grant-CsOUPermission</STRONG> コマンドレットを実行することで付与されます。 詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。

</td>
<td><p><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Microsoft Exchange Server のユニファイド メッセージングと連動させるための Lync Server 2013 の構成</a></p></td>
</tr>
<tr class="even">
<td><p>必要に応じて、その他のエンタープライズボイス構成手順を実行します。</p></td>
<td><p>サーバーまたはユーザーのエンタープライズ Voip 設定をまだ構成していない場合は、次の操作のいずれか、または複数の操作を行います。</p>
<ul>
<li><p>公衆交換電話網 (PSTN) ゲートウェイ</p>
<p>および仲介サーバーを展開および構成します。</p></li>
<li><p>音声ポリシー、PSTN 使用法レコード、および発信通話ルートを定義します。</p></li>
<li><p>エンタープライズ VoIP に対してユーザーを有効化します。</p></li>
<li><p>必要に応じて、特定のユーザーにダイヤル プランを構成します。</p></li>
</ul>
<p>有効になっているエンタープライズ Voip 機能によっては、その他の構成手順が必要になることがあります。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>RTCUniversalUserAdmins</p></td>
<td><p>次のセクションのトピックを参照してください。</p>
<ul>
<li><p><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Lync Server 2013 での音声ポリシー、PSTN 使用状況レコード、および音声ルートの構成</a></p></li>
<li><p><a href="lync-server-2013-deploying-enterprise-voice.md">Lync Server 2013 でのエンタープライズボイスの展開</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>エンタープライズボイスユーザーに Exchange UM を有効にします。</p></td>
<td><p>Exchange UM サーバーで、ユニファイドメッセージングメールボックスポリシーが作成されていて、各ユーザーに固有の内線番号の割り当てが含まれていることを確認してから、そのユーザーのユニファイドメッセージングを有効にします。</p></td>
<td><p>Exchange 受信者の管理者</p></td>
<td><p>Exchange 2007 SP1 または最新の service pack に&quot;ついては、「のユニファイド&quot;メッセージング<a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>に対してユーザーを有効にする方法」を参照してください。</p>
<p>Exchange 2010 または最新の service pack に&quot;ついては、「ユーザー&quot;が<a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>ユニファイドメッセージングを有効にする」を参照してください。</p>
<p>Exchange 2013 については、の<a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>「ユニファイドメッセージング」を参照してください。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

