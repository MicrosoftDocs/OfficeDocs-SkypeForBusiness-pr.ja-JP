---
title: 'Lync Server 2013: XMPP フェデレーション ユーザー アクセスを制御するポリシーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control XMPP federated user access
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552446(v=OCS.15)
ms:contentKeyID: 48679557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc79a915d0735f87c0852dff0ba4228b1e391fd8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="5d235-102">Lync Server 2013 での XMPP フェデレーション ユーザー アクセスを制御するポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="5d235-102">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d235-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5d235-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5d235-104">このドキュメントは暫定版であり、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5d235-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="5d235-105">空白のトピックがプレースホルダーとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="5d235-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="5d235-106">拡張メッセージングとプレゼンスプロトコル (XMPP) フェデレーションパートナーをサポートするためにポリシーを構成すると、そのポリシーは XMPP フェデレーションドメインのユーザーに適用されますが、セッション開始プロトコル (SIP) のインスタントメッセージング (IM) サービスプロバイダーのユーザーには適用されません。(たとえば、Windows Live など)、または SIP フェデレーションドメイン。</span><span class="sxs-lookup"><span data-stu-id="5d235-106">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="5d235-107">ユーザーが連絡先を追加して通信できるようにする、各 XMPP フェデレーションドメインに対して**Xmpp フェデレーションパートナー**を構成します。</span><span class="sxs-lookup"><span data-stu-id="5d235-107">You configure an **XMPP Federated Partner** for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="5d235-108">XMPP フェデレーションパートナーのポリシーは1つのスコープでのみ使用できますが、グローバルポリシーとして定義されていませんが、グローバルポリシーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="5d235-108">XMPP federated partners policies are only available in a single scope, though it is not defined as a global policy, acts as a global policy.</span></span> <span data-ttu-id="5d235-109">XMPP フェデレーションパートナー用のグローバル、サイト、またはユーザーのポリシーを定義するには、まず、必要なスコープの外部アクセスポリシーを作成して構成することによって、ポリシーのスコープを構成します。</span><span class="sxs-lookup"><span data-stu-id="5d235-109">To define a global, site or user policy for XMPP Federation Partners, you configure the policy scope by first creating and configuring the External Access Policy for the scope you require.</span></span> <span data-ttu-id="5d235-110">外部アクセスとフェデレーションに対して構成できるポリシーの種類の詳細については、操作のドキュメントで「 [Lync Server 2013 へのフェデレーションと外部アクセスを管理する](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d235-110">For details about the types of policies that you can configure for external access and federation, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5d235-111">すべての<STRONG>フェデレーションと外部アクセス</STRONG>ポリシーは、インバンドプロビジョニングによって適用されます。</span><span class="sxs-lookup"><span data-stu-id="5d235-111">All <STRONG>Federation and External Access</STRONG> policies are applied through in-band provisioning.</span></span> <span data-ttu-id="5d235-112">ユーザーに適用されるポリシー、サイトに属しているポリシー、またはスコープ内のグローバルのポリシーは、ログイン時にクライアントに伝達されます。</span><span class="sxs-lookup"><span data-stu-id="5d235-112">The policies that apply to the user, belong to a site, or are global in scope are communicated to the client during login.</span></span> <span data-ttu-id="5d235-113">組織に対して XMPP フェデレーションを有効にしていない場合でも、ポリシーを構成して XMPP フェデレーションパートナーアクセスを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="5d235-113">You can configure policies to control XMPP federated partner access, even if you have not enabled XMPP federation for your organization.</span></span> <span data-ttu-id="5d235-114">ただし、構成したポリシーは、XMPP パートナーフェデレーションが展開されていて、有効になっており、組織で構成されている場合にのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="5d235-114">However, the policies that you configure take effect only when you have XMPP partner federation deployed, enabled and configured for your organization.</span></span> <span data-ttu-id="5d235-115">XMPP パートナーフェデレーションの展開と構成の詳細については、展開ドキュメントの「 <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Lync Server 2013 で SIP フェデレーション、XMPP フェデレーションおよびパブリックインスタントメッセージングを構成する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d235-115">For details about deploying and configuring XMPP partner federation, see <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="5d235-116">さらに、外部アクセスポリシーのユーザーポリシーを指定して XMPP フェデレーションパートナーを制御している場合、ポリシーは Lync Server 2013 で有効になっていて、ポリシーを使用するように構成されているユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="5d235-116">Additionally, if you specify a user policy in External Access Policy to control XMPP federated partners, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a><span data-ttu-id="5d235-117">XMPP フェデレーションパートナーのグローバルポリシーを編集するには</span><span class="sxs-lookup"><span data-stu-id="5d235-117">To edit a global policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="5d235-118">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5d235-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5d235-119">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5d235-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5d235-120">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5d235-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5d235-121">左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**外部アクセスポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d235-121">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="5d235-122">[**外部アクセスポリシー** ] ページで、グローバルポリシーに対して次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5d235-122">On the **External Access Policy** page, do the following for the global policy:</span></span>

5.  <span data-ttu-id="5d235-123">グローバルポリシーをクリックし、[**編集**] をクリックして、[詳細の表示] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d235-123">Click the global policy, click **Edit**, and then click Show details.</span></span>

6.  <span data-ttu-id="5d235-124">グローバルポリシーの説明を入力します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="5d235-124">Provide a description for the Global policy (optional).</span></span>

7.  <span data-ttu-id="5d235-125">[**フェデレーションユーザーとの通信を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d235-125">Select **Enable communications with federated users**.</span></span>

8.  <span data-ttu-id="5d235-126">[ **XMPP フェデレーションユーザーとの通信を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d235-126">Select **Enable communications with XMPP federated users**.</span></span>

9.  <span data-ttu-id="5d235-127">[**コミット**] をクリックして、変更内容をグローバルポリシーに保存します。</span><span class="sxs-lookup"><span data-stu-id="5d235-127">Click **Commit** to save your changes to the Global policy.</span></span>

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a><span data-ttu-id="5d235-128">XMPP フェデレーションパートナーのサイトまたはユーザーポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="5d235-128">To create a site or user policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="5d235-129">[**新規作成**] をクリックし、[**サイトポリシー** ] または [**ユーザーポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d235-129">Click **New**, and then click **Site policy** or **User policy**.</span></span> <span data-ttu-id="5d235-130">[**サイトの選択**] で、一覧から該当するサイトをクリックし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d235-130">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>

2.  <span data-ttu-id="5d235-131">サイトポリシーの説明を入力します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="5d235-131">Provide a description for the Site policy (optional).</span></span>

3.  <span data-ttu-id="5d235-132">サイトまたはユーザーポリシーで、[**フェデレーションされたユーザーとの通信を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d235-132">In the site or user policy, select **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="5d235-133">[ **XMPP フェデレーションユーザーとの通信を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d235-133">Select **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="5d235-134">[**コミット**] をクリックして、サイトまたはユーザーポリシーの変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="5d235-134">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a><span data-ttu-id="5d235-135">XMPP フェデレーションパートナーの既存のポリシーを編集するには</span><span class="sxs-lookup"><span data-stu-id="5d235-135">To edit an existing policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="5d235-136">既存のポリシーを変更するには、一覧で適切なポリシーを選択し、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d235-136">To change an existing policy, select the appropriate policy in the list, click **Edit**, and then click **Show details**.</span></span>

2.  <span data-ttu-id="5d235-137">ポリシーの説明を変更または更新します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="5d235-137">Change or update the description for the policy (optional).</span></span>

3.  <span data-ttu-id="5d235-138">[**フェデレーションユーザーとの通信を有効にする**] をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="5d235-138">Select or unselect **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="5d235-139">[ **XMPP フェデレーションユーザーとの通信を有効にする**] をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="5d235-139">Select or unselect **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="5d235-140">[**コミット**] をクリックして、変更内容をポリシーに保存します。</span><span class="sxs-lookup"><span data-stu-id="5d235-140">Click **Commit** to save your changes to the policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="5d235-141">Windows PowerShell を使用して XMPP フェデレーションパートナーの既存のポリシーを編集するには</span><span class="sxs-lookup"><span data-stu-id="5d235-141">To edit an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="5d235-142">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5d235-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5d235-143">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d235-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5d235-144">Lync Server 管理シェルで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5d235-144">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="5d235-145">フェデレーションされたユーザーアクセスのグローバルポリシーを True (有効) と XMPP ドメインアクセスの True (有効) に設定するコマンドの例です。</span><span class="sxs-lookup"><span data-stu-id="5d235-145">An example command that will set the global policy for Federated user access to True (enabled) and XMPP domain access to True (enabled):</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a><span data-ttu-id="5d235-146">Windows PowerShell を使用して XMPP フェデレーションパートナー用のサイトまたはユーザーポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="5d235-146">To create a site or user policy for XMPP federated partners using Windows PowerShell</span></span>

1.  <span data-ttu-id="5d235-147">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5d235-147">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5d235-148">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d235-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5d235-149">Lync Server 管理シェルで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5d235-149">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="5d235-150">フェデレーションされたユーザーアクセスを有効にして、XMPP ドメインアクセスを有効にするために Redmond サイトのサイトポリシーを設定するコマンドの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5d235-150">An example command that will set a site policy for the Redmond site for Federated user access to enabled and XMPP domain access to enabled:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="5d235-151">Windows PowerShell を使用して XMPP フェデレーションパートナーの既存のポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="5d235-151">To delete an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="5d235-152">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5d235-152">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5d235-153">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d235-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5d235-154">Lync Server 管理シェルで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5d235-154">Type the following in the Lync Server Management Shell:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    <span data-ttu-id="5d235-155">ユーザーポリシーを削除するコマンドの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5d235-155">An example command that will delete a user policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  <span data-ttu-id="5d235-156">グローバルポリシーを既定値にリセットするコマンドの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5d235-156">An example command that will reset the global policy to defaults:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5d235-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d235-157">See Also</span></span>


[<span data-ttu-id="5d235-158">Lync Server 2013 での Lync が有効なユーザーに対する外部ユーザー アクセス ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="5d235-158">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[<span data-ttu-id="5d235-159">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="5d235-159">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[<span data-ttu-id="5d235-160">Lync Server 2013 での組織の XMPP フェデレーション パートナーの管理</span><span class="sxs-lookup"><span data-stu-id="5d235-160">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[<span data-ttu-id="5d235-161">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="5d235-161">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="5d235-162">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="5d235-162">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="5d235-163">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="5d235-163">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="5d235-164">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="5d235-164">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="5d235-165">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="5d235-165">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

