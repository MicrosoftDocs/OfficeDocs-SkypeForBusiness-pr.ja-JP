---
title: 'Lync Server 2013: サポートされているハイブリッド構成'
description: 'Lync Server 2013: サポートされているハイブリッド構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported hybrid configurations
ms:assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945633(v=OCS.15)
ms:contentKeyID: 51541482
ms.date: 05/10/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a51667a9c10322b4e2503d81c8b3ddb07c17855
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550883"
---
# <a name="supported-lync-server-2013-hybrid-configurations"></a>サポートされている Lync Server 2013 ハイブリッド構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-05-10_

Lync Server 2013 の展開は、Microsoft Exchange Server 2010 と Microsoft Exchange Server 2013 および SharePoint Server (オンプレミスとオンラインの両方) との統合のために構成できます。 次の表に示す機能は、特に指定のない限り、すべてのクライアントでサポートされています。 クライアントサポートの詳細については、「 [client comparison tables For Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md) 」および「skype For business online クライアントでの skype for business online [の](https://go.microsoft.com/fwlink/p/?linkid=281902)クライアントの比較表」を参照してください。

<div>

## <a name="integration-with-exchange-server"></a>Exchange Server との統合

次の表に、Microsoft Exchange Server と統合した場合にハイブリッド展開でサポートされる機能を示します。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>オンプレミスの Exchange</th>
<th>Exchange Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 オンプレミス</strong></p></td>
<td><ul>
<li><p>Outlook での IM/プレゼンス</p>
<p>詳細については、「 <a href="lync-server-2013-im-and-presence.md">Lync Server 2013 の IM とプレゼンス</a>」を参照してください。</p></li>
<li><p>Outlook を使用してオンライン会議のスケジュールを設定して参加する</p>
<p>詳細については、「 <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 の統合</a>」を参照してください。</p></li>
<li><p>Outlook Web App での IM/プレゼンス</p>
<p>詳細については、「 <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">Microsoft Lync Server 2013 をクロスプレミス環境で構成する</a>」を参照してください。</p></li>
<li><p>Outlook Web App を使用したオンライン会議のスケジュールと参加</p></li>
<li><p>モバイルクライアントでの IM/プレゼンス</p></li>
<li><p>モバイルクライアントでのオンライン会議への参加</p>
<p>詳細については、「 <a href="lync-server-2013-deploying-mobility.md">Lync Server でのモビリティの展開 2013</a> 」を参照してください。</p></li>
<li><p>Outlook 予定表の空き時間情報に基づく状態の公開</p></li>
<li><p>連絡先リスト (統合連絡先ストア経由)</p>
<p>詳細については、「 <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Microsoft Lync Server 2013 を構成して統合連絡先ストアを使用する</a>」を参照してください。</p>
<div>

> [!NOTE]  
> Exchange 2013 が必要です。<BR>Lync 2013 デスクトップクライアントが必要です。


</div></li>
<li><p>Lync 2013 クライアントおよび Lync Web App の、高解像度の連絡先写真。</p>
<p>詳細については、「 <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Microsoft Lync Server 2013 で高解像度写真の使用を構成する</a>」を参照してください。</p>
<div>

> [!NOTE]  
> Exchange 2013 が必要です。


</div></li>
<li><p>会議の委任</p>
<p>両方のユーザーが同じフォレストでオンラインになっている場合、または両方のユーザーがオンプレミスに所属している場合にのみサポートされます。</p></li>
<li><p>不在着信した会話の履歴と通話ログはユーザーの exchange メールボックスに書き込まれる</p></li>
<li><p>Exchange のアーカイブコンテンツ (IM および会議)</p>
<p>詳細については、「 <a href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 のアーカイブの展開チェックリスト</a>」を参照してください。</p>
<div>

> [!NOTE]  
> Exchange 2013 が必要です。


</div></li>
<li><p>アーカイブされたコンテンツの検索</p>
<div>

> [!NOTE]  
> Exchange 2013 が必要です。


</div></li>
<li><p>ボイス メール</p>
<p>詳細については、「<a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">オンプレミスの EXCHANGE UM を展開して Lync Server 2013 ボイスメールを提供する</a>」を参照してください。</p></li>
</ul></td>
<td><ul>
<li><p>Outlook での IM/プレゼンス</p>
<p>詳細については、「<a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">オンプレミスの Lync Server 2013 と Exchange Online との統合の構成</a>」を参照してください。</p></li>
<li><p>Outlook を使用してオンライン会議のスケジュールを設定して参加する</p></li>
<li><p>OWA での IM/プレゼンス</p>
<p>詳細については、「<a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">オンプレミスの Lync Server 2013 と Exchange Online との統合の構成</a>」を参照してください。</p></li>
<li><p>Outlook Web App からのオンライン会議のスケジュールと参加</p>
<p>詳細については、「<a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">オンプレミスの Lync Server 2013 と Exchange Online との統合の構成</a>」を参照してください。</p></li>
<li><p>モバイルクライアントでの IM/プレゼンス</p></li>
<li><p>モバイルクライアントでのオンライン会議への参加</p></li>
<li><p>Outlook 予定表の空き時間情報に基づく状態の公開</p></li>
<li><p>連絡先リスト (統合連絡先ストア経由)。 詳細については、「 <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Microsoft Lync Server 2013 を構成して統合連絡先ストアを使用する</a>」を参照してください。</p>
<div>

> [!NOTE]  
> Lync Server 2013 のみ。 Lync 2013 デスクトップクライアントが必要です。


</div></li>
<li><p>Lync 2013 クライアントおよび Lync Web App の、高解像度の連絡先写真。</p>
<p>詳細については、「 <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Microsoft Lync Server 2013 で高解像度写真の使用を構成する</a>」を参照してください。</p></li>
<li><p>会議の委任</p>
<p>両方のユーザーが同じフォレストでオンラインになっている場合、または両方のユーザーがオンプレミスに所属している場合にのみサポートされます。</p></li>
<li><p>不在着信した会話の履歴と通話ログはユーザーの exchange メールボックスに書き込まれる</p></li>
<li><p>Exchange のアーカイブコンテンツ (IM および会議)。</p>
<p>詳細については、「 <a href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 のアーカイブの展開チェックリスト</a>」を参照してください。</p></li>
<li><p>アーカイブされたコンテンツを検索します。 詳細については、「 <a href="https://go.microsoft.com/fwlink/p/?linkid=285448">Configure Exchange For SharePoint EDiscovery Center</a> 」を参照してください。</p></li>
<li><p>ボイスメール 詳細については、「 <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">Lync Server 2013 ユーザーのボイスメールをホストされている EXCHANGE UM で提供</a>する」を参照してください。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Outlook での IM とプレゼンス</p></li>
<li><p>Outlook を使用してオンライン会議のスケジュールを設定して参加する</p></li>
<li><p>モバイルクライアントでの IM/プレゼンス</p></li>
<li><p>不在着信した会話の履歴と通話ログはユーザーの exchange メールボックスに書き込まれる</p></li>
<li><p>Lync 2013 クライアントの高解像度の連絡先写真。</p>
<div>

> [!NOTE]  
> Microsoft Exchange Server 2013 が必要です。 これは、ユーザーが Skype for Business Online に所属している場合、Lync Web App ではサポートされません。


</div></li>
<li><p>モバイルクライアントでのオンライン会議への参加</p></li>
<li><p>Outlook 予定表の空き時間情報に基づく状態の公開</p></li>
<li><p>会議の委任</p>
<p>両方のユーザーが同じフォレストでオンラインになっている場合、または両方のユーザーがオンプレミスに所属している場合にのみサポートされます。</p></li>
</ul></td>
<td><ul>
<li><p>Outlook での IM/プレゼンス</p></li>
<li><p>Outlook を使用してオンライン会議のスケジュールを設定して参加する</p></li>
<li><p>Outlook Web App での IM/プレゼンス</p></li>
<li><p>Outlook Web App からのオンライン会議のスケジュールと参加</p></li>
<li><p>モバイルクライアントでの IM/プレゼンス</p></li>
<li><p>モバイルクライアントでのオンライン会議への参加</p></li>
<li><p>Outlook 予定表の空き時間情報に基づく状態の公開</p></li>
<li><p>不在着信した会話の履歴と通話ログはユーザーの exchange メールボックスに書き込まれる</p></li>
<li><p>連絡先リスト (統合連絡先ストア経由)</p>
<div>

> [!NOTE]  
> Lync Server 2013 クライアントが必要


</div></li>
<li><p>Lync 2013 クライアントおよび Lync Web App の高解像度の連絡先写真</p></li>
<li><p>会議の委任</p>
<p>両方のユーザーが同じフォレストでオンラインになっている場合、または両方のユーザーがオンプレミスに所属している場合にのみサポートされます。</p></li>
<li><p>Exchange のアーカイブコンテンツ (IM および会議)</p></li>
<li><p>アーカイブされたコンテンツの検索</p></li>
<li><p>ボイスメール</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="integration-with-sharepoint"></a>SharePoint との統合

次の表に、SharePoint と統合した場合に Lync Server 2013 ハイブリッド展開でサポートされる機能を示します。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>SharePoint 社内展開</th>
<th>SharePoint Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 オンプレミス</strong></p></td>
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


</div>

</div>

<span> </span>

</div>

</div>

</div>

