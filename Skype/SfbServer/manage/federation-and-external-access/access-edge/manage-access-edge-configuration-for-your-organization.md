---
title: 組織のアクセス エッジ構成の管理
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 1 つまたは複数のエッジ サーバーを展開するには後に、、外部ドメインまたはプロバイダーのアクセス、リモート ユーザー アクセス、および会議を組織でサポートされるエッジ トランスポート サーバーに匿名ユーザー アクセスの種類を有効にする必要があります。
ms.openlocfilehash: 8428815a0f3d89124d1b5e681b79924171916f6d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199921"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a><span data-ttu-id="8ce6a-103">組織のアクセス エッジ構成の管理</span><span class="sxs-lookup"><span data-stu-id="8ce6a-103">Manage Access Edge Configuration for your organization</span></span>

<span data-ttu-id="8ce6a-104">1 つまたは複数のエッジ サーバーを展開するには後に、、外部ドメインまたはプロバイダーのアクセス、リモート ユーザー アクセス、および会議を組織でサポートされるエッジ トランスポート サーバーに匿名ユーザー アクセスの種類を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ce6a-104">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="8ce6a-105">これらのオプションには、次の種類の**アクセス エッジの構成**] ページで構成可能なアクセスがあります。</span><span class="sxs-lookup"><span data-stu-id="8ce6a-105">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="8ce6a-106">**フェデレーションとパブリック IM 接続を有効にする**   、フェデレーション パートナーのドメインへのユーザー アクセスをサポートする場合にこれを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8ce6a-106">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="8ce6a-107">この設定は、SIP に適用されます、グローバル、サイトのフェデレーションを構成またはユーザー スコープの**外部アクセス ポリシー**のページです。</span><span class="sxs-lookup"><span data-stu-id="8ce6a-107">This setting applies to SIP federation configured for global, site, or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="8ce6a-108">フェデレーションの設定を適用する、両方のページでフェデレーション サポートを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ce6a-108">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="8ce6a-109">2 つのオプションで存在するのオプションの設定方法、フェデレーション パートナーを検出すると、免責事項をアーカイブするかどうか (フェデレーションの連絡先に通知すると通信できることを展開には有効なアーカイブとの通信詳細はアーカイブされる) の連絡先に送信されます。</span><span class="sxs-lookup"><span data-stu-id="8ce6a-109">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts:</span></span>
    
      - <span data-ttu-id="8ce6a-110">**パートナー ドメインの検出を有効にする**   とフェデレーションを行うことができるドメインの自動検出を有効にこのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="8ce6a-110">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="8ce6a-111">Skype ビジネス サーバーのドメイン ネーム システム (DNS) レコードを使用して自動的に検出されたフェデレーション パートナーからの着信トラフィックを評価することを制限することや信頼関係に基づいてトラフィックをブロック、許可されるドメインの一覧に表示されていないドメインを探索しようレベル、トラフィック、および管理者設定の量です。</span><span class="sxs-lookup"><span data-stu-id="8ce6a-111">Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="8ce6a-112">このオプションをオフにすると、フェデレーション ユーザーのアクセスは許可するドメイン] ボックスの一覧に含まれているドメインのユーザーに対してのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="8ce6a-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="8ce6a-113">このオプションを選択するかどうかは、その個人を指定することをブロックまたは許可されているドメイン フェデレーション ドメインのアクセス エッジ サービスを実行して特定のサーバーにアクセスを制限することです。</span><span class="sxs-lookup"><span data-stu-id="8ce6a-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="8ce6a-114">詳細については、[許可された外部ドメインのサポートを構成する](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ce6a-114">For details, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>
    
      - <span data-ttu-id="8ce6a-115">**フェデレーション パートナーへのアーカイブ免責事項を送信**   このオプションを選択するには、通信の詳細が記録されていることが示されますが、フェデレーション パートナーにアーカイブについての免責事項メッセージの送信が有効にします。</span><span class="sxs-lookup"><span data-stu-id="8ce6a-115">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="8ce6a-116">フェデレーション パートナーのドメインとの外部通信をアーカイブする場合は、アーカイブについての免責事項パートナーに通知、展開でのメッセージとの通信の詳細をバックアップしていますが有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ce6a-116">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="8ce6a-117">アーカイブの詳細については、[有効にするかフェデレーション パートナーに、アーカイブの免責事項の送信を無効にする](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ce6a-117">For details on archiving, see [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

  - <span data-ttu-id="8ce6a-118">**リモート ユーザー アクセスを有効にする**   在宅勤務者、出張中には、Skype のビジネス サーバーに接続できるユーザーなど、ファイアウォールの外側には、組織内のユーザーの場合、このオプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8ce6a-118">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server.</span></span> <span data-ttu-id="8ce6a-119">詳細については、[有効にするかリモート ユーザー アクセスを無効にする](enable-or-disable-remote-user-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ce6a-119">For details, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="8ce6a-120">**会議にアクセスする匿名ユーザーを有効にする**   内部のユーザーが開催する会議に外部の匿名ユーザーを招待する場合にこのオプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8ce6a-120">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="8ce6a-121">この設定を有効にするだけでは、匿名ユーザー会議。</span><span class="sxs-lookup"><span data-stu-id="8ce6a-121">Enabling this setting only allows anonymous users for conferences.</span></span>

> [!NOTE]  
> <span data-ttu-id="8ce6a-122">外部ユーザー アクセスを有効にするだけでなくサポート、また任意の種類の外部ユーザー アクセスのユーザーが利用できる前に、組織内のリモート ユーザー アクセスの使用を制御するポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="8ce6a-122">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="8ce6a-123">作成、構成、および外部ユーザー アクセスのポリシーの適用に関する詳細については、[組織の外部アクセス ポリシーの管理](../external-access-policies/manage-external-access-policy-for-your-organization.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ce6a-123">For details about creating, configuring, and applying policies for external user access, see [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span></span>

<span data-ttu-id="8ce6a-124">**Windows PowerShell コマンドレットを使用して、アクセス エッジの構成情報を表示します。**</span><span class="sxs-lookup"><span data-stu-id="8ce6a-124">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="8ce6a-125">Windows PowerShell と**Get CsAccessEdgeConfiguration**コマンドレットを使用して、アクセス エッジの構成情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="8ce6a-125">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="8ce6a-126">ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8ce6a-126">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="8ce6a-127">すべてのアクセス エッジ構成設定に関する情報を表示するのには、Skype のビジネス サーバー管理シェルの次のコマンドを入力し、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8ce6a-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
     `Get-CsAccessEdgeConfiguration`
    
    <span data-ttu-id="8ce6a-128">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ce6a-128">That will return information similar to this:</span></span>
    
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

