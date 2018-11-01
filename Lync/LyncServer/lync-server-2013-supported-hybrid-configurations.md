---
title: 'Lync Server 2013: サポートされるハイブリッド構成'
TOCTitle: サポートされるハイブリッド構成
ms:assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ945633(v=OCS.15)
ms:contentKeyID: 52056615
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# サポートされる Lync Server 2013 ハイブリッド構成

 

_**トピックの最終更新日:** 2016-12-08_

社内およびオンラインで Microsoft Exchange Server 2010、Microsoft Exchange Server 2013、SharePoint Server の両者と統合するために、Lync Server 2013 の展開を構成できます。次の表に示す機能は、特に注記がない限り、すべてのクライアントでサポートされています。クライアント サポートの詳細については、「[Lync Server 2013 のクライアントの比較表](lync-server-2013-desktop-client-comparison-tables.md)」および「[Lync Online のクライアント](http://go.microsoft.com/fwlink/p/?linkid=281902)」の「Lync Online クライアントの比較表」を参照してください。

## Exchange Server との統合

以下の表に、Microsoft Exchange Server と統合されたハイブリッド展開でサポートされる機能を示します。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>社内の Exchange</th>
<th>Exchange Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>社内の Lync Server 2013</strong></p></td>
<td><ul>
<li><p>Outlook での IM/プレゼンス</p>
<p>詳細については「<a href="lync-server-2013-im-and-presence.md">Lync Server 2013 IM とプレゼンス</a>」を参照してください。</p></li>
<li><p>Outlook を使用したオンライン会議の予約と参加</p>
<p>詳細については「<a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">Microsoft Lync Server 2013 および Microsoft Exchange Server 2013 の統合</a>」を参照してください。</p></li>
<li><p>Outlook Web App での IM/プレゼンス</p>
<p>詳細については「<a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">クロスプレミス環境での Microsoft Lync Server 2013 の構成</a>」を参照してください。</p></li>
<li><p>Outlook Web App を使用したオンライン会議の予約と参加</p></li>
<li><p>モバイル クライアントでの IM/プレゼンス</p></li>
<li><p>モバイル クライアントでのオンライン会議への参加</p>
<p>詳細については「<a href="lync-server-2013-deploying-mobility.md">Lync Server 2013 でのモビリティの展開</a>」を参照してください。</p></li>
<li><p>Outlook カレンダーの空き時間情報に基づく状態の公開</p></li>
<li><p>連絡先リスト (統合連絡先ストア経由)</p>
<p>詳細については、「<a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">統合連絡先ストアを使用する Microsoft Lync Server 2013 の構成</a>」を参照してください。</p>

> [!NOTE]
> Exchange 2013 が必要です。<br />
Lync 2013 デスクトップ クライアントが必要です。

</div></li>
<li><p>Lync 2013 クライアントと Lync Web App での担当者の高解像度写真。</p>
<p>詳細については「<a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Microsoft Lync Server 2013 で高解像度写真を使用する構成</a>」を参照してください。</p>

> [!NOTE]
> Exchange 2013 が必要です。

</div></li>
<li><p>会議の委任</p>
<p>両方のユーザーが同じフォレスト内で常時オンラインである場合、または両方のユーザーが社内に所属する場合にのみサポートされます。</p></li>
<li><p>不在着信した会話の履歴と通話ログはユーザーの Exchange メールボックスに書き込まれます。</p></li>
<li><p>Exchange でのコンテンツのアーカイブ (IM および会議)</p>
<p>詳細については「<a href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 のアーカイブの展開チェックリスト</a>」を参照してください。</p>

> [!NOTE]
> Exchange 2013 が必要です。


> [!NOTE]
> Exchange 2013 が必要です。

</div></li>
<li><p>ボイス メール</p>
<p>詳細については「<a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">内部設置型 Exchange UM を展開して Lync Server 2013 ボイス メールを提供する</a>」を参照してください。</p></li>
</ul></td>
<td><ul>
<li><p>Outlook での IM/プレゼンス</p>
<p>詳細については「<a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">社内の Lync Server 2013 と Exchange Online との統合の構成</a>」を参照してください。</p></li>
<li><p>Outlook を使用したオンライン会議の予約と参加</p></li>
<li><p>OWA での IM/プレゼンス</p>
<p>詳細については「<a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">社内の Lync Server 2013 と Exchange Online との統合の構成</a>」を参照してください。</p></li>
<li><p>Outlook Web App からのオンライン会議の予約と参加</p>
<p>詳細については「<a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">社内の Lync Server 2013 と Exchange Online との統合の構成</a>」を参照してください。</p></li>
<li><p>モバイル クライアントでの IM/プレゼンス</p></li>
<li><p>モバイル クライアントでのオンライン会議への参加</p></li>
<li><p>Outlook カレンダーの空き時間情報に基づく状態の公開</p></li>
<li><p>連絡先リスト (統合連絡先ストア経由)。詳細については、「<a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">統合連絡先ストアを使用する Microsoft Lync Server 2013 の構成</a>」を参照してください。</p>

> [!NOTE]
> Lync Server 2013 のみ。 Lync 2013 デスクトップ クライアントが必要です。

</div></li>
<li><p>Lync 2013 クライアントと Lync Web App での担当者の高解像度写真。</p>
<p>詳細については、「<a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Microsoft Lync Server 2013 で高解像度写真を使用する構成</a>」を参照してください。</p></li>
<li><p>会議の委任</p>
<p>両方のユーザーが同じフォレスト内で常時オンラインである場合、または両方のユーザーが社内に所属する場合にのみサポートされます。</p></li>
<li><p>不在着信した会話の履歴と通話ログはユーザーの Exchange メールボックスに書き込まれます。</p></li>
<li><p>Exchange でのコンテンツのアーカイブ (IM および会議)</p>
<p>詳細については「<a href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 のアーカイブの展開チェックリスト</a>」を参照してください。</p></li>
<li><p>アーカイブされたコンテンツの検索。詳細は、「<a href="http://go.microsoft.com/fwlink/p/?linkid=285448">SharePoint の電子情報開示センター用の Exchange の構成</a>」を参照してください。</p></li>
<li><p>ボイス メール。詳細については、「<a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">Lync Server 2013 ユーザーに Hosted Exchange UM のボイス メールを提供する</a>」を参照してください。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Outlook での IM とプレゼンス</p></li>
<li><p>Outlook を使用したオンライン会議の予約と参加</p></li>
<li><p>モバイル クライアントでの IM/プレゼンス</p></li>
<li><p>不在着信した会話の履歴と通話ログはユーザーの Exchange メールボックスに書き込まれます。</p></li>
<li><p>Lync 2013 クライアントでの担当者の高解像度写真。</p>

> [!NOTE]
> Microsoft Exchange Server 2013 が必要です。ユーザーが Skype for Business Online に属している場合、Lync Web App ではサポートされません。

</div></li>
<li><p>モバイル クライアントでのオンライン会議への参加</p></li>
<li><p>Outlook カレンダーの空き時間情報に基づく状態の公開</p></li>
<li><p>会議の委任</p>
<p>両方のユーザーが同じフォレスト内で常時オンラインである場合、または両方のユーザーが社内に所属する場合にのみサポートされます。</p></li>
</ul></td>
<td><ul>
<li><p>Outlook での IM/プレゼンス</p></li>
<li><p>Outlook を使用したオンライン会議の予約と参加</p></li>
<li><p>Outlook Web App での IM/プレゼンス</p></li>
<li><p>Outlook Web App からのオンライン会議の予約と参加</p></li>
<li><p>モバイル クライアントでの IM/プレゼンス</p></li>
<li><p>モバイル クライアントでのオンライン会議への参加</p></li>
<li><p>Outlook カレンダーの空き時間情報に基づく状態の公開</p></li>
<li><p>不在着信した会話の履歴と通話ログはユーザーの Exchange メールボックスに書き込まれます。</p></li>
<li><p>連絡先リスト (統合連絡先ストア経由)</p>

> [!NOTE]
> Lync Server 2013 クライアント必須

</div></li>
<li><p>Lync 2013 クライアントと Lync Web App での担当者の高解像度写真</p></li>
<li><p>会議の委任</p>
<p>両方のユーザーが同じフォレスト内で常時オンラインである場合、または両方のユーザーが社内に所属する場合にのみサポートされます。</p></li>
<li><p>Exchange でのコンテンツのアーカイブ (IM および会議)</p></li>
<li><p>アーカイブされたコンテンツの検索</p></li>
<li><p>ボイスメール</p></li>
</ul></td>
</tr>
</tbody>
</table>


## SharePoint との統合

以下の表に、SharePoint と統合された Lync Server 2013 ハイブリッド展開でサポートされる機能を示します。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>社内の SharePoint</th>
<th>SharePoint オンライン</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>社内の Lync Server 2013</strong></p></td>
<td><ul>
<li><p>スキル検索</p></li>
<li><p>SharePoint でのプレゼンス</p></li>
</ul></td>
<td><ul>
<li><p>SharePoint でのプレゼンス</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>SharePoint でのプレゼンス</p></li>
</ul></td>
<td><ul>
<li><p>SharePoint でのプレゼンス</p></li>
</ul></td>
</tr>
</tbody>
</table>

