---
title: DNS の基本
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
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 には DNS サービスを提供できるソフトウェアが組み込まれています。そのため、DNS ポリシー シナリオ ガイドなどの利用可能なドキュメントを確認できます。 必要に応じて、サード パーティ製のソリューションを選択できます。
ms.openlocfilehash: dc60bab84220cad306deee408a6a09fc16df5a10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825587"
---
# <a name="dns-basics"></a><span data-ttu-id="1c7fe-104">DNS の基本</span><span class="sxs-lookup"><span data-stu-id="1c7fe-104">DNS basics</span></span>
 
<span data-ttu-id="1c7fe-105">Windows Server 2016 には DNS サービスを提供できるソフトウェアが組み込まれています。そのため [、DNS](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide)ポリシー シナリオ ガイドなどの利用可能なドキュメントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-105">Windows Server 2016 has built-in software that can provide DNS services, so you may want to review the available documentation such as the [DNS Policy Scenario Guide](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide).</span></span> <span data-ttu-id="1c7fe-106">必要に応じて、サード パーティ製のソリューションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-106">You can choose a third-party solution if you prefer.</span></span>
  
<span data-ttu-id="1c7fe-107">ベスト プラクティスとして、DNS を提供するために実装内の特定のサーバーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-107">We recommend that as a best practice you dedicate a specific server in your implementation to provide DNS.</span></span> <span data-ttu-id="1c7fe-108">Skype for Business サーバーの役割の 1 つ専用のサーバーの 1 つでセットアップできる可能性がありますが、そのサーバーもプールの一部であり、誤って Skype for Business が使用停止になっていた場合は、DNS サービスが再確立されるまで正常に機能しなけれなっていた可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-108">You could potentially set it up on one of the servers dedicated to one of the Skype for Business server roles, but if that server was also part of a pool and got decommissioned by accident Skype for Business would malfunction until DNS services were re-established.</span></span>
  
## <a name="dns-records"></a><span data-ttu-id="1c7fe-109">DNS レコード</span><span class="sxs-lookup"><span data-stu-id="1c7fe-109">DNS Records</span></span>

<span data-ttu-id="1c7fe-110">IP アドレスへの名前のマッピング (および IPv4 または IPv6 アドレスの可能性がある) は、DNS サーバー上の DNS レコードに格納されます。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-110">Each mapping of a name to an IP address (and that could be an IPv4 or IPv6 address) is stored in a DNS record on the DNS server.</span></span> <span data-ttu-id="1c7fe-111">この名前は、DNS レポートで、具体的には FQDN (完全修飾ドメイン名) として記述されます。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-111">The name is described in the DNS Report specifically as an FQDN — a Fully Qualified Domain Name.</span></span> <span data-ttu-id="1c7fe-112">この *contoso.com* 有効なドメイン名ですが *\* 、.contoso.com* の短い形式なので、あいまいで、ドメイン内の任意のサーバーを参照する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-112">While  *contoso.com*  is a valid domain name, it's shorthand for *\*.contoso.com*  , so it's ambiguous and could possibly refer to any server in the domain.</span></span> <span data-ttu-id="1c7fe-113">ドメイン内の 1 つのサーバーを参照する FQDN の例は、次 **meeting01.contoso.com。**</span><span class="sxs-lookup"><span data-stu-id="1c7fe-113">An example of an FQDN that would refer to a single server in your domain might be **meeting01.contoso.com**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1c7fe-114">既定では、ドメインに参加していないコンピューターのコンピューター名はホスト名であり、完全修飾ドメイン名 (FQDN) ではありません。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-114">By default the computer name of a computer that is not joined to a domain is a host name, and not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="1c7fe-115">トポロジ ビルダーでは、ホスト名ではなく FQDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-115">Topology Builder uses FQDNs, not host names.</span></span> <span data-ttu-id="1c7fe-116">そのため、エッジ サーバーとして展開する、ドメインに参加していないコンピューターの名前には、DNS サフィックスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-116">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="1c7fe-117">Skype for Business Server を実行しているサーバーに FQDN を割り当てる場合は、標準文字 **(A** ~ Z、a ~ z、0 ~ 9、およびハイフンを含む) のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-117">**Use only standard characters** (including A-Z, a-z, 0-9, and hyphens) when assigning FQDNs to your servers running Skype for Business Server.</span></span> <span data-ttu-id="1c7fe-118">Unicode 文字およびアンダースコアは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-118">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="1c7fe-119">一般に、外部 DNS および公的 CA では、FQDN に非標準文字はサポートされていません (証明書で FQDN を SN に割り当てることが必要になります)。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-119">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>
  
<span data-ttu-id="1c7fe-120">IP アドレスに加えて、FQDN は **VIP** (仮想 IP アドレス) にマップできます。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-120">In addition to an IP address, the FQDN could map to a **VIP** — A virtual IP address.</span></span> <span data-ttu-id="1c7fe-121">VIP は、実際の物理ネットワーク インターフェイスに対応しない IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-121">A VIP is an IP address that doesn't correspond to an actual physical network interface.</span></span> <span data-ttu-id="1c7fe-122">VIP は、多くの場合、サーバーの役割を実行するサーバーのプール、または冗長性とフォールト トレランス用に構成されたサーバーのペアをポイントします。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-122">A VIP often points to a pool of servers performing a server role, or to a pair of servers configured for redundancy and fault-tolerance.</span></span>
  
<span data-ttu-id="1c7fe-123">DNS レコードにはいくつかの種類があります。この説明に最も関連する DNS レコードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-123">There are several types of DNS record, the ones that are most relevant to this discussion are:</span></span> 
  
- <span data-ttu-id="1c7fe-124">**A** — Address レコードまたは Host レコード。32 ビット IPv4 アドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-124">**A** — an Address record or Host record, Returns a 32-bit IPv4 address.</span></span> <span data-ttu-id="1c7fe-125">ホスト名をホストの IP アドレスにマップするために最も一般的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-125">Most commonly used to map hostnames to an IP address of the host.</span></span>
    
- <span data-ttu-id="1c7fe-126">**AAAA** — IPv6 アドレス レコード。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-126">**AAAA** — an IPv6 address record.</span></span> <span data-ttu-id="1c7fe-127">128 ビット IPv6 アドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-127">Returns a 128-bit IPv6 address.</span></span> <span data-ttu-id="1c7fe-128">ホスト名をホストの IP アドレスにマップするために最も一般的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-128">Most commonly used to map hostnames to an IP address of the host.</span></span>
    
- <span data-ttu-id="1c7fe-129">**CNAME** — 正規名レコード。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-129">**CNAME** — a Canonical name record.</span></span> <span data-ttu-id="1c7fe-130">これにより、1 つの名前が別の名前に解決されます。DNS 参照は新しい名前で検索を再試行します。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-130">This resolves one name to another: the DNS lookup will retry the lookup with the new name.</span></span>
    
- <span data-ttu-id="1c7fe-131">**SRV** — サービス レコード (SRV レコード) は、特定のポートと IP の組み合わせでアクセスされるサービス (サーバー上のプロセス) を指定します。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-131">**SRV** — a Service record (SRV record) specifies a service (a process on a server) that is accessed on a specific port and IP combination.</span></span> <span data-ttu-id="1c7fe-132">サービス レコードを必要とするサービスの名前は固定され、SIP ドメインの一部以外にカスタマイズできません。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-132">The names of services requiring a service record are fixed, and can't be customized beyond making them part of your SIP domain.</span></span> <span data-ttu-id="1c7fe-133">一部のユーザー サービスでは簡易 URL を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-133">Some user services use Simple URLs.</span></span> <span data-ttu-id="1c7fe-134">SRV レコードは同じ SIP ドメイン内の場所を指している必要があります。したがって、複数のドメインがある場合は、特定のサービスに複数の SRV レコードが必要になります。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-134">An SRV record must point to a location in the same SIP domain, so if you have multiple domains you'll need multiple SRV records for a given service.</span></span>
    
## <a name="how-to-choose-a-sip-domain-name"></a><span data-ttu-id="1c7fe-135">SIP ドメイン名を選択する方法</span><span class="sxs-lookup"><span data-stu-id="1c7fe-135">How to choose a SIP domain name</span></span>
<span data-ttu-id="1c7fe-136"><a name="BK_NameSIP"> </a></span><span class="sxs-lookup"><span data-stu-id="1c7fe-136"><a name="BK_NameSIP"> </a></span></span>

<span data-ttu-id="1c7fe-137">組織の SIP ドメイン名は、通常、ユーザーに与えられた電子メール アドレスと一致します。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-137">An organization's SIP domain name usually aligns with the email addresses given to its users.</span></span> <span data-ttu-id="1c7fe-138">組織内のユーザーが Brown@contoso.com のような電子メール アドレスを持つ場合、contoso.com ドメイン名を持つ組織の優先は単に \<sip-domain\> contoso.com。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-138">If a user in your organization would have an email address like Brown@contoso.com, the preferred \<sip-domain\> for an organization with the contoso.com domain name is simply contoso.com.</span></span>
  
### <a name="multiple-sip-domains"></a><span data-ttu-id="1c7fe-139">複数の SIP ドメイン</span><span class="sxs-lookup"><span data-stu-id="1c7fe-139">Multiple SIP domains</span></span>

 <span data-ttu-id="1c7fe-140">組織によっては、複数の SIP ドメインが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-140">Your organization might in some cases need several SIP domains.</span></span> <span data-ttu-id="1c7fe-141">たとえば、Fabrikam.com が contoso.com によって取得された場合、Skype for Business Server が認識し、接続を受け入れる新しい SIP ドメインを作成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-141">As an example, if Fabrikam.com was acquired by contoso.com, you might need to create a new SIP domain that Skype for Business Server recognizes and will accept connection from.</span></span> <span data-ttu-id="1c7fe-142">これを行う場合は、fabrikam の要求を送信する場所を示す新しい FQDN を使用して、contoso.com を使用する DNS レコードの追加セットを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-142">When you do this, you'd need to create an additional set of all the DNS records that use contoso.com, with new FQDNs that show where to send requests for Fabrikam.</span></span>
  
## <a name="dns-load-balancing"></a><span data-ttu-id="1c7fe-143">DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="1c7fe-143">DNS Load Balancing</span></span>
<span data-ttu-id="1c7fe-144"><a name="BK_NameSIP"> </a></span><span class="sxs-lookup"><span data-stu-id="1c7fe-144"><a name="BK_NameSIP"> </a></span></span>

<span data-ttu-id="1c7fe-145">DNS を使用して、サーバー プールとして設定されている複数のサーバー間でトラフィック負荷を共有できます。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-145">You can use DNS to share traffic load among several servers that are set up as a server pool.</span></span> <span data-ttu-id="1c7fe-146">これを行うには、プールの FQDN に対して複数の A レコードを作成し、各レコードがプール内のノードの IP アドレスをポイントします。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-146">To do this, you would create several A records for the pool's FQDN, each of which points to the IP address of a node in the pool.</span></span>
  
<span data-ttu-id="1c7fe-147">負荷分散 [の詳細については、「DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) 負荷分散」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c7fe-147">See [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) for additional discussions of load balancing.</span></span>
  

