---
title: 組織のアクセス エッジ構成の管理
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 1 つ以上のエッジ サーバーを展開した後、組織でサポートされるエッジ サーバーを介した会議への外部ドメインまたはプロバイダー アクセス、リモート ユーザー アクセス、および匿名ユーザー アクセスの種類を有効にする必要があります。
ms.openlocfilehash: 63d33a5dd3459aef5f657d8ab5772515a16e7915
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817337"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a><span data-ttu-id="ac08c-103">組織のアクセス エッジ構成の管理</span><span class="sxs-lookup"><span data-stu-id="ac08c-103">Manage Access Edge Configuration for your organization</span></span>

<span data-ttu-id="ac08c-104">1 つ以上のエッジ サーバーを展開した後、組織でサポートされるエッジ サーバーを介した会議への外部ドメインまたはプロバイダー アクセス、リモート ユーザー アクセス、および匿名ユーザー アクセスの種類を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac08c-104">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="ac08c-105">こうしたオプションには、[**アクセス エッジ構成**] ページで構成できる次の種類のアクセスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ac08c-105">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="ac08c-106">**フェデレーションとパブリック IM 接続を有効にする**   フェデレーション パートナー ドメインへのユーザー アクセスをサポートする場合は、これを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="ac08c-106">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="ac08c-107">この設定は、[外部アクセス ポリシー] ページでグローバル スコープ、サイト スコープ、またはユーザー スコープ用に構成された SIP フェデレーション **に適用** されます。</span><span class="sxs-lookup"><span data-stu-id="ac08c-107">This setting applies to SIP federation configured for global, site, or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="ac08c-108">フェデレーション設定を適用するには、両方のページでフェデレーション サポートを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac08c-108">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="ac08c-109">フェデレーション パートナーの検出方法に関するオプションの設定と、アーカイブについての免責事項 (展開でアーカイブが有効で通信の詳細がアーカイブされるフェデレーション連絡先への通知) を連絡先に送信するかどうかの 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="ac08c-109">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts:</span></span>
    
      - <span data-ttu-id="ac08c-110">**パートナー ドメインの検出を有効にする**   このオプションを選択すると、フェデレーションを行えるドメインの自動検出が有効になります。</span><span class="sxs-lookup"><span data-stu-id="ac08c-110">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="ac08c-111">Skype for Business Server は、ドメイン ネーム システム (DNS) レコードを使用して、許可されたドメインの一覧に記載されていないドメインの検出を試み、検出されたフェデレーション パートナーからの受信トラフィックを自動的に評価し、信頼レベル、トラフィック量、および管理者設定に基づいてトラフィックを制限またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="ac08c-111">Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="ac08c-112">このオプションを無効にすると、フェデレーション ユーザーは、許可済みのドメイン一覧に含めたドメインのユーザーにしか、アクセスできません。</span><span class="sxs-lookup"><span data-stu-id="ac08c-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="ac08c-113">このオプションの有効、無効にかかわらず、フェデレーション ドメイン内のアクセス エッジ サービスを実行する特定のサーバーへのアクセスを制限するなど、個々のドメインを禁止するか許可するかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ac08c-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="ac08c-114">詳細については、「許可された [外部ドメインのサポートを構成する」を参照してください](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="ac08c-114">For details, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>
    
      - <span data-ttu-id="ac08c-115">**フェデレーション パートナーにアーカイブ免責事項を送信する**   このオプションを選択すると、通信の詳細が記録されるという通知を受け取ったフェデレーション パートナーにアーカイブについての免責事項メッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="ac08c-115">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="ac08c-116">フェデレーション パートナー ドメインとの外部通信をアーカイブする場合は、アーカイブについての免責事項通知を有効にして、展開によってメッセージと通信の詳細がアーカイブされているという警告をパートナーに表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac08c-116">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="ac08c-117">アーカイブの詳細については、「フェデレーション パートナーへのアーカイブについての免責事項の送信を [有効または無効にする」を参照してください](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)。</span><span class="sxs-lookup"><span data-stu-id="ac08c-117">For details on archiving, see [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

  - <span data-ttu-id="ac08c-118">**リモート ユーザー アクセスを有効にする**   在宅勤務者や出張中のユーザーなど、ファイアウォールの外側に位置する組織内のユーザーが Skype for Business Server に接続する場合は、このオプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ac08c-118">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server.</span></span> <span data-ttu-id="ac08c-119">詳細については、「リモート ユーザー [アクセスを有効または無効にする」を参照してください](enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="ac08c-119">For details, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="ac08c-120">**匿名ユーザーが会議にアクセスできる**   内部ユーザーが組織する会議に外部の匿名ユーザーを招待する場合は、このオプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ac08c-120">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="ac08c-121">この設定を有効にすると、匿名ユーザーは会議にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ac08c-121">Enabling this setting only allows anonymous users for conferences.</span></span>

> [!NOTE]  
> <span data-ttu-id="ac08c-122">外部ユーザー アクセスのサポートを有効にする以外に、いずれかの種類の外部ユーザー アクセスを利用可能にする前に、組織内でのリモート ユーザー アクセスの使用を制御するポリシーの構成も行います。</span><span class="sxs-lookup"><span data-stu-id="ac08c-122">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="ac08c-123">外部ユーザー アクセスのポリシーの作成、構成、適用の詳細については、「組織の外部アクセス ポリシーの管理」 [を参照してください](../external-access-policies/manage-external-access-policy-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="ac08c-123">For details about creating, configuring, and applying policies for external user access, see [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span></span>

<span data-ttu-id="ac08c-124">**次のコマンドレットを使用してアクセス エッジWindows PowerShell表示する**</span><span class="sxs-lookup"><span data-stu-id="ac08c-124">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="ac08c-125">アクセス エッジ構成情報は、このコマンドレットと **Get-CsAccessEdgeConfiguration** Windows PowerShell使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="ac08c-125">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="ac08c-126">このコマンドレットは、Skype for Business Server 管理シェルまたは Skype for Business Server のリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ac08c-126">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="ac08c-127">すべてのアクセス エッジ構成設定に関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ac08c-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
     `Get-CsAccessEdgeConfiguration`
    
    <span data-ttu-id="ac08c-128">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac08c-128">That will return information similar to this:</span></span>
    
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

