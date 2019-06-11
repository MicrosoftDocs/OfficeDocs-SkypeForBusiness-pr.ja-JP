---
title: 'Lync Server 2013: フェデレーションおよびパブリック IM 接続の有効化または無効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4123a17c01ad6358038b1937b57bab29eeec85c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a><span data-ttu-id="08194-102">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="08194-102">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08194-103">_**最終更新日:** 2013-06-24_</span><span class="sxs-lookup"><span data-stu-id="08194-103">_**Topic Last Modified:** 2013-06-24_</span></span>

<span data-ttu-id="08194-104">フェデレーションのサポートは、信頼された顧客またはパートナー組織のアカウントを持っているユーザー (パートナーのドメインや、サポートしているパブリックインスタントメッセージング (IM) プロバイダーのユーザーを含む) を有効にして、ユーザーとの共同作業を行うことができるようにする必要があります。組織.</span><span class="sxs-lookup"><span data-stu-id="08194-104">Support for federation is required to enable users who have an account with a trusted customer or partner organization, including partner domains and users of public instant messaging (IM) provider users that you support, to collaborate with users in your organization.</span></span> <span data-ttu-id="08194-105">また、ホストされている exchange サービスプロバイダーを使用して、メールボックスが Microsoft Exchange Online などのホスティングされた Exchange サービス上にあるエンタープライズボイスユーザーに、ボイスメールを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08194-105">Federation is also required to use a hosted Exchange service provider to provide voice mail to Enterprise Voice users whose mailboxes are located on a hosted Exchange service such as Microsoft Exchange Online.</span></span> <span data-ttu-id="08194-106">これらの外部ドメインとの信頼関係を確立したら、これらのドメインのユーザーに対して、展開にアクセスして Lync Server の通信に参加することを許可することができます。</span><span class="sxs-lookup"><span data-stu-id="08194-106">When you have established a trust relationship with these external domains, you can authorize users in those domains to access your deployment and participate in Lync Server communications.</span></span> <span data-ttu-id="08194-107">この信頼関係はフェデレーションと呼ばれており、Active Directory の信頼関係に関連していない、または依存していません。</span><span class="sxs-lookup"><span data-stu-id="08194-107">This trust relationship is called a federation and it is not related to, or dependent upon, an Active Directory trust relationship.</span></span>

<span data-ttu-id="08194-108">フェデレーションドメインのユーザーによるアクセスをサポートするには、フェデレーションを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="08194-108">To support access by users of federated domains, you must enable federation.</span></span> <span data-ttu-id="08194-109">組織のフェデレーションを有効にする場合は、次のオプションを実装するかどうかも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08194-109">If you enable federation for your organization, you must also specify whether to implement the following options:</span></span>

  - <span data-ttu-id="08194-110">**パートナードメインの検出**   を有効にするこのオプションを有効にすると、Lync Server はドメインネームシステム (DNS) レコードを使用して、[許可したドメイン] 一覧にないドメインの検出を試みます。検出されたフェデレーションから受信トラフィックが自動的に評価されます。信頼レベル、トラフィック量、管理者設定に基づいて、そのトラフィックを制限またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="08194-110">**Enable partner domain discovery**   If you enable this option, Lync Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="08194-111">このオプションが選択されていない場合、フェデレーションされたユーザーのアクセス許可は、[許可したドメイン] リストに含めるドメイン内のユーザーに対してのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="08194-111">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="08194-112">このオプションが選択されているかどうかにかかわらず、フェデレーションドメインでアクセスエッジサービスを実行している特定のサーバーへのアクセスを制限するなど、個々のドメインをブロックまたは許可するように指定することができます。</span><span class="sxs-lookup"><span data-stu-id="08194-112">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="08194-113">フェデレーションドメインによるアクセスの制御の詳細については、「 [Lync Server 2013 で許可されている外部ドメインのサポートを構成する](lync-server-2013-configure-support-for-allowed-external-domains.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08194-113">For details about controlling access by federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>

  - <span data-ttu-id="08194-114">**フェデレーションパートナー**    にアーカイブの免責事項を送信する免責事項は、展開にアーカイブすることが適切に行われるフェデレーションパートナーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="08194-114">**Send an archiving disclaimer to federated partners**    Disclaimer notice is sent to federated partners that archiving in your deployment is in place.</span></span> <span data-ttu-id="08194-115">フェデレーションパートナードメインとの外部通信のアーカイブをサポートしている場合は、アーカイブの免責事項の通知を有効にして、メッセージがアーカイブされていることをパートナーに警告する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08194-115">If you support archiving of external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages are being archived.</span></span>

<span data-ttu-id="08194-116">後でフェデレーションドメインのユーザーによるアクセスを一時的または完全に禁止する場合は、組織のフェデレーションを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="08194-116">If you later want to temporarily or permanently prevent access by users of federated domains, you can disable federation for your organization.</span></span> <span data-ttu-id="08194-117">このセクションの手順を使用して、組織のフェデレーションされたユーザーアクセスを有効または無効にします。組織でサポートする必要のあるフェデレーションオプションを指定するなどの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="08194-117">Use the procedure in this section to enable or disable federated user access for your organization, including specifying the appropriate federation options to be supported for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="08194-118">組織でフェデレーションを有効にすると、アクセスエッジサービスを実行しているサーバーでフェデレーションドメインへのルーティングがサポートされるようになります。</span><span class="sxs-lookup"><span data-stu-id="08194-118">Enabling federation for your organization only specifies that your servers running the Access Edge service support routing to federated domains.</span></span> <span data-ttu-id="08194-119">フェデレーションドメイン内のユーザーは、フェデレーションされたユーザーアクセスをサポートするために少なくとも1つのポリシーを構成するまで、組織内の IM または会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="08194-119">Users in federated domains cannot participate in IM or conferences in your organization until you also configure at least one policy to support federated user access.</span></span> <span data-ttu-id="08194-120">パブリック IM サービスプロバイダーのユーザーは、パブリック IM 接続をサポートするように少なくとも1つのポリシーを構成するまで、組織内の IM または会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="08194-120">Users of public IM service providers cannot participate in IM or conferences in your organization until you also configure at least one policy to support public IM connectivity.</span></span> <span data-ttu-id="08194-121">ホストされている exchange サービスを使用して、ホストされているボイスメールポリシーを構成するまで、ホストされている Exchange サービスにメールボックスがあるユーザーのために、通話応答、Outlook Voice Access (ボイスメールを含む)、自動応答サービスを提供することはできません。ルーティング情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="08194-121">Lync Server cannot use a hosted Exchange service to provide call answering, Outlook Voice Access (including voice mail), or auto-attendant services for users whose mailboxes are located on a hosted Exchange service until you configure a hosted voice mail policy that provides routing information.</span></span> <span data-ttu-id="08194-122">他の組織のフェデレーションドメインのユーザーと通信するためのポリシーを構成する方法について詳しくは、「運用ドキュメントの「 <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Lync Server 2013 で組織の SIP フェデレーションドメインを管理</A>する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="08194-122">For details about configuring policies for communication with users of federated domains in other organizations, see <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP federated domains for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="08194-123">さらに、IM サービスプロバイダーのユーザーとの通信をサポートする必要がある場合は、それをサポートするようにポリシーを構成し、サポートする個々のサービスプロバイダーのサポートも構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08194-123">Additionally, if you want to support communication with users of IM service providers, you must configure policies to support it and also configure support for the individual service providers that you want to support.</span></span> <span data-ttu-id="08194-124">詳細については、操作のドキュメントの「 <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Lync Server 2013 で組織の SIP フェデレーションプロバイダーを管理</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08194-124">For details, see <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Manage SIP federated providers for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="08194-125">ホスト型ボイスメールのポリシーを作成する方法の詳細については、展開ドキュメントの「 <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Lync Server 2013 でホストされているボイスメールポリシーを管理</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08194-125">For details about creating a hosted voice mail policy, see <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a><span data-ttu-id="08194-126">組織のフェデレーションされたユーザーアクセスを有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="08194-126">To enable or disable federated user access for your organization</span></span>

1.  <span data-ttu-id="08194-127">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="08194-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="08194-128">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="08194-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="08194-129">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="08194-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="08194-130">左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**アクセスエッジ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08194-130">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="08194-131">[**アクセスエッジの構成**] ページで [**グローバル**] をクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08194-131">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="08194-132">[ **Access Edge 構成の編集**] で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="08194-132">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="08194-133">組織のフェデレーションされたユーザーアクセスを有効にするには、[**フェデレーションユーザーとの通信を有効**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="08194-133">To enable federated user access for your organization, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="08194-134">組織のフェデレーションされたユーザーアクセスを無効にするには、[フェデレーションされ**たユーザーとの通信を有効**にする] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="08194-134">To disable federated user access for your organization, clear the **Enable communications with federated users** check box.</span></span>

6.  <span data-ttu-id="08194-135">[**フェデレーションユーザーとの通信を有効に**する] チェックボックスをオンにした場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="08194-135">If you selected the **Enable communications with federated users** check box, do the following:</span></span>
    
    1.  <span data-ttu-id="08194-136">パートナードメインの自動検出をサポートするには、[**パートナードメイン探索を有効に**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="08194-136">If you want to support automatic discovery of partner domains, select the **Enable partner domain discovery** check box.</span></span>
    
    2.  <span data-ttu-id="08194-137">組織で外部通信のアーカイブがサポートされている場合は、[**フェデレーションパートナーにアーカイブの免責事項を送信する**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="08194-137">If your organization supports archiving of external communications, select the **Send archiving disclaimer to federated partners** check box.</span></span>

7.  <span data-ttu-id="08194-138">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08194-138">Click **Commit**.</span></span>

<span data-ttu-id="08194-139">フェデレーションされたユーザーが Lync Server 2013 の展開でユーザーと共同作業できるようにするには、フェデレーションされたユーザーアクセスをサポートするために、少なくとも1つの外部アクセスポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08194-139">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must also configure at least one external access policy to support federated user access.</span></span> <span data-ttu-id="08194-140">詳細については、「展開ドキュメントまたは運用ドキュメントの「 [Lync Server 2013 でフェデレーションされたユーザーアクセスを制御するためのポリシーを構成する](lync-server-2013-configure-policies-to-control-federated-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08194-140">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="08194-141">特定のフェデレーションドメインへのアクセスを制御するには、展開ドキュメントまたは操作のドキュメントの「 [Lync Server 2013 で許可されている外部ドメインのサポートを構成](lync-server-2013-configure-support-for-allowed-external-domains.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08194-141">To control access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="08194-142">Windows PowerShell コマンドレットを使用してフェデレーションおよびパブリック IM 接続を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="08194-142">Enabling or Disabling Federation and Public IM Connectivity by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="08194-143">フェデレーションとパブリック IM 接続は、Windows PowerShell と CsAccessEdgeConfiguration コマンドレットを使用して管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="08194-143">Federation and public IM connectivity can also be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="08194-144">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="08194-144">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="08194-145">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08194-145">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a><span data-ttu-id="08194-146">フェデレーションとパブリック IM 接続を有効にするには</span><span class="sxs-lookup"><span data-stu-id="08194-146">To enable federation and public IM connectivity</span></span>

  - <span data-ttu-id="08194-147">フェデレーションとパブリック IM 接続を有効にするには、 **AllowFederatedUsers**プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="08194-147">To enable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a><span data-ttu-id="08194-148">フェデレーションとパブリック IM 接続を無効にするには</span><span class="sxs-lookup"><span data-stu-id="08194-148">To disable federation and public IM connectivity</span></span>

  - <span data-ttu-id="08194-149">フェデレーションとパブリック IM 接続を無効にするには、 **AllowFederatedUsers**プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="08194-149">To disable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

