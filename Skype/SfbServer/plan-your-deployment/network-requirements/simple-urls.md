---
title: Skype for Business Server の単純な Url の DNS 要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: '概要: Skype for Business Server の DNS レコードを実装する前に、このトピックで簡単な URL の考慮事項を確認してください。'
ms.openlocfilehash: 7eb734fb4a9005f833f27efd3b0d180593155f39
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815785"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a><span data-ttu-id="9f15d-103">Skype for Business Server の単純な Url の DNS 要件</span><span class="sxs-lookup"><span data-stu-id="9f15d-103">DNS requirements for simple URLs in Skype for Business Server</span></span>

<span data-ttu-id="9f15d-104">**概要:** Skype for Business Server の DNS レコードを実装する前に、このトピックの簡単な URL の考慮事項を確認してください。</span><span class="sxs-lookup"><span data-stu-id="9f15d-104">**Summary:** Review the Simple URL considerations in this topic before implementing DNS records for Skype for Business Server.</span></span>

<span data-ttu-id="9f15d-105">簡単な Url を使用すると、ユーザーは簡単に会議に参加できるようになり、管理者にとって Skype for Business Server の管理ツールがさらに簡単になります。</span><span class="sxs-lookup"><span data-stu-id="9f15d-105">Simple URLs make joining meetings easier for your users, and make getting to Skype for Business Server administrative tools easier for administrators.</span></span> <span data-ttu-id="9f15d-106">単純な Url では独自のドメインが使用されます。これは、定義した SIP ドメインと一致しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f15d-106">Simple URLs use their own domain, which must not match any of the SIP domains you define.</span></span> 

<span data-ttu-id="9f15d-107">Skype for Business Server では、次の3つの簡単な Url (会議、ダイヤルイン、管理者) がサポートされています。会議とダイヤルインの簡単な url を設定する必要があります。管理者の単純な URL は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9f15d-107">Skype for Business Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="9f15d-108">単純な Url をサポートするために必要なドメインネームシステム (DNS) レコードは、これらの単純な Url を定義した方法と、単純な Url の障害回復をサポートするかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="9f15d-108">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span> 

## <a name="simple-url-scope"></a><span data-ttu-id="9f15d-109">単純な URL スコープ</span><span class="sxs-lookup"><span data-stu-id="9f15d-109">Simple URL scope</span></span>

<span data-ttu-id="9f15d-110">グローバルなスコープを持つように単純な Url を構成することも、組織内のセントラルサイトごとに異なる簡単な Url を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="9f15d-110">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="9f15d-111">グローバルな単純 URL とサイトの単純 URL の両方が指定されている場合は、サイトの単純な url が優先されます。</span><span class="sxs-lookup"><span data-stu-id="9f15d-111">If both a global simple URL and a site simple URL are specified, the site simple URL has precedence.</span></span> 

<span data-ttu-id="9f15d-112">ほとんどの場合、単純な url の設定はグローバルレベルでのみ行うことをお勧めします。そのため、あるサイトから別のサイトに移動しても、ユーザーの単純な URL が変わらないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9f15d-112">In most cases, we recommend that you set simple URLs only at the global level, so that a user's Meet simple URL does not change if they move from one site to another.</span></span> <span data-ttu-id="9f15d-113">例外として、さまざまなサイトのダイヤルインユーザーに異なる電話番号を使用する必要がある組織が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="9f15d-113">The exception would be organizations that need to use different telephone numbers for dial-in users at different sites.</span></span> <span data-ttu-id="9f15d-114">1つの単純な URL (ダイヤルインの単純な url など) をサイトレベルの単純な URL として設定する場合は、そのサイトの他の単純な Url もサイトレベルに設定する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9f15d-114">Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<span data-ttu-id="9f15d-115">トポロジビルダーでは、グローバルな単純 Url を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="9f15d-115">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="9f15d-116">サイトレベルで単純な URL を設定するには、Set-CsSimpleURLConfiguration コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9f15d-116">To set a simple URL at the site level, use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

<span data-ttu-id="9f15d-117">単純な URL を定義する場合も、DNS 構成で A/AAAA レコードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f15d-117">Defining a simple URL will also require setting an A and/or AAAA record in your DNS configuration.</span></span>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="9f15d-118">単純な URL の名前付けと入力規則</span><span class="sxs-lookup"><span data-stu-id="9f15d-118">Simple URL naming and validation rules</span></span>
<span data-ttu-id="9f15d-119"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="9f15d-119"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="9f15d-120">トポロジビルダーと Skype for Business Server 管理シェルコマンドレットでは、単純な Url に対して複数の入力規則を適用します。</span><span class="sxs-lookup"><span data-stu-id="9f15d-120">Topology Builder and the Skype for Business Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="9f15d-121">会議とダイヤルインのための単純な Url を設定する必要がありますが、管理者用の設定は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9f15d-121">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="9f15d-122">各 SIP ドメインは、個別の単純な url を持つ必要がありますが、組織全体に1つのダイヤルインの単純な url と管理者の単純な URL を1つだけ用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f15d-122">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="9f15d-123">組織内の各単純 URL には一意の名前を指定する必要があります。また、別の単純な URL のプレフィックスとして使用することはできません (たとえば、SfB2015.contoso.com/Meet の単純な url と SfB2015.contoso.com/Meet/Dialin をダイヤルインの単純な URL として設定することはできません)。</span><span class="sxs-lookup"><span data-stu-id="9f15d-123">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set SfB2015.contoso.com/Meet as your Meet simple URL and SfB2015.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="9f15d-124">単純な URL 名には、任意のプールの FQDN または任意のポート情報を含めることhttps://FQDN:88/meetはできません (たとえば、許可されません)。</span><span class="sxs-lookup"><span data-stu-id="9f15d-124">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="9f15d-125">すべての単純な Url は、https://プレフィックスで始める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f15d-125">All simple URLs must start with the https:// prefix.</span></span> 

<span data-ttu-id="9f15d-126">単純な Url には、英数字 (a ~ z、A ~ z、0-9、ピリオド (.) のみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9f15d-126">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.).</span></span> <span data-ttu-id="9f15d-127">他の文字を使用している場合、単純な Url は期待どおりに動作しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9f15d-127">If you use other characters, the simple URLs might not work as expected.</span></span>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="9f15d-128">展開後の単純な Url の変更</span><span class="sxs-lookup"><span data-stu-id="9f15d-128">Changing Simple URLs after deployment</span></span>
<span data-ttu-id="9f15d-129"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="9f15d-129"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="9f15d-130">最初の展開後に単純な URL を変更する場合は、変更によって、単純な Url の DNS レコードと証明書にどのように影響するかに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f15d-130">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="9f15d-131">単純な URL のベースが変更された場合は、DNS レコードと証明書も変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f15d-131">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="9f15d-132">たとえば、to https://SfB2015.contoso.com/Meet https://meet.contoso.comから MEET.CONTOSO.COM へのベース URL の変更は、SfB2015.contoso.com を参照するように DNS レコードと証明書を変更する必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="9f15d-132">For example, changing from https://SfB2015.contoso.com/Meet to https://meet.contoso.com changes the base URL from SfB2015.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="9f15d-133">Simple URL をからhttps://SfB2015.contoso.com/Meetにhttps://SfB2015.contoso.com/Meetings変更した場合、SfB2015.contoso.com のベース url は変わりません。そのため、DNS や証明書の変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9f15d-133">If you changed the simple URL from https://SfB2015.contoso.com/Meet to https://SfB2015.contoso.com/Meetings, the base URL of SfB2015.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="9f15d-134">ただし、単純な URL 名を変更する場合は必ず、各ディレクターとフロントエンドサーバーで [ユーザーの**有効化**] を実行して、変更を登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f15d-134">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

## <a name="naming-examples-for-simple-urls"></a><span data-ttu-id="9f15d-135">単純な Url の名前付けの例</span><span class="sxs-lookup"><span data-stu-id="9f15d-135">Naming examples for Simple URLs</span></span>
<span data-ttu-id="9f15d-136"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="9f15d-136"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="9f15d-137">簡単な Url に名前を付けるための推奨される3つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="9f15d-137">There are three recommended options for naming your simple URLs.</span></span> <span data-ttu-id="9f15d-138">どちらのオプションを選択するかは、DNS A レコードと単純な Url をサポートする証明書のセットアップ方法によって決まります。</span><span class="sxs-lookup"><span data-stu-id="9f15d-138">Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs.</span></span> <span data-ttu-id="9f15d-139">各オプションで、組織内の各 SIP ドメインに対して、単一の会議の単純 URL を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f15d-139">In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span> 

<span data-ttu-id="9f15d-140">使用している SIP ドメインの数に関係なく、ダイヤルイン用の組織全体に、または管理者用に1つだけ簡単な URL を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f15d-140">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="9f15d-141">オプション1では、各シンプル URL の新しい SIP ドメイン名を作成します。</span><span class="sxs-lookup"><span data-stu-id="9f15d-141">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="9f15d-142">このオプションを使用する場合は、各シンプル URL に個別の DNS A レコードが必要です。また、それぞれの [simple URL] を証明書で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f15d-142">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

<span data-ttu-id="9f15d-143">**簡単な URL の名前付けオプション1**</span><span class="sxs-lookup"><span data-stu-id="9f15d-143">**Simple URL Naming Option 1**</span></span>


| <span data-ttu-id="9f15d-144">**単純な URL**</span><span class="sxs-lookup"><span data-stu-id="9f15d-144">**Simple URL**</span></span> <br/> | <span data-ttu-id="9f15d-145">**例**</span><span class="sxs-lookup"><span data-stu-id="9f15d-145">**Example**</span></span> <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="9f15d-146">即時</span><span class="sxs-lookup"><span data-stu-id="9f15d-146">Meet</span></span>  <br/>          | <span data-ttu-id="9f15d-147">https://meet.contoso.com、 https://meet.fabrikam.comなどの場合 (組織の SIP ドメインごとに1つ)</span><span class="sxs-lookup"><span data-stu-id="9f15d-147">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span>  <br/> |
| <span data-ttu-id="9f15d-148">ダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="9f15d-148">Dial-in</span></span>  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| <span data-ttu-id="9f15d-149">同期</span><span class="sxs-lookup"><span data-stu-id="9f15d-149">Admin</span></span>  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

<span data-ttu-id="9f15d-150">オプション2では、ドメイン名 SfB2015.contoso.com に基づいて単純な Url が作成されます。</span><span class="sxs-lookup"><span data-stu-id="9f15d-150">With Option 2, simple URLs are based on the domain name SfB2015.contoso.com.</span></span> <span data-ttu-id="9f15d-151">そのため、3種類の単純な Url をすべて有効にする DNS A レコードは1つだけである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f15d-151">Therefore, you need only one DNS A record which enables all three types of simple URLs.</span></span> <span data-ttu-id="9f15d-152">この DNS A レコードは SfB2015.contoso.com を参照しています。</span><span class="sxs-lookup"><span data-stu-id="9f15d-152">This DNS A record references SfB2015.contoso.com.</span></span> <span data-ttu-id="9f15d-153">さらに、組織内の他の SIP ドメイン用の DNS A レコードも別途必要です。</span><span class="sxs-lookup"><span data-stu-id="9f15d-153">Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span> 

<span data-ttu-id="9f15d-154">**簡単な URL の名前付けオプション2**</span><span class="sxs-lookup"><span data-stu-id="9f15d-154">**Simple URL Naming Option 2**</span></span>


| <span data-ttu-id="9f15d-155">**単純な URL**</span><span class="sxs-lookup"><span data-stu-id="9f15d-155">**Simple URL**</span></span> <br/> | <span data-ttu-id="9f15d-156">**例**</span><span class="sxs-lookup"><span data-stu-id="9f15d-156">**Example**</span></span> <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="9f15d-157">即時</span><span class="sxs-lookup"><span data-stu-id="9f15d-157">Meet</span></span>  <br/>          | <span data-ttu-id="9f15d-158">https://SfB2015.contoso.com/Meet、 https://SfB2015.fabrikam.com/Meetなどの場合 (組織の SIP ドメインごとに1つ)</span><span class="sxs-lookup"><span data-stu-id="9f15d-158">https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span>  <br/> |
| <span data-ttu-id="9f15d-159">ダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="9f15d-159">Dial-in</span></span>  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| <span data-ttu-id="9f15d-160">同期</span><span class="sxs-lookup"><span data-stu-id="9f15d-160">Admin</span></span>  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

<span data-ttu-id="9f15d-161">オプション3は、多数の SIP ドメインを持っていて、それらのユーザーが単純な Url を個別に指定して、DNS レコードと証明書の要件を最小限に抑える必要がある場合に最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9f15d-161">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span> 

<span data-ttu-id="9f15d-162">**簡単な URL の名前付けオプション3**</span><span class="sxs-lookup"><span data-stu-id="9f15d-162">**Simple URL Naming Option 3**</span></span>


| <span data-ttu-id="9f15d-163">**単純な URL**</span><span class="sxs-lookup"><span data-stu-id="9f15d-163">**Simple URL**</span></span> <br/> | <span data-ttu-id="9f15d-164">**例**</span><span class="sxs-lookup"><span data-stu-id="9f15d-164">**Example**</span></span> <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="9f15d-165">即時</span><span class="sxs-lookup"><span data-stu-id="9f15d-165">Meet</span></span>  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| <span data-ttu-id="9f15d-166">ダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="9f15d-166">Dial-in</span></span>  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| <span data-ttu-id="9f15d-167">同期</span><span class="sxs-lookup"><span data-stu-id="9f15d-167">Admin</span></span>  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="9f15d-168">簡単な Url の障害回復オプション</span><span class="sxs-lookup"><span data-stu-id="9f15d-168">Disaster Recovery option for simple URLs</span></span>
<span data-ttu-id="9f15d-169"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="9f15d-169"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="9f15d-170">フロントエンドプールが含まれている複数のサイトがあり、DNS プロバイダーが GeoDNS をサポートしている場合は、フロントエンドプール全体が停止した場合でも、簡単な URL 機能が続行されるように、単純な URL の DNS レコードを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="9f15d-170">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="9f15d-171">この障害回復機能は、会議とダイヤルインのシンプルな Url をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9f15d-171">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="9f15d-172">これを構成するには、2つの GeoDNS アドレスを作成します。</span><span class="sxs-lookup"><span data-stu-id="9f15d-172">To configure this, create two GeoDNS addresses.</span></span> <span data-ttu-id="9f15d-173">各アドレスには2つの DNS A レコードまたは CNAME レコードがあり、これらは1つのプールに対応しているため、それらは共に災害回復目的でペアリングされます。</span><span class="sxs-lookup"><span data-stu-id="9f15d-173">Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes.</span></span> <span data-ttu-id="9f15d-174">内部アクセスには1つの GeoDNS アドレスが使われ、2つのプールの内部 web FQDN またはロードバランサー IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="9f15d-174">One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="9f15d-175">その他の GeoDNS アドレスは、外部アクセスに使われ、2つのプールの外部 web FQDN またはロードバランサー IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="9f15d-175">The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="9f15d-176">次に示すのは、プールの Fqdn を使用した [simple URL の会議] の例です。</span><span class="sxs-lookup"><span data-stu-id="9f15d-176">The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span> 

```
Meet-int.geolb.contoso.com
     Pool1InternalWebFQDN.contoso.com
     Pool2InternalWebFQDN.contoso.com
```

```
Meet-ext.geolb.contoso.com
     Pool1ExternalWebFQDN.contoso.com
     Pool2ExternalWebFQDN.contoso.com
```

<span data-ttu-id="9f15d-177">次に、会議の単純な URL (meet.contoso.com など) を2つの GeoDNS アドレスに解決する CNAME レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="9f15d-177">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

> [!NOTE]
> <span data-ttu-id="9f15d-178">ネットワークで hairpinning (組織内から送信されるトラフィックを含む、すべての単純な URL トラフィックをルーティングする) が使用されている場合、外部 GeoDNS アドレスを構成して、それに合わせて単純な URL を解決することができます。外部住所。</span><span class="sxs-lookup"><span data-stu-id="9f15d-178">If your network uses hairpinning (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>

<span data-ttu-id="9f15d-179">この方法を使用する場合は、ラウンドロビン方式を使って要求を2つのプールに配布するか、主に1つのプール (地理的に近い場所にあるプールなど) に接続して、次の場合にのみ他のプールを使用するように、各 GeoDNS アドレスを構成できます。接続に失敗します。</span><span class="sxs-lookup"><span data-stu-id="9f15d-179">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span> 

<span data-ttu-id="9f15d-180">ダイヤルインの単純な URL に同じ構成を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="9f15d-180">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="9f15d-181">これを行うには、前の例のように、DNS レコード`dialin`で`meet`の代用として、他のレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="9f15d-181">To do so, create additional records like those in the previous example, substituting  `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="9f15d-182">管理者の簡易 URL については、このセクションで既に説明した3つのオプションのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="9f15d-182">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="9f15d-183">この構成が設定されたら、監視アプリケーションを使用して、エラーを監視するために HTTP 監視を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f15d-183">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="9f15d-184">外部アクセスの場合、監視して HTTPS GET lyncdiscover があることを確認します。<sipdomain></span><span class="sxs-lookup"><span data-stu-id="9f15d-184">For external access, monitor to make sure that HTTPS GET lyncdiscover.<sipdomain></span></span> <span data-ttu-id="9f15d-185">2つのプールの外部 web FQDN またはロードバランサー IP アドレスへの要求が成功します。</span><span class="sxs-lookup"><span data-stu-id="9f15d-185">requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="9f15d-186">たとえば、次の要求には**ACCEPT**ヘッダーが含まれておらず、 **200 OK**を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f15d-186">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

```
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

<span data-ttu-id="9f15d-187">内部アクセスの場合は、2つのプールの内部 web FQDN またはロードバランサー IP アドレスのポート5061を監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f15d-187">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="9f15d-188">接続エラーが検出された場合、これらのプールの VIP は、ポート80、443、4443を閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f15d-188">If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 4443.</span></span>


