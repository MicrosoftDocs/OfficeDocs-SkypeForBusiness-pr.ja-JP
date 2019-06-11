---
title: 'Lync Server 2013: 組織の外部アクセス ポリシーの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10a08e096d517d2ac53866df763ab2f553480da5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a><span data-ttu-id="01783-102">Lync Server 2013 での組織の外部アクセス ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="01783-102">Manage external access policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01783-103">_**最終更新日:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="01783-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="01783-104">1つ以上のエッジサーバーを展開した後は、組織でサポートされる外部アクセスの種類を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="01783-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="01783-105">既定では、組織の外部ユーザーアクセスのサポートを有効にしている場合でも、リモートユーザーアクセス、フェデレーションされたユーザーアクセスなどの外部ユーザーアクセスをサポートするように構成されたポリシーはありません。</span><span class="sxs-lookup"><span data-stu-id="01783-105">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization.</span></span> <span data-ttu-id="01783-106">外部ユーザーアクセスの使用を制御するには、1つ以上のポリシーを構成して、各ポリシーでサポートされている外部ユーザーアクセスの種類を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01783-106">To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy.</span></span> <span data-ttu-id="01783-107">作成と構成では、次のポリシースコープを使用できます。</span><span class="sxs-lookup"><span data-stu-id="01783-107">The following policy scopes are available for creation and configuration.</span></span> <span data-ttu-id="01783-108">既定では、グローバルポリシーは作成されますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="01783-108">By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="01783-109">**グローバルポリシー**   エッジサーバーを展開すると、グローバルポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="01783-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="01783-110">既定では、グローバルポリシーで外部ユーザーアクセスオプションは有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="01783-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="01783-111">グローバルレベルで外部ユーザーのアクセスをサポートするには、1つ以上の種類の外部ユーザーアクセスオプションをサポートするようにグローバルポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="01783-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="01783-112">グローバルポリシーは組織内のすべてのユーザーに適用されますが、サイトポリシーとユーザーポリシーはグローバルポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="01783-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="01783-113">グローバルポリシーを削除しても、削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="01783-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="01783-114">代わりに、既定の設定にリセットします。</span><span class="sxs-lookup"><span data-stu-id="01783-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="01783-115">**サイトポリシー**   1 つ以上のサイトポリシーを作成し、構成して、特定のサイトへの外部ユーザーアクセスのサポートを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="01783-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="01783-116">サイト ポリシーの構成はグローバル ポリシーよりも優先されますが、サイト ポリシーで指定されたサイトだけが対象となります。</span><span class="sxs-lookup"><span data-stu-id="01783-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="01783-117">たとえば、グローバルポリシーでリモートユーザーアクセスを有効にする場合、特定のサイトのリモートユーザーアクセスを無効にするサイトポリシーを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="01783-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="01783-118">既定では、サイトポリシーはそのサイトのすべてのユーザーに適用されますが、サイトポリシー設定を上書きするユーザーポリシーをユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="01783-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="01783-119">**ユーザーポリシー**   1 つまたは複数のユーザーポリシーを作成および構成して、リモートユーザーアクセスのサポートを特定のユーザーに制限することができます。</span><span class="sxs-lookup"><span data-stu-id="01783-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="01783-120">ユーザーポリシーの構成は、グローバルポリシーおよびサイトポリシーを上書きしますが、ユーザーポリシーが割り当てられている特定のユーザーに対してのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="01783-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="01783-121">たとえば、グローバルポリシーとサイトポリシーでリモートユーザーアクセスを有効にすると、リモートユーザーアクセスを無効にするユーザーポリシーを指定して、そのユーザーポリシーを特定のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="01783-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="01783-122">ユーザーポリシーを作成する場合は、それを有効にする前に1人以上のユーザーに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01783-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="01783-123">1つのポリシーレベルで適用される Lync Server ポリシーの設定は、別のポリシーレベルで適用されている設定を上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="01783-123">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="01783-124">Lync Server ポリシーの優先順位: ユーザーポリシー (ほとんどの影響) によってサイトポリシーが上書きされ、サイトポリシーがグローバルポリシーを上書きします (最も影響が少なくなります)。</span><span class="sxs-lookup"><span data-stu-id="01783-124">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="01783-125">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="01783-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="01783-126">これらのオプションには、次のような外部アクセスがあります。</span><span class="sxs-lookup"><span data-stu-id="01783-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="01783-127">**フェデレーションされたユーザー**   との通信を有効にするフェデレーションパートナードメインへのユーザーアクセスをサポートする場合は、これを有効にします。</span><span class="sxs-lookup"><span data-stu-id="01783-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="01783-128">この設定では、ユーザーが他の SIP フェデレーションドメインと、Microsoft Office 365 などのホストされるプロバイダーと通信する機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="01783-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft Office 365.</span></span> <span data-ttu-id="01783-129">この設定を選択すると、XMPP フェデレーションドメインとの通信を許可するオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="01783-129">Selecting this setting allows you to select the option to allow communication with XMPP federated domains.</span></span>
    
    <span data-ttu-id="01783-130">オプションとして、[フェデレーションされた**ユーザーとの通信を有効**にする] を選択した場合は、[ **xmpp フェデレーションパートナーとの通信を有効**にする] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="01783-130">As an option, you can select **Enable communications with XMPP federated partners** if you first select **Enable communications with federated users**.</span></span> <span data-ttu-id="01783-131">XMPP フェデレーションは、拡張メッセージングとプレゼンスプロトコル (XMPP) を使用する組織とのフェデレーションです。</span><span class="sxs-lookup"><span data-stu-id="01783-131">XMPP federation is a federation with organizations that use extensible messaging and presence protocol (XMPP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="01783-132">XMPP フェデレーションを有効にした場合、トポロジビルダーの Edge プール構成セクションで、[ <STRONG>xmpp フェデレーション</STRONG>の展開] も選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01783-132">If you enable XMPP federation, you must also select to deploy <STRONG>XMPP federation</STRONG> in the Edge pools configuration section of Topology Builder.</span></span> <span data-ttu-id="01783-133">XMPP フェデレーション用に構成すると、microsoft Edge サーバー上の XMPP プロキシと、フロントエンドサーバー上の XMPP ゲートウェイが展開されます。</span><span class="sxs-lookup"><span data-stu-id="01783-133">Configuring for XMPP federation deploys an XMPP Proxy on the Edge Server and an XMPP gateway on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="01783-134">**[リモートユーザー**   との通信を有効にする] 出張中の在宅勤務者やユーザーなど、組織内のユーザーがインターネット経由で Lync Server に接続できるようにする場合は、このオプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="01783-134">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

  - <span data-ttu-id="01783-135">**[パブリックユーザー**   との通信を有効にする] このオプションは、内部ユーザーが、Windows Live、Yahoo\!、America Online (AOL) によって提供される連絡先などのパブリック IM プロバイダーの連絡先と通信できるようにする場合に有効にします。</span><span class="sxs-lookup"><span data-stu-id="01783-135">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts, such as those provided by Windows Live, Yahoo\!, and America Online (AOL).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="01783-136">2012年9月1日以降、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規または更新契約の購入に使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="01783-136">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="01783-137">アクティブなライセンスを持っているお客様は、Yahoo! とのフェデレーションを継続できます。</span><span class="sxs-lookup"><span data-stu-id="01783-137">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="01783-138">サービスが終了するまでの Messenger。</span><span class="sxs-lookup"><span data-stu-id="01783-138">Messenger until the service shut down date.</span></span> <span data-ttu-id="01783-139">AOL および Yahoo! の2014年6月の終了日</span><span class="sxs-lookup"><span data-stu-id="01783-139">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="01783-140">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="01783-140">has been announced.</span></span> <span data-ttu-id="01783-141">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01783-141">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="01783-142">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要な1か月あたりのユーザーごとのサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="01783-142">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="01783-143">Messenger.</span><span class="sxs-lookup"><span data-stu-id="01783-143">Messenger.</span></span> <span data-ttu-id="01783-144">このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートによって決定されたものであり、その基となる契約は "巻停止" となります。</span><span class="sxs-lookup"><span data-stu-id="01783-144">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="01783-145">Lync は、組織間、および世界各地の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="01783-145">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="01783-146">Windows Live Messenger とのフェデレーションには、Lync 標準 CAL 以外の追加のユーザー/デバイスライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="01783-146">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="01783-147">Skype federation はこのリストに追加されます。 Lync ユーザーは、IM と音声を使用して、数百人の何百万ものユーザーに連絡できます。</span><span class="sxs-lookup"><span data-stu-id="01783-147">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="01783-148">外部ユーザーアクセスのサポートを有効にするだけでなく、ユーザーが外部ユーザーアクセスを利用できるようにする前に、組織で外部ユーザーアクセスの使用を制御するためのポリシーも構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01783-148">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="01783-149">外部ユーザーアクセスのポリシーの作成、構成、適用の詳細については、「 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でリモートユーザーアクセスを有効または無効</A>にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01783-149">For details about creating, configuring, and applying policies for external user access see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="01783-150">**Windows PowerShell コマンドレットを使用して外部アクセスポリシーを表示するには**</span><span class="sxs-lookup"><span data-stu-id="01783-150">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="01783-151">Lync Server 管理シェルと**CsExternalAccessPolicy**コマンドレットを使用して、外部アクセスポリシーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="01783-151">You can view external access policies by using Lync Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="01783-152">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="01783-152">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="01783-153">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01783-153">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="01783-154">すべての外部アクセスポリシーに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="01783-154">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsExternalAccessPolicy
    
    <span data-ttu-id="01783-155">このコマンドは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="01783-155">This command returns information similar to the following:</span></span>
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a><span data-ttu-id="01783-156">このセクション中</span><span class="sxs-lookup"><span data-stu-id="01783-156">In This Section</span></span>

  - [<span data-ttu-id="01783-157">Lync Server 2013 でのフェデレーション ユーザー アクセスを制御するポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="01783-157">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [<span data-ttu-id="01783-158">Lync Server 2013 での XMPP フェデレーション ユーザー アクセスを制御するポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="01783-158">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [<span data-ttu-id="01783-159">Lync Server 2013 でのリモート ユーザー アクセスを制御するポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="01783-159">Configure policies to control remote user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [<span data-ttu-id="01783-160">Lync Server 2013 でのパブリック ユーザー アクセスを制御するポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="01783-160">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [<span data-ttu-id="01783-161">Lync Server 2013 での Lync が有効なユーザーに対する外部ユーザー アクセス ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="01783-161">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="01783-162">Lync Server 2013 外部ユーザー アクセス ポリシーのリセットまたは削除</span><span class="sxs-lookup"><span data-stu-id="01783-162">Resetting or deleting external user access policies in Lync Server 2013</span></span>](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

