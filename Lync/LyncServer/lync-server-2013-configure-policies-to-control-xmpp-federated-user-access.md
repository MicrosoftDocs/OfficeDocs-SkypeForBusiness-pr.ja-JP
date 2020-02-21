---
title: 'Lync Server 2013: XMPP フェデレーションユーザーアクセスを制御するポリシーの構成'
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
ms.openlocfilehash: 31889fa60f86d269e5efab696c2c27e48cc55d59
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="67f0d-102">Lync Server 2013 での XMPP フェデレーションユーザーアクセスを制御するポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="67f0d-102">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67f0d-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="67f0d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="67f0d-104">このドキュメントは暫定版であり、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="67f0d-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="67f0d-105">空白のトピックがプレースホルダーとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="67f0d-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="67f0d-106">XMPP (eXtensible Messaging and Presence Protocol) フェデレーション パートナーをサポートするポリシーを構成すると、そのポリシーは XMPP フェデレーション ドメインのユーザーには適用されますが、SIP (セッション開始プロトコル) インスタント メッセージング (IM) サービス プロバイダー (Windows Live など) のユーザーや、SIP フェデレーション ドメインのユーザーには適用されません。</span><span class="sxs-lookup"><span data-stu-id="67f0d-106">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="67f0d-107">ユーザーが連絡先を追加して通信できるようにする XMPP フェデレーションドメインごとに**Xmpp フェデレーションパートナー**を構成します。</span><span class="sxs-lookup"><span data-stu-id="67f0d-107">You configure an **XMPP Federated Partner** for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="67f0d-108">XMPP フェデレーションパートナーポリシーは単一のスコープでのみ使用できますが、グローバルポリシーとして定義されていませんが、グローバルポリシーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="67f0d-108">XMPP federated partners policies are only available in a single scope, though it is not defined as a global policy, acts as a global policy.</span></span> <span data-ttu-id="67f0d-109">XMPP フェデレーションパートナーのグローバル、サイト、またはユーザーポリシーを定義するには、まず、必要なスコープの外部アクセスポリシーを作成して構成することによって、ポリシースコープを構成します。</span><span class="sxs-lookup"><span data-stu-id="67f0d-109">To define a global, site or user policy for XMPP Federation Partners, you configure the policy scope by first creating and configuring the External Access Policy for the scope you require.</span></span> <span data-ttu-id="67f0d-110">外部アクセスおよびフェデレーションに対して構成できるポリシーの種類の詳細については、「操作」のドキュメントの「[管理フェデレーション」および「Lync Server 2013 への外部アクセス」を](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="67f0d-110">For details about the types of policies that you can configure for external access and federation, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="67f0d-111"><STRONG>フェデレーションおよび外部アクセス</STRONG> ポリシーは、インバンド プロビジョニングを通じて適用されます。</span><span class="sxs-lookup"><span data-stu-id="67f0d-111">All <STRONG>Federation and External Access</STRONG> policies are applied through in-band provisioning.</span></span> <span data-ttu-id="67f0d-112">ユーザーに適用されるポリシー、サイトに所属するポリシー、またはスコープ内のグローバル ポリシーは、ログイン時にクライアントとの間でやり取りされます。</span><span class="sxs-lookup"><span data-stu-id="67f0d-112">The policies that apply to the user, belong to a site, or are global in scope are communicated to the client during login.</span></span> <span data-ttu-id="67f0d-113">組織で XMPP フェデレーションを有効にしていない場合でも、XMPP フェデレーション パートナーのアクセスを制御するポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="67f0d-113">You can configure policies to control XMPP federated partner access, even if you have not enabled XMPP federation for your organization.</span></span> <span data-ttu-id="67f0d-114">ただし、これらのポリシーが有効になるのは、組織に XMPP パートナー フェデレーションが展開、有効化、および構成されている場合に限られます。</span><span class="sxs-lookup"><span data-stu-id="67f0d-114">However, the policies that you configure take effect only when you have XMPP partner federation deployed, enabled and configured for your organization.</span></span> <span data-ttu-id="67f0d-115">XMPP パートナーフェデレーションの展開と構成の詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Lync Server 2013 での SIP フェデレーション、XMPP フェデレーションおよびパブリックインスタントメッセージングの構成</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67f0d-115">For details about deploying and configuring XMPP partner federation, see <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="67f0d-116">また、外部アクセスポリシーで XMPP フェデレーションパートナーを制御するユーザーポリシーを指定した場合、このポリシーは Lync Server 2013 が有効になっていて、そのポリシーを使用するように構成されているユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="67f0d-116">Additionally, if you specify a user policy in External Access Policy to control XMPP federated partners, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a><span data-ttu-id="67f0d-117">XMPP フェデレーション パートナーのグローバル ポリシーを編集するには</span><span class="sxs-lookup"><span data-stu-id="67f0d-117">To edit a global policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="67f0d-118">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="67f0d-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="67f0d-119">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="67f0d-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="67f0d-120">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67f0d-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="67f0d-121">左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67f0d-121">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="67f0d-122">[**外部アクセス ポリシー**] ページで、グローバル ポリシーに対して、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="67f0d-122">On the **External Access Policy** page, do the following for the global policy:</span></span>

5.  <span data-ttu-id="67f0d-123">グローバル ポリシーをクリックし、[**編集**] をクリックして、[詳細の表示] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67f0d-123">Click the global policy, click **Edit**, and then click Show details.</span></span>

6.  <span data-ttu-id="67f0d-124">グローバル ポリシーの説明を指定します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="67f0d-124">Provide a description for the Global policy (optional).</span></span>

7.  <span data-ttu-id="67f0d-125">[**フェデレーション ユーザーとの通信を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="67f0d-125">Select **Enable communications with federated users**.</span></span>

8.  <span data-ttu-id="67f0d-126">[**XMPP フェデレーション ユーザーとの通信を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="67f0d-126">Select **Enable communications with XMPP federated users**.</span></span>

9.  <span data-ttu-id="67f0d-127">[**コミット**] をクリックして、グローバル ポリシーに加えた変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="67f0d-127">Click **Commit** to save your changes to the Global policy.</span></span>

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a><span data-ttu-id="67f0d-128">XMPP フェデレーション パートナーのサイト ポリシーまたはユーザー ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="67f0d-128">To create a site or user policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="67f0d-p105">[**新規**] をクリックし、[**サイト ポリシー**] または [**ユーザー ポリシー**] をクリックします。[**サイトの選択**] で、一覧から適切なサイトをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67f0d-p105">Click **New**, and then click **Site policy** or **User policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>

2.  <span data-ttu-id="67f0d-131">サイト ポリシーの説明を指定します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="67f0d-131">Provide a description for the Site policy (optional).</span></span>

3.  <span data-ttu-id="67f0d-132">サイト ポリシーまたはユーザー ポリシーで、[**フェデレーション ユーザーとの通信を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="67f0d-132">In the site or user policy, select **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="67f0d-133">[**XMPP フェデレーション ユーザーとの通信を有効にする**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="67f0d-133">Select **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="67f0d-134">[**コミット**] をクリックして、サイト ポリシーまたはユーザー ポリシーに加えた変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="67f0d-134">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a><span data-ttu-id="67f0d-135">XMPP フェデレーション パートナーの既存のポリシーを編集するには</span><span class="sxs-lookup"><span data-stu-id="67f0d-135">To edit an existing policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="67f0d-136">既存のポリシーを変更するには、一覧から該当するポリシーを選択し、[**編集**]、[**詳細の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="67f0d-136">To change an existing policy, select the appropriate policy in the list, click **Edit**, and then click **Show details**.</span></span>

2.  <span data-ttu-id="67f0d-137">ポリシーの説明を変更または更新します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="67f0d-137">Change or update the description for the policy (optional).</span></span>

3.  <span data-ttu-id="67f0d-138">[**フェデレーション ユーザーとの通信を有効にする**] を選択または選択解除します。</span><span class="sxs-lookup"><span data-stu-id="67f0d-138">Select or unselect **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="67f0d-139">[**XMPP フェデレーション ユーザーとの通信を有効にする**] を選択または選択解除します。</span><span class="sxs-lookup"><span data-stu-id="67f0d-139">Select or unselect **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="67f0d-140">[**コミット**] をクリックして、ポリシーに加えた変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="67f0d-140">Click **Commit** to save your changes to the policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="67f0d-141">Windows PowerShell を使用して XMPP フェデレーションパートナーの既存のポリシーを編集するには</span><span class="sxs-lookup"><span data-stu-id="67f0d-141">To edit an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="67f0d-142">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="67f0d-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="67f0d-143">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="67f0d-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="67f0d-144">Lync Server 管理シェルで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="67f0d-144">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="67f0d-145">フェデレーションユーザーアクセスのグローバルポリシーを True (有効) に、XMPP ドメインアクセスを True (有効) に設定するコマンドの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="67f0d-145">An example command that will set the global policy for Federated user access to True (enabled) and XMPP domain access to True (enabled):</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a><span data-ttu-id="67f0d-146">Windows PowerShell を使用して XMPP フェデレーションパートナーのサイトポリシーまたはユーザーポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="67f0d-146">To create a site or user policy for XMPP federated partners using Windows PowerShell</span></span>

1.  <span data-ttu-id="67f0d-147">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="67f0d-147">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="67f0d-148">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="67f0d-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="67f0d-149">Lync Server 管理シェルで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="67f0d-149">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="67f0d-150">このサンプル コマンドは、フェデレーション ユーザーのアクセスと XMPP ドメインのアクセスに対して、サイト ポリシー (Redmond サイト用) をそれぞれ有効に設定します。</span><span class="sxs-lookup"><span data-stu-id="67f0d-150">An example command that will set a site policy for the Redmond site for Federated user access to enabled and XMPP domain access to enabled:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="67f0d-151">Windows PowerShell を使用して XMPP フェデレーションパートナーの既存のポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="67f0d-151">To delete an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="67f0d-152">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="67f0d-152">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="67f0d-153">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="67f0d-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="67f0d-154">Lync Server 管理シェルで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="67f0d-154">Type the following in the Lync Server Management Shell:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    <span data-ttu-id="67f0d-155">次のサンプル コマンドは、ユーザー ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="67f0d-155">An example command that will delete a user policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  <span data-ttu-id="67f0d-156">次のサンプル コマンドは、グローバル ポリシーを既定値にリセットします。</span><span class="sxs-lookup"><span data-stu-id="67f0d-156">An example command that will reset the global policy to defaults:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="67f0d-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="67f0d-157">See Also</span></span>


[<span data-ttu-id="67f0d-158">Lync Server 2013 での Lync が有効なユーザーへの外部ユーザーアクセスポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="67f0d-158">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[<span data-ttu-id="67f0d-159">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="67f0d-159">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[<span data-ttu-id="67f0d-160">Lync Server 2013 での XMPP フェデレーションパートナーの管理</span><span class="sxs-lookup"><span data-stu-id="67f0d-160">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[<span data-ttu-id="67f0d-161">Get-csexternalaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="67f0d-161">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="67f0d-162">Get-csexternalaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="67f0d-162">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="67f0d-163">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="67f0d-163">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="67f0d-164">Get-csexternalaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="67f0d-164">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="67f0d-165">Get-csexternalaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="67f0d-165">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

