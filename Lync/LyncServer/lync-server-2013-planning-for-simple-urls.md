---
title: 'Lync Server 2013: 簡単な URL の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for simple URLs
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398287(v=OCS.15)
ms:contentKeyID: 48183610
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17dbfce9f699f31e09bb66d6d596e0a3cbf0ba96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a>Lync Server 2013 での簡単な URL の計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2015-12-11_

簡単な Url を使用すると、ユーザーは簡単に会議に参加できるようになり、管理者は Lync Server の管理ツールに簡単にアクセスできるようになります。

Lync Server は、次の3つの簡単な Url をサポートします。

  - **会議**は、サイトまたは組織内のすべての会議のベース URL として使用されます。 単純な URL の例を次にhttps://meet.contoso.com示します。 特定の会議の URL は、 https://meet.contoso.com/*ユーザー名*/7322994 の可能性があります。
    
    [会議への参加] の [シンプル URL] を使用すると、会議に参加するためのリンクを簡単に理解して、簡単に連絡して配布することができます。

  - [**ダイヤル**イン] は、ダイヤルイン会議の設定の web ページにアクセスできるようにします。 このページには、会議のダイヤルイン番号が表示されます。このページには、利用可能な言語、割り当てられている会議情報 (スケジュールされていない会議)、会議中の DTMF コントロールが表示され、個人識別番号の管理がサポートされています (PIN) および割り当てられた会議情報。 ダイヤルインの簡易 URL は、会議にダイヤルインするユーザーが必要な電話番号と PIN 情報にアクセスできるように、すべての会議出席依頼に含まれています。 ダイヤルインの簡易 URL の例を次にhttps://dialin.contoso.com示します。

  - **管理者**が Lync Server コントロールパネルにすばやくアクセスできるようにします。 組織のファイアウォール内の任意のコンピューターから、管理者は、ブラウザーに管理者の簡易 URL を入力して Lync Server コントロールパネルを開くことができます。 管理者の簡易 URL は、組織の内部にあります。 管理者簡易 URL の例を次に示します。https://admin.contoso.com

<div>

## <a name="simple-url-scope"></a>単純な URL スコープ

グローバルなスコープを持つように単純な Url を構成することも、組織内のセントラルサイトごとに異なる簡単な Url を指定することもできます。 グローバルスコープの単純な url とサイトスコープの単純な URL の両方が指定されている場合、サイトスコープの単純な url が優先されます。

ほとんどの場合、単純な url の設定はグローバルレベルでのみ行うことをお勧めします。そのため、あるサイトから別のサイトに移動しても、ユーザーの単純な URL が変わらないようにすることをお勧めします。 例外として、さまざまなサイトのダイヤルインユーザーに異なる電話番号を使用する必要がある組織が挙げられます。 1つの単純な URL (ダイヤルインの単純な url など) をサイトレベルの単純な URL として設定する場合は、そのサイトの他の単純な Url もサイトレベルに設定する必要があることに注意してください。

<div>


> [!NOTE]  
> サイトスコープのシンプルな Url を使用するように選択した場合、ユーザーは、スケジュールされたすべての会議を再スケジュールしたときに、サイト間で異なるフロントエンドプール間を移動することはできません。 これには、バックアップリレーションシップのプールが別のサイトにあるというフェイルオーバーシナリオが含まれます。 サイトスコープの単純な Url が展開されているサイト間でフェールオーバーする必要がある場合は、URL のスコープが原因で、ユーザーが会議に参加することはできません。 詳細については、「<A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">ダウンロード</A>」をご覧ください。



</div>

トポロジビルダーでは、グローバルな単純 Url を設定することができます。 サイトレベルで単純な URL を設定するには、Set-CsSimpleURLConfiguration コマンドレットを使用する必要があります。

</div>

<div>

## <a name="naming-your-simple-urls"></a>単純な Url に名前を付ける

簡単な Url に名前を付けるための推奨される3つのオプションがあります。 どちらのオプションを選択するかは、DNS A レコードと単純な Url をサポートする証明書のセットアップ方法によって決まります。 各オプションで、組織内の各 SIP ドメインに対して、単一の会議の単純 URL を構成する必要があります。

使用している SIP ドメインの数に関係なく、ダイヤルイン用の組織全体に、または管理者用に1つだけ簡単な URL を作成する必要があります。

必要な DNS A レコードと証明書の詳細については、「 [Lync server 2013 の単純な url の DNS 要件](lync-server-2013-dns-requirements-for-simple-urls.md)」および「計画ドキュメントの[lync server 2013 の内部サーバーの証明書の要件](lync-server-2013-certificate-requirements-for-internal-servers.md)」を参照してください。

オプション1では、各シンプル URL の新しい SIP ドメイン名を作成します。

このオプションを使用する場合は、各シンプル URL に個別の DNS A レコードが必要です。また、それぞれの [simple URL] を証明書で指定する必要があります。

### <a name="simple-url-naming-option-1"></a>簡単な URL の名前付けオプション1

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>単純な URL</strong></p></td>
<td><p><strong>例</strong></p></td>
</tr>
<tr class="even">
<td><p>即時</p></td>
<td><p>https://meet.contoso.com、 https://meet.fabrikam.comなどの場合 (組織の SIP ドメインごとに1つ)</p></td>
</tr>
<tr class="odd">
<td><p>ダイヤルイン</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>同期</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


オプション2では、ドメイン名 lync.contoso.com に基づいて単純な Url が作成されます。 そのため、3種類の単純な Url をすべて有効にする DNS A レコードは1つだけである必要があります。 この DNS A レコードは lync.contoso.com を参照しています。 さらに、組織内の他の SIP ドメイン用の DNS A レコードも別途必要です。

### <a name="simple-url-naming-option-2"></a>簡単な URL の名前付けオプション2

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>単純な URL</strong></p></td>
<td><p><strong>例</strong></p></td>
</tr>
<tr class="even">
<td><p>即時</p></td>
<td><p>https://lync.contoso.com/Meet、 https://lync.fabrikam.com/Meetなどの場合 (組織の SIP ドメインごとに1つ)</p></td>
</tr>
<tr class="odd">
<td><p>ダイヤルイン</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>同期</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


オプション3は、多数の SIP ドメインを持っていて、それらのユーザーが単純な Url を個別に指定して、DNS レコードと証明書の要件を最小限に抑える必要がある場合に最も役立ちます。

### <a name="simple-url-naming-option-3"></a>簡単な URL の名前付けオプション3

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>単純な URL</strong></p></td>
<td><p><strong>例</strong></p></td>
</tr>
<tr class="even">
<td><p>即時</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>ダイヤルイン</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>同期</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a>単純な URL の名前付けと入力規則

トポロジビルダーと Lync Server 管理シェルコマンドレットでは、単純な Url に対して複数の入力規則を適用します。 会議とダイヤルインのための単純な Url を設定する必要がありますが、管理者用の設定は省略可能です。 各 SIP ドメインは、個別の単純な url を持つ必要がありますが、組織全体に1つのダイヤルインの単純な url と管理者の単純な URL を1つだけ用意する必要があります。

組織内の各単純 URL には一意の名前を指定する必要があります。また、別の単純な URL のプレフィックスとして使用することはできません (たとえば、lync.contoso.com/Meet の単純な url と lync.contoso.com/Meet/Dialin をダイヤルインの単純な URL として設定することはできません)。 単純な URL 名には、任意のプールの FQDN または任意のポート情報を含めることhttps://FQDN:88/meetはできません (たとえば、許可されません)。 すべての単純な Url は、https://プレフィックスで始める必要があります。

単純な Url には、英数字 (a ~ z、A ~ z、0-9、ピリオド (.) のみを含めることができます。 他の文字を使用している場合、単純な Url は期待どおりに動作しない可能性があります。

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a>展開後の単純な Url の変更

最初の展開後に単純な URL を変更する場合は、変更によって、単純な Url の DNS レコードと証明書にどのように影響するかに注意する必要があります。 単純な URL のベースが変更された場合は、DNS レコードと証明書も変更する必要があります。 たとえば、to https://lync.contoso.com/Meet https://meet.contoso.comから MEET.CONTOSO.COM へのベース URL の変更は、lync.contoso.com を参照するように DNS レコードと証明書を変更する必要があるためです。 Simple URL をからhttps://lync.contoso.com/Meetにhttps://lync.contoso.com/Meetings変更した場合、lync.contoso.com のベース url は変わりません。そのため、DNS や証明書の変更は必要ありません。

ただし、単純な URL 名を変更する場合は必ず、各ディレクターとフロントエンドサーバーで [ユーザーの**有効化**] を実行して、変更を登録する必要があります。

</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の簡易 URL の DNS 要件](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

