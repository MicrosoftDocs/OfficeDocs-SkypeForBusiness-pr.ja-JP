---
title: 'Lync Server 2013: パブリック ユーザー アクセスを制御するポリシーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b348abcce00eb57988c7aa5184c0cfb5ea302adb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763279"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a><span data-ttu-id="3544d-102">Lync Server 2013 でのパブリック ユーザー アクセスを制御するポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="3544d-102">Configure policies to control public user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3544d-103">_**最終更新日:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="3544d-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="3544d-104">パブリックインスタントメッセージング (IM) 接続を使うと、組織内のユーザーは、インターネットサービス、Yahoo\!、AOL の Windows Live ネットワークなど、パブリック im サービスプロバイダーによって提供される im サービスのユーザーと通信することができます。</span><span class="sxs-lookup"><span data-stu-id="3544d-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live network of Internet services, Yahoo\!, and AOL.</span></span> <span data-ttu-id="3544d-105">1つ以上の外部ユーザーアクセスポリシーを構成して、パブリックユーザーが内部の Lync Server ユーザーと共同作業できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3544d-105">You configure one or more external user access policies to control whether public users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="3544d-106">パブリックインスタントメッセージング接続は、展開とユーザーの構成に依存する追加機能です。</span><span class="sxs-lookup"><span data-stu-id="3544d-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="3544d-107">また、パブリック IM プロバイダーでのサービスのプロビジョニングにも依存します。</span><span class="sxs-lookup"><span data-stu-id="3544d-107">It also depends on the provisioning of the service at the public IM provider.</span></span> <span data-ttu-id="3544d-108">パブリックプロバイダーを使用するために展開をプロビジョニングする方法については、「Microsoft Lync Server、Office Communications Server、Live Communications Server 用のパブリック IM 接続プロビジョニングガイド」を参照してください。[http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)</span><span class="sxs-lookup"><span data-stu-id="3544d-108">For information on how to provision your deployment to use the public providers, see the “Public IM Connectivity Provisioning Guide for Microsoft Lync Server, Office Communications Server, and Live Communications Server” guide: [http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="3544d-109">2012年9月1日以降、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規または更新契約の購入に使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="3544d-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="3544d-110">アクティブなライセンスを持っているお客様は、Yahoo! とのフェデレーションを継続できます。</span><span class="sxs-lookup"><span data-stu-id="3544d-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="3544d-111">サービスが終了するまでの Messenger。</span><span class="sxs-lookup"><span data-stu-id="3544d-111">Messenger until the service shut down date.</span></span> <span data-ttu-id="3544d-112">AOL および Yahoo! の2014年6月の終了日</span><span class="sxs-lookup"><span data-stu-id="3544d-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="3544d-113">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="3544d-113">has been announced.</span></span> <span data-ttu-id="3544d-114">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3544d-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="3544d-115">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要な1か月あたりのユーザーごとのサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="3544d-115">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="3544d-116">Messenger.</span><span class="sxs-lookup"><span data-stu-id="3544d-116">Messenger.</span></span> <span data-ttu-id="3544d-117">このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートによって決定されたものであり、その基となる契約は "巻停止" となります。</span><span class="sxs-lookup"><span data-stu-id="3544d-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="3544d-118">Lync は、組織間、および世界各地の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="3544d-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="3544d-119">Windows Live Messenger とのフェデレーションには、Lync 標準 CAL 以外の追加のユーザー/デバイスライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="3544d-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="3544d-120">Skype federation はこのリストに追加されます。 Lync ユーザーは、IM と音声を使用して、数百人の何百万ものユーザーに連絡できます。</span><span class="sxs-lookup"><span data-stu-id="3544d-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="3544d-121">Microsoft Lync Server パブリック IM 接続プロビジョニングサイトにアクセスするには、次のリンクを使用します。[http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)</span><span class="sxs-lookup"><span data-stu-id="3544d-121">To access the Microsoft Lync Server Public IM Connectivity Provisioning site, use the following link: [http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)</span></span>

<span data-ttu-id="3544d-122">パブリックユーザーアクセスを制御するために、グローバル、サイト、ユーザーレベルでポリシーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="3544d-122">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="3544d-123">構成できるポリシーの種類の詳細については、「展開ドキュメントまたは計画ドキュメントの「 [Lync Server 2013 で外部ユーザーアクセスのサポートを構成](lync-server-2013-configuring-support-for-external-user-access.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3544d-123">For details about the types of policies that you can configure, see [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) in the Deployment documentation or the Planning documentation.</span></span> <span data-ttu-id="3544d-124">1つのポリシーレベルで適用される Lync Server ポリシーの設定は、別のポリシーレベルで適用されている設定を上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="3544d-124">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="3544d-125">Lync Server ポリシーの優先順位: ユーザーポリシー (ほとんどの影響) によってサイトポリシーが上書きされ、サイトポリシーがグローバルポリシーを上書きします (最も影響が少なくなります)。</span><span class="sxs-lookup"><span data-stu-id="3544d-125">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="3544d-126">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="3544d-126">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="3544d-127">IM 招待の場合、応答はクライアントソフトウェアによって異なります。</span><span class="sxs-lookup"><span data-stu-id="3544d-127">In the case of IM invitations, the response depends on the client software.</span></span> <span data-ttu-id="3544d-128">外部の送信者が、ユーザーによって構成されたルールによって明示的にブロックされていない限り、要求は承認されます (つまり、ユーザーのクライアントの**許可**リストと**ブロック**リスト内の設定)。</span><span class="sxs-lookup"><span data-stu-id="3544d-128">The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists).</span></span> <span data-ttu-id="3544d-129">さらに、ユーザーが**許可**リストにないユーザーからのすべての im をブロックすることにした場合、im 招待をブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="3544d-129">Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3544d-130">組織のフェデレーションを有効にしていない場合でも、パブリックユーザーアクセスを制御するためのポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="3544d-130">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="3544d-131">ただし、構成したポリシーは、組織でフェデレーションが有効になっている場合にのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="3544d-131">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="3544d-132">フェデレーションを有効にする方法について詳しくは、展開ドキュメントまたは運用ドキュメントの「 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でのリモートユーザーアクセスを有効または無効</A>にする」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3544d-132">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="3544d-133">さらに、ユーザーポリシーを指定してパブリックユーザーアクセスを制御している場合、ポリシーは、Lync Server が有効になっていて、ポリシーを使用するように構成されているユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="3544d-133">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="3544d-134">Lync Server にサインインできるパブリックユーザーの指定の詳細については、展開ドキュメントまたは操作のドキュメントの「lync <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">server 2013 での lync 対応ユーザーへの外部ユーザーアクセスポリシーの割り当て</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3544d-134">For details about specifying public users that can sign in to Lync Server, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<span data-ttu-id="3544d-135">次の手順を使用して、1つ以上のパブリック IM プロバイダーのユーザーによるアクセスをサポートするポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="3544d-135">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="3544d-136">パブリックユーザーのアクセスをサポートするように外部アクセスポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="3544d-136">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="3544d-137">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3544d-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3544d-138">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3544d-138">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3544d-139">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3544d-139">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3544d-140">左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**外部アクセスポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3544d-140">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="3544d-141">[**外部アクセスポリシー** ] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3544d-141">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="3544d-142">パブリックユーザーアクセスをサポートするようにグローバルポリシーを構成するには、グローバルポリシーをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3544d-142">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="3544d-143">新しいサイトポリシーを作成するには、[**新規**作成] をクリックし、[**サイトポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3544d-143">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="3544d-144">[**サイトの選択**] で、一覧から該当するサイトをクリックし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3544d-144">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="3544d-145">新しいユーザーポリシーを作成するには、[**新規**作成] をクリックし、[**ユーザーポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3544d-145">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="3544d-146">[**新しい外部アクセスポリシー**] で、[**名前**] フィールドに、ユーザーポリシーがどのようなものであるかを示す一意の名前を作成します (たとえば、パブリックユーザーの通信を可能にするユーザーポリシーの**enablepublicusers** )。</span><span class="sxs-lookup"><span data-stu-id="3544d-146">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="3544d-147">既存のポリシーを変更するには、表に記載されている適切なポリシーをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3544d-147">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="3544d-148">省略説明を追加または編集する場合は、ポリシーの情報を [**説明**] で指定します。</span><span class="sxs-lookup"><span data-stu-id="3544d-148">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="3544d-149">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="3544d-149">Do one of the following:</span></span>
    
      - <span data-ttu-id="3544d-150">ポリシーのパブリックユーザーアクセスを有効にするには、[**パブリックユーザーとの通信を有効**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3544d-150">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="3544d-151">ポリシーのパブリックユーザーアクセスを無効にするには、[**パブリックユーザーとの通信を有効に**する] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="3544d-151">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="3544d-152">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3544d-152">Click **Commit**.</span></span>

<span data-ttu-id="3544d-153">パブリックユーザーアクセスを有効にするには、組織のフェデレーションのサポートも有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3544d-153">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="3544d-154">詳細については、「 [Lync Server 2013 でフェデレーションされたユーザーアクセスを制御するためのポリシーを構成する](lync-server-2013-configure-policies-to-control-federated-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3544d-154">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="3544d-155">ユーザーポリシーの場合は、パブリックユーザーとの共同作業を可能にするパブリックユーザーにもポリシーを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3544d-155">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> <span data-ttu-id="3544d-156">詳細については、「 [Lync Server 2013 でユーザーごとのポリシーを割り当てる](lync-server-2013-assigning-per-user-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3544d-156">For details, see [Assigning per-user policies in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3544d-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="3544d-157">See Also</span></span>


[<span data-ttu-id="3544d-158">Lync Server 2013 での公開 SIP フェデレーション プロバイダーの作成または編集</span><span class="sxs-lookup"><span data-stu-id="3544d-158">Create or edit public SIP federated providers in Lync Server 2013</span></span>](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[<span data-ttu-id="3544d-159">Lync Server 2013 での組織の SIP フェデレーション プロバイダーの管理</span><span class="sxs-lookup"><span data-stu-id="3544d-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

