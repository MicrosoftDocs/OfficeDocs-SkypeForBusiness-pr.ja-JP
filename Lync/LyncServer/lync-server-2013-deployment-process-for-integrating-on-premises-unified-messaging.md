---
title: 'Lync Server 2013: 内部設置型ユニファイド メッセージングを統合するための展開プロセス'
TOCTitle: 内部設置型ユニファイド メッセージングと Lync Server を統合するための展開プロセス
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48271516
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 内部設置型ユニファイド メッセージングと Lync Server 2013 を統合するための展開プロセス

 

_**トピックの最終更新日:** 2016-12-08_

Exchange ユニファイド メッセージング (UM) を Lync Server 2013 と統合する場合、このトピックに記載されているタスクを実行する必要があります。また、「[内部設置型ユニファイド メッセージングおよび Lync Server 2013 を統合するためのガイドライン](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)」に記載されている計画および展開の最良事例をしっかり確認しておいてください。このトピックでは、併置された仲介サーバーと共に Lync Server 2013 が展開されており、ユーザーが Lync Server 2013 を使用できるようになっていることを前提としていますが、「展開」のドキュメントの「[Lync Server 2013 でのエンタープライズ VoIP の展開](lync-server-2013-deploying-enterprise-voice.md)」に記載されている、エンタープライズ VoIP を有効にする展開および構成のステップを必ずしもすべて実行しておく必要はありません。

## ユニファイド メッセージング統合プロセス


> [!IMPORTANT]
> スムーズに問題なく統合できるように、組織の Exchange 管理者と協力して、各自が実施する作業を確認することが重要です。




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
<li><p>Microsoft Exchange Server 2007 Service Pack 1 (SP2) または最新 Service Pack</p></li>
<li><p>Microsoft Exchange Server 2010 または最新 Service Pack</p></li>
<li><p>Microsoft Exchange Server 2013</p></li>
</ul></td>
<td><p>Microsoft Exchange Server 2013 を使用している場合は、Lync Server 2013 と同じフォレストまたは異なるフォレストに次の Exchange Server の役割をインストールします。</p>
<ul>
<li><p>クライアント アクセス</p></li>
<li><p>メールボックス</p></li>
</ul>
<p>Microsoft Exchange Server 2013 と Exchange ユニファイド メッセージング (UM) がそれぞれ別のフォレストにインストールされている場合は、Lync Server 2013 フォレストを信頼するように各 Exchange フォレストを構成します。</p>
<p>Exchange 2010 を使用している場合は、Lync Server 2013 と同じフォレストまたは異なるフォレストに次の Exchange Server の役割をインストールします。</p>
<ul>
<li><p>ユニファイド メッセージング</p></li>
<li><p>ハブ トランスポート</p></li>
<li><p>クライアント アクセス</p></li>
<li><p>メールボックス</p></li>
</ul>
<p>Lync Server 2013 と Exchange ユニファイド メッセージング (UM) がそれぞれ別のフォレストにインストールされている場合は、Lync Server 2013 フォレストを信頼するように各 Exchange フォレストを構成します。</p></td>
<td><p>エンタープライズ管理者 (これが組織内で最初の Exchange Server である場合)</p>
<p>- または -</p>
<p>Exchange 組織管理者 (これが組織内で最初の Exchange Server ではない場合)</p></td>
<td><p>お使いの Exchange Server のバージョンに適したドキュメントを参照してください。</p>
<dl>
<dt><span></span></dt>
<dd><p>Exchange Server 2007 の展開ドキュメント (<a href="http://go.microsoft.com/fwlink/?linkid=268694%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=268694&amp;clcid=0x411</a>)</p>
</dd>
<dt><span></span></dt>
<dd><p>Exchange Server 2010 または最新 Service Pack の展開ドキュメント (<a href="http://go.microsoft.com/fwlink/?linkid=268695%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=268695&amp;clcid=0x411</a>)</p>
</dd>
<dt><span></span></dt>
<dd><p>Microsoft Exchange Server 2013 の「計画と展開」(<a href="http://go.microsoft.com/fwlink/?linkid=266569%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=266569&amp;clcid=0x411</a>)</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>証明書をインストールします。</p></td>
<td><p>信頼されたルート証明機関 (CA) から、それぞれの Exchange UM サーバーに証明書をダウンロードおよびインストールします。証明書は、Exchange UM と Lync Server 2013 を実行しているサーバーとの間での相互トランスポート レベルのセキュリティ (MTLS) に必要です。</p></td>
<td><p>管理者</p></td>
<td><p><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Microsoft Exchange Server ユニファイド メッセージングを実行しているサーバーでの証明書の構成</a></p></td>
</tr>
<tr class="odd">
<td><p>新しい Exchange UM SIP ダイヤル プランを作成および構成します。</p></td>
<td><p>Exchange UM サーバーで、組織特有の展開要件に基づいた SIP ダイヤル プランを作成します。</p></td>
<td><p>Exchange 組織管理者</p></td>
<td><p>Exchange 2007 SP1 または最新 Service Pack の場合は、「ユニファイド メッセージング SIP URI ダイヤル プランを作成する方法」(<a href="http://go.microsoft.com/fwlink/?linkid=268632%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=268632&amp;clcid=0x411</a>) を参照してください。</p>
<p>Exchange 2010 または最新 Service Pack の場合は、「UM ダイヤル プランの作成」(<a href="http://go.microsoft.com/fwlink/?linkid=268674%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=268674&amp;clcid=0x411</a>) を参照してください。</p>
<p>Exchange 2013 の場合は、「ユニファイド メッセージング」(<a href="http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=266579&amp;clcid=0x411</a>) を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>Exchange UM SIP ダイヤル プランのセキュリティ設定を構成します。</p></td>
<td><p>エンタープライズ VoIP トラフィックを暗号化するには、Exchange UM SIP ダイヤル プランのセキュリティ設定を [ <strong>セキュリティで保護された SIP</strong>] または [ <strong>セキュリティで保護</strong>] に構成します。ご使用の環境に Lync Phone Edition デバイスを展開しているか、展開する計画をしている場合は、これは特に重要なステップです。Lync Phone Edition デバイスを Exchange UM が統合された環境で機能させるためには、Lync Server 暗号化設定を Exchange UM ダイヤル プラン セキュリティ設定に合わせておかなければなりません。詳細については、「展開」のドキュメントを参照してください。</p></td>
<td><p>Exchange 組織管理者</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Lync Server 2013 での Microsoft Exchange のユニファイド メッセージングの構成</a></p>
<p>Exchange 2007 (SP1) または最新 Service Pack の場合は、次のドキュメントも参照してください。</p>
<p>「ユニファイド メッセージング ダイヤル プランのセキュリティ設定の構成」(<a href="http://go.microsoft.com/fwlink/?linkid=268696%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=268696&amp;clcid=0x411</a>)</p>
<p></p>
<p>Exchange 2010 または最新 Service Pack の場合は、次のドキュメントも参照してください。</p>
<p>「UM ダイヤル プランで VoIP セキュリティを構成する」(<a href="http://go.microsoft.com/fwlink/?linkid=268697%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=268697&amp;clcid=0x411</a>)</p>
<p></p>
<p>Exchange 2013 の場合は、「ユニファイド メッセージング」(<a href="http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=266579&amp;clcid=0x411</a>) を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>Exchange UM SIP ダイヤル プランにユニファイド メッセージング サーバーを追加します。</p></td>
<td><p>新しくインストールされたユニファイド メッセージング サーバーを、着信通話に応答および着信通話を処理できるようにするには、ユニファイド メッセージング サーバーを UM ダイヤル プランに追加しなければなりません。 このケースの場合、サーバーを Exchange UM SIP ダイヤル プランに追加してください。</p></td>
<td><p>管理者</p>
<p>Exchange Server 管理者</p></td>
<td><p>Exchange 2007 SP1 または最新 Service Pack の場合は、「ユニファイド メッセージング サーバーをダイヤル プランに追加する方法」(<a href="http://go.microsoft.com/fwlink/?linkid=268681%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=268681&amp;clcid=0x411</a>) を参照してください。</p>
<p>Exchange 2010 または最新 Service Pack の場合は、「UM サーバーのプロパティの表示または構成」(<a href="http://go.microsoft.com/fwlink/?linkid=268682%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=268682&amp;clcid=0x411</a>) を参照してください。</p>
<p></p>
<p>Exchange 2013 の場合は、「ユニファイド メッセージング」(<a href="http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=266579&amp;clcid=0x411</a>) を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>SIP アドレスでメールボックスを構成します。</p></td>
<td><p>Exchange UM 機能を利用するであろうエンタープライズ VoIP ユーザーのメールボックスに、SIP アドレスを割り当てます。</p></td>
<td><p>Lync Server 2013 管理者</p>
<p>Exchange 受信者管理者</p></td>
<td><p>Exchange 2007 SP1 または最新 Service Pack の場合は、「UM が有効なユーザーの SIP アドレスを追加、削除、変更する方法」(<a href="http://go.microsoft.com/fwlink/?linkid=268698%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=268698&amp;clcid=0x411</a>) を参照してください。</p>
<p>Exchange 2010 または最新 Service Pack の場合は、「UM が有効なユーザーの SIP アドレスを変更する」(<a href="http://go.microsoft.com/fwlink/?linkid=268699%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=268699&amp;clcid=0x411</a>) を参照してください。</p>
<p></p>
<p>Exchange 2013 の場合は、「ユニファイド メッセージング」(<a href="http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=266579&amp;clcid=0x411</a>) を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>exchucutil.ps1 スクリプトを実行します。</p></td>
<td><p>Exchange UM サービスを実行しているサーバーで、Exchange 管理シェルを開き、exchucutil.ps1 スクリプトを実行します。このスクリプトは次の処理を行います。</p>
<ul>
<li><p>Exchange UM  Active Directory ドメイン サービス オブジェクト (具体的には、前の作業で作成した SIP ダイヤル プラン) の読み取りに必要な Lync Server 2013 のアクセス許可を付与します。</p></li>
<li><p>エンタープライズ VoIP に対して有効化されているユーザーをホストする各 Lync Server 2013 Enterprise Edition プールまたは Standard Edition サーバーのユニファイド メッセージング IP ゲートウェイ オブジェクトを Active Directory に作成します。</p></li>
<li><p>各ゲートウェイの Exchange UM ハント グループを作成します。ハント グループのパイロット ID は、対応するゲートウェイに関連付けられたダイヤル プランの名前になります。 複数のダイヤル プランが存在する場合は、これらは 1 対 1 でマップされる必要があります。</p></li>
</ul></td>
<td><p>Exchange 組織管理者</p>
<p>Exchange 受信者管理者</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Lync Server 2013 での Microsoft Exchange のユニファイド メッセージングの構成</a></p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 ダイヤル プランを構成します。</p></td>
<td><p>Exchange 2007 SP1 または最新 Service Pack、あるいは Exchange 2010 と統合されている場合、Exchange UM ダイヤル プランの完全修飾ドメイン名 (FQDN) と一致する名前で新しい エンタープライズ VoIP ダイヤル プランを作成します。</p>

> [!NOTE]
> これを UM ダイヤル プランごとに行う必要があります。

</div>
<p>Exchange 2010 SP1 と統合されている場合は、適したグローバル/サイト レベルの エンタープライズ VoIP ダイヤル プランが構成されていることを確認します。</p>

> [!NOTE]
> Exchange 2010 SP1 と統合されている場合、Lync Server ダイヤル プラン名および Exchange UM SIP ダイヤル プラン名が一致する必要はありません。

</div></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-dial-plans.md">Lync Server 2013 でのダイヤル プランの構成</a></p></td>
</tr>
<tr class="odd">
<td><p>Exchange UM 統合ツールを実行します。</p></td>
<td><p>Lync Server 2013 で、<strong>ocsumutil.exe</strong> を実行します。次の作業が行われます。</p>
<ul>
<li><p>サブスクライバー アクセスおよび自動応答連絡先オブジェクトを作成します。</p></li>
<li><p>Exchange UM ダイヤル プランの FQDN と一致する名前の エンタープライズ VoIP ダイヤル プランの存在を確認します。Exchange 2010 SP1 以降を実行している場合、ダイヤル プラン名が一致する必要はないので、これに関するツールの警告は無視してください。</p></li>
</ul>
<p>このツールは、Exchange UM 設定の Active Directory をスキャンし、Lync Server 2013 管理者による連絡先オブジェクトの表示、作成、および編集ができるようにすることで機能します。</p></td>
<td><p>RTCUniversalServerAdmins および RTCUniversalUserAdmins</p>
<div>

> [!IMPORTANT]
> ocsumutil.exe を正常に実行するため、ユーザーはこれらのグループの両方に属していなければなりません。



> [!NOTE]
> 連絡先オブジェクトを作成するには、ocsumutil.exe を実行するユーザーが、新しい連絡先オブジェクトが保存される Active Directory 組織単位 (OU) への適切なアクセス許可を持たなければなりません。このアクセス許可は、<strong>Grant-CsOUPermission</strong> コマンドレットを実行することで付与されます。詳細については、Lync Server 管理シェルのドキュメントを参照してください。

</div></td>
<td><p><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Microsoft Exchange Server のユニファイド メッセージングと連動させるための Lync Server 2013 の構成</a></p></td>
</tr>
<tr class="even">
<td><p>必要に応じて、その他の エンタープライズ VoIP 構成ステップを実行します。</p></td>
<td><p>サーバーまたはユーザーの エンタープライズ VoIP 設定をまだ構成していない場合、次の 1 つ以上の操作を実行します。</p>
<ul>
<li><p>公衆交換電話網 (PSTN) ゲートウェイ</p>
<p>および仲介サーバーを展開および構成します。</p></li>
<li><p>音声ポリシー、PSTN 使用法レコード、および発信通話ルートを定義します。</p></li>
<li><p>エンタープライズ VoIP に対してユーザーを有効化します。</p></li>
<li><p>必要に応じて、特定のユーザーにダイヤル プランを構成します。</p></li>
</ul>
<p>有効にする エンタープライズ VoIP 機能によっては、その他の構成ステップが必要となる場合があります。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>RTCUniversal-UserAdmins</p></td>
<td><p>次のセクションのトピックを参照してください。</p>
<ul>
<li><p><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Lync Server 2013 での音声ポリシー、PSTN 使用法レコード、およびボイス ルートの構成</a></p></li>
<li><p><a href="lync-server-2013-deploying-enterprise-voice.md">Lync Server 2013 でのエンタープライズ VoIP の展開</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Exchange UM に対してエンタープライズ VoIP ユーザーを有効化します。</p></td>
<td><p>Exchange UM サーバーで、ユニファイド メッセージング メールボックス ポリシーが作成され、各ユーザーに一意の内線番号が割り振られているのを確認してから、ユニファイド メッセージングに対してユーザーを有効化します。</p></td>
<td><p>Exchange 受信者管理者</p></td>
<td><p>Exchange 2007 SP1 または最新 Service Pack の場合は、「ユーザーのユニファイド メッセージングを有効にする方法」(<a href="http://go.microsoft.com/fwlink/?linkid=268700%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=268700&amp;clcid=0x411</a>) を参照してください。</p>
<p>Exchange 2010 または最新 Service Pack の場合は、「ユーザーのユニファイド メッセージングの有効化」(<a href="http://go.microsoft.com/fwlink/?linkid=268701%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=268701&amp;clcid=0x411</a>) を参照してください。</p>
<p></p>
<p>Exchange 2013 の場合は、「ユニファイド メッセージング」(<a href="http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=266579&amp;clcid=0x411</a>) を参照してください。</p></td>
</tr>
</tbody>
</table>

