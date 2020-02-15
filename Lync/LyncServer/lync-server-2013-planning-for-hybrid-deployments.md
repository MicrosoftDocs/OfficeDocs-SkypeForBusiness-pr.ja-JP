---
title: 'Lync Server 2013: ハイブリッド展開の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for hybrid deployments
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48185910
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b0efc4a6a9e9f195705801969b8459c17855388
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a><span data-ttu-id="9424b-102">Lync Server 2013 ハイブリッド展開の計画</span><span class="sxs-lookup"><span data-stu-id="9424b-102">Planning for Lync Server 2013 hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9424b-103">_**トピックの最終更新日:** 2016-05-25_</span><span class="sxs-lookup"><span data-stu-id="9424b-103">_**Topic Last Modified:** 2016-05-25_</span></span>

<span data-ttu-id="9424b-104">ハイブリッド展開の計画では、ユーザーとネットワークインフラストラクチャの次の要件を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-104">You should consider the following requirements for users and your network infrastructure while planning for a hybrid deployment.</span></span>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="9424b-105">インフラストラクチャの要件</span><span class="sxs-lookup"><span data-stu-id="9424b-105">Infrastructure Requirements</span></span>

<span data-ttu-id="9424b-106">ハイブリッド展開を実装して展開するには、環境内に次のものが構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-106">You must have the following configured in your environment in order to implement and deploy a hybrid deployment.</span></span>

  - <span data-ttu-id="9424b-107">Skype for Business Online が有効になっている Microsoft Office 365 テナント。</span><span class="sxs-lookup"><span data-stu-id="9424b-107">A Microsoft Office 365 tenant with Skype for Business Online enabled.</span></span> <span data-ttu-id="9424b-108">オンプレミス展開でハイブリッド構成に使用できるのは1つのテナントのみであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9424b-108">Note that you can use only a single tenant for a hybrid configuration with your on-premises deployment.</span></span>

  - <span data-ttu-id="9424b-109">サポートされているトポロジに展開されている Skype for Business Server または Lync Server の単一のオンプレミス展開 (インフラストラクチャ)。</span><span class="sxs-lookup"><span data-stu-id="9424b-109">A single on-premises deployment (infrastructure) of Skype for Business Server or Lync Server that is deployed in a supported topology.</span></span> <span data-ttu-id="9424b-110">「トポロジ要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9424b-110">See Topology Requirements.</span></span>
    
    <span data-ttu-id="9424b-111">ハイブリッド用の Lync Server 2013 または Lync Server 2010 の展開の構成の詳細については、「 [Lync server 2013 ハイブリッド展開の構成](lync-server-2013-configuring-hybrid-deployments.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9424b-111">For information about configuring your Lync Server 2013 or Lync Server 2010 deployment for hybrid, see [Configuring Lync Server 2013 hybrid deployments](lync-server-2013-configuring-hybrid-deployments.md).</span></span>

  - <span data-ttu-id="9424b-112">Skype for Business Server 2015 管理ツール。</span><span class="sxs-lookup"><span data-stu-id="9424b-112">Skype for Business Server 2015 administrative tools.</span></span> <span data-ttu-id="9424b-113">Lync server 2013 または Lync Server 2010 を使用している場合は、Lync Server 2013 管理ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9424b-113">If you are using Lync Server 2013 or Lync Server 2010, you can use the Lync Server 2013 administrative tools.</span></span>

  - <span data-ttu-id="9424b-114">Office 365 でシングルサインオンをサポートし、ユーザーがオンプレミスの場合と同じログイン資格情報を使用して Office にサインインできるようにするには、Azure Active Directory (AAD) Connect のパスワード同期機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9424b-114">To support Single Sign-on with Office 365 so that users can use the same login credentials for signing in to Office as they do on-premises, you can use the password sync features of Azure Active Directory (AAD) Connect.</span></span> <span data-ttu-id="9424b-115">Active Directory フェデレーションサービス (AD FS) を使用して、Office 365 でシングルサインオンを行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="9424b-115">You can also use Active Directory Federation Services (AD FS) for single sign-on with Office 365.</span></span>
    
    <span data-ttu-id="9424b-116">詳しくは「[オンプレミスの ID を Azure Active Directory と統合する](http://go.microsoft.com/fwlink/p/?linkid=619754)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9424b-116">For more information, see [Integrating your on-premises identities with Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754).</span></span>

  - <span data-ttu-id="9424b-117">1つのディレクトリ同期ソリューションを使用して、オンプレミスとオンラインの Active Directory オブジェクトを同期させます。</span><span class="sxs-lookup"><span data-stu-id="9424b-117">A single directory synchronization solution to keep your on-premises and online Active Directory objects synchronized.</span></span> <span data-ttu-id="9424b-118">ディレクトリ同期の詳細については、「[ディレクトリ統合ツール](http://go.microsoft.com/fwlink/p/?linkid=530320)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9424b-118">For details about Directory Synchronization, see [Directory Integration Tools](http://go.microsoft.com/fwlink/p/?linkid=530320).</span></span>

</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="9424b-119">Lync クライアントのサポート</span><span class="sxs-lookup"><span data-stu-id="9424b-119">Lync Client Support</span></span>

<span data-ttu-id="9424b-120">Lync クライアントでサポートされている機能と、オンプレミスおよびオンライン環境で使用できる機能にはいくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="9424b-120">There are some differences in the features supported in Lync clients, as well as the features available in on-premises and online environments.</span></span> <span data-ttu-id="9424b-121">組織内のユーザーをホームにする場所を決定する前に、Lync Server のさまざまな構成のクライアントサポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="9424b-121">Before you decide where you want to home users in your organization, you can view the client support for the various configurations of Lync Server.</span></span> <span data-ttu-id="9424b-122">Lync ハイブリッド展開では、以下のクライアントが Skype for Business Online でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9424b-122">The following clients are supported with Skype for Business Online in a Lync hybrid deployment:</span></span>

  - <span data-ttu-id="9424b-123">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="9424b-123">Lync 2010</span></span>

  - <span data-ttu-id="9424b-124">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="9424b-124">Lync 2013</span></span>

  - <span data-ttu-id="9424b-125">Lync Windows ストアアプリ</span><span class="sxs-lookup"><span data-stu-id="9424b-125">Lync Windows Store app</span></span>

  - <span data-ttu-id="9424b-126">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="9424b-126">Lync Web App</span></span>

  - <span data-ttu-id="9424b-127">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="9424b-127">Lync Mobile</span></span>

  - <span data-ttu-id="9424b-128">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="9424b-128">Lync for Mac 2011</span></span>

  - <span data-ttu-id="9424b-129">Lync Room System</span><span class="sxs-lookup"><span data-stu-id="9424b-129">Lync Room System</span></span>

  - <span data-ttu-id="9424b-130">Lync Basic 2013</span><span class="sxs-lookup"><span data-stu-id="9424b-130">Lync Basic 2013</span></span>

<span data-ttu-id="9424b-131">クライアントサポートの詳細については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9424b-131">For details about client support, see the following topics:</span></span>

  - [<span data-ttu-id="9424b-132">Lync Online のクライアント</span><span class="sxs-lookup"><span data-stu-id="9424b-132">Clients for Lync Online</span></span>](http://go.microsoft.com/fwlink/?linkid=281902)

  - [<span data-ttu-id="9424b-133">Lync Server 2013 のクライアントの比較表</span><span class="sxs-lookup"><span data-stu-id="9424b-133">Client comparison tables for Lync Server 2013</span></span>](lync-server-2013-desktop-client-comparison-tables.md)

  - [<span data-ttu-id="9424b-134">Lync Server 2013 のモバイルクライアントの比較表</span><span class="sxs-lookup"><span data-stu-id="9424b-134">Mobile client comparison tables for Lync Server 2013</span></span>](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="9424b-135">トポロジ要件</span><span class="sxs-lookup"><span data-stu-id="9424b-135">Topology Requirements</span></span>

<span data-ttu-id="9424b-136">Skype for Business Online でハイブリッド展開を構成するには、次のサポートされているトポロジのいずれかを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-136">To configure your deployment for hybrid with Skype for Business Online, you need to have one of the following supported topologies:</span></span>

  - <span data-ttu-id="9424b-137">Skype for business Server 2015 を Skype for business Server 2015 を実行しているすべてのサーバーと共に展開します。</span><span class="sxs-lookup"><span data-stu-id="9424b-137">A Skype for Business Server 2015 deployment with all servers running Skype for Business Server 2015.</span></span>

  - <span data-ttu-id="9424b-138">Lync server 2013 を実行して2013いるすべてのサーバーでの Lync Server の展開。</span><span class="sxs-lookup"><span data-stu-id="9424b-138">A Lync Server 2013 deployment with all servers running Lync Server 2013.</span></span>

  - <span data-ttu-id="9424b-139">Lync server 2010 の展開は、最新の累積的な更新プログラムを適用して Lync Server 2010 を実行しているすべてのサーバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9424b-139">A Lync Server 2010 deployment with all servers running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="9424b-140">フェデレーションエッジサーバーおよびフェデレーションエッジサーバーの次ホップサーバーは、最新の累積更新プログラムを使用して Lync Server 2010 を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-140">The federation Edge Server and next hop server from the federation Edge Server must be running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="9424b-141">Skype for Business Server 2015 または Lync Server 2013 の管理ツールは、少なくとも1つのサーバーまたは管理ワークステーションにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-141">The Skype for Business Server 2015 or Lync Server 2013 Administrative Tools must be installed on at least one server or management workstation.</span></span>

  - <span data-ttu-id="9424b-142">Skype for Business Server 2015 を実行している少なくとも1つのサイトに、次のサーバーの役割を持つ Lync Server 2013 と Skype for Business 2015 Server の混在した展開。</span><span class="sxs-lookup"><span data-stu-id="9424b-142">A mixed Lync Server 2013 and Skype for Business Server 2015 deployment with the following server roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="9424b-143">少なくとも1つのエンタープライズプールまたは Standard Edition サーバー</span><span class="sxs-lookup"><span data-stu-id="9424b-143">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="9424b-144">SIP フェデレーションに関連付けられたディレクタープール (存在する場合)</span><span class="sxs-lookup"><span data-stu-id="9424b-144">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="9424b-145">SIP フェデレーションに関連付けられているエッジプール</span><span class="sxs-lookup"><span data-stu-id="9424b-145">The Edge Pool associated with SIP federation</span></span>

  - <span data-ttu-id="9424b-146">Skype for Business Server 2015 を実行している少なくとも1つのサイトに、次のサーバーの役割を持つ Lync Server 2010 と Skype for Business 2015 Server の混在した展開。</span><span class="sxs-lookup"><span data-stu-id="9424b-146">A mixed Lync Server 2010 and Skype for Business Server 2015 deployment with the following servers roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="9424b-147">少なくとも1つのエンタープライズプールまたは Standard Edition サーバー</span><span class="sxs-lookup"><span data-stu-id="9424b-147">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="9424b-148">SIP フェデレーションに関連付けられたディレクタープール (存在する場合)</span><span class="sxs-lookup"><span data-stu-id="9424b-148">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="9424b-149">サイトの SIP フェデレーションに関連付けられているエッジプール</span><span class="sxs-lookup"><span data-stu-id="9424b-149">The Edge Pool associated with SIP federation for the Site</span></span>

  - <span data-ttu-id="9424b-150">少なくとも1つのサイトで lync Server 2013 を実行しているサーバーの役割が混在する Lync Server 2010 および Lync Server 2013 の混在:</span><span class="sxs-lookup"><span data-stu-id="9424b-150">A mixed Lync Server 2010 and Lync Server 2013 deployment with the following server roles in at least one site running Lync Server 2013:</span></span>
    
      - <span data-ttu-id="9424b-151">サイト内の少なくとも1つのエンタープライズプールまたは Standard Edition サーバー</span><span class="sxs-lookup"><span data-stu-id="9424b-151">At least one Enterprise Pool or Standard Edition server in the site</span></span>
    
      - <span data-ttu-id="9424b-152">SIP フェデレーションに関連付けられたディレクタープール (サイトに存在する場合)</span><span class="sxs-lookup"><span data-stu-id="9424b-152">The Director Pool associated with SIP federation, if it exists in the site</span></span>
    
      - <span data-ttu-id="9424b-153">サイトの SIP フェデレーションに関連付けられているエッジプール</span><span class="sxs-lookup"><span data-stu-id="9424b-153">The Edge Pool associated with SIP federation for the site</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9424b-154">オンプレミスと UNRESOLVED_TOKEN_VAL (skypeforbusiness) 間のユーザー移動を含む、すべてのユーザー管理は、管理ツールの最新バージョンを使用して実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-154">All user management, including user moves between on-premises and UNRESOLVED_TOKEN_VAL(skypeforbusiness) Online, needs to be done using the latest installed version of the administrative tools.</span></span> <span data-ttu-id="9424b-155">管理ツールは、既存のオンプレミス展開およびインターネットへの接続アクセス権を持つ別のサーバーにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-155">The administrative tools must be installed on a separate server that has connect access to the existing on-premises deployment and to the Internet.</span></span> <span data-ttu-id="9424b-156">オンプレミス展開から UNRESOLVED_TOKEN_VAL (skype16_online) にユーザーを移動するための<A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">移動ユーザー</A>コマンドレットは、オンプレミス展開に接続された管理ツールから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-156">The <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> cmdlet to move users from your on-premises deployment to UNRESOLVED_TOKEN_VAL(skype16_online) must be run from the administrative tools connected to your on-premises deployment.</span></span>



</div>

<span data-ttu-id="9424b-157">サポートされるトポロジの詳細については、「 [Lync server 2013 のサポートされるトポロジ](lync-server-2013-supported-topologies.md)」および「[エンタープライズハイブリッド展開用の Lync Server 2013 Reference トポロジ](http://go.microsoft.com/fwlink/p/?linkid=398709)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9424b-157">For more information about supported topologies, see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md), and [Lync Server 2013 Reference Topologies for Enterprise Hybrid Deployments](http://go.microsoft.com/fwlink/p/?linkid=398709).</span></span>

<span data-ttu-id="9424b-158">ハイブリッド展開のトラブルシューティングと、PowerShell を Lync Online に接続する方法については、「 [Lync online: Lync PowerShell」および「ハイブリッドトラブルシューティング](http://go.microsoft.com/fwlink/p/?linkid=306718)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9424b-158">For troubleshooting information about hybrid deployments and connecting PowerShell to Lync Online, see [Lync Online: Lync PowerShell and Hybrid Troubleshooting](http://go.microsoft.com/fwlink/p/?linkid=306718).</span></span>

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a><span data-ttu-id="9424b-159">フェデレーション許可/ブロックリストの要件</span><span class="sxs-lookup"><span data-stu-id="9424b-159">Requirements for Federation Allowed/Blocked Lists</span></span>

<span data-ttu-id="9424b-160">許可されるドメインの一覧には、パートナーエッジの完全修飾ドメイン名 (FQDN) が構成されているドメインが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9424b-160">The Allowed domains list includes domains that have a partner Edge fully qualified domain name (FQDN) configured.</span></span> <span data-ttu-id="9424b-161">これらは、*許可されたパートナーサーバー*または*直接フェデレーションパートナー*と呼ばれることがあります。</span><span class="sxs-lookup"><span data-stu-id="9424b-161">These are sometimes referred to as *allowed partner servers* or *direct federation partners*.</span></span> <span data-ttu-id="9424b-162">オンプレミス展開では、*パートナー検出*と*許可されたパートナードメインリスト*と呼ばれる、オープンフェデレーションと閉じられたフェデレーションの違いについて理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-162">You should be familiar with the difference between Open Federation and Closed Federation, referred to as *partner discovery* and *allowed partner domain list*, respectively, in on-premises deployments.</span></span>

<span data-ttu-id="9424b-163">ハイブリッド展開を正しく構成するには、次の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-163">The following requirements must be met to successfully configure a hybrid deployment:</span></span>

  - <span data-ttu-id="9424b-164">オンプレミス展開と Office 365 テナントでは、ドメインの一致が同じように構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-164">Domain matching must be configured the same for your on-premises deployment and your Office 365 tenant.</span></span> <span data-ttu-id="9424b-165">オンプレミス展開でパートナー検出が有効になっている場合は、オンラインテナントに対してオープンフェデレーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-165">If partner discovery is enabled on the on-premises deployment, then open federation must be configured for your online tenant.</span></span> <span data-ttu-id="9424b-166">パートナー検出が有効になっていない場合は、オンラインテナント用に閉じられたフェデレーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-166">If partner discovery is not enabled, then closed federation must be configured for your online tenant.</span></span>

  - <span data-ttu-id="9424b-167">オンプレミス展開の禁止ドメインリストは、オンラインテナントの禁止ドメインリストと正確に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-167">The Blocked domains list in the on-premises deployment must exactly match the Blocked domains list for your online tenant.</span></span>

  - <span data-ttu-id="9424b-168">オンプレミス展開の許可ドメインリストは、オンラインテナントの許可されたドメインリストと正確に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-168">The Allowed domains list in the on-premises deployment must exactly match the Allowed domains list for your online tenant.</span></span>

  - <span data-ttu-id="9424b-169">オンラインテナントの外部通信に対してフェデレーションを有効にする必要があります。これは、Lync Online コントロールパネルを使用して構成されます。</span><span class="sxs-lookup"><span data-stu-id="9424b-169">Federation must be enabled for the external communications for the online tenant, which is configured by using the Lync Online Control Panel.</span></span>

</div>

<div>

## <a name="dns-settings"></a><span data-ttu-id="9424b-170">DNS 設定</span><span class="sxs-lookup"><span data-stu-id="9424b-170">DNS Settings</span></span>

<span data-ttu-id="9424b-171">ハイブリッド展開用の DNS レコードを作成する場合は、すべての Lync 外部 DNS レコードがオンプレミスのインフラストラクチャをポイントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-171">When creating DNS records for hybrid deployments, all Lync external DNS records should point to the on-premises infrastructure.</span></span> <span data-ttu-id="9424b-172">必要な DNS レコードの詳細については、「 [Lync Server 2013 のドメインネームシステム (DNS) の要件](lync-server-2013-domain-name-system-dns-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9424b-172">For details on required DNS records, please refer to [Domain Name System (DNS) requirements for Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span></span>

<span data-ttu-id="9424b-173">さらに、次の表に記載されている DNS 解決がオンプレミスの展開でも動作することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-173">Additionally you need to ensure that the DNS resolution described in the following table works in your on-premises deployment:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9424b-174">DNS レコード</span><span class="sxs-lookup"><span data-stu-id="9424b-174">DNS record</span></span></p></td>
<td><p><span data-ttu-id="9424b-175">解決方法</span><span class="sxs-lookup"><span data-stu-id="9424b-175">Resolvable by</span></span></p></td>
<td><p><span data-ttu-id="9424b-176">DNS 要件</span><span class="sxs-lookup"><span data-stu-id="9424b-176">DNS requirement</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9424b-177">_Sipfederationtls _tcp の DNS SRV レコード。&lt;エッジ&gt;の外部 IP へのアクセスを解決するための、サポートされているすべての SIP ドメインの sipdomain.com</span><span class="sxs-lookup"><span data-stu-id="9424b-177">DNS SRV record for _sipfederationtls._tcp.&lt;sipdomain.com&gt; for all supported SIP domains resolving to Access Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="9424b-178">エッジサーバー</span><span class="sxs-lookup"><span data-stu-id="9424b-178">Edge server(s)</span></span></p></td>
<td><p><span data-ttu-id="9424b-179">ハイブリッド構成でフェデレーション通信を有効にします。</span><span class="sxs-lookup"><span data-stu-id="9424b-179">Enable federated communication in a hybrid configuration.</span></span> <span data-ttu-id="9424b-180">エッジサーバーは、オンプレミスとオンラインの間で分割されている SIP ドメインのフェデレーショントラフィックをルーティングする場所を知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-180">The Edge Server needs to know where to route federated traffic for the SIP domain that is split between on premises and online.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9424b-181">エッジ Web 会議サービス FQDN 用の DNS A レコード (webcon.contoso.com、Web 会議エッジ外部 IP への解決など)</span><span class="sxs-lookup"><span data-stu-id="9424b-181">DNS A record(s) for Edge Web Conferencing Service FQDN, e.g. webcon.contoso.com resolving to Web Conferencing Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="9424b-182">内部の企業ネットワークに接続されたユーザーのコンピューター</span><span class="sxs-lookup"><span data-stu-id="9424b-182">Internal corporate network connected users’ computers</span></span></p></td>
<td><p><span data-ttu-id="9424b-183">オンラインユーザーがオンプレミスでホストされている会議のコンテンツを表示または表示できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9424b-183">Enable online users to present or view content in on-premises hosted meetings.</span></span> <span data-ttu-id="9424b-184">コンテンツには、PowerPoint ファイル、ホワイトボード、投票、および共有メモが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9424b-184">Content includes PowerPoint files, whiteboards, polls, and shared notes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9424b-185">組織での DNS の構成方法によっては、これらのレコードを対応する SIP ドメインの内部ホスト DNS ゾーンに追加して、これらのレコードに対する内部 DNS 解決を提供する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-185">Depending on how DNS is configured in your organization, you may need to add these records to the internal hosted DNS zone for the corresponding SIP domain(s) to provide internal DNS resolution to these records.</span></span>

</div>

<div>

## <a name="firewall-considerations"></a><span data-ttu-id="9424b-186">ファイアウォールの考慮</span><span class="sxs-lookup"><span data-stu-id="9424b-186">Firewall Considerations</span></span>

<span data-ttu-id="9424b-p113">ネットワーク上のコンピューターは、標準のインターネット DNS 参照を実行できる必要があります。これらのコンピューターが標準のインターネット サイトに接続できれば、ネットワークはこの要件を満たしています。</span><span class="sxs-lookup"><span data-stu-id="9424b-p113">Computers on your network must be able to perform standard Internet DNS lookups. If these computers can reach standard Internet sites, your network meets this requirement.</span></span>

<span data-ttu-id="9424b-189">Microsoft Online Services データセンターの場所によっては、ネットワークファイアウォールデバイスが、ワイルドカードドメイン名 (たとえば、outlook.com から\*のすべてのトラフィック) に基づいて接続を受け入れるように構成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="9424b-189">Depending on the location of your Microsoft Online Services data center, you must also configure your network firewall devices to accept connections based on wildcard domain names (for example, all traffic from \*.outlook.com).</span></span> <span data-ttu-id="9424b-190">組織のファイアウォールがワイルドカードを使用した名前の構成方法をサポートしない場合は、許可する IP アドレスの範囲や特定のポートを手動で決める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-190">If your organization’s firewalls do not support wildcard name configurations, you will have to manually determine the IP address ranges that you would like to allow and the specified ports.</span></span>

<span data-ttu-id="9424b-191">ヘルプトピック「 [Office 365 の url と IP アドレスの範囲](http://go.microsoft.com/fwlink/p/?linkid=252942)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9424b-191">Refer to the Help topic [Office 365 URLs and IP address ranges](http://go.microsoft.com/fwlink/p/?linkid=252942).</span></span>

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a><span data-ttu-id="9424b-192">ポートとプロトコルの要件</span><span class="sxs-lookup"><span data-stu-id="9424b-192">Port and Protocol Requirements</span></span>

<span data-ttu-id="9424b-193">内部 Lync Server 2013 の通信のポート要件に加えて、次のポートも構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-193">In addition to the port requirements for internal Lync Server 2013 communication, you must also configure the following ports.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9424b-194">プロトコル/ポート</span><span class="sxs-lookup"><span data-stu-id="9424b-194">Protocol / Port</span></span></th>
<th><span data-ttu-id="9424b-195">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="9424b-195">Applications</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9424b-196">TCP 443</span><span class="sxs-lookup"><span data-stu-id="9424b-196">TCP 443</span></span></p></td>
<td><p><span data-ttu-id="9424b-197">受信を開く</span><span class="sxs-lookup"><span data-stu-id="9424b-197">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="9424b-198">Active Directory フェデレーション サービス (フェデレーション サーバーの役割)</span><span class="sxs-lookup"><span data-stu-id="9424b-198">Active Directory Federation Services (federation server role)</span></span></p>
<p><span data-ttu-id="9424b-199">詳細については、「 <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">AD FS の役割サービスについ</a>て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9424b-199">For more information, see <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS Role Services</a>.</span></span></p></li>
<li><p><span data-ttu-id="9424b-200">Active Directory フェデレーション サービス (プロキシ サーバーの役割)</span><span class="sxs-lookup"><span data-stu-id="9424b-200">Active Directory Federation Services (proxy server role)</span></span></p></li>
<li><p><span data-ttu-id="9424b-201">Microsoft Online Services ポータル</span><span class="sxs-lookup"><span data-stu-id="9424b-201">Microsoft Online Services Portal</span></span></p></li>
<li><p><span data-ttu-id="9424b-202">ポータル サイト</span><span class="sxs-lookup"><span data-stu-id="9424b-202">My Company Portal</span></span></p></li>
<li><p><span data-ttu-id="9424b-203">Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="9424b-203">Outlook Web App</span></span></p></li>
<li><p><span data-ttu-id="9424b-204">Lync クライアント (オンプレミスの Lync Server から Lync Online への通信)</span><span class="sxs-lookup"><span data-stu-id="9424b-204">Lync client (communication to Lync Online from on-premises Lync Server)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9424b-205">TCP 80 および 443</span><span class="sxs-lookup"><span data-stu-id="9424b-205">TCP 80 and 443</span></span></p></td>
<td><p><span data-ttu-id="9424b-206">受信を開く</span><span class="sxs-lookup"><span data-stu-id="9424b-206">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="9424b-207">Microsoft Online Services ディレクトリ同期ツール</span><span class="sxs-lookup"><span data-stu-id="9424b-207">Microsoft Online Services Directory Synchronization Tool</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9424b-208">TCP 5061</span><span class="sxs-lookup"><span data-stu-id="9424b-208">TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="9424b-209">エッジサーバーで受信/送信を開く</span><span class="sxs-lookup"><span data-stu-id="9424b-209">Open inbound/outbound on the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9424b-210">PSOM/TLS 443</span><span class="sxs-lookup"><span data-stu-id="9424b-210">PSOM/TLS 443</span></span></p></td>
<td><p><span data-ttu-id="9424b-211">データ共有セッションの受信/送信を開く</span><span class="sxs-lookup"><span data-stu-id="9424b-211">Open inbound/outbound for data sharing sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9424b-212">STUN/TCP 443</span><span class="sxs-lookup"><span data-stu-id="9424b-212">STUN/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="9424b-213">音声、ビデオ、アプリケーション共有セッションで受信/送信を開く</span><span class="sxs-lookup"><span data-stu-id="9424b-213">Open inbound/outbound for audio, video, application sharing sessions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9424b-214">STUN/UDP 3478</span><span class="sxs-lookup"><span data-stu-id="9424b-214">STUN/UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="9424b-215">音声およびビデオセッションの受信/送信を開く</span><span class="sxs-lookup"><span data-stu-id="9424b-215">Open inbound/outbound for audio and video sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9424b-216">RTP/TCP 50000-59999</span><span class="sxs-lookup"><span data-stu-id="9424b-216">RTP/TCP 50000-59999</span></span></p></td>
<td><p><span data-ttu-id="9424b-217">オーディオおよびビデオセッションの送信を開く</span><span class="sxs-lookup"><span data-stu-id="9424b-217">Open outbound for audio and video sessions</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a><span data-ttu-id="9424b-218">ユーザー アカウントおよびデータ</span><span class="sxs-lookup"><span data-stu-id="9424b-218">User Accounts and Data</span></span>

<span data-ttu-id="9424b-219">Lync Server 2013 ハイブリッド展開では、Lync Online のホームにするすべてのユーザーが、Active Directory ドメインサービスでユーザーアカウントが作成されるように、最初に社内展開で作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-219">In a Lync Server 2013 hybrid deployment, any user that you want to home in Lync Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="9424b-220">その後、ユーザーを Skype for Business Online に移動して、ユーザーの連絡先リストを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="9424b-220">You can then move the user to Skype for Business Online, which will move the user’s contact list.</span></span>

<span data-ttu-id="9424b-221">Lync オンプレミスと Lync Online の展開との間で AD FS および Dirsync を使用してユーザーアカウントを同期する場合は、ユーザーがオンプレミスとオンラインの Lync 展開の間で組織内のすべての Lync ユーザーの AD アカウントを同期する必要があります。Lync Online には移動されません。</span><span class="sxs-lookup"><span data-stu-id="9424b-221">When you synchronize user accounts between your Lync on-premises and Lync Online deployments with AD FS and Dirsync, you need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="9424b-222">すべてのユーザーを同期しない場合は、組織内のオンプレミスのユーザーとオンラインユーザーとの間の通信が期待どおりに機能しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="9424b-222">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9424b-223">ユーザーがオンラインポータルの Office 365 を使用して作成されている場合、ユーザーアカウントは社内 Active Directory と同期されず、ユーザーはオンプレミスの Active Directory に存在しません。</span><span class="sxs-lookup"><span data-stu-id="9424b-223">If the user is created by using the online portal for Office 365, the user account will not be synchronized with on-premises Active Directory, and the user will not exist in the on-premises Active Directory.</span></span> <span data-ttu-id="9424b-224">既に Lync Online でユーザーを作成していて、オンプレミスの Lync Server でハイブリッドを構成する場合は、「lync <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">online から Lync online 2013 へのユーザーの移行</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9424b-224">If you have already created users in Lync Online, and want to configure hybrid with an on-premises Lync Server, see <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="9424b-225">ハイブリッド展開を計画する場合は、次のユーザー関連の問題も考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-225">You should also consider the following user-related issues when planning for a hybrid deployment.</span></span>

  - <span data-ttu-id="9424b-226">**ユーザーの連絡先**   Lync Online ユーザーの連絡先の制限は250です。</span><span class="sxs-lookup"><span data-stu-id="9424b-226">**User contacts**   The limit for contacts for Lync Online users is 250.</span></span> <span data-ttu-id="9424b-227">その番号を超える連絡先は、アカウントが Lync Online に移動されたときにユーザーの連絡先リストから削除されます。</span><span class="sxs-lookup"><span data-stu-id="9424b-227">Any contacts beyond that number will be removed from the user’s contact list when the account is moved to Lync Online.</span></span>

  - <span data-ttu-id="9424b-228">**インスタントメッセージングとプレゼンス**   ユーザーの連絡先リスト、グループ、アクセス制御リスト (acl) は、ユーザーアカウントと共に移行されます。</span><span class="sxs-lookup"><span data-stu-id="9424b-228">**Instant Messaging and Presence**   User contact lists, groups, and access control lists (ACLs) are migrated with the user account.</span></span>

  - <span data-ttu-id="9424b-229">**会議データ、会議コンテンツ、および予約済み会議**   このコンテンツは、ユーザーアカウントと共に移行されません。</span><span class="sxs-lookup"><span data-stu-id="9424b-229">**Conferencing data, meeting content, and scheduled meetings**   This content is not migrated with the user account.</span></span> <span data-ttu-id="9424b-230">ユーザーは、アカウントが Lync Online に移行された後で会議を予約し直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-230">Users must reschedule meetings after their accounts are migrated to Lync Online.</span></span>

</div>

<div>

## <a name="user-policies-and-features"></a><span data-ttu-id="9424b-231">ユーザー ポリシと機能</span><span class="sxs-lookup"><span data-stu-id="9424b-231">User Policies and Features</span></span>

  - <span data-ttu-id="9424b-232">Lync Server 2013 ハイブリッド環境では、ユーザーは、オンプレミスまたはオンラインのいずれかで、インスタントメッセージング、音声、および会議を有効にすることができますが、両方を同時に有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9424b-232">In a Lync Server 2013 hybrid environment, users can be enabled for Instant Messaging, voice, and meetings either on-premises or online, but not both simultaneously.</span></span>

  - <span data-ttu-id="9424b-233">**Lync クライアント**   ユーザーによっては、lync Online に移行する際に新しいクライアントバージョンが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-233">**Lync Client**    Some users may require a new client version when they are moved to Lync Online.</span></span> <span data-ttu-id="9424b-234">Office Communications Server 2007 R2 の場合、Lync Online に移行する前に、ユーザーを Lync Server 2013 プールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9424b-234">For Office Communications Server 2007 R2, users must be moved to a Lync Server 2013 pool prior to migration to Lync Online.</span></span>
    
    <span data-ttu-id="9424b-235">クライアントサポートの詳細については、「 [Lync Online のクライアント](http://go.microsoft.com/fwlink/p/?linkid=281902)」および「[サポートされている lync クライアントとネットワークポートの構成](http://go.microsoft.com/fwlink/p/?linkid=281901)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9424b-235">For more information about client support, see [Clients for Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) and [Supported Lync clients and network port configurations](http://go.microsoft.com/fwlink/p/?linkid=281901).</span></span>

  - <span data-ttu-id="9424b-236">**オンプレミスのポリシーと構成 (非ユーザー)**   のオンラインおよびオンプレミスのポリシーには、個別の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="9424b-236">**On-premises policies and configuration (non-user)**   Online and on-premises policies require separate configuration.</span></span> <span data-ttu-id="9424b-237">両方に適用されるグローバル ポリシーを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="9424b-237">You cannot set global policies that apply to both.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

