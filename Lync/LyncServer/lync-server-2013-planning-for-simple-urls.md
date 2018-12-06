---
title: 'Lync Server 2013: 簡単な URL の計画'
TOCTitle: 簡単な URL の計画
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398287(v=OCS.15)
ms:contentKeyID: 48271554
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での簡単な URL の計画

 

_**トピックの最終更新日:** 2015-12-11_

簡易 URL を使用すると、ユーザーは会議への参加が容易になり、管理者は Lync Server 管理ツールへのアクセスが容易になります。

Lync Server  では、次に示す 3 つの簡易 URL がサポートされています。

  - **meet** は、サイトまたは組織内のすべての会議のベース URL として使用されます。たとえば、https://meet.contoso.com が簡単な会議 URL です。この場合、個別の会議の URL は、https://meet.contoso.com/*ユーザー名*/7322994 などになります。
    
    簡単な会議 URL を使用すると、会議に参加するためのリンクが覚えやすくなり、通知も配布も簡単になります。

  - **ダイヤルイン** URL を使用すると、\[ダイヤルイン会議の設定\] Web ページにアクセスできます。 このページには、使用可能な言語、割り当て済み会議情報 (すなわち、スケジュールされる必要がない会議用)、および会議内 DTMF コントロールと組み合わされた会議のダイヤルイン番号が表示されます。また、このページは、暗証番号 (PIN) および割り当て済みの会議情報の管理をサポートします。 簡単なダイヤルイン URL は、すべての会議への招待に含まれるため、会議にダイヤルインするユーザーは、必要な電話番号および PIN 情報にアクセスできます。 たとえば、https://dialin.contoso.com が簡単なダイヤルイン URL です。

  - **管理** URL を使用すると、 Lync Server コントロール パネルに迅速にアクセスできます。管理者は、組織のファイアウォール内の任意のコンピューターから、簡単な管理 URL をブラウザーに入力して Lync Server コントロール パネルを開くことができます。簡単な管理 URL は、組織内部の URL です。たとえば、https://admin.contoso.com が簡単な管理 URL です。

## 簡易 URL の範囲

簡易 URL には、グローバル スコープを適用できます。また、組織内の各セントラル サイトで別々の簡易 URL を指定することもできます。 簡単なグローバル URL と簡単なサイト URL の両方が指定されている場合は、簡単なサイト URL が優先されます。

ほとんどのケースでは、簡易 URL はグローバル レベルだけで設定することをお勧めします。そうしておけば、ユーザーがサイト間で移動した場合に、ユーザーの簡単な会議 URL が変更される心配がなくなります。ただし、これは、各サイトのダイヤルイン ユーザーごとに別々の電話番号を使用する必要がある組織には該当しません。あるサイトで任意のタイプの簡易 URL (簡単なダイヤルイン URL など) をサイト レベルの簡易 URL として設定すると、そのサイトでは残りの 2 つの簡易 URL もサイト レベルで設定する必要があることに注意してください。

簡単なグローバル URL は、 トポロジ ビルダーで設定できます。 サイト レベルで簡易 URL を設定するには、Set-CsSimpleURLConfiguration コマンドレットを使用します。

## 簡易 URL の命名

簡易 URL の命名には、推奨される 3 つのオプションがあります。選択するオプションによって、簡易 URL をサポートする DNS A レコードと証明書の設定方法が影響を受けます。各オプションでは、組織内の SIP ドメインごとに簡単な会議 URL を 1 つ構成する必要があります。

簡単なダイヤルインおよび管理 URL については、所有している SIP ドメインの数とは関係なく、組織全体で必要な数は、常に 1 つだけです。

必要な DNS A レコードおよび証明書の詳細については、「計画」のドキュメントの「 [Lync Server 2013 の簡易 URL の DNS 要件](lync-server-2013-dns-requirements-for-simple-urls.md)」および「 [Lync Server 2013 の内部サーバーに対する証明書要件](lync-server-2013-certificate-requirements-for-internal-servers.md)」を参照してください。

オプション 1 では、簡易 URL ごとに、新しい SIP ドメイン名を作成します。

このオプションを使用する場合は、簡易 URL ごとに独立した DNS A レコードが必要であり、証明書で各簡単な会議 URL を指定する必要があります。

### 簡易 URL 命名オプション 1

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
<td><p>会議</p></td>
<td><p>https://meet.contoso.com、https://meet.fabrikam.com、など (組織内の SIP ドメインに 1 つずつ割り当てます)</p></td>
</tr>
<tr class="odd">
<td><p>ダイヤルイン</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>管理</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


オプション 2 では、簡易 URL のベースとしてドメイン名の lync.contoso.com を使います。このため、必要な DNS A レコードは 1 つだけであり、この DNS A レコードで、簡易 URL の 3 つのタイプすべてを有効にします。 この DNS A レコードは、lync.contoso.com を参照します。この場合も、組織内の他の SIP ドメインについては、独立した DNS A レコードが必要です。

### 簡易 URL 命名オプション 2

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
<td><p>会議</p></td>
<td><p>https://lync.contoso.com/Meet、https://lync.fabrikam.com/Meet、など (組織内の SIP ドメインに 1 つずつ割り当てます)</p></td>
</tr>
<tr class="odd">
<td><p>ダイヤルイン</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>管理</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


SIP ドメインの数が多く、これらのドメインに独立した簡単会議 URL を持たせて、これらの簡易 URL の DNS レコードと証明書の要件をできるだけ少なくする場合は、オプション 3 が最も便利です。

### 簡易 URL 命名オプション 3

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
<td><p>会議</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>ダイヤルイン</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>管理</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


## 簡易 URL の命名および入力規則

トポロジ ビルダーおよび Lync Server 管理シェル コマンドレットは、簡易 URL についてのいくつかの入力規則を強制的に適用します。 ユーザーは、簡単な会議 URL およびダイヤルイン URL の設定を要求されますが、簡単な管理 URL の設定はオプションです。 各 SIP ドメインは独立した簡単な会議 URL を持つ必要がありますが、簡単なダイヤルイン URL と簡単な会議 URL については組織全体で必要な数は 1 つだけです。

組織内の各簡易 URL は一意の名前を持つ必要があり、別の簡易 URL のプレフィックスにすることはできません (たとえば、簡単な会議 URL として lync.contoso.com/Meet、簡単なダイヤルイン URL として lync.contoso.com/Meet/Dialin を設定することはできません)。簡易 URL 名には、プールの FQDN、またはポート情報を含めることはできません (たとえば、https://FQDN:88/meet は許可されません)。簡易 URL は、すべてプレフィックス https:// で始まる必要があります。

簡易 URL の名前には、英数字 (すなわち、a ～ z、A ～ Z、0 ～ 9) およびピリオド (.) 以外は使用できません。 他の文字を使用すると、簡易 URL が予想どおりに機能しない可能性があります。

## 展開後の簡易 URL の変更

初回の展開後に簡易 URL を変更する場合は、その変更が簡易 URL の DNS レコードと証明書に及ぼす影響について認識しておく必要があります。簡易 URL の基本部分が変わる場合は、DNS レコードと証明書も変更する必要があります。たとえば、https://lync.contoso.com/Meet を https://meet.contoso.com に変更すると、ベース URL が lync.contoso.com から meet.contoso.com に変わるため、meet.contoso.com を参照するように DNS レコードと証明書を変更する必要があります。簡易 URL を https://lync.contoso.com/Meet から https://lync.contoso.com/Meetings に変更した場合は、ベース URL の lync.contoso.com は同じなので、DNS と証明書の変更は必要ありません。

ただし、簡易 URL 名を変更する場合は必ず、各ディレクターおよびフロントエンド サーバーで **Enable-CsComputer** を実行して変更を登録する必要があります。

## 関連項目

#### 概念

[Lync Server 2013 の簡易 URL の DNS 要件](lync-server-2013-dns-requirements-for-simple-urls.md)

