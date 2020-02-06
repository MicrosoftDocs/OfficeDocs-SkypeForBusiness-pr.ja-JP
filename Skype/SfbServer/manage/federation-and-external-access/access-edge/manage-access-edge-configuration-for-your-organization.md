---
title: 組織のアクセス エッジ構成の管理
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 1つ以上のエッジサーバーを展開した後、組織でサポートされているエッジサーバー経由での会議への外部ドメインまたはプロバイダーアクセス、リモートユーザーアクセス、匿名ユーザーアクセスの種類を有効にする必要があります。
ms.openlocfilehash: 7308d6914f3f6d79cd217a31c0246c6f2d189516
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818348"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a><span data-ttu-id="28a37-103">組織のアクセス エッジ構成の管理</span><span class="sxs-lookup"><span data-stu-id="28a37-103">Manage Access Edge Configuration for your organization</span></span>

<span data-ttu-id="28a37-104">1つ以上のエッジサーバーを展開した後、組織でサポートされているエッジサーバー経由での会議への外部ドメインまたはプロバイダーアクセス、リモートユーザーアクセス、匿名ユーザーアクセスの種類を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="28a37-104">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="28a37-105">これらのオプションには、[**アクセスエッジ構成**] ページから構成できる次の種類のアクセスがあります。</span><span class="sxs-lookup"><span data-stu-id="28a37-105">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="28a37-106">**フェデレーションとパブリック IM 接続**   を有効にするフェデレーションパートナードメインへのユーザーアクセスをサポートする場合は、この機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="28a37-106">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="28a37-107">この設定は、[**外部アクセスポリシー** ] ページのグローバル、サイト、またはユーザーのスコープ用に構成された SIP フェデレーションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="28a37-107">This setting applies to SIP federation configured for global, site, or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="28a37-108">フェデレーション設定を適用するには、両方のページでフェデレーションのサポートを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28a37-108">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="28a37-109">フェデレーションパートナーの検出方法に関するオプションの設定である2つのオプションと、アーカイブの免責事項 (展開によって通信するフェデレーションされた連絡先に通知します。詳細がアーカイブされます) がコンタクトに送信されます。</span><span class="sxs-lookup"><span data-stu-id="28a37-109">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts:</span></span>
    
      - <span data-ttu-id="28a37-110">**[パートナードメインの検出**   を有効にする] このオプションをオンにすると、フェデレーションできるドメインの自動検出が有効になります。</span><span class="sxs-lookup"><span data-stu-id="28a37-110">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="28a37-111">Skype for Business Server では、ドメインネームシステム (DNS) レコードを使って、[許可したドメイン] 一覧にないドメインを検出し、検出されたフェデレーションパートナーから受信トラフィックを自動的に評価し、信頼関係に基づいてそのトラフィックを制限またはブロックします。レベル、トラフィックの量、管理者の設定。</span><span class="sxs-lookup"><span data-stu-id="28a37-111">Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="28a37-112">このオプションが選択されていない場合、フェデレーションされたユーザーのアクセス許可は、[許可したドメイン] リストに含めるドメイン内のユーザーに対してのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="28a37-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="28a37-113">このオプションが選択されているかどうかにかかわらず、フェデレーションドメインでアクセスエッジサービスを実行している特定のサーバーへのアクセスを制限するなど、個々のドメインをブロックまたは許可するように指定することができます。</span><span class="sxs-lookup"><span data-stu-id="28a37-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="28a37-114">詳細については、「[許可された外部ドメインのサポートを構成する](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28a37-114">For details, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>
    
      - <span data-ttu-id="28a37-115">**[アーカイブに関する免責事項をフェデレーションパートナー**   に送信する] このオプションをオンにすると、フェデレーションパートナーにアーカイブの免責事項メッセージを送信し、通信の詳細が記録されることを通知します。</span><span class="sxs-lookup"><span data-stu-id="28a37-115">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="28a37-116">フェデレーションパートナードメインとの外部通信をアーカイブする場合は、アーカイブの免責事項の通知を有効にして、展開によってメッセージと通信の詳細がアーカイブされていることをパートナーに警告する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28a37-116">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="28a37-117">アーカイブの詳細については、「[フェデレーションパートナーへのアーカイブの免責事項の送信を有効または無効](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28a37-117">For details on archiving, see [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

  - <span data-ttu-id="28a37-118">**[リモートユーザーアクセス**   を有効にする] このオプションは、出張中の在宅勤務者やユーザーなど、組織内のユーザーが Skype for business Server に接続できるようにする場合に有効にします。</span><span class="sxs-lookup"><span data-stu-id="28a37-118">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server.</span></span> <span data-ttu-id="28a37-119">詳細について[は、「リモートユーザーアクセスを有効または無効](enable-or-disable-remote-user-access.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28a37-119">For details, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="28a37-120">**[匿名ユーザーが会議**   にアクセスできるようにする] このオプションを有効にすると、内部ユーザーが、自分が開催する会議に外部匿名ユーザーを招待することができます。</span><span class="sxs-lookup"><span data-stu-id="28a37-120">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="28a37-121">この設定を有効にすると、会議の匿名ユーザーのみを許可します。</span><span class="sxs-lookup"><span data-stu-id="28a37-121">Enabling this setting only allows anonymous users for conferences.</span></span>

> [!NOTE]  
> <span data-ttu-id="28a37-122">外部ユーザーアクセスのサポートを有効にするだけでなく、組織でのリモートユーザーアクセスの使用を制御するポリシーも構成して、ユーザーが外部ユーザーアクセスの種類を利用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="28a37-122">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="28a37-123">外部ユーザーアクセスのポリシーの作成、構成、適用の詳細については、「[組織の外部アクセスポリシーを管理](../external-access-policies/manage-external-access-policy-for-your-organization.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28a37-123">For details about creating, configuring, and applying policies for external user access, see [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span></span>

<span data-ttu-id="28a37-124">**Windows PowerShell コマンドレットを使用してアクセスエッジ構成情報を表示する**</span><span class="sxs-lookup"><span data-stu-id="28a37-124">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="28a37-125">Access Edge の構成情報は、Windows PowerShell と**CsAccessEdgeConfiguration**コマンドレットを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="28a37-125">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="28a37-126">このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="28a37-126">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="28a37-127">すべてのアクセスエッジの構成設定に関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力して、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="28a37-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
     `Get-CsAccessEdgeConfiguration`
    
    <span data-ttu-id="28a37-128">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="28a37-128">That will return information similar to this:</span></span>
    
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

