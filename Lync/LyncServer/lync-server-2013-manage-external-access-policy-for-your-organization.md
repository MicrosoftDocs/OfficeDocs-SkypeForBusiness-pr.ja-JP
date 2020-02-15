---
title: 'Lync Server 2013: 組織の外部アクセスポリシーの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a7a3d612de9cf530e512031b7009a83ad9c391c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a><span data-ttu-id="b732d-102">Lync Server 2013 での外部アクセスポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="b732d-102">Manage external access policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b732d-103">_**トピックの最終更新日:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="b732d-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="b732d-104">1つ以上のエッジサーバーを展開した後、組織でサポートされる外部アクセスの種類を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b732d-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="b732d-p101">組織で外部ユーザー アクセス (リモート ユーザー アクセス、フェデレーション ユーザー アクセスなど) のサポートを既に有効にしていても、既定では外部ユーザー アクセスをサポートするように構成されているポリシーはありません。外部ユーザー アクセスの使用を制御するには、1 つ以上のポリシーを構成し、各ポリシーでサポートする外部ユーザー アクセスの種類を指定する必要があります。ポリシーの作成および構成時に使用できるスコープを次に示します。既定では、グローバル ポリシーが作成されますが、このポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="b732d-p101">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization. To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy. The following policy scopes are available for creation and configuration. By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="b732d-109">**グローバルポリシー**   エッジサーバーを展開すると、グローバルポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b732d-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="b732d-110">既定では、グローバルポリシーでは、外部ユーザーアクセスオプションが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="b732d-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="b732d-111">グローバルレベルで外部ユーザーアクセスをサポートするには、1つまたは複数の種類の外部ユーザーアクセスオプションをサポートするようにグローバルポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="b732d-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="b732d-112">グローバルポリシーは、組織内のすべてのユーザーに適用されますが、サイトポリシーとユーザーポリシーはグローバルポリシーより優先されます。</span><span class="sxs-lookup"><span data-stu-id="b732d-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="b732d-113">グローバルポリシーを削除した場合は、削除しないようにします。</span><span class="sxs-lookup"><span data-stu-id="b732d-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="b732d-114">代わりに、既定の設定にリセットします。</span><span class="sxs-lookup"><span data-stu-id="b732d-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="b732d-115">**サイトポリシー**   1 つ以上のサイトポリシーを作成および構成して、特定のサイトへの外部ユーザーアクセスのサポートを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="b732d-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="b732d-116">サイト ポリシーの構成はグローバル ポリシーの構成よりも優先されますが、対象になるのはサイト ポリシーで指定された特定のサイトだけです。</span><span class="sxs-lookup"><span data-stu-id="b732d-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="b732d-117">たとえば、グローバル ポリシーでリモート ユーザー アクセスが有効になっていても、特定のサイトのリモート ユーザー アクセスを無効にするサイト ポリシーを指定することが可能です。</span><span class="sxs-lookup"><span data-stu-id="b732d-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="b732d-118">既定では、サイト ポリシーはそのサイトのすべてのユーザーに適用されますが、特定のユーザーにユーザー ポリシーを割り当てて、サイト ポリシーの設定を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b732d-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="b732d-119">**ユーザーポリシー**   1 つ以上のユーザーポリシーを作成および構成して、特定のユーザーへのリモートユーザーアクセスのサポートを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="b732d-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="b732d-120">ユーザー ポリシーの構成はグローバル ポリシーやサイト ポリシーよりも優先されますが、そのユーザー ポリシーが割り当てられている特定のユーザーのみを対象にします。</span><span class="sxs-lookup"><span data-stu-id="b732d-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="b732d-121">たとえば、グローバル ポリシーとサイト ポリシーでリモート ユーザー アクセスが有効になっていても、リモート ユーザー アクセスを無効にするユーザー ポリシーを指定して、そのポリシーを特定のユーザーに割り当てることは可能です。</span><span class="sxs-lookup"><span data-stu-id="b732d-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="b732d-122">ユーザー ポリシーを作成した場合は、1 人以上のユーザーに適用しないと、実際には使用できません。</span><span class="sxs-lookup"><span data-stu-id="b732d-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b732d-p105">あるポリシー レベルで適用されている Lync Server ポリシー設定が、他のポリシー レベルで適用されている設定によって無効になることがあります。Lync Server ポリシーの優先順位は、ユーザー ポリシーが最も高く、サイト ポリシー、グローバル ポリシー (優先度が最も低い) と続きます。つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="b732d-p105">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level. Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="b732d-126">これらのオプションには、次の種類の外部アクセスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b732d-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="b732d-127">**フェデレーションユーザー**   との通信を有効にするフェデレーションパートナードメインへのユーザーアクセスをサポートする場合は、これを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b732d-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="b732d-128">この設定では、ユーザーが他の SIP フェデレーションドメインと、Microsoft Office 365 などのホストされるプロバイダーと通信する機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="b732d-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft Office 365.</span></span> <span data-ttu-id="b732d-129">この設定を選択すると、XMPP フェデレーションドメインとの通信を許可するオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="b732d-129">Selecting this setting allows you to select the option to allow communication with XMPP federated domains.</span></span>
    
    <span data-ttu-id="b732d-p107">[**フェデレーション ユーザーとの通信を有効にする**] を選択していれば、必要に応じて、[**XMPP フェデレーション ユーザーとの通信を有効にする**] を選択できます。XMPP フェデレーションは、Extensible Messaging and Presence Protocol (XMPP) を使用する組織とのフェデレーションです。</span><span class="sxs-lookup"><span data-stu-id="b732d-p107">As an option, you can select **Enable communications with XMPP federated partners** if you first select **Enable communications with federated users**. XMPP federation is a federation with organizations that use extensible messaging and presence protocol (XMPP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b732d-132">XMPP フェデレーションを有効にする場合は、トポロジビルダーのエッジプール構成セクションで<STRONG>xmpp フェデレーション</STRONG>を展開することも選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b732d-132">If you enable XMPP federation, you must also select to deploy <STRONG>XMPP federation</STRONG> in the Edge pools configuration section of Topology Builder.</span></span> <span data-ttu-id="b732d-133">XMPP フェデレーションを構成すると、エッジサーバーには XMPP プロキシが展開され、フロントエンドサーバーには XMPP ゲートウェイが展開されます。</span><span class="sxs-lookup"><span data-stu-id="b732d-133">Configuring for XMPP federation deploys an XMPP Proxy on the Edge Server and an XMPP gateway on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="b732d-134">**[リモートユーザー**   との通信を有効にする] このオプションを有効にすると、出張中の在宅勤務やユーザーなど、ファイアウォールの外側にいる組織内のユーザーがインターネット経由で Lync Server に接続できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b732d-134">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

  - <span data-ttu-id="b732d-135">**[パブリックユーザー**   との通信を有効にする] 内部ユーザーがパブリック IM プロバイダーの連絡先 (Windows Live、Yahoo\!、および America Online (AOL) によって提供される連絡先など) と通信できるようにする場合は、このオプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b732d-135">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts, such as those provided by Windows Live, Yahoo\!, and America Online (AOL).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="b732d-136">2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規購入時または契約の更新時に購入することができなくなりました。</span><span class="sxs-lookup"><span data-stu-id="b732d-136">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="b732d-137">アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。</span><span class="sxs-lookup"><span data-stu-id="b732d-137">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="b732d-138">メッセンジャーサービスが終了するまでの期間。</span><span class="sxs-lookup"><span data-stu-id="b732d-138">Messenger until the service shut down date.</span></span> <span data-ttu-id="b732d-139">AOL および Yahoo! の2014年6月の寿命の終了日</span><span class="sxs-lookup"><span data-stu-id="b732d-139">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="b732d-140">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="b732d-140">has been announced.</span></span> <span data-ttu-id="b732d-141">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b732d-141">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="b732d-142">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの月ごとのサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="b732d-142">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="b732d-143">Messenger.</span><span class="sxs-lookup"><span data-stu-id="b732d-143">Messenger.</span></span> <span data-ttu-id="b732d-144">このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートに応じて決定されました。これは、使用する基礎となる契約です。</span><span class="sxs-lookup"><span data-stu-id="b732d-144">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="b732d-145">Lync は、組織間や世界中の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="b732d-145">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="b732d-146">Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b732d-146">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="b732d-147">Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を使用して数百人のユーザーにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="b732d-147">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="b732d-148">外部ユーザー アクセスのサポートを有効にするだけでなく、ユーザーが任意の種類の外部ユーザー アクセスを使用できるようにする前に、組織内での外部ユーザー アクセスの使用を制御するポリシーも構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b732d-148">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="b732d-149">外部ユーザーアクセスのポリシーの作成、構成、および適用の詳細については、「 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でのリモートユーザーアクセスの有効化または無効化</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b732d-149">For details about creating, configuring, and applying policies for external user access see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="b732d-150">**Windows PowerShell コマンドレットを使用して外部アクセスポリシーを表示するには**</span><span class="sxs-lookup"><span data-stu-id="b732d-150">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="b732d-151">外部アクセスポリシーは、Lync Server 管理シェルと**get-csexternalaccesspolicy**コマンドレットを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="b732d-151">You can view external access policies by using Lync Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="b732d-152">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="b732d-152">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b732d-153">リモート Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Microsoft Lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)を使用したリモート PowerShell の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b732d-153">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="b732d-154">すべての外部アクセスポリシーに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b732d-154">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsExternalAccessPolicy
    
    <span data-ttu-id="b732d-155">このコマンドは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="b732d-155">This command returns information similar to the following:</span></span>
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a><span data-ttu-id="b732d-156">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b732d-156">In This Section</span></span>

  - [<span data-ttu-id="b732d-157">Lync Server 2013 でフェデレーションユーザーアクセスを制御するポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="b732d-157">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [<span data-ttu-id="b732d-158">Lync Server 2013 での XMPP フェデレーションユーザーアクセスを制御するポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="b732d-158">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [<span data-ttu-id="b732d-159">Lync Server 2013 でのリモートユーザーアクセスを制御するポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="b732d-159">Configure policies to control remote user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [<span data-ttu-id="b732d-160">Lync Server 2013 でのパブリックユーザーアクセスを制御するポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="b732d-160">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [<span data-ttu-id="b732d-161">Lync Server 2013 での Lync が有効なユーザーへの外部ユーザーアクセスポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="b732d-161">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="b732d-162">Lync Server 2013 での外部ユーザーアクセスポリシーのリセットまたは削除</span><span class="sxs-lookup"><span data-stu-id="b732d-162">Resetting or deleting external user access policies in Lync Server 2013</span></span>](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

