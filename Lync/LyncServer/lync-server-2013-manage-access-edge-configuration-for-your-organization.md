---
title: 'Lync Server 2013: 組織のアクセスエッジ構成の管理'
description: 'Lync Server 2013: 組織のアクセスエッジ構成を管理します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Access Edge Configuration for your organization
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2161385f9c03f025bcf6f5e599b7e0276f6d592c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550643"
---
# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a><span data-ttu-id="1270b-103">Lync Server 2013 での組織のアクセスエッジ構成の管理</span><span class="sxs-lookup"><span data-stu-id="1270b-103">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1270b-104">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1270b-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1270b-105">このドキュメントは暫定版であり、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1270b-105">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="1270b-106">空白のトピックがプレースホルダーとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="1270b-106">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="1270b-107">1つ以上のエッジサーバーを展開した後、外部ドメインまたはプロバイダーアクセス、リモートユーザーアクセス、および匿名ユーザーアクセスの種類を有効にして、組織でサポートされるエッジサーバー経由で会議を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="1270b-107">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="1270b-108">こうしたオプションには、[**アクセス エッジ構成**] ページで構成できる次の種類のアクセスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1270b-108">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="1270b-109">**フェデレーションとパブリック IM 接続**     を有効にするフェデレーションパートナードメインへのユーザーアクセスをサポートする場合は、これを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1270b-109">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="1270b-110">この設定は、[ **外部アクセスポリシー** ] ページのグローバル、サイト、またはユーザースコープに対して構成されている SIP フェデレーションと xmpp フェデレーションの両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="1270b-110">This setting applies to both SIP federation and XMPP federation that are configured for global, site or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="1270b-111">フェデレーション設定を適用するには、両方のページでフェデレーションのサポートを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1270b-111">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="1270b-112">フェデレーション パートナーの検出方法に関する省略可能な設定と、(部門でアーカイブが有効になっていること、また通信の詳細情報がアーカイブされることを、通信するフェデレーション連絡先に通知する) アーカイブについての免責事項を連絡先に送信するかどうかという 2 つのオプションが存在します。</span><span class="sxs-lookup"><span data-stu-id="1270b-112">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts</span></span>
    
      - <span data-ttu-id="1270b-113">**パートナードメインの検出**     を有効にするこのオプションを選択すると、フェデレーションを行うことができるドメインの自動検出が有効になります。</span><span class="sxs-lookup"><span data-stu-id="1270b-113">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="1270b-114">Lync Server 2013 は、ドメインネームシステム (DNS) レコードを使用して、許可されたドメインリストに含まれていないドメインの検出を試み、検出されたフェデレーションパートナーからの受信トラフィックを自動的に評価し、信頼レベル、トラフィックの量、および管理設定に基づいてトラフィックを制限またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="1270b-114">Lync Server 2013 uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="1270b-115">このオプションを無効にすると、フェデレーション ユーザーは、許可済みのドメイン一覧に含めたドメインのユーザーにしか、アクセスできません。</span><span class="sxs-lookup"><span data-stu-id="1270b-115">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="1270b-116">このオプションの有効、無効にかかわらず、フェデレーション ドメイン内のアクセス エッジ サービスを実行する特定のサーバーへのアクセスを制限するなど、個々のドメインを禁止するか許可するかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="1270b-116">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="1270b-117">詳細については、「 [Lync Server 2013 で許可されている外部ドメインのサポートを構成する](lync-server-2013-configure-support-for-allowed-external-domains.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1270b-117">For details, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>
    
      - <span data-ttu-id="1270b-118">**フェデレーションパートナー**     へのアーカイブ免責事項の送信このオプションを選択すると、アーカイブ免責事項メッセージをフェデレーションパートナーに送信して、通信の詳細が記録されることを通知できます。</span><span class="sxs-lookup"><span data-stu-id="1270b-118">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="1270b-119">フェデレーションパートナードメインとの外部通信をアーカイブする場合は、アーカイブについての免責事項の通知を有効にして、展開によってメッセージと通信の詳細がアーカイブされていることをパートナーに警告する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1270b-119">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="1270b-120">アーカイブの詳細については、「 [Lync Server 2013 でのアーカイブの要件の定義](lync-server-2013-defining-your-requirements-for-archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1270b-120">For details on archiving, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).</span></span>

  - <span data-ttu-id="1270b-121">**リモートユーザーアクセス**     を有効にするこのオプションを有効にするのは、ユーザーがファイアウォールの外側にいて、在宅中のユーザーが Lync Server に接続できるようにする場合です。</span><span class="sxs-lookup"><span data-stu-id="1270b-121">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server.</span></span> <span data-ttu-id="1270b-122">詳細については、「 [Lync Server 2013 でリモートユーザーアクセスを有効または無効](lync-server-2013-enable-or-disable-remote-user-access.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1270b-122">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="1270b-123">**匿名ユーザーが会議にアクセスできるように**     する内部ユーザーが外部の匿名ユーザーを開催する会議に招待するようにする場合は、このオプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1270b-123">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="1270b-124">この設定を有効にすると、匿名ユーザーのみが会議に対して許可します。</span><span class="sxs-lookup"><span data-stu-id="1270b-124">Enabling this setting only allows anonymous users for conferences.</span></span> <span data-ttu-id="1270b-125">会議の機能と、ユーザーが会議に対して行うことができることと、匿名ユーザーの追加を行うためのオプションを構成するには、「 [サイトまたはユーザーのための会議ユーザーの操作を作成または変更](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) する」および「 [Lync Server 2013 の会議ポリシー設定リファレンス](lync-server-2013-conferencing-policy-settings-reference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1270b-125">To configure the conferencing experience and options that will define how and what your users can do with conferences and for the inclusion of anonymous users, see details at [Create or Modify Conferencing User Experience for a Site or Users](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) and [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1270b-126">外部ユーザー アクセスのサポートを有効にする以外に、いずれかの種類の外部ユーザー アクセスを利用可能にする前に、組織内でのリモート ユーザー アクセスの使用を制御するポリシーの構成も行います。</span><span class="sxs-lookup"><span data-stu-id="1270b-126">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="1270b-127">外部ユーザーアクセスのポリシーの作成、構成、および適用の詳細については、「 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Lync Server 2013 の外部アクセスポリシーの管理</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1270b-127">For details about creating, configuring, and applying policies for external user access, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="1270b-128">**Windows PowerShell コマンドレットを使用してアクセスエッジ構成情報を表示する**</span><span class="sxs-lookup"><span data-stu-id="1270b-128">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="1270b-129">アクセスエッジ構成情報は、Windows PowerShell と **set-csaccessedgeconfiguration** コマンドレットを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="1270b-129">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="1270b-130">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="1270b-130">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1270b-131">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="1270b-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="1270b-132">アクセスエッジのすべての構成設定に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1270b-132">To view information about all your Access Edge configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsAccessEdgeConfiguration
    
    <span data-ttu-id="1270b-133">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1270b-133">That will return information similar to this:</span></span>
    
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

## <a name="in-this-section"></a><span data-ttu-id="1270b-134">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1270b-134">In This Section</span></span>

  - [<span data-ttu-id="1270b-135">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="1270b-135">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [<span data-ttu-id="1270b-136">Lync Server 2013 でのフェデレーションパートナーの検出を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="1270b-136">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [<span data-ttu-id="1270b-137">Lync Server 2013 でのフェデレーションパートナーへのアーカイブ免責事項の送信を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="1270b-137">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="1270b-138">Lync Server 2013 でのリモートユーザーアクセスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="1270b-138">Enable or disable remote user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [<span data-ttu-id="1270b-139">Lync Server 2013 で匿名ユーザーアクセスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="1270b-139">Enable or disable anonymous user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [<span data-ttu-id="1270b-140">Lync Server 2013 で匿名ユーザーをサポートするための会議ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="1270b-140">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

