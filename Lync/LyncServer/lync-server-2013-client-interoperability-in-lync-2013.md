---
title: 'Lync Server 2013: Lync 2013 でのクライアントの相互運用性'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69a4616cbe9519a8196ce78e35f21c673a0d2c95
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a>Lync 2013 でのクライアントの相互運用性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-03-04_

このトピックでは、Microsoft Lync Server 2013 クライアントが、以前のバージョンの Lync Server および Office Communications Server のクライアントと共存して対話する機能について説明します。

<div>

## <a name="server-and-client-compatibility"></a>サーバーとクライアントの互換性

次の表に、サポートされるクライアント バージョンとサーバー バージョンの組み合わせを示します。 次の表は、クライアントが指定されたサーバーに接続しようとした場合に、サインインがサポートされるかどうかを示します。 Lync Server 2013 では、以前のクライアントバージョンがサポートされています。 また、以前のリリースとは異なり、Lync Server 2010 は新しい Lync 2013 クライアントをサポートしています。 これにより、Lync server 2010 からアップグレードする組織は、Lync Server のアップグレードに関係なく新しいクライアントをロールアウトすることができます。


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
<td><p>サポート済み</p></td>
<td><p>Supported5</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>サポート済み</p></td>
<td><p>サポート済み</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2013</p></td>
<td><p>サポートされている</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>サポート済み</p></td>
<td><p>サポート済み</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendant</p></td>
<td><p>サポート済み</p></td>
<td><p>サポート済み</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 グループ チャット</p></td>
<td><p>1</p></td>
<td><p>Supported2</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2010</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポートされている</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendee</p></td>
<td><p>Not Supported3</p></td>
<td><p>サポートされている</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable4</p></td>
<td><p>サポート済み</p></td>
<td><p>サポート済み</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Office Communications Server 2007 R2 Attendant</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポート済み</p></td>
<td><p>サポート済み</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポート済み</p></td>
<td><p>サポート済み</p></td>
</tr>
<tr class="even">
<td><p>Office Live Meeting 2007</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポート済み</p></td>
<td><p>サポート済み</p></td>
</tr>
<tr class="odd">
<td><p>Lync Windows ストアアプリ</p></td>
<td><p>サポート済み</p></td>
<td><p>サポート済み</p></td>
<td><p>サポート対象外</p></td>
</tr>
</tbody>
</table>


1For については、「 [Lync server 2010、グループチャットまたは Office Communications server 2007 R2 グループチャットから Lync server 2013、常設チャットサーバーへの移行](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)」を参照してください。

2In Lync Server 2010 では、グループチャットの機能は、Lync Server 2010 用のサードパーティの信頼されたアプリケーションであるグループチャットサーバーで利用できました。 Lync 2013 クライアントは、Lync Server 2010、グループチャットと互換性がありません。

3Lync Web App 2013 には、コンピューターの音声とビデオを含む完全な会議環境が提供されており、Lync 2010 の出席者に代わるものと見なされています。 Lync 2010 出席者は、サポートされていないブラウザー (Internet Explorer 6 または Internet Explorer 7) および Windows XP を使用している場合にのみ Lync Server 2013 に接続します。

4The Communicator 2007 R2 のプレゼンスおよび IM 機能は Lync Server 2013 と互換性がありますが、会議機能はサポートされていません。 Office Communications Server 2007 R2 からの移行時に、Office Communicator 2007 R2 はプレゼンスおよび IM の相互運用性に適していますが、ユーザーは lync Server の2013会議に参加するために Lync Web App 2013 を使用する必要があります。

5制限については、このトピックの後の「Lync Server 2010 会議での Lync 2013 クライアントの会議機能のサポート」を参照してください。

</div>

<div>

## <a name="interoperability-among-clients"></a>クライアント間の相互運用性

Lync Server 2013 リリースでは、さまざまなクライアントバージョンがピアツーピアおよび電話会議の両方のシナリオでシームレスに対話できます。 このセクションでは、別のバージョンのクライアントやサーバーを使用しているユーザーとやり取りするときに利用できる機能について説明します。

<div>

## <a name="peer-to-peer-feature-support"></a>ピアツーピア機能のサポート

ピアツーピア機能は、さまざまなバージョンのサーバーに所属するユーザーや、さまざまなクライアント バージョンを使用するユーザー向けにサポートされています。エンド ユーザー エクスペリエンスと使用できる機能は、ユーザーのクライアントの機能と、ユーザーがサインインするサーバーのバージョンに準じます。つまり、次のとおりです。

  - 以前のクライアントを使用して Lync Server 2013 にサインインしている場合、そのユーザーはと同じ操作を実行できます。 Lync Server 2013 で導入された新機能は、ユーザーのクライアントがアップグレードされるまで使用できません。 例としては、ビデオギャラリービュー、HD ビデオ、更新された PowerPoint 共有、会議エントリ時にすべての参加者の音声とビデオをミュートするオプションなどがあります。 新しい機能については、「 [Lync server 2013 の新しい会議機能](lync-server-2013-new-conferencing-features.md)」と「 [lync server 2013 のクライアント向けの新](lync-server-2013-what-s-new-for-clients.md)機能」に記載されています。

  - Lync 2013 クライアントで Lync Server 2010 にサインインしている場合、lync server 2010 でサポートされていないすべての新機能は、ユーザーが Lync Server 2013 に移行されるまで使用できなくなります。

次の表では、クライアントが Lync Server 2013 または Lync Server 2010 のどちらかにサインインしているピアツーピアセッションでの機能の可用性を比較します。

<div>


> [!NOTE]  
> Lync Web App および Lync 2010 の出席者は、会議専用クライアントであり、この表には含まれていません。



</div>


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
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Mobile</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td></td>
<td></td>
<td></td>
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
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>パブリック IM (MSN、Windows Live Messenger)</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス (PIC USL) は、新規購入または更新契約の購入に使用できなくなりました。 アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。 サービスの終了日までの Messenger。 AOL および Yahoo! の2014年6月の寿命の終了日 が発表されました。 詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</P>
> <LI>
> <P>PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの1か月あたりのサブスクリプションライセンスです。 Messenger. このサービスを提供する Microsoft の機能は、Yahoo! からのサポートを受けています。これは、更新されない基になる契約です。</P>
> <LI>
> <P>Lync は、組織間や世界中の個人と接続するための強力なツールです。 Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。 Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を通じて数十万のユーザーにアクセスできるようになります。</P></LI></UL>



</div>

1 Office Communicator 2007 R2 では、デスクトップ共有のみ (プログラム共有は不可) を使用できます。

<div>


> [!NOTE]  
> Skype for Business 2015 クライアントユーザーインターフェイスが適用されている場合、Office Communicator 2007 R2 と Skype for Business 2015 間のデスクトップ共有を新しいクライアントから開始することはできません。



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a>Lync Server 2010 での Lync 2013 クライアントの会議機能のサポート

ユーザーが lync Server 2010 会議に Lync 2013 クライアントを参加させると、次の例外を除き、Lync 2013 クライアント機能にアクセスすることができます。

  - [**参加者**の管理] オプションでは、会議ウィンドウの [ユーザー] アイコンをポイントすることによってアクセスできます。 [**会議 IM**を利用しない] オプションは機能しません。

  - ギャラリービューは、ビデオ会議では機能しません。 ユーザーには、すべてのスピーカーではなく、アクティブなスピーカーのみが表示されます。 [レイアウトオプションの**選択**] の一覧で、**ギャラリービュー**を使用できません

  - 参加者リストは、既定では、ビデオ会議に表示されます。

  - [参加者] リストでユーザーを右クリックすると、[**ビデオスポットライトをロック**する] および [ギャラリー参加者管理**にピン留めする**] オプションが使用できなくなります。

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a>Lync Server 2013 会議での会議機能のサポート

Lync Server 2013 は、アカウントが Lync Server 2013 に移動され、Lync 2013 クライアントを使用してサインインした後で、ユーザーが利用できるようになる新しい会議機能を提供します。 例としては、ビデオギャラリービュー、HD ビデオ、PowerPoint 共有、会議エントリ時にすべての参加者の音声とビデオをミュートするオプションなどがあります。 新しい機能については、「 [Lync server 2013 の新しい会議機能](lync-server-2013-new-conferencing-features.md)」と「 [lync server 2013 のクライアント向けの新](lync-server-2013-what-s-new-for-clients.md)機能」に記載されています。

Lync Server 2013 の会議では、さまざまなバージョンのサーバーに所属しており、異なるクライアントとクライアントバージョンを使用しているユーザーが、特定の会議機能をサポートしています。 クライアントが Lync Server 2013 会議に参加すると、ユーザーはこの表に示されている機能にアクセスできるようになります。


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
<th>Whiteboard</th>
<th>投票</th>
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
<td><p>Office Communicator 2007 R2 4</p></td>
<td><p>はい</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


1 Office Communicator 2007 R2 では、デスクトップ共有のみ (プログラム共有は不可) を使用できます。

2 Lync Server 2013 は、PowerPoint ファイルをアップロードするための更新されたメカニズムを使用します。 Lync Server 2010 で最初に予約された会議に参加している lync Web App ユーザーは、PowerPoint プレゼンテーションを表示して移動することはできますが、PowerPoint ファイルをアップロードすることはできません。

3 Lync Server 2013 で会議がスケジュールされており、PowerPoint スライドが Lync 2013 クライアントによってアップロードされている場合、Lync 2010 ユーザーはスライドに対して表示専用のアクセス権を持ちます。 反対に、PowerPoint スライドが Lync 2010 ユーザーによってアップロードされている場合、Lync Server 2013 ユーザーは、表示およびスライドし、Office Web Apps サーバーが構成されている場合は、高解像度表示、アニメーション、スライドの切り替え、およびその他の新機能にアクセスすることができます。埋め込みビデオ。 詳細については、「 [Office Web Apps Server および Lync Server 2013 との統合の構成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。

4The Communicator 2007 R2 のプレゼンスおよび IM 機能は Lync Server 2013 と互換性がありますが、会議機能はサポートされていません。 Office Communications Server 2007 R2 からの移行時に、Office Communicator 2007 R2 はプレゼンスおよび IM の相互運用性に適していますが、ユーザーは lync Server の2013会議に参加するために Lync Web App 2013 を使用する必要があります。

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a>スケジュールのアドインのサポート

スケジュールのさまざまなアドインに対するサーバーのサポートは、サーバーとクライアントのバージョンの互換性に準じます。 一般に、Lync Server 2013 では、次のスケジュール設定アドインがサポートされています。 ただし、以前のバージョンのアドインでは、会議の入力時にすべての参加者の音声とビデオをミュートするオプションなど、Lync 2013 アドインの新しい機能は提供されません。

  - **Lync 2013**   用オンラインミーティングアドインは、lync 2010 用オンラインミーティングアドインと同じ機能を提供します。参加者のミュートコントロールを追加すると、会議の開催者は参加者の音声とビデオが既定でミュートされた会議をスケジュールすることができます。 管理者は、カスタムのロゴ、サポート URL、法的免責事項 URL、またはカスタムのフッター テキストを追加して、組織の会議出席依頼をカスタマイズすることもできます。

  - **Lync 2010**   用オンラインミーティングアドインは、lync 会議のスケジュールを提供し、Office Live meeting 会議をスケジュールする機能を削除します。

  - **Office communicator 2007 r2 会議アドイン**   は、office Live Meeting 会議と office Communicator 2007 R2 会議の両方のスケジュールを提供します。 

<div>


> [!NOTE]  
> Live Meeting 会議を Lync Server 2013 でスケジュールすることはできません。



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
<th>スケジュール クライアント</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013 用オンラインミーティングアドイン (Office 2013、Outlook 2010、および Outlook 2007 で使用できます)</p></td>
<td><p>サポート済み</p></td>
<td><p>サポート対象 (新しいアドイン機能は使用不可)</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Web Scheduler</p></td>
<td><p>サポートされている</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="odd">
<td><p>Online Meeting Add-in for Lync 2010</p></td>
<td><p>サポート済み</p></td>
<td><p>サポート済み</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2 会議アドイン</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポート済み</p></td>
<td><p>サポート済み</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a>会議参加のサポート

Lync Server 2013 がサポートするすべてのクライアントは、Lync 2013 会議への参加を許可されます。 Lync web app はサーバーの web コンポーネントであるため、lync Web App を使用して Lync Server 2013 会議に参加している場合は、新しいバージョンの Lync Web App が常に使用されます。

Lync 2013 クライアントは、拡張機能を使用して Lync 2010 および Office Communications Server 2007 R2 でホストされている会議に参加できます。 会議参加機能は、会議がホストされるサーバーのバージョンによって制限されます。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の lync Windows ストアアプリの要件](lync-server-2013-lync-windows-store-app-requirements.md)  
[Lync Server 2013 の新しい会議機能](lync-server-2013-new-conferencing-features.md)  
[Lync Server 2013 のクライアントの新機能](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

