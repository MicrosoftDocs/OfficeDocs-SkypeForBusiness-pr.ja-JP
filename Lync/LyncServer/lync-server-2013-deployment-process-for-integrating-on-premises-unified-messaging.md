---
title: オンプレミスのユニファイドメッセージングを統合するための展開プロセス
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
ms.openlocfilehash: d6d60b120db57ad73c33e682fa8150e99f5606e3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>オンプレミスのユニファイドメッセージングと Lync Server 2013 を統合するための展開プロセス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-12-17_

Exchange ユニファイドメッセージング (UM) と Lync Server 2013 を統合する場合は、このトピックで説明するタスクを実行する必要があります。 また、「[オンプレミスのユニファイドメッセージングと Lync Server 2013 を統合するためのガイドライン](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)」に記載されている計画および展開のベストプラクティスを確認してください。 このトピックでは、Lync server 2013 を併置された仲介2013サーバーと共に展開し、「展開」のドキュメントの「 [Lync server 2013 でのエンタープライズ voip の展開](lync-server-2013-deploying-enterprise-voice.md)」で説明するように、エンタープライズ voip を有効にするための展開と構成の手順をすべて実行したことを前提としています。

<div>

## <a name="unified-messaging-integration-process"></a>ユニファイド メッセージング統合プロセス

<div>


> [!IMPORTANT]
> 円滑で成功した統合を確実にするために、組織の Exchange 管理者と協力して、各ユーザーが実行するタスクを確認することが重要です。



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
<th>手順</th>
<th>必要なグループおよび役割</th>
<th>展開のドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>次のいずれかを展開します。</p>
<ul>
<li><p>Microsoft Exchange Server 2007 Service Pack 1 (SP2) または最新のサービスパック</p></li>
<li><p>Microsoft Exchange Server 2010 または最新のサービスパック</p></li>
<li><p>Microsoft Exchange Server 2013</p></li>
</ul></td>
<td><p>Microsoft Exchange Server 2013 を使用している場合は、次の Exchange サーバーの役割を同じフォレストまたは別のフォレストの Lync Server 2013 としてインストールします。</p>
<ul>
<li><p>クライアント アクセス</p></li>
<li><p>メールボックス</p></li>
</ul>
<p>Microsoft Exchange Server 2013 と Exchange ユニファイドメッセージング (UM) が異なるフォレストにインストールされている場合は、Lync Server 2013 フォレストを信頼するように各 Exchange フォレストを構成します。</p>
<p>Exchange 2010 を使用している場合は、Lync Server 2013 と同じフォレストまたは別のフォレストに、次の Exchange サーバーの役割をインストールします。</p>
<ul>
<li><p>ユニファイド メッセージング</p></li>
<li><p>ハブ トランスポート</p></li>
<li><p>クライアント アクセス</p></li>
<li><p>メールボックス</p></li>
</ul>
<p>Lync Server 2013 と Exchange ユニファイドメッセージング (UM) が異なるフォレストにインストールされている場合は、Lync Server 2013 フォレストを信頼するように各 Exchange フォレストを構成します。</p></td>
<td><p>エンタープライズ管理者 (これが組織内で最初の Exchange Server である場合)</p>
<p>または -</p>
<p>Exchange 組織管理者 (これが組織内で最初の Exchange Server ではない場合)</p></td>
<td><p>お使いの Exchange Server のバージョンに適したドキュメントを参照してください。</p>
<dl>
<dt><span></span></dt>
<dd><p>Exchange Server 2007 の展開に<a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a>関するドキュメント</p>
</dd>
<dt><span></span></dt>
<dd><p>Exchange Server 2010 または最新の service pack の<a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a>展開に関するドキュメント</p>
</dd>
<dt><span></span></dt>
<dd><p>Microsoft Exchange Server 2013 の計画と展開<a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a>」</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>証明書をインストールします。</p></td>
<td><p>信頼されたルート証明機関 (CA) から、各 Exchange UM サーバーの証明書をダウンロードしてインストールします。 この証明書は、Exchange UM と Lync Server 2013 を実行しているサーバー間の相互トランスポートレベルのセキュリティ (MTLS) に必要です。</p></td>
<td><p>管理者</p></td>
<td><p><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Microsoft Exchange Server ユニファイドメッセージングを実行しているサーバーで証明書を構成する</a></p></td>
</tr>
<tr class="odd">
<td><p>新しい Exchange UM SIP ダイヤルプランを作成して構成します。</p></td>
<td><p>Exchange UM サーバーで、組織の特定の展開要件に基づいて SIP ダイヤルプランを作成します。</p></td>
<td><p>Exchange 組織管理者</p></td>
<td><p>Exchange 2007 SP1 または最新のサービスパックに&quot;ついては、「How to Create a ユニファイ&quot;ド<a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a>メッセージング SIP URI ダイヤルプラン」を参照してください。</p>
<p>Exchange 2010 または最新のサービスパックに&quot;ついては、「&quot; UM <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a>ダイヤルプランを作成する」を参照してください。</p>
<p>Exchange 2013 については、「 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>ユニファイドメッセージング」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>Exchange UM SIP ダイヤルプランのセキュリティ設定を構成します。</p></td>
<td><p>エンタープライズ Voip トラフィックを暗号化するには、Exchange UM SIP ダイヤルプランのセキュリティ設定を、SIP がセキュリティで<strong>保護</strong><strong>されているか、</strong>セキュリティで保護されるように構成します。 これは、お客様の環境に Lync Phone Edition デバイスを展開または展開する予定がある場合に特に重要な手順です。 Exchange UM 統合を使用した環境で Lync Phone Edition デバイスを機能させるには、Lync Server の暗号化設定を Exchange UM ダイヤルプランのセキュリティ設定と揃える必要があります。 詳細については、「展開」のドキュメントを参照してください。</p></td>
<td><p>Exchange 組織管理者</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Lync Server 2013 の Microsoft Exchange でのユニファイドメッセージングの構成</a></p>
<p>Exchange 2007 SP1 または最新の service pack の場合は、次の項目も参照してください。</p>
<p>&quot;ユニファイドメッセージングダイヤルプラン&quot;でセキュリティを構成する方法<a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a>について説明します。</p>
<p>Exchange 2010 または最新 Service Pack の場合は、次のドキュメントも参照してください。</p>
<p>&quot;UM ダイヤルプラン&quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a>で VoIP セキュリティを構成します。</p>
<p>Exchange 2013 については、「 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>ユニファイドメッセージング」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>ユニファイドメッセージングサーバーを Exchange UM SIP ダイヤルプランに追加します。</p></td>
<td><p>新しくインストールされたユニファイド メッセージング サーバーを、着信通話に応答および着信通話を処理できるようにするには、ユニファイド メッセージング サーバーを UM ダイヤル プランに追加しなければなりません。 この場合は、Exchange UM SIP ダイヤルプランにサーバーを追加します。</p></td>
<td><p>管理者</p>
<p>Exchange Server 管理者</p></td>
<td><p>Exchange 2007 SP1 または最新のサービスパックに&quot;ついては、「方法: ユニファイドメッセージング&quot;サーバー <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a>をダイヤルプランに追加する方法」を参照してください。</p>
<p>Exchange 2010 または最新のサービスパックに&quot;ついては、「UM サーバー&quot;のプロパティを<a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a>表示または構成する」を参照してください。</p>
<p>Exchange 2013 については、「 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>ユニファイドメッセージング」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>SIP アドレスでメールボックスを構成します。</p></td>
<td><p>Exchange UM の機能を使用するエンタープライズ Voip ユーザーのメールボックスに SIP アドレスを割り当てます。</p></td>
<td><p>Lync Server 2013 管理者</p>
<p>Exchange 受信者管理者</p></td>
<td><p>Exchange 2007 SP1 または最新のサービスパックに&quot;ついては、「UM が有効なユーザー&quot;の SIP アドレスをで<a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a>追加、削除、または変更する方法」を参照してください。</p>
<p>Exchange 2010 または最新のサービスパックに&quot;ついては、「UM が有効なユーザー&quot;の<a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a>SIP アドレスを変更する」を参照してください。</p>
<p>Exchange 2013 については、「 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>ユニファイドメッセージング」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>exchucutil.ps1 スクリプトを実行します。</p></td>
<td><p>Exchange UM サービスを実行しているサーバーで、Exchange 管理シェルを開き、次の処理を実行する exchucutil. ps1 スクリプトを実行します。</p>
<ul>
<li><p>Lync Server 2013 に、Exchange UM Active Directory ドメインサービスオブジェクト (特に、前のタスクで作成した SIP ダイヤルプラン) を読み取るためのアクセス許可を付与します。</p></li>
<li><p>エンタープライズ Voip が有効になっているユーザーをホストする Lync Server 2013 Enterprise Edition プールまたは Standard Edition サーバーごとに、Active Directory 内にユニファイドメッセージング IP ゲートウェイオブジェクトを作成します。</p></li>
<li><p>各ゲートウェイの Exchange UM ハントグループを作成します。 ハント グループのパイロット ID は、対応するゲートウェイに関連付けられたダイヤル プランの名前になります。 複数のダイヤル プランが存在する場合は、これらは 1 対 1 でマップされる必要があります。</p></li>
</ul></td>
<td><p>Exchange 組織管理者</p>
<p>Exchange 受信者管理者</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Lync Server 2013 の Microsoft Exchange でのユニファイドメッセージングの構成</a></p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 ダイヤルプランを構成します。</p></td>
<td><p>Exchange 2007 SP1 または最新の service pack または Exchange 2010 と統合する場合は、Exchange UM ダイヤルプランの完全修飾ドメイン名 (FQDN) と一致する名前を持つ新しいエンタープライズ Voip ダイヤルプランを作成します。</p>



> [!NOTE]
> UM ダイヤルプランごとにこれを行う必要があります。


<p>Exchange 2010 SP1 と統合する場合は、適切なグローバル/サイトレベルまたはプールレベルのエンタープライズ Voip ダイヤルプランが構成されていることを確認してください。</p>



> [!NOTE]
> Exchange 2010 SP1 と統合する場合は、Lync Server のダイヤルプランと Exchange UM SIP ダイヤルプランの名前を一致させる必要はありません。

</td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-dial-plans.md">Lync Server 2013 でのダイヤルプランの構成</a></p></td>
</tr>
<tr class="odd">
<td><p>Exchange UM 統合ツールを実行します。</p></td>
<td><p>Lync Server 2013 で、 <strong>ocsumutil</strong>を次のように実行します。</p>
<ul>
<li><p>サブスクライバー アクセスおよび自動応答連絡先オブジェクトを作成します。</p></li>
<li><p>Exchange UM ダイヤルプランの FQDN と一致する名前のエンタープライズ Voip ダイヤルプランがあることを検証します。 Exchange 2010 SP1 以降を実行している場合は、ダイヤルプラン名を一致させる必要がないため、このツールの警告を無視することができます。</p></li>
</ul>
<p>このツールは、Active Directory の Exchange UM 設定をスキャンし、Lync Server 2013 管理者が連絡先オブジェクトを表示、作成、および編集できるようにすることによって機能します。</p></td>
<td><p>RTCUniversalServerAdmins <em>および</em> RTCUniversalUserAdmins</p>



> [!IMPORTANT]
> ocsumutil.exe を正常に実行するため、ユーザーはこれらのグループの両方に属していなければなりません。





> [!NOTE]
> 連絡先オブジェクトを作成するには、ocsumutil.exe を実行するユーザーが、新しい連絡先オブジェクトが保存される Active Directory 組織単位 (OU) への適切なアクセス許可を持たなければなりません。 このアクセス許可は、 <STRONG>Grant-CsOUPermission</STRONG>コマンドレットを実行することによって付与できます。 詳細については、Lync Server 管理シェルのドキュメントを参照してください。

</td>
<td><p><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Microsoft Exchange Server でユニファイドメッセージングを使用するように Lync Server 2013 を構成する</a></p></td>
</tr>
<tr class="even">
<td><p>必要に応じて、その他のエンタープライズ VoIP 構成ステップを実行します。</p></td>
<td><p>サーバーまたはユーザーにエンタープライズ VoIP 設定をまだ構成していない場合、次の 1 つ以上の操作を実行します。</p>
<ul>
<li><p>展開と構成</p>
<p>公衆交換電話網 (PSTN) ゲートウェイと仲介サーバー</p></li>
<li><p>音声ポリシー、PSTN 使用法レコード、および発信通話ルートを定義します。</p></li>
<li><p>エンタープライズ VoIP に対してユーザーを有効化します。</p></li>
<li><p>必要に応じて、特定のユーザーにダイヤル プランを構成します。</p></li>
</ul>
<p>有効にするエンタープライズ VoIP 機能によっては、その他の構成ステップが必要となる場合があります。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>RTCUniversalUserAdmins</p></td>
<td><p>次のセクションのトピックを参照してください。</p>
<ul>
<li><p><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Lync Server 2013 での音声ポリシー、PSTN 使用法レコード、およびボイスルートの構成</a></p></li>
<li><p><a href="lync-server-2013-deploying-enterprise-voice.md">Lync Server 2013 でのエンタープライズ Voip の展開</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Exchange UM のエンタープライズ Voip ユーザーを有効にします。</p></td>
<td><p>Exchange UM サーバーで、ユニファイドメッセージングメールボックスポリシーが作成されており、各ユーザーが固有の内線番号の割り当てを持っていることを確認してから、ユーザーのユニファイドメッセージングを有効にします。</p></td>
<td><p>Exchange 受信者管理者</p></td>
<td><p>Exchange 2007 SP1 または最新のサービスパックに&quot;ついては、「ユーザーのユニファイ&quot;ド<a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a>メッセージングを有効にする方法」を参照してください。</p>
<p>Exchange 2010 または最新のサービスパックに&quot;ついては、「を&quot;使用<a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a>してユーザーのユニファイドメッセージングを有効にする」を参照してください。</p>
<p>Exchange 2013 については、「 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>ユニファイドメッセージング」を参照してください。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

