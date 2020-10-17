---
title: 'Lync Server 2013: リモートユーザーアクセスを制御するポリシーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a195a0bbca8bdfcc0b150504635d3f86cca376c3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527014"
---
# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="c42eb-102">Lync Server 2013 でのリモートユーザーアクセスを制御するポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="c42eb-102">Configure policies to control remote user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c42eb-103">_**トピックの最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="c42eb-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="c42eb-104">1つ以上の外部ユーザーアクセスポリシーを構成して、リモートユーザーが内部の Lync Server ユーザーと共同作業できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="c42eb-104">You configure one or more external user access policies to control whether remote users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="c42eb-105">リモート ユーザー アクセスを管理するため、グローバル、サイト、およびユーザー レベルでポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c42eb-105">To control remote user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="c42eb-106">サイト ポリシーはグローバル ポリシーより優先され、ユーザー ポリシーはサイト ポリシーとグローバル ポリシーより優先されます。</span><span class="sxs-lookup"><span data-stu-id="c42eb-106">Site policies override the global policy, and user policies override site and global policies.</span></span> <span data-ttu-id="c42eb-107">構成できるポリシーの種類の詳細については、「 [Lync Server 2013 へのフェデレーションと外部アクセスの管理](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c42eb-107">For details about the types of policies that you can configure, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span> <span data-ttu-id="c42eb-108">あるポリシー レベルで適用されている Lync Server ポリシー設定が、他のポリシー レベルで適用されている設定によって無効になることがあります。</span><span class="sxs-lookup"><span data-stu-id="c42eb-108">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="c42eb-109">Lync Server ポリシーの優先順位は、ユーザー ポリシーが最も高く、サイト ポリシー、グローバル ポリシー (優先度が最も低い) と続きます。</span><span class="sxs-lookup"><span data-stu-id="c42eb-109">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="c42eb-110">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="c42eb-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c42eb-111">組織のリモート ユーザー アクセスを有効にしていない場合でも、リモート ユーザー アクセスを制御するポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c42eb-111">You can configure policies to control remote user access, even if you have not enabled remote user access for your organization.</span></span> <span data-ttu-id="c42eb-112">ただし、構成したポリシーは、組織のリモート ユーザー アクセスを有効にしているときのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="c42eb-112">However, the policies that you configure are in effect only when you have remote user access enabled for your organization.</span></span> <span data-ttu-id="c42eb-113">リモートユーザーアクセスの有効化の詳細については、「 <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 のフェデレーションとパブリック IM 接続を有効または無効</A>にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c42eb-113">For details about enabling remote user access, see <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</A>.</span></span> <span data-ttu-id="c42eb-114">また、リモートユーザーアクセスを制御するユーザーポリシーを指定した場合、このポリシーは、Lync Server が有効になっていて、そのポリシーを使用するように構成されているユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c42eb-114">Additionally, if you specify a user policy to control remote user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="c42eb-115">リモートの場所から Lync Server にサインインできるユーザーの指定の詳細については、「 <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Lync server 2013 で lync が有効なユーザーへの外部ユーザーアクセスポリシーの割り当て</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c42eb-115">For details about specifying users that can sign in to Lync Server from remote locations, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="c42eb-116">リモート ユーザー アクセスの制御に使用する各外部アクセス ポリシーを構成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c42eb-116">Use the following procedure to configure each external access policy that you want to use to control remote user access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c42eb-117">この手順で説明するのは、リモート ユーザーとの通信を有効にするだけのポリシーを構成する方法ですが、リモート ユーザー アクセスをサポートするため構成する各ポリシーで、フェデレーション ユーザー アクセスやパブリック ユーザー アクセスも構成できます。</span><span class="sxs-lookup"><span data-stu-id="c42eb-117">This procedure describes how to configure a policy only to enable communications with remote users, but each policy that you configure to support remote user access can also configure federated user access and public user access.</span></span> <span data-ttu-id="c42eb-118">フェデレーションユーザーをサポートするようにポリシーを構成する方法の詳細については、「 <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013 でフェデレーションユーザーアクセスを制御するようにポリシーを構成する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c42eb-118">For details about configuring policies to support federated users, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="c42eb-119">パブリックユーザーをサポートするためのポリシーの構成の詳細については、「 <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Lync Server 2013 でのパブリック SIP フェデレーションプロバイダーの作成または編集</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c42eb-119">For details about configuring policies to support public users, see <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a><span data-ttu-id="c42eb-120">リモート ユーザー アクセスをサポートする外部アクセス ポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="c42eb-120">To configure an external access policy to support remote user access</span></span>

1.  <span data-ttu-id="c42eb-121">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c42eb-121">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c42eb-122">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c42eb-122">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c42eb-123">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c42eb-123">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c42eb-124">左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c42eb-124">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="c42eb-125">[**外部アクセス ポリシー**] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c42eb-125">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="c42eb-126">リモート ユーザー アクセスをサポートするグローバル ポリシーを構成するには、グローバル ポリシーをクリックして [**編集**] をクリックし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c42eb-126">To configure the global policy to support remote user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="c42eb-p105">新しいサイト ポリシーを作成するには、[**新規作成**] をクリックし、[**サイト ポリシー**] をクリックします。 [**サイトの選択**] で一覧から適切なサイトをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c42eb-p105">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="c42eb-p106">新しいユーザー ポリシーを作成するには、[**新規作成**] をクリックし、[**ユーザー ポリシー**] をクリックします。 [**新しい外部アクセス ポリシー**] の [**名前**] フィールドに、ユーザー ポリシーの範囲を示す一意の名前を作成します (リモート ユーザーの通信を有効にするユーザー ポリシーの場合は **EnableRemoteUsers** など)。</span><span class="sxs-lookup"><span data-stu-id="c42eb-p106">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableRemoteUsers** for a user policy that enables communications for remote users).</span></span>
    
      - <span data-ttu-id="c42eb-131">既存のポリシーを変更するには、表に表示されている適切なポリシーをクリックし、[**編集**] に続いて [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c42eb-131">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="c42eb-132">(オプション) 説明を追加または編集する場合は、[**説明**] でポリシーの情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="c42eb-132">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="c42eb-133">次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c42eb-133">Do one of the following:</span></span>
    
      - <span data-ttu-id="c42eb-134">ポリシーのリモート ユーザー アクセスを有効にするには、[**リモート ユーザーとの通信を有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c42eb-134">To enable remote user access for the policy, select the **Enable communications with remote users** check box.</span></span>
    
      - <span data-ttu-id="c42eb-135">ポリシーのリモート ユーザー アクセスを無効にするには、[**リモート ユーザーとの通信を有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="c42eb-135">To disable remote user access for the policy, clear the **Enable communications with remote users** check box.</span></span>

7.  <span data-ttu-id="c42eb-136">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c42eb-136">Click **Commit**.</span></span>

<span data-ttu-id="c42eb-137">リモート ユーザー アクセスを有効にするには、組織のリモート ユーザー アクセスのサポートも有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c42eb-137">To enable remote user access, you must also enable support for remote user access in your organization.</span></span> <span data-ttu-id="c42eb-138">詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 [Lync Server 2013 でのフェデレーションとパブリック IM 接続の有効化または無効化](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c42eb-138">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="c42eb-139">これがユーザー ポリシーである場合は、リモート接続を許可するユーザーにポリシーを適用する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="c42eb-139">If this is a user policy, you must also apply the policy to users that you want to be able to connect remotely.</span></span> <span data-ttu-id="c42eb-140">詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「lync [Server 2013 での lync が有効なユーザーへの外部ユーザーアクセスポリシーの割り当て](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c42eb-140">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

