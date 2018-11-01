---
title: Lync 2013 の互換性
TOCTitle: Lync 2013 の互換性
ms:assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412817(v=OCS.15)
ms:contentKeyID: 52056669
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync 2013 の互換性

 

_**トピックの最終更新日:** 2015-03-09_

このセクションでは、Lync 2013 と、さまざまなバージョンの Microsoft Office スイート、Microsoft Exchange Server、Windows オペレーティング システム、および特定のパブリック インスタント メッセージング (IM) クライアントとの互換性について説明します。

## Office と Lync 2013

次の表に、各バージョンの Office でサポートされている Lync 2013 の機能を示します。

### Lync 2013 と Microsoft Office の互換性

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
<td><p>Outlook の会議の招待 (およびロゴ、ヘルプ URL、免責事項、フッター テキスト) をカスタマイズする</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
</tr>
<tr class="even">
<td><p>Outlook で、会議オプションを構成して、参加者の音声とビデオを既定でミュートにする</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
</tr>
<tr class="odd">
<td><p>Office および Lync で連絡先リストを管理するための統合連絡先ストア</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>はい (Exchange 2013 が必要です)1</p></td>
</tr>
<tr class="even">
<td><p>高解像度画像</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>はい (Exchange 2013 が必要です)1</p></td>
</tr>
<tr class="odd">
<td><p>Office のセットアップ プログラムに統合された Lync 2013 セットアップ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
</tr>
<tr class="even">
<td><p>OneNote 共有メモ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
</tr>
<tr class="odd">
<td><p>PowerPoint プレゼンテーションのコンテンツ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Outlook の &quot;宛先&quot; および &quot;Cc&quot; フィールドのプレゼンス状態</p></td>
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
<td><p>受信した電子メール メッセージのツール バーまたはリボンから、IM または電話で返信</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
<td><p>はい</p></td>
</tr>
<tr class="even">
<td><p>Outlook の &quot;差出人&quot; フィールドのプレゼンス状態</p></td>
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


1 詳細については、「計画」のドキュメントの「[Microsoft Lync Server 2013 および Microsoft Exchange Server 2013 の統合](lync-server-2013-integrating-with-microsoft-exchange-server-2013.md)」を参照してください。

次の機能は、Office 2010 または Office 2013 でのみ使用できます。

  - 拡張オプション付きの連絡先カード (ビデオ通話、デスクトップ共有など)

  - Outlook の \[連絡先の検索\] フィールドのクイック検索

  - \[メール\]、\[予定表\]、\[連絡先\]、および \[仕事\] フォルダーの Outlook ホーム リボンからの IM または通話での返信

  - Outlook の \[To Do バー\] の Lync 連絡先リストを表示

  - Office Backstage (\[ファイル\] タブ) のプレゼンス状態、プログラム共有、およびファイル転送

  - Microsoft Office SharePoint Workspace 2010 (旧 Microsoft Office Groove 2007) の \[プレゼンス\] メニュー

  - \[プレゼンス\] メニューの拡張性

## Exchange Server と Lync 2013

次の表は、各バージョンの Exchange Server に対する Lync 2013 のサポート状況を示します。Extended MAPI 通話を処理するには、クライアント コンピューターに Outlook がインストールされている必要があり、一部の機能は Exchange Web サービス (EWS) を使用する必要があります。

### Lync 2013 と Exchange Server の互換性

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Exchange Server のバージョン</th>
<th>Lync 2013 のサポート状況</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Exchange Server 2013</p></td>
<td><p>Exchange Server 2010 のサポート状況と同じ。統合連絡先ストア、高解像度画像、アーカイブの統合が追加されています。</p>
<div>

> [!NOTE]
> 詳細については、「<a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">Microsoft Lync Server 2013 および Microsoft Exchange Server 2013 の統合</a>」を参照してください。

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


## Windows と Lync 2013

Lync 2013 と Windows のサポートの詳細については、「計画」のドキュメントの「[Lync Server 2013 での Lync クライアント ソフトウェアのサポート](lync-server-2013-lync-client-software-support.md)」を参照してください。

## Macintosh と Lync 2013

Lync Server 2013 は、Macintosh オペレーティング システムを実行するコンピューター上の特定のクライアントをサポートしています。詳細については、「計画」のドキュメントの「[Lync Server 2013 での Lync クライアント ソフトウェアのサポート](lync-server-2013-lync-client-software-support.md)」を参照してください。

## パブリック インスタント メッセージング クライアントと Lync 2013

パブリック IM 接続が使用できるようにサーバーを構成した場合、Lync はパブリック IM ネットワークの次の機能をサポートします。プレゼンス状態は、パブリック IM クライアントでサポートされているものに限定されます。詳細については、「計画」のドキュメントの「[パブリック インスタント メッセージング接続の計画](lync-server-2013-planning-for-public-instant-messaging-connectivity.md)」と、「操作」のドキュメントの「[Lync Server 2013 での組織の外部アクセス ポリシーの管理](lync-server-2013-manage-external-access-policy-for-your-organization.md)」を参照してください。

さらに、Lync Server 2013 の XMPP 統合機能により、ユーザーはインスタント メッセージングとプレゼンス情報を、Google Talk などの XMPP (Extensible Messaging and Presence Protocol) を使用するパブリック IM プロバイダーのユーザーと交換できます。詳細については、「計画」のドキュメントの「[Lync Server 2013 での XMPP (Extensible Messaging and Presence Protocol) フェデレーションの計画](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)」を参照してください。

### Lync 2013 とパブリック IM クライアントの互換性

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
<td><p>IM、基本的なプレゼンス、音声</p></td>
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


\* 音声ビデオは、Windows Live Messenger の最新バージョンでサポートされます。Windows Live Messenger で音声ビデオ フェデレーションを実装する場合は、サーバーの暗号化レベルも変更する必要があります。既定では、暗号化レベルは「必須」です。Lync Server 管理シェルを使用して、この設定を「サポート」に変更する必要があります。


> [!IMPORTANT]
> <UL>
> <LI>
> <P>2012 年 9 月 1 日の時点で、Microsoft Lync パブリック IM 接続のユーザー サブスクリプション ライセンス ("PIC USL") を新規または更新契約で購入できなくなりました。アクティブなライセンスをお持ちのお客様は、サービスの停止日まで Yahoo! Messenger とのフェデレーションを引き続きご利用いただけます。AOL と Yahoo! のサービス終了日は 2014 年 6 月と発表されています。詳しくは、「<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリック インスタント メッセンジャーの接続のサポート</A>」をご覧ください。</P>
> <LI>
> <P>PIC USL は、ユーザー単位および月単位のサブスクリプション ライセンスであり、Lync Server または Office Communications Server と Yahoo! Messenger とのフェデレーションを行うにはこのライセンスが必要です。Microsoft がこのサービスを提供できるのは、Yahoo! からのサポートを条件とするものでしたが、その基盤となる契約の終了が近づいてきました。</P>
> <LI>
> <P>Lync は組織間や世界中のユーザーを接続するための、これまで以上の強力なツールとなります。Windows Live Messenger とのフェデレーションに、Lync Standard CAL 以外のユーザー/デバイス ライセンスを追加する必要はありません。Lync</P></LI></UL>



## 関連項目

#### 概念

[Lync 2013 でのクライアント相互運用性](lync-server-2013-client-interoperability-in-lync-2013.md)  
[Lync Server 2013 での Lync クライアント ソフトウェアのサポート](lync-server-2013-lync-client-software-support.md)  
[Lync Server 2013 の Lync Web App がサポートされるプラットフォーム](lync-server-2013-lync-web-app-supported-platforms.md)  
[Lync Windows ストア アプリの要件](lync-server-2013-lync-windows-store-app-requirements.md)  

#### その他のリソース

[クライアントのシステム要件](lync-server-2013-client-system-requirements.md)

