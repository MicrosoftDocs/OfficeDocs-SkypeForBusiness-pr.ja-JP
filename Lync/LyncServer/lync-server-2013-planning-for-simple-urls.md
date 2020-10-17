---
title: 'Lync Server 2013: 簡単な Url の計画'
description: 'Lync Server 2013: 簡単な Url の計画。'
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
ms.openlocfilehash: 10a7f2aaf85dafe5facba7cfd2509cfcc8812d67
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558403"
---
# <a name="planning-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="92f3f-103">Lync Server 2013 での簡単な Url の計画</span><span class="sxs-lookup"><span data-stu-id="92f3f-103">Planning for simple URLs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92f3f-104">_**トピックの最終更新日:** 2015-12-11_</span><span class="sxs-lookup"><span data-stu-id="92f3f-104">_**Topic Last Modified:** 2015-12-11_</span></span>

<span data-ttu-id="92f3f-105">簡易 Url を使用すると、ユーザーの会議への参加が容易になり、管理者が Lync Server 管理ツールをより簡単に利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="92f3f-105">Simple URLs make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span>

<span data-ttu-id="92f3f-106">Lync Server は、次の3つの簡単な Url をサポートします。</span><span class="sxs-lookup"><span data-stu-id="92f3f-106">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="92f3f-107">**Meet** は、サイトまたは組織内のすべての電話会議のベース URL として使用されます。</span><span class="sxs-lookup"><span data-stu-id="92f3f-107">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="92f3f-108">簡単な会議 URL の例を次に示し https://meet.contoso.com ます。</span><span class="sxs-lookup"><span data-stu-id="92f3f-108">An example of a Meet simple URL is https://meet.contoso.com.</span></span> <span data-ttu-id="92f3f-109">特定の会議の URL は、 https://meet.contoso.com/ *ユーザー名*/7322994 の場合があります。</span><span class="sxs-lookup"><span data-stu-id="92f3f-109">A URL for a particular meeting might be https://meet.contoso.com/*username*/7322994.</span></span>
    
    <span data-ttu-id="92f3f-110">簡単な会議 URL を使用すると、会議に参加するためのリンクが覚えやすくなり、通知も配布も簡単になります。</span><span class="sxs-lookup"><span data-stu-id="92f3f-110">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="92f3f-111">**ダイヤル** インは、ダイヤルイン会議設定 web ページへのアクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="92f3f-111">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="92f3f-112">このページには、使用可能な言語で会議のダイヤルイン番号、割り当てられている会議情報 (スケジュールする必要がない会議の場合)、および会議中の DTMF コントロールが表示され、個人識別番号 (PIN) と割り当てられた会議情報の管理をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="92f3f-112">This page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="92f3f-113">ダイヤルインの簡易 URL は、すべての会議出席依頼に含まれているため、会議にダイヤルインするユーザーは必要な電話番号と PIN 情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="92f3f-113">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> <span data-ttu-id="92f3f-114">ダイヤルインの簡易 URL の例を次に示し https://dialin.contoso.com ます。</span><span class="sxs-lookup"><span data-stu-id="92f3f-114">An example of the Dial-in simple URL is https://dialin.contoso.com.</span></span>

  - <span data-ttu-id="92f3f-115">**管理者** は、Lync Server コントロールパネルにすばやくアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="92f3f-115">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="92f3f-116">組織のファイアウォール内の任意のコンピューターから、管理者は管理者の簡易 URL をブラウザーに入力して Lync Server コントロールパネルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="92f3f-116">From any computer within your organization’s firewalls, an admin can open the Lync Server Control Panel by typing the Admin simple URL into a browser.</span></span> <span data-ttu-id="92f3f-117">簡単な管理 URL は、組織内部の URL です。</span><span class="sxs-lookup"><span data-stu-id="92f3f-117">The Admin simple URL is internal to your organization.</span></span> <span data-ttu-id="92f3f-118">管理簡易 URL の例を次に示します。 https://admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="92f3f-118">An example of the Admin simple URL is https://admin.contoso.com</span></span>

<div>

## <a name="simple-url-scope"></a><span data-ttu-id="92f3f-119">簡易 URL の範囲</span><span class="sxs-lookup"><span data-stu-id="92f3f-119">Simple URL Scope</span></span>

<span data-ttu-id="92f3f-120">簡単な Url をグローバルスコープに構成することも、組織内の中央サイトごとに異なる簡単な Url を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="92f3f-120">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="92f3f-121">グローバルスコープの単純な URL とサイトスコープの単純な url の両方が指定されている場合は、サイトスコープの簡易 url が優先されます。</span><span class="sxs-lookup"><span data-stu-id="92f3f-121">If both a global scope simple URL and a site scope simple URL are specified, the site scope simple URL has precedence.</span></span>

<span data-ttu-id="92f3f-p105">ほとんどのケースでは、簡易 URL はグローバル レベルだけで設定することをお勧めします。そうしておけば、ユーザーがサイト間で移動した場合に、ユーザーの簡単な会議 URL が変更される心配がなくなります。ただし、これは、各サイトのダイヤルイン ユーザーごとに別々の電話番号を使用する必要がある組織には該当しません。あるサイトで任意のタイプの簡易 URL (簡単なダイヤルイン URL など) をサイト レベルの簡易 URL として設定すると、そのサイトでは残りの 2 つの簡易 URL もサイト レベルで設定する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="92f3f-p105">In most cases, we recommend that you set simple URLs only at the global level, so that a user’s Meet simple URL does not change if they move from one site to another. The exception would be organizations that need to use different telephone numbers for dial-in users at different sites. Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="92f3f-125">サイトスコープの簡易 Url を使用することを選択した場合、ユーザーはサイトごとに異なるサイトの Front-End プール間で移動することはできません。これらのユーザーは、会議の簡単な Url がサイトごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="92f3f-125">If you choose to use site scoped simple URLs, your users won't be able to move between Front-End pools in different sites without those users rescheduling all of their scheduled meetings as the meeting simple URLs are different between sites.</span></span> <span data-ttu-id="92f3f-126">これには、バックアップ関係のプールが別のサイトに存在するフェールオーバーのシナリオが含まれます。</span><span class="sxs-lookup"><span data-stu-id="92f3f-126">This includes fail-over scenarios where pools in backup relationships are in separate sites.</span></span> <span data-ttu-id="92f3f-127">サイトスコープの簡易 Url が展開されているサイト間でフェールオーバーする必要がある場合は、URL のスコープによって、ユーザーは会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="92f3f-127">When you need to fail-over between sites where site scoped simple URLs are deployed, users won't be able to join their meetings because of the scope for URL.</span></span> <span data-ttu-id="92f3f-128">詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="92f3f-128">For further information, check <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span></span>



</div>

<span data-ttu-id="92f3f-129">トポロジビルダーでは、グローバルな簡易 Url を設定できます。</span><span class="sxs-lookup"><span data-stu-id="92f3f-129">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="92f3f-130">サイト レベルで簡易 URL を設定するには、Set-CsSimpleURLConfiguration コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="92f3f-130">To set a simple URL at the site level, you must use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="naming-your-simple-urls"></a><span data-ttu-id="92f3f-131">簡易 URL の命名</span><span class="sxs-lookup"><span data-stu-id="92f3f-131">Naming Your Simple URLs</span></span>

<span data-ttu-id="92f3f-p108">簡易 URL の命名には、推奨される 3 つのオプションがあります。選択するオプションによって、簡易 URL をサポートする DNS A レコードと証明書の設定方法が影響を受けます。各オプションでは、組織内の SIP ドメインごとに簡単な会議 URL を 1 つ構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92f3f-p108">There are three recommended options for naming your simple URLs. Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs. In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span>

<span data-ttu-id="92f3f-135">簡単なダイヤルインおよび管理 URL については、所有している SIP ドメインの数とは関係なく、組織全体で必要な数は、常に 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="92f3f-135">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="92f3f-136">必要な DNS A レコードおよび証明書の詳細については、「計画」のドキュメントの「 [Lync server 2013 の簡易 url の DNS 要件](lync-server-2013-dns-requirements-for-simple-urls.md) 」および「 [lync server 2013 の内部サーバーの証明書要件](lync-server-2013-certificate-requirements-for-internal-servers.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92f3f-136">For details about the necessary DNS A records and certificates, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) and [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="92f3f-137">オプション 1 では、簡易 URL ごとに、新しい SIP ドメイン名を作成します。</span><span class="sxs-lookup"><span data-stu-id="92f3f-137">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="92f3f-138">このオプションを使用する場合は、簡易 URL ごとに独立した DNS A レコードが必要であり、証明書で各簡単な会議 URL を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92f3f-138">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

### <a name="simple-url-naming-option-1"></a><span data-ttu-id="92f3f-139">簡易 URL 命名オプション 1</span><span class="sxs-lookup"><span data-stu-id="92f3f-139">Simple URL Naming Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92f3f-140"><strong>簡易 URL</strong></span><span class="sxs-lookup"><span data-stu-id="92f3f-140"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="92f3f-141"><strong>例</strong></span><span class="sxs-lookup"><span data-stu-id="92f3f-141"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92f3f-142">満たせ</span><span class="sxs-lookup"><span data-stu-id="92f3f-142">Meet</span></span></p></td>
<td><p><span data-ttu-id="92f3f-143">https://meet.contoso.com、 https://meet.fabrikam.com など (組織内の SIP ドメインごとに1つずつ)</span><span class="sxs-lookup"><span data-stu-id="92f3f-143">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92f3f-144">ダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="92f3f-144">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92f3f-145">管理者</span><span class="sxs-lookup"><span data-stu-id="92f3f-145">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="92f3f-p109">オプション 2 では、簡易 URL のベースとしてドメイン名の lync.contoso.com を使います。このため、必要な DNS A レコードは 1 つだけであり、この DNS A レコードで、簡易 URL の 3 つのタイプすべてを有効にします。 この DNS A レコードは、lync.contoso.com を参照します。この場合も、組織内の他の SIP ドメインについては、独立した DNS A レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="92f3f-p109">With Option 2, simple URLs are based on the domain name lync.contoso.com. Therefore, you need only one DNS A record which enables all three types of simple URLs. This DNS A record references lync.contoso.com. Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span>

### <a name="simple-url-naming-option-2"></a><span data-ttu-id="92f3f-150">簡易 URL 命名オプション 2</span><span class="sxs-lookup"><span data-stu-id="92f3f-150">Simple URL Naming Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92f3f-151"><strong>簡易 URL</strong></span><span class="sxs-lookup"><span data-stu-id="92f3f-151"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="92f3f-152"><strong>例</strong></span><span class="sxs-lookup"><span data-stu-id="92f3f-152"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92f3f-153">満たせ</span><span class="sxs-lookup"><span data-stu-id="92f3f-153">Meet</span></span></p></td>
<td><p><span data-ttu-id="92f3f-154">https://lync.contoso.com/Meet、 https://lync.fabrikam.com/Meet など (組織内の SIP ドメインごとに1つずつ)</span><span class="sxs-lookup"><span data-stu-id="92f3f-154">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92f3f-155">ダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="92f3f-155">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92f3f-156">管理者</span><span class="sxs-lookup"><span data-stu-id="92f3f-156">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="92f3f-157">SIP ドメインの数が多く、これらのドメインに独立した簡単会議 URL を持たせて、これらの簡易 URL の DNS レコードと証明書の要件をできるだけ少なくする場合は、オプション 3 が最も便利です。</span><span class="sxs-lookup"><span data-stu-id="92f3f-157">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span>

### <a name="simple-url-naming-option-3"></a><span data-ttu-id="92f3f-158">簡易 URL 命名オプション 3</span><span class="sxs-lookup"><span data-stu-id="92f3f-158">Simple URL Naming Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92f3f-159"><strong>簡易 URL</strong></span><span class="sxs-lookup"><span data-stu-id="92f3f-159"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="92f3f-160"><strong>例</strong></span><span class="sxs-lookup"><span data-stu-id="92f3f-160"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92f3f-161">満たせ</span><span class="sxs-lookup"><span data-stu-id="92f3f-161">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92f3f-162">ダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="92f3f-162">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92f3f-163">管理者</span><span class="sxs-lookup"><span data-stu-id="92f3f-163">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="92f3f-164">簡易 URL の命名および入力規則</span><span class="sxs-lookup"><span data-stu-id="92f3f-164">Simple URL Naming and Validation Rules</span></span>

<span data-ttu-id="92f3f-165">トポロジビルダーおよび Lync Server 管理シェルコマンドレットを使用すると、簡単な Url に対していくつかの入力規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="92f3f-165">Topology Builder and the Lync Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="92f3f-166">ユーザーは、簡単な会議 URL およびダイヤルイン URL の設定を要求されますが、簡単な管理 URL の設定はオプションです。</span><span class="sxs-lookup"><span data-stu-id="92f3f-166">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="92f3f-167">各 SIP ドメインは独立した簡単な会議 URL を持つ必要がありますが、簡単なダイヤルイン URL と簡単な会議 URL については組織全体で必要な数は 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="92f3f-167">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="92f3f-168">組織内の各簡易 URL は一意の名前を持つ必要があり、別の簡易 URL のプレフィックスにすることはできません (たとえば、簡単な会議 URL として lync.contoso.com/Meet、簡単なダイヤルイン URL として lync.contoso.com/Meet/Dialin を設定することはできません)。</span><span class="sxs-lookup"><span data-stu-id="92f3f-168">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set lync.contoso.com/Meet as your Meet simple URL and lync.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="92f3f-169">簡易 URL 名には、任意のプールの FQDN、または任意のポート情報を含めることはできません (例: https://FQDN:88/meet は許可されません)。</span><span class="sxs-lookup"><span data-stu-id="92f3f-169">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="92f3f-170">簡易 URL は、すべてプレフィックス https:// で始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="92f3f-170">All simple URLs must start with the https:// prefix.</span></span>

<span data-ttu-id="92f3f-p112">簡易 URL の名前には、英数字 (すなわち、a ～ z、A ～ Z、0 ～ 9) およびピリオド (.) 以外は使用できません。 他の文字を使用すると、簡易 URL が予想どおりに機能しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="92f3f-p112">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.). If you use other characters, the simple URLs might not work as expected.</span></span>

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="92f3f-173">展開後の簡易 URL の変更</span><span class="sxs-lookup"><span data-stu-id="92f3f-173">Changing Simple URLs after Deployment</span></span>

<span data-ttu-id="92f3f-174">初回の展開後に簡易 URL を変更する場合は、その変更が簡易 URL の DNS レコードと証明書に及ぼす影響について認識しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="92f3f-174">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="92f3f-175">簡易 URL の基本部分が変わる場合は、DNS レコードと証明書も変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92f3f-175">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="92f3f-176">たとえば、からに変更すると https://lync.contoso.com/Meet https://meet.contoso.com ベース URL が lync.contoso.com から meet.contoso.com に変更されるため、meet.contoso.com を参照するように DNS レコードと証明書を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92f3f-176">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="92f3f-177">からに簡単な URL を変更した場合、 https://lync.contoso.com/Meet https://lync.contoso.com/Meetings lync.contoso.com のベース url は同じままになるため、DNS や証明書の変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="92f3f-177">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="92f3f-178">ただし、簡単な URL 名を変更する場合は必ず、各ディレクターおよびフロントエンドサーバーで **Enable CsComputer** を実行して変更を登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92f3f-178">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="92f3f-179">関連項目</span><span class="sxs-lookup"><span data-stu-id="92f3f-179">See Also</span></span>


[<span data-ttu-id="92f3f-180">Lync Server 2013 の簡易 Url の DNS 要件</span><span class="sxs-lookup"><span data-stu-id="92f3f-180">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

