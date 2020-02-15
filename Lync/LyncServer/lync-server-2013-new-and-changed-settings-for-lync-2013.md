---
title: 'Lync Server 2013: Lync 2013 の新規および変更された設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New and changed settings for Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205204(v=OCS.15)
ms:contentKeyID: 48185241
ms.date: 12/08/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45282476beac35df7248c4ef6bd04c6642a0f1e2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a>Lync 2013 の新しい設定と変更された設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-12-05_

このトピックでは、クライアント管理に直接関連する Lync Server 管理シェルコマンドレットの変更点について説明します。 Lync Server 2013 には、いくつかの新しいパラメーターと、他の手段で構成できる機能の deprecates パラメータが導入されています。

<div>

## <a name="new-client-management-parameters"></a>新しいクライアント管理パラメーター


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>新</th>
<th>Lync Server 管理シェルコマンドレット</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TracingLevel</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>True に設定すると、Lync でソフトウェアトレースが有効になります。False に設定されている場合、ソフトウェアトレースは無効になります。 ソフトウェアトレースには、プログラムが実行しているすべて (追跡 API 呼び出しを含む) の詳細な記録が保存されます。 トレースは、開発者やアプリケーションサポート担当者にとって主に役立ちます。この設定は、Communications Server 2007 R2 のグループポリシー設定&quot;と同等です。 Communicator のトレースをオンにします。&quot;設定値は次のとおりです。</p>
<ul>
<li><p>Off = トレースは無効になっており、ユーザーはこの設定を変更できません。</p></li>
<li><p>Light = 最小のトレースが実行され、ユーザーはこの設定を変更できません。</p></li>
<li><p>On = 詳細なトレースが実行され、ユーザーはこの設定を変更できません。</p></li>
</ul>
<p>既定では、TracingLevel は null 値に設定されます。 これは、最小限のトレースが実行されることを意味しますが、ユーザーはこの最小限のトレースを有効または無効にすることができます。</p></td>
</tr>
<tr class="even">
<td><p>対して enablemediaredirection</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>True ($True) に設定すると、オーディオおよびビデオストリームが他のネットワークトラフィックから分離されるようになります。これにより、クライアントデバイスはオーディオとビデオをローカルでエンコードおよびデコードできるようになります。 通常、メディアのリダイレクトでは、帯域幅の使用率が低くなり、サーバーのスケーラビリティが向上します。また、デバイスのリモート処理やコーデックの圧縮などの同様の手法と比較して、より最適なユーザーの操作が実現されます。</p></td>
</tr>
<tr class="odd">
<td><p>AllowLargeMeetings</p></td>
<td><p>CsConferencing</p></td>
<td><p>True に設定すると、すべての Lync 会議が&quot;大規模な会議として扱われます。&quot;大規模な会議では、既定で送信される会議名簿のサイズに加えて、参加者に送信される通知の数に制限が適用されます。</p></td>
</tr>
<tr class="even">
<td><p>DisablePowerPointAnnotations</p></td>
<td><p>CsConferencing</p></td>
<td><p>True ($True) に設定すると、ユーザーは会議で使用される PowerPoint スライドにコメントを追加できなくなります。 ただし、AllowAnnotations プロパティの値に応じて、ユーザーは他のホワイトボード機能にアクセスできます。 既定値は False です。これは、PowerPoint の注釈が許可されることを意味します。</p></td>
</tr>
<tr class="odd">
<td><p>AllowSharedNotes</p></td>
<td><p>CsConferencing</p></td>
<td><p>True (既定値) に設定すると、会議にリンクされている開いている OneNote ノートブックはすべて、会議参加者、会議中に共有されるコンテンツの詳細などの情報で自動的に更新されます。</p></td>
</tr>
<tr class="even">
<td><p>EnableInviteCustomization</p></td>
<td><p>Get-csmeetingconfiguration</p></td>
<td><p>他の新しい Csmeeting 構成パラメーターと共に使用して、Lync 2013 用オンラインミーティングアドインによって生成される会議出席依頼をカスタマイズします。</p></td>
</tr>
<tr class="odd">
<td><p>LogoURL</p></td>
<td><p>Get-csmeetingconfiguration</p></td>
<td><p>Lync 2013 用のオンラインミーティングアドインによって生成されたすべての招待に組織のロゴを追加します。 GIF または JPG 画像の URL を指定します。</p></td>
</tr>
<tr class="even">
<td><p>HelpURL</p></td>
<td><p>Get-csmeetingconfiguration</p></td>
<td><p>Lync 2013 用オンラインミーティングアドインによって生成されたすべての招待に組織のヘルプまたはサポート URL を追加します。</p></td>
</tr>
<tr class="odd">
<td><p>LegalURL</p></td>
<td><p>Get-csmeetingconfiguration</p></td>
<td><p>Lync 2013 用オンラインミーティングアドインによって生成されたすべての招待に、法的なテキストまたは免責事項のテキストを追加します。 テキストの場所の URL を指定します。</p></td>
</tr>
<tr class="even">
<td><p>Customフッターテキスト</p></td>
<td><p>Get-csmeetingconfiguration</p></td>
<td><p>Lync 2013 用のオンラインミーティングアドインによって生成されたすべての招待にカスタムフッターを追加します。 カスタムフッターテキストの場所の URL を指定します。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a>非推奨のクライアント管理パラメーター


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>パラメーター</th>
<th>Lync Server 管理シェルコマンドレット</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CustomizedHelpUrl</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>このパラメーターは、Lync Server 2013 で使用するために廃止されました。 このパラメーターを Enableenterprisecustomizedhelp がと組み合わせて使用すると、ユーザーが Lync の [ヘルプ] メニューをクリックしたときに、カスタマイズしたヘルプが表示されるように、組織で URL を指定することができます。</p></td>
</tr>
<tr class="even">
<td><p>Enableenterprisecustomizedhelp が</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>このパラメーターは、Lync Server 2013 で使用するために廃止されました。 このパラメーターを CustomizedHelpUrl と組み合わせて使用すると、カスタマイズされたヘルプを表示することができます。</p></td>
</tr>
<tr class="odd">
<td><p>EnableSQMData</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>EnableSQMData コマンドレットのパラメーターが Lync Server 2013 で削除されました。 代わりに、Software Quality Management (SQM) データの共有グループポリシー設定を使用して、Lync クライアントの [全般オプション] ページの [カスタマーエクスペリエンス向上オプション] のユーザーインターフェイスを決定することができます。</p>
<p>HKEY_CURRENT_USER \Software\Policies\Microsoft\Office\Common\QMEnable</p>
<p>数値</p>
<p>1 = チェックボックスを表示および選択します (ユーザーはチェックボックスをオフにできます)</p>
<p>0 = チェックボックスをオフにし、無効にします (ユーザーは上書きできません)</p>
<p>Null = 値は Office セットアップによって決定され、ユーザーが選択したとおりに設定するためのチェックボックスが表示されます。</p></td>
</tr>
<tr class="even">
<td><p>AllowExchangeContactStore</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>このパラメーターは削除されました。 その代わりに、Lync Server 2013 を展開してトポロジを公開すると、すべてのユーザーに対して統合連絡先ストアが既定で有効になります。 これは、すべてのユーザーの連絡先が Exchange に保持され、Lync、Outlook、および Outlook Web Access で使用できることを意味します。 このコマンドレットを使用して、統合連絡先ストアを使用できるユーザーをカスタマイズできます。 ユーザーをグローバルに、サイト、テナント、または個人または個人のグループごとに有効にすることができます。 詳細については、「 <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Lync Server 2013 の統合連絡先ストアでユーザーを有効にする</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>MAPIPollInterval</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>このパラメーターは Lync 2013 では使用されません。 以前のリリースでは、このパラメーターは、クライアントが Exchange パブリックフォルダーから MAPI データを取得する頻度を指定していました。</p></td>
</tr>
<tr class="even">
<td><p>DisableICE</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>このパラメーターは Lync 2013 で廃止されました。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

