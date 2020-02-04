---
title: 'Lync Server 2013: Lync 2013 でのクライアント相互運用性'
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
ms.openlocfilehash: b28d0de09a46a2be8b968e55c8f551e397da6ae8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a>Lync 2013 でのクライアント相互運用性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-03-04_

このトピックでは、Microsoft Lync Server 2013 クライアントが、以前のバージョンの Lync Server と Office Communications Server からクライアントとの共存と操作を行うことができるようにする機能について説明します。

<div>

## <a name="server-and-client-compatibility"></a>サーバーとクライアントの互換性

次の表は、クライアントバージョンとサーバーバージョンのサポートされる組み合わせを示しています。 次の表は、クライアントが指定したサーバーに接続しようとしたときにサインインがサポートされるかどうかを示します。 Lync Server 2013 では、以前のクライアントバージョンがサポートされています。 また、以前のリリースとは異なり、Lync Server 2010 では新しい Lync 2013 クライアントがサポートされています。 これにより、Lync Server 2010 からアップグレードしている組織は、Lync Server のアップグレードに関係なく、新しいクライアントを展開することができます。


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
<td><p>Supported5</p></td>
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
<td><p>Supported1</p></td>
<td><p>Supported2</p></td>
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
<td><p>Supported3 しない</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable4</p></td>
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


1For については、「 [Lync server 2010、グループチャット、または Office Communications Server 2007 R2 グループチャットから Lync server 2013、常設チャットサーバーへの移行](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)」を参照してください。

2In Lync Server 2010 では、グループチャット機能は、Lync Server 2010 用のサードパーティの信頼済みアプリケーションであるグループチャットサーバーで利用できました。 Lync 2013 クライアントは、Lync Server 2010、グループチャットとは互換性がありません。

3Lync Web App 2013 は、コンピューターの音声やビデオなどの完全な会議エクスペリエンスを提供するようになりました。 Lync 2010 の出席者に代わるものと見なされます。 Lync 2010 出席者は、サポートされていないブラウザー (Internet Explorer 6 または Internet Explorer 7) と Windows XP を使用している場合にのみ Lync Server 2013 に接続します。

4 Office Communicator 2007 R2 のプレゼンス機能と IM 機能は Lync Server 2013 と互換性がありますが、会議機能は使用できません。 Office Communications Server 2007 R2 からの移行中、Office Communicator 2007 R2 はプレゼンスと IM の相互運用性に適していますが、ユーザーは Lync Web App 2013 を使って Lync Server 2013 会議に参加する必要があります。

5制限事項については、このトピックで後述する「lync Server 2010 会議での Lync 2013 クライアントの会議機能のサポート」を参照してください。

</div>

<div>

## <a name="interoperability-among-clients"></a>クライアント間の相互運用性

Lync Server 2013 リリースでは、さまざまなクライアントバージョンがピアツーピアと会議の両方のシナリオでシームレスに対話できます。 このセクションでは、ユーザーがさまざまなバージョンのクライアントとサーバーを使用している他のユーザーと対話する場合の、使用可能な機能について説明します。

<div>

## <a name="peer-to-peer-feature-support"></a>ピアツーピア機能のサポート

ピアツーピア機能は、異なるバージョンのサーバーを使用していて、異なるクライアントバージョンを使っているユーザーに対してサポートされています。 エンドユーザーエクスペリエンスと利用可能な機能は、ユーザーのクライアントの機能と、ユーザーがサインインしているサーバーのバージョンによって一貫しています。 つまり、次のとおりです。

  - ユーザーが古いクライアントを使って Lync Server 2013 にサインインしている場合、ユーザーの使用経験は同じになります。 Lync Server 2013 で導入された新機能は、ユーザーのクライアントがアップグレードされるまで使用できません。 例としては、ビデオギャラリービュー、HD ビデオ、更新された PowerPoint 共有、すべての参加者の音声とビデオを会議の入力時にミュートするオプションがあります。 新しい機能については、「 [Lync server 2013 の新しい会議機能](lync-server-2013-new-conferencing-features.md)」と「 [lync server 2013 でのクライアントの新](lync-server-2013-what-s-new-for-clients.md)機能」で説明しています。

  - ユーザーが lync 2013 クライアントを使って Lync Server 2010 にサインインしている場合、lync server 2010 でサポートされていないすべての新機能は、ユーザーが Lync Server 2013 に移動されるまで使用できません。

次の表では、クライアントが Lync Server 2013 または Lync Server 2010 のいずれかにサインインしているピアツーピアセッションの機能の可用性を比較します。

<div>


> [!NOTE]  
> Lync Web App と Lync 2010 の出席者は会議専用クライアントであり、この表には含まれていません。



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
<th>インスタントメッセージ (im)</th>
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
> <P>2012年9月1日以降、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス (PIC USL) は、新規または更新契約の購入に使用できなくなりました。 アクティブなライセンスを持っているお客様は、Yahoo! とのフェデレーションを継続できます。 サービスのシャットダウン日までメッセンジャーを終了します。 AOL および Yahoo! の2014年6月の終了日 が発表されました。 詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</P>
> <LI>
> <P>PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの1か月間のサブスクリプションライセンスです。 Messenger. このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートによって決定されましたが、その基となる契約は更新されません。</P>
> <LI>
> <P>Lync は、組織間、および世界各地の個人と接続するための強力なツールです。 Windows Live Messenger とのフェデレーションには、Lync 標準 CAL 以外の追加のユーザー/デバイスライセンスは必要ありません。 Skype federation はこのリストに追加されるため、Lync ユーザーは IM や音声を通じて数百人の何百万ものユーザーに連絡できます。</P></LI></UL>



</div>

1 Office Communicator 2007 R2 では、デスクトップ共有 (プログラムによる共有ではない) のみを使用できます。

<div>


> [!NOTE]  
> Skype for Business 2015 クライアントのユーザーインターフェイスが適用されている場合、Office Communicator 2007 R2 と Skype for Business 2015 の間のデスクトップ共有を新しいクライアントから開始することはできません。



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a>Lync Server 2010 会議での Lync 2013 クライアントの会議機能のサポート

Lync 2013 クライアントを使って Lync Server 2010 会議に参加している場合、lync 2013 クライアントの機能にアクセスできますが、次の例外があります。

  - [会議] ウィンドウの [連絡先] アイコンをポイントしてアクセスできる**参加者**の管理オプションでは、[**会議 IM**を使わない] オプションは機能しません。

  - ギャラリービューは、ビデオ会議では機能しません。 ユーザーは、すべてのスピーカーではなく、アクティブなスピーカーのみを表示します。 [**レイアウトの選択**] オプションの一覧で、**ギャラリービュー**を使用できない

  - 参加者リストは、ビデオ会議の既定で表示されます。

  - [参加者] リストでユーザーを右クリックすると、[**ビデオスポットライトをロック**する] と [**ギャラリーに参加するための Pin** ] オプションは使用できません。

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a>Lync Server 2013 会議での会議機能のサポート

Lync Server 2013 には、アカウントを Lync Server 2013 に移行した後でユーザーが利用できる新しい会議機能が用意されています。また、lync 2013 クライアントでサインインします。 例としては、ビデオギャラリービュー、HD ビデオ、PowerPoint 共有、すべての出席者の音声とビデオを会議の入力時にミュートするオプションがあります。 新しい機能については、「 [Lync server 2013 の新しい会議機能](lync-server-2013-new-conferencing-features.md)」と「 [lync server 2013 でのクライアントの新](lync-server-2013-what-s-new-for-clients.md)機能」で説明しています。

Lync Server 2013 会議では、特定の会議機能が、さまざまなバージョンのサーバーを使用していて、異なるクライアントとクライアントバージョンを使っているユーザーがサポートしています。 クライアントが Lync Server 2013 会議に参加すると、ユーザーは次の表に示す機能にアクセスできます。


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
<td><p>Yes2</p></td>
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


1 Office Communicator 2007 R2 では、デスクトップ共有 (プログラムによる共有ではない) のみを使用できます。

2 Lync Server 2013 では、PowerPoint ファイルをアップロードするためのメカニズムが更新されています。 Lync Server 2010 でスケジュールされていた会議に参加した lync Web App ユーザーは、PowerPoint プレゼンテーションを表示したり、移動したりすることはできますが、PowerPoint ファイルをアップロードすることはできません。

3 lync Server 2013 で会議がスケジュールされていて、PowerPoint スライドが Lync 2013 クライアントによってアップロードされている場合、Lync 2010 ユーザーは、スライドへの表示のみのアクセス権を持っています。 これに対して、PowerPoint スライドが Lync 2010 ユーザーによってアップロードされた場合、Lync Server 2013 ユーザーは表示およびスライドにアクセスできます。また、Office Web Apps サーバーが構成されている場合は、高解像度のディスプレイ、アニメーション、スライドの画面切り替えなどの新しい機能にアクセスできます。埋め込みビデオ。 詳細については、「 [Office Web Apps サーバーおよび Lync server 2013 との統合を構成する](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。

4 Office Communicator 2007 R2 のプレゼンス機能と IM 機能は Lync Server 2013 と互換性がありますが、会議機能は使用できません。 Office Communications Server 2007 R2 からの移行中、Office Communicator 2007 R2 はプレゼンスと IM の相互運用性に適していますが、ユーザーは Lync Web App 2013 を使って Lync Server 2013 会議に参加する必要があります。

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a>アドインのサポートのスケジュール

各種のスケジュールアドインに対するサーバーのサポートは、サーバーとクライアントのバージョンの互換性と一貫性があります。 一般的に、次のスケジュールのアドインは Lync Server 2013 でサポートされています。 ただし、以前のバージョンのアドインでは、会議エントリにあるすべての出席者の音声とビデオをミュートするオプションなどの新しい Lync 2013 アドイン機能は提供されていません。

  - **Lync 2013**   用のオンライン会議アドインは、lync 2010 用のオンライン会議アドインと同じ機能を備えており、出席者の音声とビデオが既定でミュートになっている会議のスケジュールを設定することができます。 管理者は、カスタムロゴ、サポート URL、法的免責事項 URL、またはカスタムフッターテキストを追加して、組織の会議出席依頼をカスタマイズすることもできます。

  - **Lync 2010**   用のオンライン会議アドインは、lync 会議のスケジュールを提供し、Office Live Meeting 会議のスケジュール機能を削除します。

  - **Office communicator 2007 R2 会議アドイン**   は、office Live Meeting 会議と office Communicator 2007 R2 会議の両方のスケジュールを提供します。 

<div>


> [!NOTE]  
> Lync Server 2013 で Live Meeting の会議をスケジュールすることはできません。



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
<th>クライアントのスケジュール</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013 用のオンライン会議アドイン (Office 2013、Outlook 2010、Outlook 2007 で使用可能)</p></td>
<td><p>サポート対象</p></td>
<td><p>サポートされています (新しいアドイン機能は使用できません)</p></td>
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


</div>

<div>

## <a name="support-for-joining-meetings"></a>会議への参加のサポート

Lync Server 2013 でサポートされているすべてのクライアントは、Lync 2013 会議に参加することができます。 Lync Web App はサーバーの Web コンポーネントであるため、lync Web App を使って Lync Server 2013 会議に参加している場合は、新しいバージョンの Lync Web App が常に使用されます。

Lync 2013 クライアントは、スケールダウン機能を使用して、Lync 2010 および Office Communications Server 2007 R2 でホストされている会議に参加できます。 会議中機能は、会議がホストされているサーバーのバージョンによって制限されます。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の lync Windows ストアアプリの要件](lync-server-2013-lync-windows-store-app-requirements.md)  
[Lync Server 2013 の新しい会議機能](lync-server-2013-new-conferencing-features.md)  
[Lync Server 2013 のクライアント向けの新機能](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

