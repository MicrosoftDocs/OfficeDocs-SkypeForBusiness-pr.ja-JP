---
title: フェデレーション ユーザー アクセスを制御するポリシーの構成
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'フェデレーション パートナーとの通信をサポートするためのポリシーを構成すると、そのポリシーはフェデレーション ドメインのユーザーに適用されます。 '
ms.openlocfilehash: 6107615767d0360180baf9f22d5fddc6a5f8e565
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099043"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a><span data-ttu-id="6438b-103">Skype for Business Server でフェデレーション ユーザー アクセスを制御するポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="6438b-103">Configure policies to control federated user access in Skype for Business Server</span></span>

<span data-ttu-id="6438b-104">フェデレーション パートナーとの通信をサポートするためのポリシーを構成すると、そのポリシーはフェデレーション ドメインのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="6438b-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="6438b-105">1 つ以上の外部ユーザー アクセス ポリシーを構成して、フェデレーション ドメインのユーザーが Skype for Business Server ユーザーと共同作業できるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="6438b-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Skype for Business Server users.</span></span> <span data-ttu-id="6438b-106">フェデレーション ユーザー アクセスを制御するために、グローバル レベル、サイト レベル、およびユーザー レベルでポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="6438b-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="6438b-107">1 つのポリシー レベルで適用される Skype for Business Server ポリシー設定は、別のポリシー レベルで適用される設定を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="6438b-107">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="6438b-108">Skype for Business Server ポリシーの優先順位: ユーザー ポリシー (最も高い) はサイト ポリシーをオーバーライドし、サイト ポリシーはグローバル ポリシーをオーバーライド (最も低い) します。</span><span class="sxs-lookup"><span data-stu-id="6438b-108">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="6438b-109">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="6438b-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


> [!NOTE]  
> <span data-ttu-id="6438b-110">組織でフェデレーションを有効にしていなくても、フェデレーション ユーザー アクセスを制御するポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="6438b-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="6438b-111">ただし、構成したポリシーは、組織でフェデレーションを有効にした場合にのみ有効となります。</span><span class="sxs-lookup"><span data-stu-id="6438b-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="6438b-112">フェデレーションの有効化の詳細については、「リモート ユーザー アクセス [を有効または無効にする」を参照してください](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="6438b-112">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>  <span data-ttu-id="6438b-113">さらに、フェデレーション ユーザー アクセスを制御するユーザー ポリシーを指定した場合、ポリシーは、Skype for Business Server で有効にされ、ポリシーを使用するように構成されているユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="6438b-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span>


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="6438b-114">フェデレーション ドメインのユーザーによるアクセスをサポートするためのポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="6438b-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="6438b-115">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6438b-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6438b-116">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6438b-116">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="6438b-117">左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6438b-117">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="6438b-118">[**外部アクセス ポリシー**] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6438b-118">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="6438b-119">フェデレーション ユーザー アクセスをサポートするようにグローバル ポリシーを構成するには、グローバル ポリシーをクリックし、[**編集**] に続いて [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6438b-119">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="6438b-p103">新しいサイト ポリシーを作成するには、[**新規作成**] をクリックし、[**サイト ポリシー**] をクリックします。 [**サイトの選択**] で一覧から適切なサイトをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6438b-p103">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="6438b-p104">新しいユーザー ポリシーを作成するには、[**新規作成**] をクリックし、[**ユーザー ポリシー**] をクリックします。 [**新しい外部アクセス ポリシー**] の [**名前**] フィールドで、ユーザー ポリシーの適用範囲を示す一意の名前を作成します (たとえば、フェデレーション ドメイン ユーザーの通信を有効にするユーザー ポリシーの場合、**EnableFederatedUsers** という名前を作成します)。</span><span class="sxs-lookup"><span data-stu-id="6438b-p104">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="6438b-124">既存のポリシーを変更するには、表に表示されている適切なポリシーをクリックし、[**編集**] に続いて [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6438b-124">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="6438b-125">(オプション) 説明を追加または編集する場合は、[**説明**] でポリシーの情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="6438b-125">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="6438b-126">次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6438b-126">Do one of the following:</span></span>
    
      - <span data-ttu-id="6438b-127">ポリシーのフェデレーション ユーザー アクセスを有効にするには、[**フェデレーション ユーザーとの通信を有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6438b-127">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="6438b-128">ポリシーのフェデレーション ユーザー アクセスを無効にするには、[**フェデレーション ユーザーとの通信を有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="6438b-128">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="6438b-129">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6438b-129">Click **Commit**.</span></span>

<span data-ttu-id="6438b-130">フェデレーション ユーザー アクセスを有効にするには、組織でフェデレーションのサポートも有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6438b-130">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="6438b-131">詳細については、「フェデレーションと [パブリック IM 接続を有効または無効にする」を参照してください](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="6438b-131">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="6438b-132">ユーザー ポリシーの場合、フェデレーション ユーザーと共同作業できるようにするユーザーにもポリシーを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6438b-132">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="6438b-133">詳細については、「外部ユーザー アクセス [ポリシーの割り当て」を参照してください](assign-an-external-user-access-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="6438b-133">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="6438b-134">フェデレーション ドメインのユーザーによるアクセスをWindows PowerShellを使用して既存のポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="6438b-134">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="6438b-135">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6438b-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6438b-136">Skype for Busines Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business Server]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6438b-136">Start the Skype for Busines Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="6438b-137">Skype for Business Server 管理シェルに次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="6438b-137">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > <span data-ttu-id="6438b-138">パラメーター "EnablePublicCloudAudioVideoAccess" は、Skype for Business Server コントロール パネルで対応する選択項目を持つ</span><span class="sxs-lookup"><span data-stu-id="6438b-138">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Skype for Business Server Control Panel</span></span>


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="6438b-139">フェデレーション ドメインのユーザーによるアクセスをWindows PowerShellを使用して新しいポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="6438b-139">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="6438b-140">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6438b-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6438b-141">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Microsoft Skype for Business Server]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6438b-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="6438b-142">Skype for Business Server 管理シェルに次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="6438b-142">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    <span data-ttu-id="6438b-143">新しいサイト ポリシーを作成する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6438b-143">An example of creating a new site policy:</span></span>
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="6438b-144">フェデレーション ドメインのユーザーによるアクセスをサポートWindows PowerShellを使用してポリシーを削除またはリセットするには</span><span class="sxs-lookup"><span data-stu-id="6438b-144">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="6438b-145">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6438b-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6438b-146">Skype for Business Server 管理シェルに次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="6438b-146">Type the following in the Skype for Business Server Management Shell</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    <span data-ttu-id="6438b-p107">グローバル ポリシーをリセットする例を次に示します (グローバル ポリシーは設定のみを削除できます。ポリシー自体を削除することはできません)。</span><span class="sxs-lookup"><span data-stu-id="6438b-p107">An example of resetting the global policy (The global policy can only have its setting removed. The policy cannot be deleted):</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    <span data-ttu-id="6438b-149">サイト ポリシーを削除するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="6438b-149">To remove a site policy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    <span data-ttu-id="6438b-150">Redmond というサイト ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="6438b-150">Deletes the site policy Redmond.</span></span> <span data-ttu-id="6438b-151">UserEAPPolicy というユーザー ポリシーを削除するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="6438b-151">To delete a user policy named UserEAPPolicy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a><span data-ttu-id="6438b-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="6438b-152">See Also</span></span>


[<span data-ttu-id="6438b-153">フェデレーションおよびパブリック IM 接続の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="6438b-153">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[<span data-ttu-id="6438b-154">外部ユーザー アクセス ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="6438b-154">Assign an external user access policy</span></span>](assign-an-external-user-access-policy.md)

[<span data-ttu-id="6438b-155">組織の SIP フェデレーション ドメインの管理</span><span class="sxs-lookup"><span data-stu-id="6438b-155">Manage SIP federated domains for your organization</span></span>](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[<span data-ttu-id="6438b-156">組織の SIP フェデレーション プロバイダーの管理</span><span class="sxs-lookup"><span data-stu-id="6438b-156">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[<span data-ttu-id="6438b-157">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="6438b-157">Set-CsExternalAccessPolicy</span></span>](/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="6438b-158">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="6438b-158">New-CsExternalAccessPolicy</span></span>](/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="6438b-159">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="6438b-159">Get-CsExternalAccessPolicy</span></span>](/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="6438b-160">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="6438b-160">Remove-CsExternalAccessPolicy</span></span>](/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="6438b-161">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="6438b-161">Grant-CsExternalAccessPolicy</span></span>](/powershell/module/skype/Grant-CsExternalAccessPolicy)  
