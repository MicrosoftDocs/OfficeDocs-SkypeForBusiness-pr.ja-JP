---
title: 'Lync Server 2013: Lync 2013 の互換性'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync 2013 compatibility
ms:assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412817(v=OCS.15)
ms:contentKeyID: 51541502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af2c342e894fc15fe81ba4651ca66b5293d11c9a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151297"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-2013-compatibility"></a>Lync 2013 の互換性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-10-07_

このセクションでは、Microsoft Office スイート、Microsoft Exchange Server、Windows オペレーティングシステム、および選択されているパブリックインスタントメッセージング (IM) クライアントのさまざまなバージョンとの Lync 2013 の互換性について説明します。

<div>

## <a name="office-and-lync-2013"></a>Office および Lync 2013

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
<th>Microsoft Office 2003 と Service Pack 3 (SP3) (必須) または最新のサービス パック (推奨)</th>
<th>Microsoft Office 2007</th>
<th>Microsoft Office 2010</th>
<th>Microsoft Office 2013</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Outlook の会議出席依頼をカスタマイズする (ロゴ、ヘルプ URL、免責事項、フッターテキストの追加)</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
</tr>
<tr class="even">
<td><p>Outlook で、既定で出席者の音声とビデオをミュートするように会議オプションを構成します。</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
</tr>
<tr class="odd">
<td><p>Office と Lync で連絡先リストを管理するための統合連絡先ストア</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>はい (Exchange 2013 が必要) 1</p></td>
</tr>
<tr class="even">
<td><p>高解像度画像</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>はい (Exchange 2013 が必要) 1</p></td>
</tr>
<tr class="odd">
<td><p>Office セットアッププログラムに統合された Lync 2013 セットアップ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
</tr>
<tr class="even">
<td><p>OneNote 共有ノート</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
</tr>
<tr class="odd">
<td><p>PowerPoint プレゼンテーションコンテンツ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Outlook の "宛先" および "Cc" フィールドのプレゼンス状態</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
</tr>
<tr class="odd">
<td><p>状態メニューから電話会議で返信</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>はい (連絡先カードから)</p></td>
<td><p>はい (連絡先カードから)</p></td>
</tr>
<tr class="even">
<td><p>[スケジュール アシスタント] タブの会議出席依頼のプレゼンス状態</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
</tr>
<tr class="odd">
<td><p>受信した電子メールメッセージのツールバーまたはリボンから、IM または通話に返信する</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
</tr>
<tr class="even">
<td><p>Outlook の "差出人" フィールドのプレゼンス状態</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
</tr>
<tr class="odd">
<td><p>状態メニューから IM または音声で返信</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>はい (連絡先カードから)</p></td>
<td><p>はい (連絡先カードから)</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Word および Microsoft Excel ファイルの IM およびプレゼンス表示 (スマート タグが有効)</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>Microsoft Word のみ</p></td>
<td><p>Microsoft Word のみ</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft SharePoint サイトの IM およびプレゼンス表示 (Outlook のインストールが必要)</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
</tr>
</tbody>
</table>


1詳細については、「計画」のドキュメントの「 [Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 の統合](lync-server-2013-integrating-with-microsoft-exchange-server-2013.md)」を参照してください。

次の機能は、Office 2010 または Office 2013 でのみ使用できます。

  - 拡張オプションを備えた連絡先カード (ビデオ通話、デスクトップ共有など)

  - Outlook の [連絡先の検索] フィールドのクイック検索

  - [メール]、[予定表]、[連絡先]、および [仕事] フォルダーの Outlook ホーム リボンからの IM または通話での返信

  - Outlook To Do バーの Lync 連絡先リスト

  - Office Backstage ([ファイル] タブ) のプレゼンス状態、プログラム共有、およびファイル転送

  - Microsoft Office SharePoint Workspace 2010 (旧 Microsoft Office Groove 2007) の [プレゼンス] メニュー

  - [プレゼンス] メニューの拡張性

</div>

<div>

## <a name="exchange-server-and-lync-2013"></a>Exchange Server および Lync 2013

次の表では、さまざまなバージョンの Exchange Server の Lync 2013 サポートについて説明します。 Extended MAPI 通話を処理するには、クライアント コンピューターに Outlook がインストールされている必要があり、一部の機能は Exchange Web サービス (EWS) を使用する必要があります。

### <a name="lync-2013-and-exchange-server-compatibility"></a>Lync 2013 と Exchange Server の互換性

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Exchange Server のバージョン</th>
<th>Lync 2013 サポート</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Exchange Server 2013</p></td>
<td><p>統合連絡先ストア、高解像度の画像、およびアーカイブ統合を追加した Exchange Server 2010 サポートと同じです。</p>
<div>

> [!NOTE]  
> 詳細については、「 <A href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 の統合</A>」を参照してください。


</div></td>
</tr>
<tr class="even">
<td><p>Exchange Server 2010</p></td>
<td><p>Exchange Server 2007 と同じ (および Exchange の連絡先の同期)</p></td>
</tr>
<tr class="odd">
<td><p>Exchange Server 2007 と Service Pack 1 (SP1) (必須) または最新のサービス パック (推奨)</p></td>
<td><p>次の機能は、EWS を通してのみで使用できます。</p>
<ul>
<li><p>[会話履歴] フォルダーのアイテムを表示または削除</p></li>
<li><p>ボイス メール アイテムの読み取りまたは削除</p></li>
<li><p>拡張空き時間情報と、会議の件名と場所を表示</p></li>
</ul>
<p>パブリック フォルダーは、Exchange Server 2007 と Service Pack 1 (SP1) (必須) または最新のサービス パックまたはリリース (推奨) ではオプションです。</p></td>
</tr>
<tr class="even">
<td><p>Exchange Server 2003</p></td>
<td><p>Outlook MAPI のみ。EWS のみの機能は使用できません (前述のとおり)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="windows-and-lync-2013"></a>Windows および Lync 2013

Lync 2013 および Windows のサポートの詳細については、「計画」のドキュメントの「lync [client software support In Lync Server 2013](lync-server-2013-lync-client-software-support.md) 」を参照してください。

</div>

<div>

## <a name="macintosh-and-lync-2013"></a>Macintosh および Lync 2013

Lync Server 2013 は、Macintosh オペレーティングシステムを実行しているコンピューター上の特定のクライアントをサポートします。 詳細については、「計画」のドキュメントの「lync [Server 2013 での lync クライアントソフトウェアサポート](lync-server-2013-lync-client-software-support.md)」を参照してください。

</div>

<div>

## <a name="public-instant-messaging-clients-and-lync-2013"></a>パブリックインスタントメッセージングクライアントと Lync 2013

パブリック IM 接続用にサーバーを構成した場合、Lync はパブリック IM ネットワークで次の機能をサポートします。 プレゼンス状態は、パブリック IM クライアントでサポートされているものに限定されます。 詳細については、「操作」のドキュメントの「計画」のドキュメントと「 [Manage external access policy](lync-server-2013-manage-external-access-policy-for-your-organization.md) in lync server 2013」の「 [lync server 2013 でのパブリックインスタントメッセージング接続の計画](lync-server-2013-planning-for-public-instant-messaging-connectivity.md)」を参照してください。

さらに、Lync Server 2013 の XMPP 統合機能により、ユーザーは、インスタントメッセージとプレゼンス情報を、Google トークなどの拡張可能なメッセージングとプレゼンスプロトコルを使用するパブリック IM プロバイダーのユーザーと交換することができます。 詳細については、「計画」のドキュメントの「 [planning for 拡張メッセージング and プレゼンスプロトコル (XMPP) フェデレーション (Lync Server 2013)](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md) 」を参照してください。

### <a name="lync-2013-and-public-im-clients-compatibility"></a>Lync 2013 とパブリック IM クライアントの互換性

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>クライアント</th>
<th>サポート対象の機能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Live Messenger</p></td>
<td><p>IM、基本的なプレゼンス機能、音声ビデオ (A/V)*</p></td>
</tr>
<tr class="even">
<td><p>Skype</p></td>
<td><p>IM、基本プレゼンス、音声</p></td>
</tr>
<tr class="odd">
<td><p>AOL</p></td>
<td><p>IM と基本的なプレゼンス機能</p></td>
</tr>
<tr class="even">
<td><p>Yahoo!</p></td>
<td><p>IM と基本的なプレゼンス機能</p></td>
</tr>
<tr class="odd">
<td><p>Google Talk</p></td>
<td><p>IM と基本的なプレゼンス機能</p></td>
</tr>
</tbody>
</table>


\*音声ビデオは、最新バージョンの Windows Live Messenger でサポートされています。 Windows Live Messenger で音声ビデオ (A/V) フェデレーションを実装する場合は、サーバーの暗号化レベルも変更する必要があります。 既定では、暗号化レベルは「必須」です。 Lync Server 管理シェルを使用して、この設定を [サポート] に変更する必要があります。

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規購入時または契約の更新時に購入することができなくなりました。 アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。 メッセンジャーサービスが終了するまでの期間。 AOL および Yahoo! の2014年6月の寿命の終了日 が発表されました。 詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</P>
> <LI>
> <P>PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの月ごとのサブスクリプションライセンスです。 Messenger. このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートに応じて決定されました。これは、使用する基礎となる契約です。</P>
> <LI>
> <P>Lync は、組織間や世界中の個人と接続するための強力なツールです。 Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。</P></LI></UL>



</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync 2013 でのクライアントの相互運用性](lync-server-2013-client-interoperability-in-lync-2013.md)  
[Lync Server 2013 での lync クライアントソフトウェアのサポート](lync-server-2013-lync-client-software-support.md)  
[Lync Server 2013 の lync Web App がサポートされているプラットフォーム](lync-server-2013-lync-web-app-supported-platforms.md)  
[Lync Server 2013 の lync Windows ストアアプリの要件](lync-server-2013-lync-windows-store-app-requirements.md)  


[Lync Server 2013 のクライアントシステム要件](lync-server-2013-client-system-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

