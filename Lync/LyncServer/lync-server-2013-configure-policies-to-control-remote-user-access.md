---
title: 'Lync Server 2013: リモート ユーザー アクセスを制御するポリシーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6e542f2a2d836cce507863347384135f97db445
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="584b0-102">Lync Server 2013 でのリモート ユーザー アクセスを制御するポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="584b0-102">Configure policies to control remote user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="584b0-103">_**最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="584b0-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="584b0-104">1つ以上の外部ユーザーアクセスポリシーを構成して、リモートユーザーが内部の Lync Server ユーザーと共同作業できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="584b0-104">You configure one or more external user access policies to control whether remote users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="584b0-105">リモートユーザーアクセスを制御するには、グローバル、サイト、ユーザーレベルでポリシーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="584b0-105">To control remote user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="584b0-106">サイトポリシーはグローバルポリシーを上書きし、ユーザーポリシーはサイトとグローバルポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="584b0-106">Site policies override the global policy, and user policies override site and global policies.</span></span> <span data-ttu-id="584b0-107">構成できるポリシーの種類の詳細については、「 [Lync Server 2013 に対するフェデレーションと外部アクセスを管理する](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="584b0-107">For details about the types of policies that you can configure, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span> <span data-ttu-id="584b0-108">1つのポリシーレベルで適用される Lync Server ポリシーの設定は、別のポリシーレベルで適用されている設定を上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="584b0-108">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="584b0-109">Lync Server ポリシーの優先順位: ユーザーポリシー (ほとんどの影響) によってサイトポリシーが上書きされ、サイトポリシーがグローバルポリシーを上書きします (最も影響が少なくなります)。</span><span class="sxs-lookup"><span data-stu-id="584b0-109">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="584b0-110">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="584b0-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="584b0-111">組織のリモートユーザーアクセスを有効にしていない場合でも、リモートユーザーアクセスを制御するポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="584b0-111">You can configure policies to control remote user access, even if you have not enabled remote user access for your organization.</span></span> <span data-ttu-id="584b0-112">ただし、構成したポリシーは、組織のリモートユーザーアクセスが有効になっている場合にのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="584b0-112">However, the policies that you configure are in effect only when you have remote user access enabled for your organization.</span></span> <span data-ttu-id="584b0-113">リモートユーザーアクセスを有効にする方法の詳細については、「 <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効</A>にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="584b0-113">For details about enabling remote user access, see <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</A>.</span></span> <span data-ttu-id="584b0-114">さらに、リモートユーザーアクセスを制御するユーザーポリシーを指定した場合、このポリシーは、Lync Server が有効になっていて、ポリシーを使用するように構成されているユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="584b0-114">Additionally, if you specify a user policy to control remote user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="584b0-115">リモートの場所から Lync Server にサインインできるユーザーの指定の詳細については、「 <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Lync server 2013 で lync を有効にしたユーザーに外部ユーザーアクセスポリシーを割り当てる</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="584b0-115">For details about specifying users that can sign in to Lync Server from remote locations, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="584b0-116">リモートユーザーアクセスを制御するために使用する外部アクセスポリシーをそれぞれ構成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="584b0-116">Use the following procedure to configure each external access policy that you want to use to control remote user access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="584b0-117">この手順では、リモートユーザーとの通信を可能にするようにポリシーを構成する方法について説明します。ただし、リモートユーザーアクセスをサポートするように構成した各ポリシーでは、フェデレーションされたユーザーアクセスとパブリックユーザーアクセスを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="584b0-117">This procedure describes how to configure a policy only to enable communications with remote users, but each policy that you configure to support remote user access can also configure federated user access and public user access.</span></span> <span data-ttu-id="584b0-118">フェデレーションユーザーをサポートするポリシーの構成の詳細については、「 <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013 でフェデレーションされたユーザーアクセスを制御するためのポリシーを構成する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="584b0-118">For details about configuring policies to support federated users, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="584b0-119">パブリックユーザーをサポートするためのポリシーの構成の詳細については、「 <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Lync Server 2013 でパブリック SIP フェデレーションプロバイダーを作成または編集</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="584b0-119">For details about configuring policies to support public users, see <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a><span data-ttu-id="584b0-120">外部アクセスポリシーを構成してリモートユーザーのアクセスをサポートするには</span><span class="sxs-lookup"><span data-stu-id="584b0-120">To configure an external access policy to support remote user access</span></span>

1.  <span data-ttu-id="584b0-121">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="584b0-121">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="584b0-122">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="584b0-122">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="584b0-123">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="584b0-123">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="584b0-124">左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**外部アクセスポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="584b0-124">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="584b0-125">[**外部アクセスポリシー** ] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="584b0-125">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="584b0-126">リモートユーザーアクセスをサポートするようにグローバルポリシーを構成するには、グローバルポリシーをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="584b0-126">To configure the global policy to support remote user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="584b0-127">新しいサイトポリシーを作成するには、[**新規**作成] をクリックし、[**サイトポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="584b0-127">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="584b0-128">[**サイトの選択**] で、一覧から該当するサイトをクリックし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="584b0-128">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="584b0-129">新しいユーザーポリシーを作成するには、[**新規**作成] をクリックし、[**ユーザーポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="584b0-129">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="584b0-130">[**新しい外部アクセスポリシー**] で、[**名前**] フィールドに、ユーザーポリシーがどのようなものであるかを示す一意の名前を作成します (たとえば、リモートユーザーの通信を有効にするユーザーポリシーの**EnableRemoteUsers** )。</span><span class="sxs-lookup"><span data-stu-id="584b0-130">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableRemoteUsers** for a user policy that enables communications for remote users).</span></span>
    
      - <span data-ttu-id="584b0-131">既存のポリシーを変更するには、表に記載されている適切なポリシーをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="584b0-131">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="584b0-132">省略説明を追加または編集する場合は、ポリシーの情報を [**説明**] で指定します。</span><span class="sxs-lookup"><span data-stu-id="584b0-132">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="584b0-133">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="584b0-133">Do one of the following:</span></span>
    
      - <span data-ttu-id="584b0-134">ポリシーのリモートユーザーアクセスを有効にするには、[**リモートユーザーとの通信を有効**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="584b0-134">To enable remote user access for the policy, select the **Enable communications with remote users** check box.</span></span>
    
      - <span data-ttu-id="584b0-135">ポリシーのリモートユーザーアクセスを無効にするには、[**リモートユーザーとの通信を有効に**する] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="584b0-135">To disable remote user access for the policy, clear the **Enable communications with remote users** check box.</span></span>

7.  <span data-ttu-id="584b0-136">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="584b0-136">Click **Commit**.</span></span>

<span data-ttu-id="584b0-137">リモートユーザーアクセスを有効にするには、組織内のリモートユーザーアクセスのサポートも有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="584b0-137">To enable remote user access, you must also enable support for remote user access in your organization.</span></span> <span data-ttu-id="584b0-138">詳細については、展開ドキュメントまたは運用マニュアルの「 [Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="584b0-138">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="584b0-139">ユーザーポリシーの場合は、リモートで接続できるようにするユーザーにもポリシーを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="584b0-139">If this is a user policy, you must also apply the policy to users that you want to be able to connect remotely.</span></span> <span data-ttu-id="584b0-140">詳細については、「展開ドキュメントまたは運用ドキュメントの[Lync Server 2013 で lync を有効にしたユーザーに外部ユーザーアクセスポリシーを割り当てる](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="584b0-140">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

