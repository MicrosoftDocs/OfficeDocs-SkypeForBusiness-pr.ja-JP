---
title: 'Lync Server 2013: Lync 2013 の新しい設定と変更された設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New and changed settings for Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205204(v=OCS.15)
ms:contentKeyID: 48185241
ms.date: 12/08/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675997e815dc80ec173e75ca68358ef23c12f380
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a>Lync 2013 の新しい設定と変更された設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-12-05_

このトピックでは、クライアント管理に直接関連する Lync Server 管理シェルコマンドレットの変更について説明します。 Lync Server 2013 には、いくつかの新しいパラメーターと、他の手段で構成できる機能の deprecates パラメーターが導入されています。

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
<th>新機能</th>
<th>Lync Server Management Shell コマンドレット</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TracingLevel</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>True に設定すると、Lync でソフトウェアのトレースが有効になります。False に設定すると、ソフトウェアのトレースが無効になります。 ソフトウェアトレースには、プログラムで行われるすべての情報 (追跡 API 呼び出しを含む) の詳細な記録が含まれています。 トレースは、ほとんどが開発者やアプリケーションのサポート担当者にとって役立ちます。この設定は、Communications Server 2007 R2 グループポリシー設定&quot;と同じです。 Communicator のトレースを有効にします。&quot;設定は次のとおりです。</p>
<ul>
<li><p>オフ = トレースは無効になり、ユーザーはこの設定を変更できません。</p></li>
<li><p>Light = 最小トレースが実行され、ユーザーはこの設定を変更することはできません。</p></li>
<li><p>On = 詳細トレースが実行され、ユーザーはこの設定を変更できません。</p></li>
</ul>
<p>既定では、TracingLevel は null 値に設定されます。 つまり、最小限のトレースが実行されますが、ユーザーはこの最小トレースを有効または無効にすることができます。</p></td>
</tr>
<tr class="even">
<td><p>EnableMediaRedirection</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>True ($True) に設定すると、オーディオストリームとビデオストリームを他のネットワークトラフィックから分離することができます。これにより、クライアントデバイスはローカルでオーディオとビデオのエンコードとデコードを行うことができます。 メディアのリダイレクションは、一般的に、帯域幅の使用率が低くなり、サーバーのスケーラビリティも高く、デバイスリモート処理やコーデック圧縮などの同様の手法と比較して、最適なユーザーエクスペリエンスを実現します。</p></td>
</tr>
<tr class="odd">
<td><p>AllowLargeMeetings</p></td>
<td><p>CsConferencing</p></td>
<td><p>True に設定すると、すべての Lync 会議が&quot;大規模な会議として扱われます。&quot;大規模な会議では、既定で送信された会議リストのサイズに加えて、参加者に送信される通知の数に制限が適用されます。</p></td>
</tr>
<tr class="even">
<td><p>DisablePowerPointAnnotations</p></td>
<td><p>CsConferencing</p></td>
<td><p>True ($True) に設定すると、ユーザーは会議で使用されている PowerPoint スライドに注釈を追加することはできません。 ただし、(AllowAnnotations プロパティの値によっては)、ユーザーは他の whiteboarding 機能に引き続きアクセスできます。 既定値は False であり、PowerPoint の注釈が許可されていることを意味します。</p></td>
</tr>
<tr class="odd">
<td><p>AllowSharedNotes</p></td>
<td><p>CsConferencing</p></td>
<td><p>True (既定値) に設定すると、会議にリンクされている開いている OneNote ノートブックが、会議の参加者や会議中に共有されたコンテンツに関する詳細などの情報で自動的に更新されます。</p></td>
</tr>
<tr class="even">
<td><p>EnableInviteCustomization</p></td>
<td><p>Cs会議構成</p></td>
<td><p>他の新しい Csmeeting 構成パラメーターと共に使用して、Lync 2013 用のオンライン会議アドインによって生成された会議出席依頼をカスタマイズします。</p></td>
</tr>
<tr class="odd">
<td><p>LogoURL</p></td>
<td><p>Cs会議構成</p></td>
<td><p>Lync 2013 用のオンライン会議アドインによって生成されたすべての招待に、組織のロゴを追加します。 GIF または JPG イメージの URL を指定します。</p></td>
</tr>
<tr class="even">
<td><p>HelpURL</p></td>
<td><p>Cs会議構成</p></td>
<td><p>Lync 2013 用のオンライン会議アドインによって生成されたすべての招待に、組織のヘルプまたはサポート URL を追加します。</p></td>
</tr>
<tr class="odd">
<td><p>LegalURL</p></td>
<td><p>Cs会議構成</p></td>
<td><p>Lync 2013 用のオンライン会議アドインによって生成されたすべての招待状に法的なテキストまたは免責事項を追加します。 テキストの場所の URL を指定します。</p></td>
</tr>
<tr class="even">
<td><p>Customフッターのテキスト</p></td>
<td><p>Cs会議構成</p></td>
<td><p>Lync 2013 用のオンライン会議アドインによって生成されたすべての招待にカスタムフッターを追加します。 ユーザー設定のフッターテキストの場所の URL を指定します。</p></td>
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
<th>Lync Server Management Shell コマンドレット</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CustomizedHelpUrl</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>このパラメーターは、Lync Server 2013 で使用するために廃止されました。 このパラメーターを EnableEnterpriseCustomizedHelp と組み合わせて使うと、ユーザーが Lync の [ヘルプ] メニューをクリックしたときに、カスタマイズされたヘルプが表示されるように、組織が URL を指定することができます。</p></td>
</tr>
<tr class="even">
<td><p>EnableEnterpriseCustomizedHelp</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>このパラメーターは、Lync Server 2013 で使用するために廃止されました。 このパラメーターを CustomizedHelpUrl と組み合わせて使用すると、ユーザー設定のヘルプを表示できます。</p></td>
</tr>
<tr class="odd">
<td><p>EnableSQMData</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>EnableSQMData パラメーターコマンドレットが Lync Server 2013 で削除されました。 代わりに、ソフトウェア品質管理 (SQM) データの共有グループポリシー設定を使用して、Lync クライアントの [全般] オプションページのカスタマーエクスペリエンス向上オプションのユーザーインターフェイスを決定することができます。</p>
<p>HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</p>
<p>Values</p>
<p>1 = チェックボックスを表示して選択する (ユーザーはチェックボックスをオフにすることができます)</p>
<p>0 = チェックボックスをオフにして無効にします (ユーザーは上書きできません)。</p>
<p>Null = 値は Office のセットアップによって決定され、ユーザーが選ぶときに設定できるチェックボックスが表示されます。</p></td>
</tr>
<tr class="even">
<td><p>AllowExchangeContactStore</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>このパラメーターは削除されました。 代わりに、Lync Server 2013 を展開してトポロジを公開すると、統合連絡先ストアは既定ですべてのユーザーに対して有効になります。 これは、すべてのユーザーの連絡先が Exchange に保存され、Lync、Outlook、Outlook Web Access で利用できることを意味します。 設定-Csuserサービスのコマンドレットを使用して、統合連絡先ストアを利用できるユーザーをカスタマイズできます。 ユーザーは、グローバルに、サイト、テナント、または個人またはグループごとに有効にすることができます。 詳細については、「 <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Lync Server 2013 で統合連絡先ストアのユーザーを有効にする</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>MAPIPollInterval</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>このパラメーターは Lync 2013 では使用されません。 以前のリリースでは、クライアントが Exchange パブリックフォルダーから MAPI データを取得する頻度を指定しています。</p></td>
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

