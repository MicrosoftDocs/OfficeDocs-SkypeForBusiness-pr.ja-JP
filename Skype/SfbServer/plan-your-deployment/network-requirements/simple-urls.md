---
title: ビジネス サーバー 2015 の Skype での簡単な Url の DNS の要件
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/9/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: '概要: は、Skype のビジネス サーバー 2015 の DNS レコードを実装する前にこのトピックの簡単な URL の注意事項を確認します。'
ms.openlocfilehash: 87346a7c4c03837e5ebfdf0143cdb7c786f0e43b
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2018
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server-2015"></a><span data-ttu-id="1e9bf-103">ビジネス サーバー 2015 の Skype での簡単な Url の DNS の要件</span><span class="sxs-lookup"><span data-stu-id="1e9bf-103">DNS requirements for simple URLs in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1e9bf-104">**の概要:**Skype のビジネス サーバー 2015 の DNS レコードを実装する前に、このトピックの簡単な URL の注意事項を確認します。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-104">**Summary:** Review the Simple URL considerations in this topic before implementing DNS records for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="1e9bf-105">単純な Url、ユーザーの参加する会議を簡単、Skype の取得 Business Server 管理ツールを簡単に管理者にします。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-105">Simple URLs make joining meetings easier for your users, and make getting to Skype for Business Server administrative tools easier for administrators.</span></span> <span data-ttu-id="1e9bf-106">単純な Url を定義する SIP ドメインのいずれにも一致する必要がありますが、自身のドメインを使用します。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-106">Simple URLs use their own domain, which must not match any of the SIP domains you define.</span></span> 
  
<span data-ttu-id="1e9bf-107">Skype ビジネス サーバーの次の 3 つの簡単な Url をサポートしています: ダイヤルして、管理者に対応対応し、ダイヤルインの簡単な Url を設定する必要があると、管理の簡単な URL は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-107">Skype for Business Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="1e9bf-108">単純な Url をサポートする必要があるドメイン ネーム システム (DNS) レコードは、このような単純な Url を定義する方法と、簡単な Url の災害復旧をサポートするかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-108">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span> 
  
## <a name="simple-url-scope"></a><span data-ttu-id="1e9bf-109">単純な URL スコープ</span><span class="sxs-lookup"><span data-stu-id="1e9bf-109">Simple URL scope</span></span>

<span data-ttu-id="1e9bf-110">グローバル スコープを持ち、単純な Url を構成することができます。 またはセントラル サイトごとに別の簡単な Url を指定するには、組織内。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-110">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="1e9bf-111">グローバルの簡単な URL とサイトの簡単な URL の両方を指定すると、サイトの簡単な URL は優先順位を持ちます。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-111">If both a global simple URL and a site simple URL are specified, the site simple URL has precedence.</span></span> 
  
<span data-ttu-id="1e9bf-112">ユーザーの対応の簡単な URL は変更されません 1 つのサイト間で移動するように、ほとんどの場合のみ、グローバル レベルで、簡単な Url を設定することを勧めします。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-112">In most cases, we recommend that you set simple URLs only at the global level, so that a user's Meet simple URL does not change if they move from one site to another.</span></span> <span data-ttu-id="1e9bf-113">例外を別のサイトでは、ダイヤルイン ユーザーの別の電話番号を使用する必要がある組織となります。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-113">The exception would be organizations that need to use different telephone numbers for dial-in users at different sites.</span></span> <span data-ttu-id="1e9bf-114">サイト レベルの簡単な URL を使用するサイトで、ダイヤルの簡単な URL) などの 1 つの簡単な URL を設定する場合設定する必要も、他の単純な Url もサイト レベルにするには、そのサイトで注意してください。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-114">Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>
  
<span data-ttu-id="1e9bf-115">トポロジ ビルダーでは、グローバルの簡単な Url を設定できます。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-115">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="1e9bf-116">サイト レベルでの簡単な URL を設定するには、セット CsSimpleURLConfiguration コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-116">To set a simple URL at the site level, use the Set-CsSimpleURLConfiguration cmdlet.</span></span>
  
<span data-ttu-id="1e9bf-117">簡単な URL を定義することも、A または AAAA レコードを DNS の構成の設定に必要です。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-117">Defining a simple URL will also require setting an A and/or AAAA record in your DNS configuration.</span></span>
  
## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="1e9bf-118">URL の簡単な名前付けと検証ルール</span><span class="sxs-lookup"><span data-stu-id="1e9bf-118">Simple URL naming and validation rules</span></span>
<span data-ttu-id="1e9bf-119"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="1e9bf-119"></span></span>

<span data-ttu-id="1e9bf-120">トポロジ ビルダーおよびビジネス サーバー管理シェル コマンドレットの Skype、簡単な Url のいくつかの入力規則を適用します。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-120">Topology Builder and the Skype for Business Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="1e9bf-121">即時会議およびダイヤルイン、単純な Url を設定する必要がありますが、オプションは、管理者のいずれかを設定します。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-121">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="1e9bf-122">SIP ドメインごとに個別対応簡単な URL を持つ必要がありますが、組織全体の 1 つだけのダイヤルインの簡単な URL と 1 つの管理者の簡単な URL を必要します。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-122">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>
  
<span data-ttu-id="1e9bf-123">組織内のそれぞれの簡単な URL が一意の名前を持つ必要があり、別の簡単な URL のプレフィックスにすることはできません (たとえば、するを設定できませんでした、対応の簡単な URL として SfB2015.contoso.com/Meet と SfB2015.contoso.com/Meet/Dialin、ダイヤルインの簡単な URL として)。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-123">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set SfB2015.contoso.com/Meet as your Meet simple URL and SfB2015.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="1e9bf-124">簡単な URL の名前は、プールでは、いずれかまたはすべてのポート情報の FQDN を含めることはできません (たとえば、https://FQDN:88/meetは許可されていません)。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-124">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="1e9bf-125">すべての単純な Url は、https:// の接頭辞で始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-125">All simple URLs must start with the https:// prefix.</span></span> 
  
<span data-ttu-id="1e9bf-126">単純な Url は英数字のみを含めることができます (つまり、a-z、A-Z、0-9、およびピリオド (.)。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-126">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.).</span></span> <span data-ttu-id="1e9bf-127">その他の文字を使用する場合、単純な Url 可能性がありますどおり動作します。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-127">If you use other characters, the simple URLs might not work as expected.</span></span>
  
## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="1e9bf-128">配置後に簡単な Url を変更します。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-128">Changing Simple URLs after deployment</span></span>
<span data-ttu-id="1e9bf-129"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="1e9bf-129"></span></span>

<span data-ttu-id="1e9bf-130">最初の展開後に、簡単な URL を変更する場合は、変更に及ぼす影響について、DNS レコードと証明書の簡単な Url に注意してくださいする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-130">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="1e9bf-131">簡単な URL のベースが変更された場合は、DNS レコードと証明書もを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-131">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="1e9bf-132">変更するたとえば、https://SfB2015.contoso.com/Meetをhttps://meet.contoso.comに変更を基本 URL SfB2015.contoso.com から meet.contoso.com、DNS レコードと meet.contoso.com を参照する証明書を変更する必要があります。簡単な URL を変更した場合はhttps://SfB2015.contoso.com/Meetにhttps://SfB2015.contoso.com/Meetings、SfB2015.contoso.com のベース URL は同じですがないため DNS、または証明書の変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-132">For example, changing from https://SfB2015.contoso.com/Meet to https://meet.contoso.com changes the base URL from SfB2015.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com. If you changed the simple URL from https://SfB2015.contoso.com/Meet to https://SfB2015.contoso.com/Meetings, the base URL of SfB2015.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>
  
<span data-ttu-id="1e9bf-133">簡単な URL 名を変更するたびに、変更を登録するには各ディレクターおよびフロント エンド サーバーで**有効にする CsComputer**を実行してください。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-133">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>
  
## <a name="naming-examples-for-simple-urls"></a><span data-ttu-id="1e9bf-134">簡単な Url の名前付けの例</span><span class="sxs-lookup"><span data-stu-id="1e9bf-134">Naming examples for Simple URLs</span></span>
<span data-ttu-id="1e9bf-135"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="1e9bf-135"></span></span>

<span data-ttu-id="1e9bf-136">簡単な Url の名前を付けるための 3 つの推奨されるオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-136">There are three recommended options for naming your simple URLs.</span></span> <span data-ttu-id="1e9bf-137">どのオプションを選択では、DNS の A レコードと単純な Url をサポートする証明書を設定する方法に影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-137">Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs.</span></span> <span data-ttu-id="1e9bf-138">各オプションでは、組織の SIP ドメインごとに 1 つの対応の簡単な URL を構成することにあります。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-138">In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span> 
  
<span data-ttu-id="1e9bf-139">ダイヤルの場合、組織全体である SIP ドメインの数に関係なく、管理者との 1 つ 1 つだけの簡単な URL を常に必要です。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-139">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>
  
<span data-ttu-id="1e9bf-140">オプション 1 では、簡単な URL ごとに、新しい SIP ドメイン名を作成します。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-140">In Option 1, you create a new SIP domain name for each simple URL.</span></span>
  
<span data-ttu-id="1e9bf-141">このオプションを使用する場合は、必要な個別の DNS A レコードごとの簡単な URL、および各対応の簡単な URL は、証明書の名前必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-141">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>
  
<span data-ttu-id="1e9bf-142">**簡単な URL 命名オプション 1**</span><span class="sxs-lookup"><span data-stu-id="1e9bf-142">**Simple URL Naming Option 1**</span></span>

|<span data-ttu-id="1e9bf-143">**簡易 URL**</span><span class="sxs-lookup"><span data-stu-id="1e9bf-143">**Simple URL**</span></span> <br/> |<span data-ttu-id="1e9bf-144">**例**</span><span class="sxs-lookup"><span data-stu-id="1e9bf-144">**Example**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="1e9bf-145">会議</span><span class="sxs-lookup"><span data-stu-id="1e9bf-145">Meet</span></span>  <br/> |<span data-ttu-id="1e9bf-146">https://meet.contoso.com、 https://meet.fabrikam.com、というように (組織内の SIP ドメインごとに 1 つ)</span><span class="sxs-lookup"><span data-stu-id="1e9bf-146">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span>  <br/> |
|<span data-ttu-id="1e9bf-147">ダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="1e9bf-147">Dial-in</span></span>  <br/> |https://dialin.contoso.com  <br/> |
|<span data-ttu-id="1e9bf-148">管理</span><span class="sxs-lookup"><span data-stu-id="1e9bf-148">Admin</span></span>  <br/> |https://admin.contoso.com  <br/> |
   
<span data-ttu-id="1e9bf-149">オプション 2 では、単純な Url は、ドメイン名 SfB2015.contoso.com に基づいています。したがって、すべての 3 種類の簡単な Url を有効にする DNS A レコードを 1 つだけ必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-149">With Option 2, simple URLs are based on the domain name SfB2015.contoso.com. Therefore, you need only one DNS A record which enables all three types of simple URLs.</span></span> <span data-ttu-id="1e9bf-150">この DNS の A レコードでは、SfB2015.contoso.com を参照します。さらに、する必要があります別の DNS の A レコードの他の SIP ドメインの組織で。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-150">This DNS A record references SfB2015.contoso.com. Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span> 
  
<span data-ttu-id="1e9bf-151">**簡単な URL 命名オプション 2**</span><span class="sxs-lookup"><span data-stu-id="1e9bf-151">**Simple URL Naming Option 2**</span></span>

|<span data-ttu-id="1e9bf-152">**簡易 URL**</span><span class="sxs-lookup"><span data-stu-id="1e9bf-152">**Simple URL**</span></span> <br/> |<span data-ttu-id="1e9bf-153">**例**</span><span class="sxs-lookup"><span data-stu-id="1e9bf-153">**Example**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="1e9bf-154">会議</span><span class="sxs-lookup"><span data-stu-id="1e9bf-154">Meet</span></span>  <br/> |<span data-ttu-id="1e9bf-155">https://SfB2015.contoso.com/Meet、 https://SfB2015.fabrikam.com/Meet、というように (組織内の SIP ドメインごとに 1 つ)</span><span class="sxs-lookup"><span data-stu-id="1e9bf-155">https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span>  <br/> |
|<span data-ttu-id="1e9bf-156">ダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="1e9bf-156">Dial-in</span></span>  <br/> |https://SfB2015.contoso.com/Dialin  <br/> |
|<span data-ttu-id="1e9bf-157">管理</span><span class="sxs-lookup"><span data-stu-id="1e9bf-157">Admin</span></span>  <br/> |https://SfB2015.contoso.com/Admin  <br/> |
   
<span data-ttu-id="1e9bf-158">オプション 3 は、多くの SIP ドメインがあるし、する個別対応の簡単な Url があるが、これらの簡単な Url の DNS レコードと証明書の要件を最小限に抑えたい場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-158">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span> 
  
<span data-ttu-id="1e9bf-159">**簡単な URL 命名オプション 3**</span><span class="sxs-lookup"><span data-stu-id="1e9bf-159">**Simple URL Naming Option 3**</span></span>

|<span data-ttu-id="1e9bf-160">**簡易 URL**</span><span class="sxs-lookup"><span data-stu-id="1e9bf-160">**Simple URL**</span></span> <br/> |<span data-ttu-id="1e9bf-161">**例**</span><span class="sxs-lookup"><span data-stu-id="1e9bf-161">**Example**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="1e9bf-162">会議</span><span class="sxs-lookup"><span data-stu-id="1e9bf-162">Meet</span></span>  <br/> |https://SfB2015.contoso.com/contosoSIPdomain/Meet  <br/> https://SfB2015.contoso.com/fabrikamSIPdomain/Meet  <br/> |
|<span data-ttu-id="1e9bf-163">ダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="1e9bf-163">Dial-in</span></span>  <br/> |https://SfB2015.contoso.com/Dialin  <br/> |
|<span data-ttu-id="1e9bf-164">管理</span><span class="sxs-lookup"><span data-stu-id="1e9bf-164">Admin</span></span>  <br/> |https://SfB2015.contoso.com/Admin  <br/> |
   
## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="1e9bf-165">簡単な Url の災害復旧オプション</span><span class="sxs-lookup"><span data-stu-id="1e9bf-165">Disaster Recovery option for simple URLs</span></span>
<span data-ttu-id="1e9bf-166"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="1e9bf-166"></span></span>

<span data-ttu-id="1e9bf-167">フロント エンド プールが含まれているサイトが複数ある場合は、DNS プロバイダーは、GeoDNS をサポートしています、全体のフロント エンド プールを 1 つがダウンした場合でも、簡単な URL の機能が解決しないように災害復旧をサポートするための簡単な Url の DNS レコードを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-167">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="1e9bf-168">この災害復旧の機能には対応し、簡単なダイヤルイン Url がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-168">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>
  
<span data-ttu-id="1e9bf-p113">これを構成するには、2 つの GeoDNS アドレスを作成します。各アドレスは、障害の復旧目的でペアになった 2 つのプールに解決される、2 つの DNS A または CNAME レコードを持っています。1 つの GeoDNS アドレスは内部アクセスに使用され、2 つのプールのロード バランサー IP アドレス、または内部 Web FQDN に解決されます。もう 1 つの GeoDNS アドレスは外部アクセスに使用され、2 つのプールのロード バランサー IP アドレス、または外部 Web FQDN に解決されます。以下は、プールの FQDN を使用した、会議簡易 URL の例です。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-p113">To configure this, create two GeoDNS addresses. Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes. One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools. The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools. The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span> 
  
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

<span data-ttu-id="1e9bf-174">次に、(meet.contoso.com のような) 会議簡易 URL を 2 つの GeoDNS アドレスに解決する CNAME レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-174">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1e9bf-175">ネットワークでは、(を通じて、組織内から送信されるトラフィックを含め、外部リンクに、簡単な URL のすべてのトラフィックをルーティングする) hairpinning を使用する場合、だけ GeoDNS の外部アドレスを構成してのみに対応、簡単な URL を解決するには外部アドレスです。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-175">If your network uses hairpinning (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>
  
<span data-ttu-id="1e9bf-176">この方式を使用するとき、2 つのプールに要求を配布するラウンドロビン方式か、または (地理的に近いプールなど) 1 つのプールに主に接続し、もう 1 つのプールは接続障害の場合にのみ使用するように、各 GeoDNS アドレスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-176">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span> 
  
<span data-ttu-id="1e9bf-177">ダイヤルイン簡易 URL でも同じ構成をセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-177">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="1e9bf-178">ような以前の例では、追加のレコードを作成するには、代わりに`dialin`の`meet`の DNS レコードです。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-178">To do so, create additional records like those in the previous example, substituting  `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="1e9bf-179">管理簡易 URL では、このセクションで以前に示した 3 つのオプションのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-179">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>
  
<span data-ttu-id="1e9bf-180">この構成をセットアップした後に、監視アプリケーションを使用して、障害の監視用に HTTP 監視をセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-180">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="1e9bf-181">外部アクセスは、HTTPS を取得 lyncdiscover はそのことを確認するのにを監視します。<sipdomain></span><span class="sxs-lookup"><span data-stu-id="1e9bf-181">For external access, monitor to make sure that HTTPS GET lyncdiscover.<sipdomain></span></span> <span data-ttu-id="1e9bf-182">外部 web FQDN またはロード バランサーの IP アドレスの 2 つのプールへの要求は、成功でした。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-182">requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="1e9bf-183">たとえば、次の要求の**ACCEPT**ヘッダーが含まれていない必要があります、返す必要があります**200 OK**。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-183">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>
  
```
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

<span data-ttu-id="1e9bf-p116">内部アクセスでは、内部 Web FQDN のポート 5061、または 2 つのプール用のロード バランサー IP アドレスを監視する必要があります。接続問題が検出された場合、これらのプールの VIP は、ポート 80、443、および 4443 を閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e9bf-p116">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools. If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 4443.</span></span>
  

