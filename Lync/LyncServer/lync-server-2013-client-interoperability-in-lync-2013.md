---
title: 'Lync Server 2013: Lync 2013 でのクライアント相互運用性'
TOCTitle: Lync 2013 でのクライアント相互運用性
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48271276
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync 2013 でのクライアント相互運用性

 

_**トピックの最終更新日:** 2016-03-04_

ここでは、Microsoft Lync Server 2013 のクライアントと、以前のバージョンの Lync Server および Office Communications Server のクライアントとを共存および連携する機能について説明します。

## サーバーとクライアントの互換性

次の表に、クライアントとサーバーのバージョンどうしの組み合わせでサポートされているものを示します。この表は、示されているサーバーにクライアントが接続しようとするときにサインインがサポートされるかどうかを示します。Lync Server 2013 は以前のバージョンのクライアントをサポートしています。以前のリリースとは異なり、Lync Server 2010 は新しい Lync 2013 クライアントをサポートしているため、Lync Server 2010 からアップグレードする組織は、Lync Server の展開とは無関係に新しいクライアントを導入できます。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>クライアント</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象5</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2013</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendant</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 グループ チャット</p></td>
<td><p>サポート対象1</p></td>
<td><p>サポート対象2</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2010</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendee</p></td>
<td><p>サポート対象外3</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>相互運用可能4</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Office Communications Server 2007 R2 Attendant</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象</p></td>
</tr>
<tr class="even">
<td><p>Office Live Meeting 2007</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象</p></td>
</tr>
<tr class="odd">
<td><p>Lync Windows ストア アプリ</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象外</p></td>
</tr>
</tbody>
</table>


1詳しくは、「[Lync Server 2010、グループ チャットまたは Office Communicatins Server 2007 R2 グループ チャットから Lync Server 2013、常設チャット サーバーへの移行](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)」をご覧ください。

2Microsoft Lync Server 2010 では、Lync Server 2010 用の信頼されたサードパーティ アプリケーションであるグループ チャット サーバーを使用してグループ チャット機能を使用できました。Lync 2013 クライアントは Lync Server 2010、グループ チャットと互換性がありません。

3Lync Web App 2013 は、コンピューターの音声とビデオを含む充実した会議のエクスペリエンスを提供するようになり、Lync 2010 Attendee を置き換えるものとして考えられています。サポート対象外のブラウザー (Internet Explorer 6 または Internet Explorer 7) や Windows XP を使用している場合、Lync 2010 Attendee は Lync Server 2013 のみに接続します。

4Office Communicator 2007 R2 のプレゼンスと IM 機能は Lync Server 2013 と互換性がありますが、会議機能は互換性がありません。Office Communications Server 2007 R2 からの移行中は、プレゼンスと IM を相互運用するのに Office Communicator 2007 R2 が適していますが、ユーザーは Lync Server 2013 会議に参加するのに Lync Web App 2013 を使用する必要があります。

5 制限事項については、このトピックの後半の「Lync Server 2010 会議の Lync 2013 クライアントの会議機能のサポート」をご覧ください。

## クライアント間の相互運用性

Lync Server 2013 リリースでは、ピアツーピアと会議の両方のシナリオで、さまざまなバージョンのクライアントがシームレスにやり取りできます。このセクションでは、別のバージョンのクライアントやサーバーを使用しているユーザーとやり取りするときに利用できる機能について説明します。

## ピアツーピア機能のサポート

ピアツーピア機能は、さまざまなバージョンのサーバーに所属するユーザーや、さまざまなクライアント バージョンを使用するユーザー向けにサポートされています。エンド ユーザー エクスペリエンスと使用できる機能は、ユーザーのクライアントの機能と、ユーザーがサインインするサーバーのバージョンに準じます。つまり、次のとおりです。

  - ユーザーが Lync Server 2013 に以前のクライアントでサインインした場合、ユーザー エクスペリエンスは以前と同じものになります。ユーザーのクライアントがアップグレードされない限り、Lync Server 2013 で導入された新機能は使用できません。このような新機能にはたとえば、ビデオ ギャラリー ビュー、HD ビデオ、PowerPoint 共有、会議のエントリ時にすべての参加者のオーディオとビデオをミュートにするオプションなどがあります。これらの新機能については、「[Lync Server 2013 の新しい会議機能](lync-server-2013-new-conferencing-features.md)」および「[Lync Server 2013 のクライアント向けの新機能](lync-server-2013-what-s-new-for-clients.md)」で簡単に説明されています。

  - ユーザーが Lync Server 2010 に Lync 2013 クライアントでサインインした場合、ユーザーが Lync Server 2013 に移行されない限り、Lync Server 2010 でサポートされていない新機能は使用できません。

次の表は、クライアントが Lync Server 2013 または Lync Server 2010 にサインインした場合にピアツーピア セッションで使用できる機能の比較です。

> [!NOTE]
> Lync Web App と Lync 2010 Attendee は会議専用クライアントで、この表には含まれていません。



<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>クライアント</th>
<th>インスタント メッセージング</th>
<th>プレゼンス</th>
<th>音声</th>
<th>ビデオ</th>
<th>アプリケーション共有</th>
<th>ファイル送信</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendant</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Mobile</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい1</p></td>
<td><p>はい</p></td>
</tr>
<tr class="even">
<td><p>パブリック IM (AOL、Yahoo!)</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>パブリック IM (MSN、Windows Live Messenger)</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>



> [!IMPORTANT]
> <UL>
> <LI>
> <P>2012 年 9 月 1 日の時点で、Microsoft Lync パブリック IM 接続のユーザー サブスクリプション ライセンス (PIC USL) を新規または更新契約において購入することができなくなりました。アクティブなライセンスをお持ちのお客様は、サービスの停止日まで Yahoo! Messenger とのフェデレーションを引き続きご利用いただけます。AOL と Yahoo! に関しては、2014 年 6 月の終了日が発表されています。詳しくは、「<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリック インスタント メッセンジャーの接続のサポート</A>」をご覧ください。</P>
> <LI>
> <P>PIC USL は、ユーザー単位および月単位のサブスクリプション ライセンスであり、Lync Server または Office Communications Server と Yahoo! Messenger とのフェデレーションを行うにはこのライセンスが必要です。Microsoft がこのサービスを提供できるのは、Yahoo! からのサポートを条件とするものでしたが、その基盤となる契約は更新されません。</P>
> <LI>
> <P>Lync は組織間を接続したり世界中のユーザーと接続するための、これまで以上の強力なツールとなります。Windows Live Messenger とのフェデレーションを行うのに、Lync Standard CAL を超えてユーザー/デバイス ライセンスを追加する必要はありません。Skype フェデレーションがこのリストに追加されることで、Lync ユーザーは IM および音声を使用して数億のユーザーにアクセスできます。</P></LI></UL>



1Office Communicator 2007 R2 では、デスクトップ共有 (プログラム共有ではない) のみが使用可能です。

## Lync Server 2010 会議の Lync 2013 クライアントの会議機能のサポート

ユーザーが Lync 2013 クライアントを使って Lync Server 2010 会議に参加すると、Lync 2013 のクライアント機能にアクセスできますが、次のものは含まれません。

  - \[**参加者**\] 管理オプションで、会議ウィンドウの人のアイコンをポイントしてアクセスできる対象を指定するとき、\[**会議 IM を使わない**\] オプションは使用できません。

  - ビデオ会議ではギャラリー ビューを使用できません。ユーザーには、すべての発表者ではなくアクティブな発表者だけが表示されます。\[**レイアウトを選びます**\] では、\[**ギャラリー ビュー**\] は選べません。

  - ビデオ会議では既定で参加者リストが表示されます。

  - 参加者リストのユーザーを右クリックしたときの、\[**ビデオ スポットライトを固定する**\] および \[**ギャラリーに固定します**\] 参加者管理オプションは使用できません。

## Lync Server 2013 会議の機能のサポート

Lync Server 2013 には新しい会議機能が提供されていますが、これらの新機能は、ユーザーのアカウントが Lync Server 2013 に移動され、ユーザーが Lync 2013 クライアントを使用してサインインすると使用できるようになります。このような新機能にはたとえば、ビデオ ギャラリー ビュー、HD ビデオ、PowerPoint 共有、会議のエントリ時にすべての参加者のオーディオとビデオをミュートにするオプションなどがあります。これらの新機能については、「[Lync Server 2013 の新しい会議機能](lync-server-2013-new-conferencing-features.md)」および「[Lync Server 2013 のクライアント向けの新機能](lync-server-2013-what-s-new-for-clients.md)」で簡単に説明されています。

Lync Server 2013 の会議では、さまざまなバージョンのサーバーに所属するユーザーや、さまざまなクライアントとクライアント バージョンを使用するユーザー向けに特定の会議機能がサポートされています。クライアントが Lync Server 2013 の会議に参加すると、ユーザーは次の表に示す機能にアクセスできます。


<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th>クライアント</th>
<th>ピアツーピア IM</th>
<th>音声</th>
<th>ビデオ</th>
<th>アプリケーション共有</th>
<th>PowerPoint</th>
<th>ファイル送信</th>
<th>ホワイトボード</th>
<th>ポーリング</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい2</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい3</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R24</p></td>
<td><p>はい</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


1Office Communicator 2007 R2 では、デスクトップ共有 (プログラム共有ではない) のみが使用可能です。

2Lync Server 2013 では、PowerPoint ファイルをアップロードするための最新のメカニズムを使用しています。Lync Server 2010 上で当初スケジュールされていた会議に参加する Lync Web App ユーザーは、PowerPoint プレゼンテーションの表示およびナビゲーションを行うことができますが、PowerPoint ファイルはアップロードできません。

3 会議が Lync Server 2013 でスケジュールされ、PowerPoint スライドが Lync 2013 クライアントによってアップロードされた場合、Lync 2010 ユーザーはスライドへの表示専用アクセス権を持っています。逆に、PowerPoint スライドが Lync 2010 ユーザーによってアップロードされた場合、Lync Server 2013 ユーザーはスライドを表示することができ、Office Web Apps Server が構成されている場合は、高解像度表示、アニメーション、スライド切り替え、埋め込みビデオなどの新しい機能にアクセスすることもできます。詳しくは、「[Lync Server 2013 と Office Web Apps サーバーの統合の構成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」をご覧ください。

4Office Communicator 2007 R2 のプレゼンスと IM 機能は Lync Server 2013 と互換性がありますが、会議機能は互換性がありません。Office Communications Server 2007 R2 からの移行中は、プレゼンスと IM を相互運用するのに Office Communicator 2007 R2 が適していますが、ユーザーは Lync Server 2013 会議に参加するのに Lync Web App 2013 を使用する必要があります。

## スケジュールのアドインのサポート

スケジュールのさまざまなアドインに対するサーバーのサポートは、サーバーとクライアントのバージョンの互換性に準じます。通常、Lync Server 2013 は以下のスケジュール アドインをサポートしています。ただし、以前のバージョンのアドインは、会議のエントリ時にすべての参加者の音声とビデオをミュートにするオプションなど、Lync 2013 の新しいアドインの機能に対応していません。

  - **Lync 2013 用オンライン ミーティング アドイン** は、Online Meeting Add-in for Lync 2010 と同じ機能を提供します。参加者のミュート コントロールが追加されているため、会議の開催者は参加者の音声とビデオが既定でミュートされた会議をスケジュールできます。管理者は、カスタムのロゴ、サポート URL、法的免責事項 URL、またはカスタムのフッター テキストを追加して、組織の会議出席依頼をカスタマイズすることもできます。

  - **Lync 2010 用オンライン ミーティング アドイン** では、Lync の会議のスケジュール機能が追加され、Office Live Meeting の会議のスケジュール機能が削除されています。

  - **Office Communicator 2007 R2 の会議アドイン** は、Office Live Meeting の会議と Office Communicator 2007 R2 の会議の両方のスケジューリングを提供します。

> [!NOTE]
> Lync Server 2013 では、Live Meeting の会議をスケジュールできません。



<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>スケジュール クライアント</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013 用オンライン ミーティング アドイン (Office 2013、Outlook 2010、および Outlook 2007 と共に使用可能)</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象 (新しいアドイン機能は使用不可)</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Web Scheduler</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 用オンライン ミーティング アドイン</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2 会議アドイン</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象</p></td>
</tr>
</tbody>
</table>


## 会議参加のサポート

Lync Server 2013 がサポートするクライアントはすべて、Lync 2013 の会議に参加できます。Lync Web App はサーバーの Web コンポーネントであるため、Lync Server 2013 の会議に参加するために Lync Web App が使用される場合は、より新しいバージョンの Lync Web App が常に使用されます。

Lync 2013 クライアントは、Lync 2010 と Office Communications Server 2007 R2 でホストされる会議に機能制限付きで参加できます。会議参加機能は、会議がホストされるサーバーのバージョンによって制限されます。

## 関連項目

#### 概念

[Lync Windows ストア アプリの要件](lync-server-2013-lync-windows-store-app-requirements.md)  
[Lync Server 2013 の新しい会議機能](lync-server-2013-new-conferencing-features.md)  
[Lync Server 2013 のクライアント向けの新機能](lync-server-2013-what-s-new-for-clients.md)

