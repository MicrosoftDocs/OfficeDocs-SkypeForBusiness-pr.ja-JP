---
title: 'Lync Server 2013: フェデレーションとパブリック IM 接続の有効化または無効化'
description: 'Lync Server 2013: フェデレーションとパブリック IM 接続を有効または無効にします。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48c77e4bf892fa891f413226a4adf068e980c352
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552473"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a><span data-ttu-id="3a9fa-103">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="3a9fa-103">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a9fa-104">_**トピックの最終更新日:** 2013-06-24_</span><span class="sxs-lookup"><span data-stu-id="3a9fa-104">_**Topic Last Modified:** 2013-06-24_</span></span>

<span data-ttu-id="3a9fa-105">組織内のユーザーと共同作業を行うために、パートナードメインや、サポートしているパブリックインスタントメッセージング (IM) プロバイダユーザーのユーザーを含む、信頼できる顧客またはパートナー組織のアカウントを持つユーザーを有効にするには、フェデレーションのサポートが必要です。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-105">Support for federation is required to enable users who have an account with a trusted customer or partner organization, including partner domains and users of public instant messaging (IM) provider users that you support, to collaborate with users in your organization.</span></span> <span data-ttu-id="3a9fa-106">また、ホストされている exchange サービスプロバイダーを使用して、Microsoft Exchange Online などのホストされた Exchange サービスにメールボックスがある場合には、フェデレーションを使用して、エンタープライズ Voip ユーザーにボイスメールを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-106">Federation is also required to use a hosted Exchange service provider to provide voice mail to Enterprise Voice users whose mailboxes are located on a hosted Exchange service such as Microsoft Exchange Online.</span></span> <span data-ttu-id="3a9fa-107">これらの外部ドメインとの信頼関係を確立したら、それらのドメイン内のユーザーによる展開へのアクセスと Lync Server の通信への参加を承認することができます。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-107">When you have established a trust relationship with these external domains, you can authorize users in those domains to access your deployment and participate in Lync Server communications.</span></span> <span data-ttu-id="3a9fa-108">この信頼関係は、フェデレーションと呼ばれ、Active Directory の信頼関係に関連していないか、またはそれに依存していません。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-108">This trust relationship is called a federation and it is not related to, or dependent upon, an Active Directory trust relationship.</span></span>

<span data-ttu-id="3a9fa-p102">フェデレーション ドメインのユーザーによるアクセスをサポートするには、フェデレーションを有効にする必要があります。 組織に対してフェデレーションを有効にする場合、次のオプションを実装するかどうかも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-p102">To support access by users of federated domains, you must enable federation. If you enable federation for your organization, you must also specify whether to implement the following options:</span></span>

  - <span data-ttu-id="3a9fa-111">**パートナードメインの検出**     を有効にするこのオプションを有効にした場合、Lync Server はドメインネームシステム (DNS) レコードを使用して、許可されたドメインリストに含まれていないドメインの検出を試み、検出されたフェデレーションパートナーからの受信トラフィックを自動的に評価し、信頼レベル、トラフィックの量、および管理設定に基づいてトラフィックを制限またはブロックします</span><span class="sxs-lookup"><span data-stu-id="3a9fa-111">**Enable partner domain discovery**   If you enable this option, Lync Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="3a9fa-112">このオプションを無効にすると、フェデレーション ユーザーは、許可済みのドメイン一覧に含めたドメインのユーザーにしか、アクセスできません。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="3a9fa-113">このオプションの有効、無効にかかわらず、フェデレーション ドメイン内のアクセス エッジ サービスを実行する特定のサーバーへのアクセスを制限するなど、個々のドメインを禁止するか許可するかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="3a9fa-114">フェデレーションドメインによるアクセス制御の詳細については、「 [Configure support for allowed external domains In Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-114">For details about controlling access by federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>

  - <span data-ttu-id="3a9fa-115">**フェデレーションパートナー**     へのアーカイブ免責事項の送信免責事項については、展開でのアーカイブが実施されていることがフェデレーションパートナーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-115">**Send an archiving disclaimer to federated partners**    Disclaimer notice is sent to federated partners that archiving in your deployment is in place.</span></span> <span data-ttu-id="3a9fa-116">フェデレーションパートナードメインとの外部通信のアーカイブをサポートする場合は、アーカイブについての免責事項の通知を有効にして、メッセージがアーカイブされることをパートナーに警告する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-116">If you support archiving of external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages are being archived.</span></span>

<span data-ttu-id="3a9fa-p105">後でフェデレーション ドメイン ユーザーからのアクセスを一時的または永久に禁止する場合は、組織に対するフェデレーションを無効にできます。組織でサポートする適切なフェデレーション オプションを指定するなど、組織に対するフェデレーション ユーザーのアクセスを有効または無効にするには、このセクションの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-p105">If you later want to temporarily or permanently prevent access by users of federated domains, you can disable federation for your organization. Use the procedure in this section to enable or disable federated user access for your organization, including specifying the appropriate federation options to be supported for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3a9fa-119">組織に対してフェデレーションを有効にしても、アクセス エッジ サービスを実行するサーバーで、フェデレーション ドメイン宛てのルーティングをサポートすることを指定するだけです。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-119">Enabling federation for your organization only specifies that your servers running the Access Edge service support routing to federated domains.</span></span> <span data-ttu-id="3a9fa-120">フェデレーション ユーザー アクセスをサポートするポリシーを少なくとも 1 つ構成するまでは、フェデレーション ドメインのユーザーは、組織の会議や IM に参加できません。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-120">Users in federated domains cannot participate in IM or conferences in your organization until you also configure at least one policy to support federated user access.</span></span> <span data-ttu-id="3a9fa-121">パブリック IM 接続をサポートするポリシーを少なくとも 1 つ構成するまでは、パブリック IM サービス プロバイダーのユーザーも、組織の会議や IM に参加できません。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-121">Users of public IM service providers cannot participate in IM or conferences in your organization until you also configure at least one policy to support public IM connectivity.</span></span> <span data-ttu-id="3a9fa-122">ルーティング情報を提供するホスト ボイス メール ポリシーを構成するまでは、Lync サーバーは、Hosted Exchange サービスを使用して、Hosted Exchange サービスにあるメールボックスを使用するユーザーに対して、通話応答、Outlook Voice Access (ボイス メールを含む)、および自動応答サービスを提供できません。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-122">Lync Server cannot use a hosted Exchange service to provide call answering, Outlook Voice Access (including voice mail), or auto-attendant services for users whose mailboxes are located on a hosted Exchange service until you configure a hosted voice mail policy that provides routing information.</span></span> <span data-ttu-id="3a9fa-123">他の組織のフェデレーションドメインのユーザーと通信するためのポリシーの構成の詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">MANAGE SIP フェデレーションドメイン for Your Lync Server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-123">For details about configuring policies for communication with users of federated domains in other organizations, see <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP federated domains for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="3a9fa-124">さらに、IM サービス プロバイダーのユーザーとの通信をサポートする場合は、これをサポートするポリシーを構成し、サポートする個々のサービス プロバイダーのサポートも構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-124">Additionally, if you want to support communication with users of IM service providers, you must configure policies to support it and also configure support for the individual service providers that you want to support.</span></span> <span data-ttu-id="3a9fa-125">詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Lync Server 2013 での組織の SIP フェデレーションプロバイダーの管理</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-125">For details, see <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Manage SIP federated providers for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="3a9fa-126">ホストボイスメールポリシーの作成の詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies In Lync Server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-126">For details about creating a hosted voice mail policy, see <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a><span data-ttu-id="3a9fa-127">組織に対するフェデレーション ユーザー アクセスを有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="3a9fa-127">To enable or disable federated user access for your organization</span></span>

1.  <span data-ttu-id="3a9fa-128">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-128">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3a9fa-129">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-129">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3a9fa-130">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-130">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3a9fa-131">左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-131">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="3a9fa-132">[**アクセス エッジ構成**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-132">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="3a9fa-133">[**アクセス エッジ構成の編集**] で、次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-133">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="3a9fa-134">組織に対してフェデレーション ユーザー アクセスを有効にするには、[**フェデレーション ユーザーとの通信を有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-134">To enable federated user access for your organization, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="3a9fa-135">組織に対してフェデレーション ユーザー アクセスを無効にするには、[**フェデレーション ユーザーとの通信を有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-135">To disable federated user access for your organization, clear the **Enable communications with federated users** check box.</span></span>

6.  <span data-ttu-id="3a9fa-136">[**フェデレーション ユーザーとの通信を有効にする**] チェック ボックスをオンにした場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-136">If you selected the **Enable communications with federated users** check box, do the following:</span></span>
    
    1.  <span data-ttu-id="3a9fa-137">パートナー ドメインの自動検出をサポートする場合は、[**パートナー ドメインの検出を有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-137">If you want to support automatic discovery of partner domains, select the **Enable partner domain discovery** check box.</span></span>
    
    2.  <span data-ttu-id="3a9fa-138">組織で外部通信のアーカイブをサポートする場合は、[**フェデレーション パートナーにアーカイブについての免責事項を送信する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-138">If your organization supports archiving of external communications, select the **Send archiving disclaimer to federated partners** check box.</span></span>

7.  <span data-ttu-id="3a9fa-139">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-139">Click **Commit**.</span></span>

<span data-ttu-id="3a9fa-140">フェデレーションユーザーが Lync Server 2013 展開内のユーザーと共同作業できるようにするには、フェデレーションユーザーアクセスをサポートするために少なくとも1つの外部アクセスポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-140">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must also configure at least one external access policy to support federated user access.</span></span> <span data-ttu-id="3a9fa-141">詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 [Configure policies to control For Lync Server 2013」](lync-server-2013-configure-policies-to-control-federated-user-access.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-141">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="3a9fa-142">特定のフェデレーションドメインのアクセスを制御するには、「展開」のドキュメントまたは「操作」のドキュメントの「 [Configure support for allowed external domains In Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-142">To control access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3a9fa-143">Windows PowerShell コマンドレットを使用してフェデレーションとパブリック IM 接続を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="3a9fa-143">Enabling or Disabling Federation and Public IM Connectivity by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3a9fa-144">フェデレーションとパブリック IM 接続は、Windows PowerShell および Set-CsAccessEdgeConfiguration コマンドレットを使用して管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-144">Federation and public IM connectivity can also be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="3a9fa-145">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-145">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3a9fa-146">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-146">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a><span data-ttu-id="3a9fa-147">フェデレーションとパブリック IM 接続を有効にするには</span><span class="sxs-lookup"><span data-stu-id="3a9fa-147">To enable federation and public IM connectivity</span></span>

  - <span data-ttu-id="3a9fa-148">フェデレーションとパブリック IM 接続を有効にするには、**AllowFederatedUsers** プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-148">To enable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a><span data-ttu-id="3a9fa-149">フェデレーションとパブリック IM 接続を無効にするには</span><span class="sxs-lookup"><span data-stu-id="3a9fa-149">To disable federation and public IM connectivity</span></span>

  - <span data-ttu-id="3a9fa-150">フェデレーションとパブリック IM 接続を無効にするには、**AllowFederatedUsers** プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="3a9fa-150">To disable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

