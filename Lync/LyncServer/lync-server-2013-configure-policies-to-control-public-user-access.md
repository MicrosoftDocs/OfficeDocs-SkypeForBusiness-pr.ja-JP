---
title: 'Lync Server 2013: パブリックユーザーアクセスを制御するポリシーの構成'
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
ms.openlocfilehash: 54c92e1da5ea1ea54ae8386cdcdce5054d76609e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a><span data-ttu-id="2029b-102">Lync Server 2013 でのパブリックユーザーアクセスを制御するポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="2029b-102">Configure policies to control public user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2029b-103">_**トピックの最終更新日:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="2029b-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="2029b-104">パブリックインスタントメッセージング (IM) 接続を使用すると、組織内のユーザーは IM を使用して、インターネットサービス、Yahoo\!、AOL の Windows Live ネットワークを含む、パブリック im サービスプロバイダーが提供する im サービスのユーザーと通信することができます。</span><span class="sxs-lookup"><span data-stu-id="2029b-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live network of Internet services, Yahoo\!, and AOL.</span></span> <span data-ttu-id="2029b-105">1つ以上の外部ユーザーアクセスポリシーを構成して、パブリックユーザーが内部の Lync Server ユーザーと共同作業できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="2029b-105">You configure one or more external user access policies to control whether public users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="2029b-106">パブリック インスタント メッセージング接続は、展開およびユーザーの構成に依存する追加機能です。</span><span class="sxs-lookup"><span data-stu-id="2029b-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="2029b-107">この機能は、パブリック IM プロバイダーでのサービスのプロビジョニングにも依存します。</span><span class="sxs-lookup"><span data-stu-id="2029b-107">It also depends on the provisioning of the service at the public IM provider.</span></span> <span data-ttu-id="2029b-108">公開プロバイダーを使用するように展開を準備する方法については、「Microsoft Lync Server、Office Communications Server、Live Communications Server のパブリック IM 接続プロビジョニングガイド:」を参照してください。[https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)</span><span class="sxs-lookup"><span data-stu-id="2029b-108">For information on how to provision your deployment to use the public providers, see the “Public IM Connectivity Provisioning Guide for Microsoft Lync Server, Office Communications Server, and Live Communications Server” guide: [https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="2029b-109">2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規購入時または契約の更新時に購入することができなくなりました。</span><span class="sxs-lookup"><span data-stu-id="2029b-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="2029b-110">アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。</span><span class="sxs-lookup"><span data-stu-id="2029b-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="2029b-111">メッセンジャーサービスが終了するまでの期間。</span><span class="sxs-lookup"><span data-stu-id="2029b-111">Messenger until the service shut down date.</span></span> <span data-ttu-id="2029b-112">AOL および Yahoo! の2014年6月の寿命の終了日</span><span class="sxs-lookup"><span data-stu-id="2029b-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="2029b-113">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="2029b-113">has been announced.</span></span> <span data-ttu-id="2029b-114">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2029b-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="2029b-115">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの月ごとのサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="2029b-115">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="2029b-116">Messenger.</span><span class="sxs-lookup"><span data-stu-id="2029b-116">Messenger.</span></span> <span data-ttu-id="2029b-117">このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートに応じて決定されました。これは、使用する基礎となる契約です。</span><span class="sxs-lookup"><span data-stu-id="2029b-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="2029b-118">Lync は、組織間や世界中の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="2029b-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="2029b-119">Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2029b-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="2029b-120">Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を使用して数百人のユーザーにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="2029b-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="2029b-121">Microsoft Lync Server パブリック IM 接続プロビジョニングサイトにアクセスするには、次のリンクを使用します。[https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)</span><span class="sxs-lookup"><span data-stu-id="2029b-121">To access the Microsoft Lync Server Public IM Connectivity Provisioning site, use the following link: [https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)</span></span>

<span data-ttu-id="2029b-122">パブリック ユーザー アクセスを制御するには、グローバル レベル、サイト レベル、およびユーザー レベルでポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="2029b-122">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="2029b-123">構成できるポリシーの種類の詳細については、「展開」のドキュメントまたは「計画」のドキュメントの「configure [support for external user access In Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2029b-123">For details about the types of policies that you can configure, see [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) in the Deployment documentation or the Planning documentation.</span></span> <span data-ttu-id="2029b-124">あるポリシー レベルで適用されている Lync Server ポリシー設定が、他のポリシー レベルで適用されている設定によって無効になることがあります。</span><span class="sxs-lookup"><span data-stu-id="2029b-124">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="2029b-125">Lync Server ポリシーの優先順位は、ユーザー ポリシーが最も高く、サイト ポリシー、グローバル ポリシー (優先度が最も低い) と続きます。</span><span class="sxs-lookup"><span data-stu-id="2029b-125">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="2029b-126">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="2029b-126">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="2029b-p106">IM の招待の場合は、クライアント ソフトウェアによって応答が異なります。 ユーザーが構成したルール (ユーザーのクライアントの [**許可**] および [**禁止**] リストの設定) によって、外部の送信者が明示的に禁止されている場合以外は、要求が受け入れられます。 また、[**許可**] リストに含まれていないユーザーからの IM はすべて禁止することを選択すると、IM の招待をブロックできます。</span><span class="sxs-lookup"><span data-stu-id="2029b-p106">In the case of IM invitations, the response depends on the client software. The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists). Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2029b-130">組織でフェデレーションを有効にしていなくても、パブリック ユーザー アクセスを制御するポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="2029b-130">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="2029b-131">ただし構成するポリシーは、組織でフェデレーションを有効にした場合にのみ有効となります。</span><span class="sxs-lookup"><span data-stu-id="2029b-131">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="2029b-132">フェデレーションを有効にする方法の詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でリモートユーザーアクセスを有効または無効</A>にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2029b-132">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="2029b-133">また、パブリックユーザーアクセスを制御するユーザーポリシーを指定した場合、このポリシーは、Lync Server が有効になっていて、そのポリシーを使用するように構成されているユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="2029b-133">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="2029b-134">Lync Server にサインインできるパブリックユーザーの指定の詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「lync <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">server 2013 で lync が有効なユーザーへの外部ユーザーアクセスポリシーの割り当て</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2029b-134">For details about specifying public users that can sign in to Lync Server, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<span data-ttu-id="2029b-135">以下の手順を使用して、1 つ以上のパブリック IM プロバイダーのユーザーによるアクセスをサポートするポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="2029b-135">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="2029b-136">パブリック ユーザー アクセスをサポートするように外部アクセス ポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="2029b-136">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="2029b-137">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="2029b-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2029b-138">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2029b-138">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2029b-139">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2029b-139">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2029b-140">左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2029b-140">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="2029b-141">[**外部アクセス ポリシー**] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2029b-141">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="2029b-142">パブリック ユーザー アクセスをサポートするようにグローバル ポリシーを構成するには、グローバル ポリシーをクリックし、[**編集**]、[**詳細の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2029b-142">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="2029b-p109">新しいサイト ポリシーを作成するには、[**新規作成**] をクリックし、[**サイト ポリシー**] をクリックします。 [**サイトの選択**] で一覧から適切なサイトをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2029b-p109">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="2029b-p110">新しいユーザー ポリシーを作成するには、[**新規作成**] をクリックし、[**ユーザー ポリシー**] をクリックします。 [**新しい外部アクセス ポリシー**] の [**名前**] フィールドで、ユーザー ポリシーの適用範囲を示す一意の名前を作成します (たとえば、パブリック ユーザーの通信を有効にするユーザー ポリシーの場合、**EnablePublicUsers** という名前を作成します)。</span><span class="sxs-lookup"><span data-stu-id="2029b-p110">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="2029b-147">既存のポリシーを変更するには、表に表示されている適切なポリシーをクリックし、[**編集**]、[**詳細の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2029b-147">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="2029b-148">(オプション) 説明を追加または編集する場合は、[**説明**] でポリシーの情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="2029b-148">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="2029b-149">次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2029b-149">Do one of the following:</span></span>
    
      - <span data-ttu-id="2029b-150">ポリシーのパブリック ユーザー アクセスを有効にするには、[**パブリック ユーザーとの通信を有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2029b-150">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="2029b-151">ポリシーのパブリック ユーザー アクセスを無効にするには、[**パブリック ユーザーとの通信を有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="2029b-151">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="2029b-152">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2029b-152">Click **Commit**.</span></span>

<span data-ttu-id="2029b-153">パブリック ユーザー アクセスを有効にするには、組織でフェデレーションのサポートも有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2029b-153">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="2029b-154">詳細については、「 [Lync Server 2013 でフェデレーションユーザーアクセスを制御するようにポリシーを構成する](lync-server-2013-configure-policies-to-control-federated-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2029b-154">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="2029b-155">これがユーザー ポリシーの場合、パブリック ユーザーと共同作業できるようにするパブリック ユーザーに対してもポリシーを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2029b-155">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> <span data-ttu-id="2029b-156">詳細については、「 [Lync Server 2013 でユーザーごとのポリシーを割り当てる](lync-server-2013-assigning-per-user-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2029b-156">For details, see [Assigning per-user policies in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2029b-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="2029b-157">See Also</span></span>


[<span data-ttu-id="2029b-158">Lync Server 2013 でのパブリック SIP フェデレーションプロバイダーの作成または編集</span><span class="sxs-lookup"><span data-stu-id="2029b-158">Create or edit public SIP federated providers in Lync Server 2013</span></span>](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[<span data-ttu-id="2029b-159">Lync Server 2013 での組織の SIP フェデレーションプロバイダーの管理</span><span class="sxs-lookup"><span data-stu-id="2029b-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

