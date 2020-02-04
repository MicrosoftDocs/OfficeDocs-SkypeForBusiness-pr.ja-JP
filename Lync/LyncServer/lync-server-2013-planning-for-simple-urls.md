---
title: 'Lync Server 2013: 簡単な URL の計画'
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
ms.openlocfilehash: 224ca0315aff2618500182398cfe792c9626b883
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750467"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="13c91-102">Lync Server 2013 での簡単な URL の計画</span><span class="sxs-lookup"><span data-stu-id="13c91-102">Planning for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13c91-103">_**最終更新日:** 2015-12-11_</span><span class="sxs-lookup"><span data-stu-id="13c91-103">_**Topic Last Modified:** 2015-12-11_</span></span>

<span data-ttu-id="13c91-104">簡単な Url を使用すると、ユーザーは簡単に会議に参加できるようになり、管理者は Lync Server の管理ツールに簡単にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="13c91-104">Simple URLs make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span>

<span data-ttu-id="13c91-105">Lync Server は、次の3つの簡単な Url をサポートします。</span><span class="sxs-lookup"><span data-stu-id="13c91-105">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="13c91-106">**会議**は、サイトまたは組織内のすべての会議のベース URL として使用されます。</span><span class="sxs-lookup"><span data-stu-id="13c91-106">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="13c91-107">単純な URL の例を次にhttps://meet.contoso.com示します。</span><span class="sxs-lookup"><span data-stu-id="13c91-107">An example of a Meet simple URL is https://meet.contoso.com.</span></span> <span data-ttu-id="13c91-108">特定の会議の URL は、 https://meet.contoso.com/*ユーザー名*/7322994 の可能性があります。</span><span class="sxs-lookup"><span data-stu-id="13c91-108">A URL for a particular meeting might be https://meet.contoso.com/*username*/7322994.</span></span>
    
    <span data-ttu-id="13c91-109">[会議への参加] の [シンプル URL] を使用すると、会議に参加するためのリンクを簡単に理解して、簡単に連絡して配布することができます。</span><span class="sxs-lookup"><span data-stu-id="13c91-109">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="13c91-110">[**ダイヤル**イン] は、ダイヤルイン会議の設定の web ページにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="13c91-110">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="13c91-111">このページには、会議のダイヤルイン番号が表示されます。このページには、利用可能な言語、割り当てられている会議情報 (スケジュールされていない会議)、会議中の DTMF コントロールが表示され、個人識別番号の管理がサポートされています (PIN) および割り当てられた会議情報。</span><span class="sxs-lookup"><span data-stu-id="13c91-111">This page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="13c91-112">ダイヤルインの簡易 URL は、会議にダイヤルインするユーザーが必要な電話番号と PIN 情報にアクセスできるように、すべての会議出席依頼に含まれています。</span><span class="sxs-lookup"><span data-stu-id="13c91-112">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> <span data-ttu-id="13c91-113">ダイヤルインの簡易 URL の例を次にhttps://dialin.contoso.com示します。</span><span class="sxs-lookup"><span data-stu-id="13c91-113">An example of the Dial-in simple URL is https://dialin.contoso.com.</span></span>

  - <span data-ttu-id="13c91-114">**管理者**が Lync Server コントロールパネルにすばやくアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="13c91-114">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="13c91-115">組織のファイアウォール内の任意のコンピューターから、管理者は、ブラウザーに管理者の簡易 URL を入力して Lync Server コントロールパネルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="13c91-115">From any computer within your organization’s firewalls, an admin can open the Lync Server Control Panel by typing the Admin simple URL into a browser.</span></span> <span data-ttu-id="13c91-116">管理者の簡易 URL は、組織の内部にあります。</span><span class="sxs-lookup"><span data-stu-id="13c91-116">The Admin simple URL is internal to your organization.</span></span> <span data-ttu-id="13c91-117">管理者簡易 URL の例を次に示します。https://admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="13c91-117">An example of the Admin simple URL is https://admin.contoso.com</span></span>

<div>

## <a name="simple-url-scope"></a><span data-ttu-id="13c91-118">単純な URL スコープ</span><span class="sxs-lookup"><span data-stu-id="13c91-118">Simple URL Scope</span></span>

<span data-ttu-id="13c91-119">グローバルなスコープを持つように単純な Url を構成することも、組織内のセントラルサイトごとに異なる簡単な Url を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="13c91-119">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="13c91-120">グローバルスコープの単純な url とサイトスコープの単純な URL の両方が指定されている場合、サイトスコープの単純な url が優先されます。</span><span class="sxs-lookup"><span data-stu-id="13c91-120">If both a global scope simple URL and a site scope simple URL are specified, the site scope simple URL has precedence.</span></span>

<span data-ttu-id="13c91-121">ほとんどの場合、単純な url の設定はグローバルレベルでのみ行うことをお勧めします。そのため、あるサイトから別のサイトに移動しても、ユーザーの単純な URL が変わらないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="13c91-121">In most cases, we recommend that you set simple URLs only at the global level, so that a user’s Meet simple URL does not change if they move from one site to another.</span></span> <span data-ttu-id="13c91-122">例外として、さまざまなサイトのダイヤルインユーザーに異なる電話番号を使用する必要がある組織が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="13c91-122">The exception would be organizations that need to use different telephone numbers for dial-in users at different sites.</span></span> <span data-ttu-id="13c91-123">1つの単純な URL (ダイヤルインの単純な url など) をサイトレベルの単純な URL として設定する場合は、そのサイトの他の単純な Url もサイトレベルに設定する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="13c91-123">Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="13c91-124">サイトスコープのシンプルな Url を使用するように選択した場合、ユーザーは、スケジュールされたすべての会議を再スケジュールしたときに、サイト間で異なるフロントエンドプール間を移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="13c91-124">If you choose to use site scoped simple URLs, your users won't be able to move between Front-End pools in different sites without those users rescheduling all of their scheduled meetings as the meeting simple URLs are different between sites.</span></span> <span data-ttu-id="13c91-125">これには、バックアップリレーションシップのプールが別のサイトにあるというフェイルオーバーシナリオが含まれます。</span><span class="sxs-lookup"><span data-stu-id="13c91-125">This includes fail-over scenarios where pools in backup relationships are in separate sites.</span></span> <span data-ttu-id="13c91-126">サイトスコープの単純な Url が展開されているサイト間でフェールオーバーする必要がある場合は、URL のスコープが原因で、ユーザーが会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="13c91-126">When you need to fail-over between sites where site scoped simple URLs are deployed, users won't be able to join their meetings because of the scope for URL.</span></span> <span data-ttu-id="13c91-127">詳細については、「<A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">ダウンロード</A>」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="13c91-127">For further information, check <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span></span>



</div>

<span data-ttu-id="13c91-128">トポロジビルダーでは、グローバルな単純 Url を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="13c91-128">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="13c91-129">サイトレベルで単純な URL を設定するには、Set-CsSimpleURLConfiguration コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13c91-129">To set a simple URL at the site level, you must use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="naming-your-simple-urls"></a><span data-ttu-id="13c91-130">単純な Url に名前を付ける</span><span class="sxs-lookup"><span data-stu-id="13c91-130">Naming Your Simple URLs</span></span>

<span data-ttu-id="13c91-131">簡単な Url に名前を付けるための推奨される3つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="13c91-131">There are three recommended options for naming your simple URLs.</span></span> <span data-ttu-id="13c91-132">どちらのオプションを選択するかは、DNS A レコードと単純な Url をサポートする証明書のセットアップ方法によって決まります。</span><span class="sxs-lookup"><span data-stu-id="13c91-132">Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs.</span></span> <span data-ttu-id="13c91-133">各オプションで、組織内の各 SIP ドメインに対して、単一の会議の単純 URL を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13c91-133">In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span>

<span data-ttu-id="13c91-134">使用している SIP ドメインの数に関係なく、ダイヤルイン用の組織全体に、または管理者用に1つだけ簡単な URL を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13c91-134">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="13c91-135">必要な DNS A レコードと証明書の詳細については、「 [Lync server 2013 の単純な url の DNS 要件](lync-server-2013-dns-requirements-for-simple-urls.md)」および「計画ドキュメントの[lync server 2013 の内部サーバーの証明書の要件](lync-server-2013-certificate-requirements-for-internal-servers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13c91-135">For details about the necessary DNS A records and certificates, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) and [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="13c91-136">オプション1では、各シンプル URL の新しい SIP ドメイン名を作成します。</span><span class="sxs-lookup"><span data-stu-id="13c91-136">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="13c91-137">このオプションを使用する場合は、各シンプル URL に個別の DNS A レコードが必要です。また、それぞれの [simple URL] を証明書で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13c91-137">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

### <a name="simple-url-naming-option-1"></a><span data-ttu-id="13c91-138">簡単な URL の名前付けオプション1</span><span class="sxs-lookup"><span data-stu-id="13c91-138">Simple URL Naming Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="13c91-139"><strong>単純な URL</strong></span><span class="sxs-lookup"><span data-stu-id="13c91-139"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="13c91-140"><strong>例</strong></span><span class="sxs-lookup"><span data-stu-id="13c91-140"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13c91-141">即時</span><span class="sxs-lookup"><span data-stu-id="13c91-141">Meet</span></span></p></td>
<td><p><span data-ttu-id="13c91-142">https://meet.contoso.com、 https://meet.fabrikam.comなどの場合 (組織の SIP ドメインごとに1つ)</span><span class="sxs-lookup"><span data-stu-id="13c91-142">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13c91-143">ダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="13c91-143">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13c91-144">同期</span><span class="sxs-lookup"><span data-stu-id="13c91-144">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="13c91-145">オプション2では、ドメイン名 lync.contoso.com に基づいて単純な Url が作成されます。</span><span class="sxs-lookup"><span data-stu-id="13c91-145">With Option 2, simple URLs are based on the domain name lync.contoso.com.</span></span> <span data-ttu-id="13c91-146">そのため、3種類の単純な Url をすべて有効にする DNS A レコードは1つだけである必要があります。</span><span class="sxs-lookup"><span data-stu-id="13c91-146">Therefore, you need only one DNS A record which enables all three types of simple URLs.</span></span> <span data-ttu-id="13c91-147">この DNS A レコードは lync.contoso.com を参照しています。</span><span class="sxs-lookup"><span data-stu-id="13c91-147">This DNS A record references lync.contoso.com.</span></span> <span data-ttu-id="13c91-148">さらに、組織内の他の SIP ドメイン用の DNS A レコードも別途必要です。</span><span class="sxs-lookup"><span data-stu-id="13c91-148">Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span>

### <a name="simple-url-naming-option-2"></a><span data-ttu-id="13c91-149">簡単な URL の名前付けオプション2</span><span class="sxs-lookup"><span data-stu-id="13c91-149">Simple URL Naming Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="13c91-150"><strong>単純な URL</strong></span><span class="sxs-lookup"><span data-stu-id="13c91-150"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="13c91-151"><strong>例</strong></span><span class="sxs-lookup"><span data-stu-id="13c91-151"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13c91-152">即時</span><span class="sxs-lookup"><span data-stu-id="13c91-152">Meet</span></span></p></td>
<td><p><span data-ttu-id="13c91-153">https://lync.contoso.com/Meet、 https://lync.fabrikam.com/Meetなどの場合 (組織の SIP ドメインごとに1つ)</span><span class="sxs-lookup"><span data-stu-id="13c91-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13c91-154">ダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="13c91-154">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13c91-155">同期</span><span class="sxs-lookup"><span data-stu-id="13c91-155">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="13c91-156">オプション3は、多数の SIP ドメインを持っていて、それらのユーザーが単純な Url を個別に指定して、DNS レコードと証明書の要件を最小限に抑える必要がある場合に最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="13c91-156">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span>

### <a name="simple-url-naming-option-3"></a><span data-ttu-id="13c91-157">簡単な URL の名前付けオプション3</span><span class="sxs-lookup"><span data-stu-id="13c91-157">Simple URL Naming Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="13c91-158"><strong>単純な URL</strong></span><span class="sxs-lookup"><span data-stu-id="13c91-158"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="13c91-159"><strong>例</strong></span><span class="sxs-lookup"><span data-stu-id="13c91-159"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13c91-160">即時</span><span class="sxs-lookup"><span data-stu-id="13c91-160">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13c91-161">ダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="13c91-161">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13c91-162">同期</span><span class="sxs-lookup"><span data-stu-id="13c91-162">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="13c91-163">単純な URL の名前付けと入力規則</span><span class="sxs-lookup"><span data-stu-id="13c91-163">Simple URL Naming and Validation Rules</span></span>

<span data-ttu-id="13c91-164">トポロジビルダーと Lync Server 管理シェルコマンドレットでは、単純な Url に対して複数の入力規則を適用します。</span><span class="sxs-lookup"><span data-stu-id="13c91-164">Topology Builder and the Lync Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="13c91-165">会議とダイヤルインのための単純な Url を設定する必要がありますが、管理者用の設定は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="13c91-165">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="13c91-166">各 SIP ドメインは、個別の単純な url を持つ必要がありますが、組織全体に1つのダイヤルインの単純な url と管理者の単純な URL を1つだけ用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13c91-166">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="13c91-167">組織内の各単純 URL には一意の名前を指定する必要があります。また、別の単純な URL のプレフィックスとして使用することはできません (たとえば、lync.contoso.com/Meet の単純な url と lync.contoso.com/Meet/Dialin をダイヤルインの単純な URL として設定することはできません)。</span><span class="sxs-lookup"><span data-stu-id="13c91-167">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set lync.contoso.com/Meet as your Meet simple URL and lync.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="13c91-168">単純な URL 名には、任意のプールの FQDN または任意のポート情報を含めることhttps://FQDN:88/meetはできません (たとえば、許可されません)。</span><span class="sxs-lookup"><span data-stu-id="13c91-168">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="13c91-169">すべての単純な Url は、https://プレフィックスで始める必要があります。</span><span class="sxs-lookup"><span data-stu-id="13c91-169">All simple URLs must start with the https:// prefix.</span></span>

<span data-ttu-id="13c91-170">単純な Url には、英数字 (a ~ z、A ~ z、0-9、ピリオド (.) のみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="13c91-170">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.).</span></span> <span data-ttu-id="13c91-171">他の文字を使用している場合、単純な Url は期待どおりに動作しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="13c91-171">If you use other characters, the simple URLs might not work as expected.</span></span>

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="13c91-172">展開後の単純な Url の変更</span><span class="sxs-lookup"><span data-stu-id="13c91-172">Changing Simple URLs after Deployment</span></span>

<span data-ttu-id="13c91-173">最初の展開後に単純な URL を変更する場合は、変更によって、単純な Url の DNS レコードと証明書にどのように影響するかに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13c91-173">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="13c91-174">単純な URL のベースが変更された場合は、DNS レコードと証明書も変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13c91-174">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="13c91-175">たとえば、to https://lync.contoso.com/Meet https://meet.contoso.comから MEET.CONTOSO.COM へのベース URL の変更は、lync.contoso.com を参照するように DNS レコードと証明書を変更する必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="13c91-175">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="13c91-176">Simple URL をからhttps://lync.contoso.com/Meetにhttps://lync.contoso.com/Meetings変更した場合、lync.contoso.com のベース url は変わりません。そのため、DNS や証明書の変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="13c91-176">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="13c91-177">ただし、単純な URL 名を変更する場合は必ず、各ディレクターとフロントエンドサーバーで [ユーザーの**有効化**] を実行して、変更を登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13c91-177">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="13c91-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="13c91-178">See Also</span></span>


[<span data-ttu-id="13c91-179">Lync Server 2013 の簡易 URL の DNS 要件</span><span class="sxs-lookup"><span data-stu-id="13c91-179">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

