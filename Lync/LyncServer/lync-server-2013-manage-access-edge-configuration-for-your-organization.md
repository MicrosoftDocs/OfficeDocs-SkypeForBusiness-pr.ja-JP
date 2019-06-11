---
title: 'Lync Server 2013: 組織のアクセス エッジ構成の管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage Access Edge Configuration for your organization
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05d2bcca7836bd451b2535fb02c350facd7fc1bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a><span data-ttu-id="a8aab-102">Lync Server 2013 での組織のアクセス エッジ構成の管理</span><span class="sxs-lookup"><span data-stu-id="a8aab-102">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8aab-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a8aab-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a8aab-104">このドキュメントは暫定版であり、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a8aab-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="a8aab-105">空白のトピックがプレースホルダーとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="a8aab-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="a8aab-106">1つ以上のエッジサーバーを展開した後、組織でサポートされているエッジサーバー経由での会議への外部ドメインまたはプロバイダーアクセス、リモートユーザーアクセス、匿名ユーザーアクセスの種類を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8aab-106">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="a8aab-107">これらのオプションには、[**アクセスエッジ構成**] ページから構成できる次の種類のアクセスがあります。</span><span class="sxs-lookup"><span data-stu-id="a8aab-107">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="a8aab-108">**フェデレーションとパブリック IM 接続**   を有効にするフェデレーションパートナードメインへのユーザーアクセスをサポートする場合は、この機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="a8aab-108">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="a8aab-109">この設定は、[**外部アクセスポリシー** ] ページのグローバル、サイト、またはユーザーのスコープに対して構成される SIP フェデレーションと xmpp フェデレーションの両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a8aab-109">This setting applies to both SIP federation and XMPP federation that are configured for global, site or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="a8aab-110">フェデレーション設定を適用するには、両方のページでフェデレーションのサポートを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8aab-110">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="a8aab-111">フェデレーションパートナーの検出方法に関するオプションの設定である2つのオプションと、アーカイブの免責事項 (展開によって通信するフェデレーションされた連絡先に通知します。詳細がアーカイブされます) がコンタクトに送信されます。</span><span class="sxs-lookup"><span data-stu-id="a8aab-111">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts</span></span>
    
      - <span data-ttu-id="a8aab-112">**[パートナードメインの検出**   を有効にする] このオプションをオンにすると、フェデレーションできるドメインの自動検出が有効になります。</span><span class="sxs-lookup"><span data-stu-id="a8aab-112">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="a8aab-113">Lync Server 2013 は、ドメインネームシステム (DNS) レコードを使って、[許可したドメイン] 一覧にないドメインを検出し、検出されたフェデレーションパートナーからの着信トラフィックを自動的に評価し、信頼レベルに基づいてそのトラフィックを制限またはブロックします。トラフィックの量と管理者の設定。</span><span class="sxs-lookup"><span data-stu-id="a8aab-113">Lync Server 2013 uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="a8aab-114">このオプションが選択されていない場合、フェデレーションされたユーザーのアクセス許可は、[許可したドメイン] リストに含めるドメイン内のユーザーに対してのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="a8aab-114">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="a8aab-115">このオプションが選択されているかどうかにかかわらず、フェデレーションドメインでアクセスエッジサービスを実行している特定のサーバーへのアクセスを制限するなど、個々のドメインをブロックまたは許可するように指定することができます。</span><span class="sxs-lookup"><span data-stu-id="a8aab-115">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="a8aab-116">詳細については、「 [Lync Server 2013 で許可されている外部ドメインのサポートを構成する](lync-server-2013-configure-support-for-allowed-external-domains.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8aab-116">For details, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>
    
      - <span data-ttu-id="a8aab-117">**[アーカイブに関する免責事項をフェデレーションパートナー**   に送信する] このオプションをオンにすると、フェデレーションパートナーにアーカイブの免責事項メッセージを送信し、通信の詳細が記録されることを通知します。</span><span class="sxs-lookup"><span data-stu-id="a8aab-117">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="a8aab-118">フェデレーションパートナードメインとの外部通信をアーカイブする場合は、アーカイブの免責事項の通知を有効にして、展開によってメッセージと通信の詳細がアーカイブされていることをパートナーに警告する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8aab-118">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="a8aab-119">アーカイブの詳細については、「 [Lync Server 2013 でアーカイブするための要件を定義](lync-server-2013-defining-your-requirements-for-archiving.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8aab-119">For details on archiving, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).</span></span>

  - <span data-ttu-id="a8aab-120">**[リモートユーザーアクセス**   を有効にする] このオプションは、出張中の在宅勤務者やユーザーなど、組織内のユーザーが Lync Server に接続できるようにする場合に有効にします。</span><span class="sxs-lookup"><span data-stu-id="a8aab-120">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server.</span></span> <span data-ttu-id="a8aab-121">詳細については、「 [Lync Server 2013 でリモートユーザーアクセスを有効または無効](lync-server-2013-enable-or-disable-remote-user-access.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8aab-121">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="a8aab-122">**[匿名ユーザーが会議**   にアクセスできるようにする] このオプションを有効にすると、内部ユーザーが、自分が開催する会議に外部匿名ユーザーを招待することができます。</span><span class="sxs-lookup"><span data-stu-id="a8aab-122">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="a8aab-123">この設定を有効にすると、会議の匿名ユーザーのみを許可します。</span><span class="sxs-lookup"><span data-stu-id="a8aab-123">Enabling this setting only allows anonymous users for conferences.</span></span> <span data-ttu-id="a8aab-124">会議のエクスペリエンスと、ユーザーが会議で何を行うことができるかを定義するオプションと、匿名ユーザーを含めるためのオプションについては、「[サイトまたはユーザーの会議ユーザーエクスペリエンスを作成または変更](https://technet.microsoft.com/en-us/library/gg429715\(v=ocs.15\))する」を参照し[てください。Lync Server 2013 の会議ポリシー設定のリファレンス](lync-server-2013-conferencing-policy-settings-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="a8aab-124">To configure the conferencing experience and options that will define how and what your users can do with conferences and for the inclusion of anonymous users, see details at [Create or Modify Conferencing User Experience for a Site or Users](https://technet.microsoft.com/en-us/library/gg429715\(v=ocs.15\)) and [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a8aab-125">外部ユーザーアクセスのサポートを有効にするだけでなく、組織でのリモートユーザーアクセスの使用を制御するポリシーも構成して、ユーザーが外部ユーザーアクセスの種類を利用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8aab-125">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="a8aab-126">外部ユーザーアクセスのポリシーの作成、構成、適用の詳細については、「 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Lync Server 2013 で外部アクセスポリシーを管理</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8aab-126">For details about creating, configuring, and applying policies for external user access, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="a8aab-127">**Windows PowerShell コマンドレットを使用してアクセスエッジ構成情報を表示する**</span><span class="sxs-lookup"><span data-stu-id="a8aab-127">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="a8aab-128">Access Edge の構成情報は、Windows PowerShell と**CsAccessEdgeConfiguration**コマンドレットを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="a8aab-128">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="a8aab-129">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="a8aab-129">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a8aab-130">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8aab-130">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="a8aab-131">すべてのアクセスエッジの構成設定に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a8aab-131">To view information about all your Access Edge configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsAccessEdgeConfiguration
    
    <span data-ttu-id="a8aab-132">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8aab-132">That will return information similar to this:</span></span>
    
        Identity                               : Global
        AllowAnonymousUsers                    : False
        AllowFederatedUsers                    : False
        AllowOutsideUsers                      : True
        BeClearingHouse                        : False
        EnablePartnerDiscovery                 : False
        EnableArchivingDisclaimer              : False
        EnableUserReplicator                   : True
        KeepCrlsUpToDateForPeers               : True
        MarkSourceVerifiableOnOutgoingMessages : True
        OutgoingTlsCountForFederatedPartners   : 4
        DiscoveredPartnerStandardRate          : 20
        EnableDiscoveredPartnerContactsLimit   : True
        MaxContactsPerDiscoveredPartner        : 1000
        DiscoveredPartnerReportPeriodMinutes   : 60
        MaxAcceptedCertificatesStored          : 1000
        MaxRejectedCertificatesStored          : 500
        CertificatesDeletedPercentage          : 20
        RoutingMethod                          : UseDnsSrvRouting

<div>

## <a name="in-this-section"></a><span data-ttu-id="a8aab-133">このセクション中</span><span class="sxs-lookup"><span data-stu-id="a8aab-133">In This Section</span></span>

  - [<span data-ttu-id="a8aab-134">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="a8aab-134">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [<span data-ttu-id="a8aab-135">Lync Server 2013 でのフェデレーション パートナーの検出の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="a8aab-135">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [<span data-ttu-id="a8aab-136">Lync Server 2013 でのフェデレーション パートナーに対するアーカイブ免責事項の送信の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="a8aab-136">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="a8aab-137">Lync Server 2013 でのリモート ユーザー アクセスの有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="a8aab-137">Enable or disable remote user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [<span data-ttu-id="a8aab-138">Lync Server 2013 匿名ユーザー アクセスの有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="a8aab-138">Enable or disable anonymous user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [<span data-ttu-id="a8aab-139">Lync Server 2013 での匿名ユーザー サポートのための会議ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="a8aab-139">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

