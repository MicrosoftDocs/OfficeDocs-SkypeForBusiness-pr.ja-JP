---
title: Skype for Business Server の簡易 URL の DNS 要件
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: '概要: Skype for Business Server の DNS レコードを実装する前に、このトピックの簡易 URL に関する考慮事項を確認してください。'
ms.openlocfilehash: d1c4213e1fe28c6f42cd4fa14f48bc8ce9b7bdf1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834587"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a><span data-ttu-id="83eb9-103">Skype for Business Server の簡易 URL の DNS 要件</span><span class="sxs-lookup"><span data-stu-id="83eb9-103">DNS requirements for simple URLs in Skype for Business Server</span></span>

<span data-ttu-id="83eb9-104">**概要:** Skype for Business Server の DNS レコードを実装する前に、このトピックの簡易 URL に関する考慮事項を確認してください。</span><span class="sxs-lookup"><span data-stu-id="83eb9-104">**Summary:** Review the Simple URL considerations in this topic before implementing DNS records for Skype for Business Server.</span></span>

<span data-ttu-id="83eb9-105">簡単な URL を使用すると、ユーザーは会議に簡単に参加できます。また、管理者は Skype for Business Server 管理ツールに簡単にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="83eb9-105">Simple URLs make joining meetings easier for your users, and make getting to Skype for Business Server administrative tools easier for administrators.</span></span> <span data-ttu-id="83eb9-106">簡易 URL は独自のドメインを使用しますが、定義する SIP ドメインと一致しすることはできません。</span><span class="sxs-lookup"><span data-stu-id="83eb9-106">Simple URLs use their own domain, which must not match any of the SIP domains you define.</span></span> 

<span data-ttu-id="83eb9-107">Skype for Business Server は、会議、ダイヤルイン、および管理者の 3 つの簡単な URL をサポートしています。会議とダイヤルインの簡易 URL を設定する必要があります。また、管理簡易 URL はオプションです。</span><span class="sxs-lookup"><span data-stu-id="83eb9-107">Skype for Business Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="83eb9-108">簡易 URL をサポートする必要があるドメイン ネーム システム (DNS) レコードは、これらの簡易 URL の定義方法、および簡易 URL の障害復旧をサポートするかどうかによって異なっています。</span><span class="sxs-lookup"><span data-stu-id="83eb9-108">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span> 

## <a name="simple-url-scope"></a><span data-ttu-id="83eb9-109">簡易 URL スコープ</span><span class="sxs-lookup"><span data-stu-id="83eb9-109">Simple URL scope</span></span>

<span data-ttu-id="83eb9-p103">簡易 URL には、グローバル スコープを適用できます。また、組織内の各セントラル サイトで別々の簡易 URL を指定することもできます。 簡単なグローバル URL と簡単なサイト URL の両方が指定されている場合は、簡単なサイト URL が優先されます。</span><span class="sxs-lookup"><span data-stu-id="83eb9-p103">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization. If both a global simple URL and a site simple URL are specified, the site simple URL has precedence.</span></span> 

<span data-ttu-id="83eb9-112">ほとんどの場合、簡単な URL はグローバル レベルでのみ設定することをお勧めします。そのため、ユーザーの簡易 URL をあるサイトから別のサイトに移動しても変更されません。</span><span class="sxs-lookup"><span data-stu-id="83eb9-112">In most cases, we recommend that you set simple URLs only at the global level, so that a user's Meet simple URL does not change if they move from one site to another.</span></span> <span data-ttu-id="83eb9-113">例外は、異なるサイトのダイヤルイン ユーザーに異なる電話番号を使用する必要がある組織です。</span><span class="sxs-lookup"><span data-stu-id="83eb9-113">The exception would be organizations that need to use different telephone numbers for dial-in users at different sites.</span></span> <span data-ttu-id="83eb9-114">サイトで 1 つの簡易 URL (ダイヤルイン簡易 URL など) をサイト レベルの簡易 URL に設定する場合は、そのサイトの他の簡易 URL もサイト レベルに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83eb9-114">Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<span data-ttu-id="83eb9-115">トポロジ ビルダーでは、グローバルな簡易 URL を設定できます。</span><span class="sxs-lookup"><span data-stu-id="83eb9-115">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="83eb9-116">サイト レベルで簡単な URL を設定するには、次のコマンドレットSet-CsSimpleURLConfigurationします。</span><span class="sxs-lookup"><span data-stu-id="83eb9-116">To set a simple URL at the site level, use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

<span data-ttu-id="83eb9-117">簡易 URL を定義するには、DNS 構成で A または AAAA レコードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83eb9-117">Defining a simple URL will also require setting an A and/or AAAA record in your DNS configuration.</span></span>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="83eb9-118">簡易 URL の名前付け規則と入力規則</span><span class="sxs-lookup"><span data-stu-id="83eb9-118">Simple URL naming and validation rules</span></span>
<span data-ttu-id="83eb9-119"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="83eb9-119"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="83eb9-120">トポロジ ビルダーと Skype for Business Server 管理シェル コマンドレットは、簡易 URL に対していくつかの検証ルールを適用します。</span><span class="sxs-lookup"><span data-stu-id="83eb9-120">Topology Builder and the Skype for Business Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="83eb9-121">ユーザーは、簡単な会議 URL およびダイヤルイン URL の設定を要求されますが、簡単な管理 URL の設定はオプションです。</span><span class="sxs-lookup"><span data-stu-id="83eb9-121">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="83eb9-122">各 SIP ドメインは独立した簡単な会議 URL を持つ必要がありますが、簡単なダイヤルイン URL と簡単な会議 URL については組織全体で必要な数は 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="83eb9-122">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="83eb9-123">組織内の各簡易 URL は一意の名前を持つ必要があります。また、別の簡易 URL のプレフィックスにすることはできません (たとえば、会議の簡易 URL として SfB2015.contoso.com/Meet を設定し、ダイヤルイン簡易 URL として SfB2015.contoso.com/Meet/Dialin を設定することはできません)。</span><span class="sxs-lookup"><span data-stu-id="83eb9-123">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set SfB2015.contoso.com/Meet as your Meet simple URL and SfB2015.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="83eb9-124">簡易 URL 名には、プールの FQDN を含め、ポート情報を含めすることはできません (たとえば https://FQDN:88/meet 、許可されません)。</span><span class="sxs-lookup"><span data-stu-id="83eb9-124">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="83eb9-125">簡易 URL は、すべてプレフィックス https:// で始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="83eb9-125">All simple URLs must start with the https:// prefix.</span></span> 

<span data-ttu-id="83eb9-p108">簡易 URL の名前には、英数字 (すなわち、a ～ z、A ～ Z、0 ～ 9) およびピリオド (.) 以外は使用できません。 他の文字を使用すると、簡易 URL が予想どおりに機能しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="83eb9-p108">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.). If you use other characters, the simple URLs might not work as expected.</span></span>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="83eb9-128">展開後の簡易 URL の変更</span><span class="sxs-lookup"><span data-stu-id="83eb9-128">Changing Simple URLs after deployment</span></span>
<span data-ttu-id="83eb9-129"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="83eb9-129"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="83eb9-130">初回の展開後に簡易 URL を変更する場合は、その変更が簡易 URL の DNS レコードと証明書に及ぼす影響について認識しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="83eb9-130">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="83eb9-131">簡易 URL の基本部分が変わる場合は、DNS レコードと証明書も変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83eb9-131">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="83eb9-132">たとえば、ベース URL を SfB2015.contoso.com から meet.contoso.com に変更する変更を行う場合、DNS レコードと証明書を変更して https://SfB2015.contoso.com/Meet https://meet.contoso.com meet.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="83eb9-132">For example, changing from https://SfB2015.contoso.com/Meet to https://meet.contoso.com changes the base URL from SfB2015.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="83eb9-133">簡易 URL を次の URL に変更した場合、SfB2015.contoso.comのベース URL は変わっていないので、DNS または証明書の変更は https://SfB2015.contoso.com/Meet https://SfB2015.contoso.com/Meetings 必要はありません。</span><span class="sxs-lookup"><span data-stu-id="83eb9-133">If you changed the simple URL from https://SfB2015.contoso.com/Meet to https://SfB2015.contoso.com/Meetings, the base URL of SfB2015.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="83eb9-134">ただし、簡単な URL 名を変更するたびに、各ディレクターとフロントエンド サーバーで **Enable-CsComputer** を実行して変更を登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83eb9-134">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

## <a name="naming-examples-for-simple-urls"></a><span data-ttu-id="83eb9-135">簡易 URL の名前付け例</span><span class="sxs-lookup"><span data-stu-id="83eb9-135">Naming examples for Simple URLs</span></span>
<span data-ttu-id="83eb9-136"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="83eb9-136"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="83eb9-p110">簡易 URL の命名には、推奨される 3 つのオプションがあります。選択するオプションによって、簡易 URL をサポートする DNS A レコードと証明書の設定方法が影響を受けます。各オプションでは、組織内の SIP ドメインごとに簡単な会議 URL を 1 つ構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83eb9-p110">There are three recommended options for naming your simple URLs. Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs. In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span> 

<span data-ttu-id="83eb9-140">簡単なダイヤルインおよび管理 URL については、所有している SIP ドメインの数とは関係なく、組織全体で必要な数は、常に 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="83eb9-140">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="83eb9-141">オプション 1 では、簡易 URL ごとに、新しい SIP ドメイン名を作成します。</span><span class="sxs-lookup"><span data-stu-id="83eb9-141">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="83eb9-142">このオプションを使用する場合は、簡易 URL ごとに独立した DNS A レコードが必要であり、証明書で各簡単な会議 URL を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83eb9-142">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

<span data-ttu-id="83eb9-143">**簡易 URL 命名オプション 1**</span><span class="sxs-lookup"><span data-stu-id="83eb9-143">**Simple URL Naming Option 1**</span></span>


| <span data-ttu-id="83eb9-144">**簡易 URL**</span><span class="sxs-lookup"><span data-stu-id="83eb9-144">**Simple URL**</span></span> <br/> | <span data-ttu-id="83eb9-145">**例**</span><span class="sxs-lookup"><span data-stu-id="83eb9-145">**Example**</span></span> <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="83eb9-146">Meet</span><span class="sxs-lookup"><span data-stu-id="83eb9-146">Meet</span></span>  <br/>          | <span data-ttu-id="83eb9-147">https://meet.contoso.com、 https://meet.fabrikam.com など (組織内の SIP ドメインごとに 1 つ)</span><span class="sxs-lookup"><span data-stu-id="83eb9-147">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span>  <br/> |
| <span data-ttu-id="83eb9-148">ダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="83eb9-148">Dial-in</span></span>  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| <span data-ttu-id="83eb9-149">管理者</span><span class="sxs-lookup"><span data-stu-id="83eb9-149">Admin</span></span>  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

<span data-ttu-id="83eb9-150">オプション 2 では、簡易 URL はドメイン名とドメイン名にSfB2015.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="83eb9-150">With Option 2, simple URLs are based on the domain name SfB2015.contoso.com.</span></span> <span data-ttu-id="83eb9-151">このため、必要な DNS A レコードは 1 つだけであり、この DNS A レコードで、簡易 URL の 3 つのタイプすべてを有効にします。</span><span class="sxs-lookup"><span data-stu-id="83eb9-151">Therefore, you need only one DNS A record which enables all three types of simple URLs.</span></span> <span data-ttu-id="83eb9-152">この DNS A レコードは、このSfB2015.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="83eb9-152">This DNS A record references SfB2015.contoso.com.</span></span> <span data-ttu-id="83eb9-153">この場合も、組織内の他の SIP ドメインについては、独立した DNS A レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="83eb9-153">Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span> 

<span data-ttu-id="83eb9-154">**簡易 URL 命名オプション 2**</span><span class="sxs-lookup"><span data-stu-id="83eb9-154">**Simple URL Naming Option 2**</span></span>


| <span data-ttu-id="83eb9-155">**簡易 URL**</span><span class="sxs-lookup"><span data-stu-id="83eb9-155">**Simple URL**</span></span> <br/> | <span data-ttu-id="83eb9-156">**例**</span><span class="sxs-lookup"><span data-stu-id="83eb9-156">**Example**</span></span> <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="83eb9-157">Meet</span><span class="sxs-lookup"><span data-stu-id="83eb9-157">Meet</span></span>  <br/>          | <span data-ttu-id="83eb9-158">https://SfB2015.contoso.com/Meet、 https://SfB2015.fabrikam.com/Meet など (組織内の SIP ドメインごとに 1 つ)</span><span class="sxs-lookup"><span data-stu-id="83eb9-158">https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span>  <br/> |
| <span data-ttu-id="83eb9-159">ダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="83eb9-159">Dial-in</span></span>  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| <span data-ttu-id="83eb9-160">管理者</span><span class="sxs-lookup"><span data-stu-id="83eb9-160">Admin</span></span>  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

<span data-ttu-id="83eb9-161">SIP ドメインの数が多く、これらのドメインに独立した簡単会議 URL を持たせて、これらの簡易 URL の DNS レコードと証明書の要件をできるだけ少なくする場合は、オプション 3 が最も便利です。</span><span class="sxs-lookup"><span data-stu-id="83eb9-161">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span> 

<span data-ttu-id="83eb9-162">**簡易 URL 命名オプション 3**</span><span class="sxs-lookup"><span data-stu-id="83eb9-162">**Simple URL Naming Option 3**</span></span>


| <span data-ttu-id="83eb9-163">**簡易 URL**</span><span class="sxs-lookup"><span data-stu-id="83eb9-163">**Simple URL**</span></span> <br/> | <span data-ttu-id="83eb9-164">**例**</span><span class="sxs-lookup"><span data-stu-id="83eb9-164">**Example**</span></span> <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="83eb9-165">Meet</span><span class="sxs-lookup"><span data-stu-id="83eb9-165">Meet</span></span>  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| <span data-ttu-id="83eb9-166">ダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="83eb9-166">Dial-in</span></span>  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| <span data-ttu-id="83eb9-167">管理者</span><span class="sxs-lookup"><span data-stu-id="83eb9-167">Admin</span></span>  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="83eb9-168">簡易 URL の障害復旧オプション</span><span class="sxs-lookup"><span data-stu-id="83eb9-168">Disaster Recovery option for simple URLs</span></span>
<span data-ttu-id="83eb9-169"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="83eb9-169"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="83eb9-170">フロントエンド プールを含むサイトが複数ある場合に、DNS プロバイダーが GeoDNS をサポートしている場合は、障害復旧をサポートするために簡易 URL の DNS レコードを設定して、1 つのフロントエンド プール全体がダウンしても簡易 URL 機能を続行できます。</span><span class="sxs-lookup"><span data-stu-id="83eb9-170">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="83eb9-171">この障害復旧機能は、会議とダイヤルインの簡易 URL をサポートします。</span><span class="sxs-lookup"><span data-stu-id="83eb9-171">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="83eb9-p113">これを構成するには、2 つの GeoDNS アドレスを作成します。各アドレスは、障害の復旧目的でペアになった 2 つのプールに解決される、2 つの DNS A または CNAME レコードを持っています。1 つの GeoDNS アドレスは内部アクセスに使用され、2 つのプールのロード バランサー IP アドレス、または内部 Web FQDN に解決されます。もう一つの GeoDNS アドレスは外部アクセスに使用され、2 つのプールのロード バランサー IP アドレス、または外部 Web FQDN に解決されます。以下は、プールの FQDN を使用した、会議簡易 URL の例です。</span><span class="sxs-lookup"><span data-stu-id="83eb9-p113">To configure this, create two GeoDNS addresses. Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes. One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools. The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools. The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span> 

```console
Meet-int.geolb.contoso.com
     Pool1InternalWebFQDN.contoso.com
     Pool2InternalWebFQDN.contoso.com
```

```console
Meet-ext.geolb.contoso.com
     Pool1ExternalWebFQDN.contoso.com
     Pool2ExternalWebFQDN.contoso.com
```

<span data-ttu-id="83eb9-177">次に、(meet.contoso.com のような) 会議簡易 URL を 2 つの GeoDNS アドレスに解決する CNAME レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="83eb9-177">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

> [!NOTE]
> <span data-ttu-id="83eb9-178">ネットワークがヘアピン (組織内部からのトラフィックを含め、すべての簡易 URL トラフィックを外部リンク経由でルーティングすること) を使用している場合は、外部 GeoDNS アドレスを構成して、その外部アドレスのみに会議簡易 URL を解決できます。</span><span class="sxs-lookup"><span data-stu-id="83eb9-178">If your network uses hairpinning (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>

<span data-ttu-id="83eb9-179">この方式を使用するとき、2 つのプールに要求を配布するラウンドロビン方式か、または (地理的に近いプールなど) 1 つのプールに主に接続し、もう 1 つのプールは接続障害の場合にのみ使用するように、各 GeoDNS アドレスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="83eb9-179">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span> 

<span data-ttu-id="83eb9-180">ダイヤルイン簡易 URL でも同じ構成をセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="83eb9-180">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="83eb9-181">これを行うには、DNS レコードに代わり、前の例のような追加  `dialin` `meet` のレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="83eb9-181">To do so, create additional records like those in the previous example, substituting  `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="83eb9-182">管理簡易 URL では、このセクションで以前に示した 3 つのオプションのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="83eb9-182">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="83eb9-183">この構成をセットアップした後に、監視アプリケーションを使用して、障害の監視用に HTTP 監視をセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="83eb9-183">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="83eb9-184">外部アクセスの場合は、HTTPS GET lyncdiscover を監視して確認します。<sipdomain></span><span class="sxs-lookup"><span data-stu-id="83eb9-184">For external access, monitor to make sure that HTTPS GET lyncdiscover.<sipdomain></span></span> <span data-ttu-id="83eb9-185">2 つのプールの外部 Web FQDN またはロード バランサー IP アドレスへの要求が成功しました。</span><span class="sxs-lookup"><span data-stu-id="83eb9-185">requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="83eb9-186">たとえば、以下の要求では、**ACCEPT** ヘッダーが含まれないようにし、**200 OK** を戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="83eb9-186">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

```console
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

<span data-ttu-id="83eb9-187">内部アクセスでは、内部 Web FQDN のポート 5061、または 2 つのプール用のロード バランサー IP アドレスを監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83eb9-187">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="83eb9-188">接続エラーが検出された場合、これらのプールの VIP はポート 80、443、4443 を閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="83eb9-188">If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 4443.</span></span>


