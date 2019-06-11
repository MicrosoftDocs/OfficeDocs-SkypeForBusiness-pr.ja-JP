---
title: 'Lync Server 2013: Lync 2013 の互換性'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync 2013 compatibility
ms:assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412817(v=OCS.15)
ms:contentKeyID: 51541502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e177003efb73cd1e16ae8fd772d579eb222af8bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-2013-compatibility"></a>Lync 2013 の互換性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-10-07_

このセクションでは、さまざまなバージョンの Microsoft Office スイート、Microsoft Exchange Server、Windows オペレーティングシステム、および選択されたパブリックインスタントメッセージング (IM) クライアントでの Lync 2013 の互換性について説明します。

<div>

## <a name="office-and-lync-2013"></a>Office と Lync 2013

次の表では、さまざまなバージョンの Office でサポートされている Lync 2013 機能について説明します。

### <a name="lync-2013-and-microsoft-office-compatibility"></a>Lync 2013 と Microsoft Office の互換性

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>機能</th>
<th>Microsoft Office 2003 Service Pack 3 (SP3) (必須) または最新の Service pack (推奨)</th>
<th>Microsoft Office 2007</th>
<th>Microsoft Office 2010</th>
<th>Microsoft Office 2013</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Outlook の会議の招待 (およびロゴ、ヘルプ URL、免責事項、フッター テキスト) をカスタマイズする</p></td>
<td><p>なし</p></td>
<td><p>なし</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
</tr>
<tr class="even">
<td><p>Outlook で会議オプションを設定して、出席者の音声とビデオを既定でミュートにする</p></td>
<td><p>なし</p></td>
<td><p>なし</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
</tr>
<tr class="odd">
<td><p>Office と Lync の間で連絡先リストを管理するための統合連絡先ストア</p></td>
<td><p>なし</p></td>
<td><p>なし</p></td>
<td><p>いいえ</p></td>
<td><p>○ (Exchange 2013 が必要) 1</p></td>
</tr>
<tr class="even">
<td><p>高解像度の画像</p></td>
<td><p>なし</p></td>
<td><p>なし</p></td>
<td><p>いいえ</p></td>
<td><p>○ (Exchange 2013 が必要) 1</p></td>
</tr>
<tr class="odd">
<td><p>Office セットアッププログラムに統合された Lync 2013 のセットアップ</p></td>
<td><p>なし</p></td>
<td><p>なし</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
</tr>
<tr class="even">
<td><p>OneNote 共有メモ</p></td>
<td><p>なし</p></td>
<td><p>なし</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
</tr>
<tr class="odd">
<td><p>PowerPoint プレゼンテーションのコンテンツ</p></td>
<td><p>なし</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
<td><p>可</p></td>
</tr>
<tr class="even">
<td><p>[Microsoft Outlook] と [Cc] フィールドのプレゼンス状態</p></td>
<td><p>なし</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
<td><p>可</p></td>
</tr>
<tr class="odd">
<td><p>[可用性] メニューから [会議通話で返信する]</p></td>
<td><p>なし</p></td>
<td><p>いいえ</p></td>
<td><p>○ (連絡先カードから)</p></td>
<td><p>○ (連絡先カードから)</p></td>
</tr>
<tr class="even">
<td><p>[スケジュール アシスタント] タブの会議出席依頼のプレゼンス状態</p></td>
<td><p>なし</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
<td><p>可</p></td>
</tr>
<tr class="odd">
<td><p>受信した電子メールメッセージのツールバーまたはリボンから [IM] または [通話] で返信する</p></td>
<td><p>なし</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
<td><p>可</p></td>
</tr>
<tr class="even">
<td><p>Outlook From フィールドのプレゼンス状態</p></td>
<td><p>なし</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
<td><p>可</p></td>
</tr>
<tr class="odd">
<td><p>[使用可能] メニューから IM または音声で返信する</p></td>
<td><p>なし</p></td>
<td><p>いいえ</p></td>
<td><p>○ (連絡先カードから)</p></td>
<td><p>○ (連絡先カードから)</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Word および Microsoft Excel ファイルの IM およびプレゼンス表示 (スマート タグが有効)</p></td>
<td><p>なし</p></td>
<td><p>いいえ</p></td>
<td><p>Microsoft Word のみ</p></td>
<td><p>Microsoft Word のみ</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft SharePoint サイトの IM およびプレゼンス (Outlook のインストールが必要)</p></td>
<td><p>なし</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
<td><p>可</p></td>
</tr>
</tbody>
</table>


1詳細については、計画ドキュメントの「 [Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 の統合](lync-server-2013-integrating-with-microsoft-exchange-server-2013.md)」を参照してください。

次の機能は、Office 2010 または Office 2013 でのみ使用できます。

  - ビデオ通話やデスクトップ共有などの拡張オプションを含む連絡先カード

  - Outlook の [連絡先の検索] フィールドのクイック検索

  - [メール]、[予定表]、[連絡先]、[タスク] の各フォルダーの Outlook の [ホーム] リボンから IM または通話で返信する

  - Outlook の To Do バーの Lync 連絡先リスト

  - Office Backstage ([ファイル] タブ) プレゼンス状態、プログラム共有、ファイル転送

  - Microsoft Office SharePoint Workspace 2010 のプレゼンスメニュー (以前の Microsoft Office Groove 2007)

  - プレゼンスメニューの拡張性

</div>

<div>

## <a name="exchange-server-and-lync-2013"></a>Exchange Server と Lync 2013

次の表では、さまざまなバージョンの Exchange Server での Lync 2013 のサポートについて説明します。 Extended MAPI 通話を処理するには、クライアント コンピューターに Outlook をインストールしておく必要があり、一部の機能には Exchange Web サービス (EWS) が必要です。

### <a name="lync-2013-and-exchange-server-compatibility"></a>Lync 2013 および Exchange Server との互換性

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Exchange Server のバージョン</th>
<th>Lync 2013 のサポート</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Exchange Server 2013</p></td>
<td><p>Exchange Server 2010 のサポートと同じ。統合連絡先ストア、高解像度の図、アーカイブ統合が追加されています。</p>
<div>

> [!NOTE]  
> 詳細については、「<A href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</A>」を参照してください。


</div></td>
</tr>
<tr class="even">
<td><p>Exchange Server 2010</p></td>
<td><p>Exchange Server 2007 のサポートと同じ。 Exchange の連絡先同期が追加されています。</p></td>
</tr>
<tr class="odd">
<td><p>Exchange Server 2007 Service Pack 1 (SP1) (必須) または最新の Service pack (推奨)</p></td>
<td><p>次の機能は、EWS を通してのみ使用できます。</p>
<ul>
<li><p>[会話履歴] フォルダーのアイテムの読み取りまたは削除</p></li>
<li><p>ボイス メール アイテムの読み取りまたは削除</p></li>
<li><p>拡張空き時間情報と、会議の件名と場所の表示</p></li>
</ul>
<p>Exchange Server 2007 のパブリックフォルダーは、Service Pack 1 (SP1) (必須) または最新の Service pack または release (推奨) でオプションです。</p></td>
</tr>
<tr class="even">
<td><p>Exchange Server 2003</p></td>
<td><p>Outlook MAPI のみ。 EWS のみの機能は使用できません (前の行を参照)。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="windows-and-lync-2013"></a>Windows と Lync 2013

Lync 2013 および Windows のサポートのサポートについては、計画ドキュメントの「lync [Server 2013 での lync クライアントソフトウェアのサポート](lync-server-2013-lync-client-software-support.md)」を参照してください。

</div>

<div>

## <a name="macintosh-and-lync-2013"></a>Macintosh および Lync 2013

Lync Server 2013 は、Macintosh オペレーティングシステムを実行しているコンピューター上の特定のクライアントをサポートしています。 詳細については、計画ドキュメントの「lync [Server 2013 での lync クライアントソフトウェアのサポート](lync-server-2013-lync-client-software-support.md)」を参照してください。

</div>

<div>

## <a name="public-instant-messaging-clients-and-lync-2013"></a>パブリックインスタントメッセージングクライアントと Lync 2013

パブリック IM 接続用にサーバーを構成している場合、Lync はパブリック IM ネットワークで次の機能をサポートします。 プレゼンス状態は、パブリック IM クライアントでサポートされているプレゼンス状態にフィルター処理されます。 詳細については、「ドキュメントの計画」の「 [Lync server 2013 でのパブリックインスタントメッセージング接続の計画](lync-server-2013-planning-for-public-instant-messaging-connectivity.md)」および「操作のドキュメント」の「 [lync server 2013 での外部アクセスポリシーの管理](lync-server-2013-manage-external-access-policy-for-your-organization.md)」を参照してください。

さらに、Lync Server 2013 の XMPP 統合機能を使用すると、ユーザーは、拡張メッセージングとプレゼンスプロトコル (Google Talk など) を使用するパブリック IM プロバイダーのユーザーとインスタントメッセージとプレゼンス情報を交換することができます。 詳細については、計画ドキュメントの[Lync Server 2013 での拡張メッセージングとプレゼンスプロトコル (XMPP) フェデレーションの計画](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)」を参照してください。

### <a name="lync-2013-and-public-im-clients-compatibility"></a>Lync 2013 およびパブリック IM クライアントの互換性

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>クライアント</th>
<th>サポートされる機能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Live Messenger</p></td>
<td><p>IM、基本的なプレゼンス、音声/ビデオ (A/V) *</p></td>
</tr>
<tr class="even">
<td><p>Skype</p></td>
<td><p>IM、基本的なプレゼンス、オーディオ</p></td>
</tr>
<tr class="odd">
<td><p>AOL</p></td>
<td><p>IM と基本的なプレゼンス</p></td>
</tr>
<tr class="even">
<td><p>Yahoo!</p></td>
<td><p>IM と基本的なプレゼンス</p></td>
</tr>
<tr class="odd">
<td><p>Google Talk</p></td>
<td><p>IM と基本的なプレゼンス</p></td>
</tr>
</tbody>
</table>


\*Windows Live Messenger の最新バージョンでは、A/V がサポートされています。 Windows Live Messenger との間で音声/ビデオ (A/V) フェデレーションを実装している場合は、サーバーの暗号化レベルも変更する必要があります。 既定では、暗号化レベルは "必須" です。 Lync Server 管理シェルを使用して、この設定を [サポート] に変更する必要があります。

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012年9月1日以降、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規または更新契約の購入に使用できなくなりました。 アクティブなライセンスを持っているお客様は、Yahoo! とのフェデレーションを継続できます。 サービスが終了するまでの Messenger。 AOL および Yahoo! の2014年6月の終了日 が発表されました。 詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</P>
> <LI>
> <P>PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要な1か月あたりのユーザーごとのサブスクリプションライセンスです。 Messenger. このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートによって決定されたものであり、その基となる契約は "巻停止" となります。</P>
> <LI>
> <P>Lync は、組織間、および世界各地の個人と接続するための強力なツールです。 Windows Live Messenger とのフェデレーションには、Lync 標準 CAL 以外の追加のユーザー/デバイスライセンスは必要ありません。</P></LI></UL>



</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync 2013 でのクライアント相互運用性](lync-server-2013-client-interoperability-in-lync-2013.md)  
[Lync Server 2013 での lync クライアントソフトウェアのサポート](lync-server-2013-lync-client-software-support.md)  
[Lync Web App が Lync Server 2013 用にサポートされているプラットフォーム](lync-server-2013-lync-web-app-supported-platforms.md)  
[Lync Server 2013 の lync Windows ストアアプリの要件](lync-server-2013-lync-windows-store-app-requirements.md)  


[Lync Server 2013 のクライアントシステム要件](lync-server-2013-client-system-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

