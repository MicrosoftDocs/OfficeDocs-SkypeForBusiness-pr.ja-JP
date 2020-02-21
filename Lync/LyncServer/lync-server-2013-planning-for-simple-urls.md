---
title: 'Lync Server 2013: 簡単な Url の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for simple URLs
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398287(v=OCS.15)
ms:contentKeyID: 48183610
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6bbbe8650ae1d7746c9b87ecf4518236f8b1575
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201873"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a>Lync Server 2013 での簡単な Url の計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-12-11_

簡易 Url を使用すると、ユーザーの会議への参加が容易になり、管理者が Lync Server 管理ツールをより簡単に利用できるようになります。

Lync Server は、次の3つの簡単な Url をサポートします。

  - **Meet**は、サイトまたは組織内のすべての電話会議のベース URL として使用されます。 簡単な会議 URL の例を次https://meet.contoso.comに示します。 特定の会議の URL は、 https://meet.contoso.com/*ユーザー名*/7322994 の場合があります。
    
    簡単な会議 URL を使用すると、会議に参加するためのリンクが覚えやすくなり、通知も配布も簡単になります。

  - **ダイヤル**インは、ダイヤルイン会議設定 web ページへのアクセスを有効にします。 このページには、使用可能な言語で会議のダイヤルイン番号、割り当てられている会議情報 (スケジュールする必要がない会議の場合)、および会議中の DTMF コントロールを表示し、個人識別番号の管理をサポートしています (PIN) と割り当てられている会議情報。 ダイヤルインの簡易 URL は、すべての会議出席依頼に含まれているため、会議にダイヤルインするユーザーは必要な電話番号と PIN 情報にアクセスできます。 ダイヤルインの簡易 URL の例をhttps://dialin.contoso.com次に示します。

  - **管理者**は、Lync Server コントロールパネルにすばやくアクセスできます。 組織のファイアウォール内の任意のコンピューターから、管理者は管理者の簡易 URL をブラウザーに入力して Lync Server コントロールパネルを開くことができます。 簡単な管理 URL は、組織内部の URL です。 管理簡易 URL の例を次に示します。https://admin.contoso.com

<div>

## <a name="simple-url-scope"></a>簡易 URL の範囲

簡単な Url をグローバルスコープに構成することも、組織内の中央サイトごとに異なる簡単な Url を指定することもできます。 グローバルスコープの単純な URL とサイトスコープの単純な url の両方が指定されている場合は、サイトスコープの簡易 url が優先されます。

ほとんどのケースでは、簡易 URL はグローバル レベルだけで設定することをお勧めします。そうしておけば、ユーザーがサイト間で移動した場合に、ユーザーの簡単な会議 URL が変更される心配がなくなります。ただし、これは、各サイトのダイヤルイン ユーザーごとに別々の電話番号を使用する必要がある組織には該当しません。あるサイトで任意のタイプの簡易 URL (簡単なダイヤルイン URL など) をサイト レベルの簡易 URL として設定すると、そのサイトでは残りの 2 つの簡易 URL もサイト レベルで設定する必要があることに注意してください。

<div>


> [!NOTE]  
> サイトスコープの簡易 Url を使用することを選択した場合、ユーザーはサイトごとに異なるサイトのフロントエンドプール間で移動することはできません。これらのユーザーは、会議の簡単な Url がサイトによって異なるので、予定されているすべての会議を再スケジュールします。 これには、バックアップ関係のプールが別のサイトに存在するフェールオーバーのシナリオが含まれます。 サイトスコープの簡易 Url が展開されているサイト間でフェールオーバーする必要がある場合は、URL のスコープによって、ユーザーは会議に参加できません。 詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>」を確認してください。



</div>

トポロジビルダーでは、グローバルな簡易 Url を設定できます。 サイト レベルで簡易 URL を設定するには、Set-CsSimpleURLConfiguration コマンドレットを使用します。

</div>

<div>

## <a name="naming-your-simple-urls"></a>簡易 URL の命名

簡易 URL の命名には、推奨される 3 つのオプションがあります。選択するオプションによって、簡易 URL をサポートする DNS A レコードと証明書の設定方法が影響を受けます。各オプションでは、組織内の SIP ドメインごとに簡単な会議 URL を 1 つ構成する必要があります。

簡単なダイヤルインおよび管理 URL については、所有している SIP ドメインの数とは関係なく、組織全体で必要な数は、常に 1 つだけです。

必要な DNS A レコードおよび証明書の詳細については、「計画」のドキュメントの「 [Lync server 2013 の簡易 url の DNS 要件](lync-server-2013-dns-requirements-for-simple-urls.md)」および「 [lync server 2013 の内部サーバーの証明書要件](lync-server-2013-certificate-requirements-for-internal-servers.md)」を参照してください。

オプション 1 では、簡易 URL ごとに、新しい SIP ドメイン名を作成します。

このオプションを使用する場合は、簡易 URL ごとに独立した DNS A レコードが必要であり、証明書で各簡単な会議 URL を指定する必要があります。

### <a name="simple-url-naming-option-1"></a>簡易 URL 命名オプション 1

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>簡易 URL</strong></p></td>
<td><p><strong>例</strong></p></td>
</tr>
<tr class="even">
<td><p>満たせ</p></td>
<td><p>https://meet.contoso.com、 https://meet.fabrikam.comなど (組織内の SIP ドメインごとに1つずつ)</p></td>
</tr>
<tr class="odd">
<td><p>ダイヤルイン</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>管理者</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


オプション 2 では、簡易 URL のベースとしてドメイン名の lync.contoso.com を使います。このため、必要な DNS A レコードは 1 つだけであり、この DNS A レコードで、簡易 URL の 3 つのタイプすべてを有効にします。 この DNS A レコードは、lync.contoso.com を参照します。この場合も、組織内の他の SIP ドメインについては、独立した DNS A レコードが必要です。

### <a name="simple-url-naming-option-2"></a>簡易 URL 命名オプション 2

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>簡易 URL</strong></p></td>
<td><p><strong>例</strong></p></td>
</tr>
<tr class="even">
<td><p>満たせ</p></td>
<td><p>https://lync.contoso.com/Meet、 https://lync.fabrikam.com/Meetなど (組織内の SIP ドメインごとに1つずつ)</p></td>
</tr>
<tr class="odd">
<td><p>ダイヤルイン</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>管理者</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


SIP ドメインの数が多く、これらのドメインに独立した簡単会議 URL を持たせて、これらの簡易 URL の DNS レコードと証明書の要件をできるだけ少なくする場合は、オプション 3 が最も便利です。

### <a name="simple-url-naming-option-3"></a>簡易 URL 命名オプション 3

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>簡易 URL</strong></p></td>
<td><p><strong>例</strong></p></td>
</tr>
<tr class="even">
<td><p>満たせ</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>ダイヤルイン</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>管理者</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a>簡易 URL の命名および入力規則

トポロジビルダーおよび Lync Server 管理シェルコマンドレットを使用すると、簡単な Url に対していくつかの入力規則が適用されます。 ユーザーは、簡単な会議 URL およびダイヤルイン URL の設定を要求されますが、簡単な管理 URL の設定はオプションです。 各 SIP ドメインは独立した簡単な会議 URL を持つ必要がありますが、簡単なダイヤルイン URL と簡単な会議 URL については組織全体で必要な数は 1 つだけです。

組織内の各簡易 URL は一意の名前を持つ必要があり、別の簡易 URL のプレフィックスにすることはできません (たとえば、簡単な会議 URL として lync.contoso.com/Meet、簡単なダイヤルイン URL として lync.contoso.com/Meet/Dialin を設定することはできません)。 簡易 URL 名には、任意のプールの FQDN、または任意のポート情報を含めることhttps://FQDN:88/meetはできません (例: は許可されません)。 簡易 URL は、すべてプレフィックス https:// で始まる必要があります。

簡易 URL の名前には、英数字 (すなわち、a ～ z、A ～ Z、0 ～ 9) およびピリオド (.) 以外は使用できません。 他の文字を使用すると、簡易 URL が予想どおりに機能しない可能性があります。

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a>展開後の簡易 URL の変更

初回の展開後に簡易 URL を変更する場合は、その変更が簡易 URL の DNS レコードと証明書に及ぼす影響について認識しておく必要があります。 簡易 URL の基本部分が変わる場合は、DNS レコードと証明書も変更する必要があります。 たとえば、からhttps://lync.contoso.com/Meetにhttps://meet.contoso.com変更するとベース URL が lync.contoso.com から meet.contoso.com に変更されるため、meet.contoso.com を参照するように DNS レコードと証明書を変更する必要があります。 からhttps://lync.contoso.com/Meetにhttps://lync.contoso.com/Meetings簡単な url を変更した場合、lync.contoso.com のベース url は同じままになるため、DNS や証明書の変更は必要ありません。

ただし、簡単な URL 名を変更する場合は必ず、各ディレクターおよびフロントエンドサーバーで**Enable CsComputer**を実行して変更を登録する必要があります。

</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の簡易 Url の DNS 要件](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

