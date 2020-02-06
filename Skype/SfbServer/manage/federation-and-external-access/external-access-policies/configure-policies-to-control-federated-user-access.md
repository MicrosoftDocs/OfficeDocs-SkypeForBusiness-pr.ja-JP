---
title: フェデレーション ユーザー アクセスを制御するポリシーの構成
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'フェデレーションパートナーとの通信をサポートするようにポリシーを構成すると、フェデレーションドメインのユーザーにポリシーが適用されます。 '
ms.openlocfilehash: 2e9385436427fd73f90e308d7747cf304bf37501
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818318"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a><span data-ttu-id="b4c4d-103">Skype for Business Server でフェデレーションされたユーザーアクセスを制御するためのポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="b4c4d-103">Configure policies to control federated user access in Skype for Business Server</span></span>

<span data-ttu-id="b4c4d-104">フェデレーションパートナーとの通信をサポートするようにポリシーを構成すると、フェデレーションドメインのユーザーにポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="b4c4d-105">フェデレーションドメインのユーザーが Skype for Business Server ユーザーと共同作業できるかどうかを制御するために、1つ以上の外部ユーザーアクセスポリシーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Skype for Business Server users.</span></span> <span data-ttu-id="b4c4d-106">フェデレーションされたユーザーアクセスを制御するには、グローバル、サイト、ユーザーレベルでポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="b4c4d-107">1つのポリシーレベルで適用される Skype for Business Server のポリシー設定は、別のポリシーレベルで適用されている設定を上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-107">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="b4c4d-108">Skype for Business Server のポリシーの優先順位: ユーザーポリシー (ほとんどの影響) でサイトポリシーが上書きされ、サイトポリシーがグローバルポリシーを上書きします (最も影響が少なくなります)。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-108">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="b4c4d-109">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


> [!NOTE]  
> <span data-ttu-id="b4c4d-110">組織でフェデレーションを有効にしていない場合でも、フェデレーションされたユーザーアクセスを制御するためのポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="b4c4d-111">ただし、構成したポリシーは、組織でフェデレーションが有効になっている場合にのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="b4c4d-112">フェデレーションを有効にする方法について詳しくは、「[リモートユーザーアクセスを有効または無効](../access-edge/enable-or-disable-remote-user-access.md)にする」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-112">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>  <span data-ttu-id="b4c4d-113">また、フェデレーションされたユーザーアクセスを制御するユーザーポリシーを指定した場合、このポリシーは、Skype for Business Server が有効になっていて、ポリシーを使用するように構成されているユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span>


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="b4c4d-114">フェデレーションドメインのユーザーによるアクセスをサポートするようにポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="b4c4d-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="b4c4d-115">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b4c4d-116">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-116">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="b4c4d-117">左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**外部アクセスポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-117">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="b4c4d-118">[**外部アクセスポリシー** ] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-118">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="b4c4d-119">フェデレーションされたユーザーアクセスをサポートするようにグローバルポリシーを構成するには、グローバルポリシーをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-119">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="b4c4d-120">新しいサイトポリシーを作成するには、[**新規**作成] をクリックし、[**サイトポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-120">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="b4c4d-121">[**サイトの選択**] で、一覧から該当するサイトをクリックし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-121">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="b4c4d-122">新しいユーザーポリシーを作成するには、[**新規**作成] をクリックし、[**ユーザーポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-122">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="b4c4d-123">[**新しい外部アクセスポリシー**] で、[**名前**] フィールドに、ユーザーポリシーがどのようなものであるかを示す一意の名前を作成します (たとえば、フェデレーションされたドメインユーザーの通信を有効にするユーザーポリシーの**EnableFederatedUsers** )。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-123">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="b4c4d-124">既存のポリシーを変更するには、表に記載されている適切なポリシーをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-124">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="b4c4d-125">省略説明を追加または編集する場合は、ポリシーの情報を [**説明**] で指定します。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-125">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="b4c4d-126">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-126">Do one of the following:</span></span>
    
      - <span data-ttu-id="b4c4d-127">ポリシーのフェデレーションされたユーザーアクセスを有効にするには、[**フェデレーションユーザーとの通信を有効**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-127">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="b4c4d-128">ポリシーのフェデレーションされたユーザーアクセスを無効にするには、[フェデレーションされ**たユーザーとの通信を有効**にする] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-128">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="b4c4d-129">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-129">Click **Commit**.</span></span>

<span data-ttu-id="b4c4d-130">フェデレーションされたユーザーアクセスを有効にするには、組織のフェデレーションのサポートも有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-130">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="b4c4d-131">詳細について[は、「フェデレーションとパブリック IM 接続を有効または無効](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-131">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="b4c4d-132">ユーザーポリシーの場合は、フェデレーションされたユーザーと共同作業できるようにするユーザーにもポリシーを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-132">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="b4c4d-133">詳細については、「[外部ユーザーアクセスポリシーを割り当てる](assign-an-external-user-access-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-133">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="b4c4d-134">Windows PowerShell を使用して既存のポリシーを構成し、フェデレーションドメインのユーザーによるアクセスをサポートするには</span><span class="sxs-lookup"><span data-stu-id="b4c4d-134">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="b4c4d-135">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b4c4d-136">Skype for Busines Server Management Shell を起動します。 [**スタート**]、[**すべてのプログラム**] の順にクリックし、[ **skype for business server**] をクリックして、[ **skype for business server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-136">Start the Skype for Busines Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="b4c4d-137">Skype for Business Server 管理シェルで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-137">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > <span data-ttu-id="b4c4d-138">Skype for Business Server コントロールパネルで、"EnablePublicCloudAudioVideoAccess" のパラメーターに対応する項目が選択されていません</span><span class="sxs-lookup"><span data-stu-id="b4c4d-138">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Skype for Business Server Control Panel</span></span>


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="b4c4d-139">フェデレーションドメインのユーザーによるアクセスをサポートするために、Windows PowerShell を使用して新しいポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="b4c4d-139">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="b4c4d-140">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b4c4d-141">Skype for Business Server 管理シェルを開始します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft skype for Business server**]、[ **skype for business server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="b4c4d-142">Skype for Business Server 管理シェルで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-142">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    <span data-ttu-id="b4c4d-143">新しいサイトポリシーを作成する例:</span><span class="sxs-lookup"><span data-stu-id="b4c4d-143">An example of creating a new site policy:</span></span>
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="b4c4d-144">フェデレーションドメインのユーザーによるアクセスをサポートするために Windows PowerShell を使用してポリシーを削除またはリセットするには</span><span class="sxs-lookup"><span data-stu-id="b4c4d-144">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="b4c4d-145">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b4c4d-146">Skype for Business Server 管理シェルで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-146">Type the following in the Skype for Business Server Management Shell</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    <span data-ttu-id="b4c4d-147">グローバルポリシーをリセットする例です (グローバルポリシーではその設定のみを削除できます)。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-147">An example of resetting the global policy (The global policy can only have its setting removed.</span></span> <span data-ttu-id="b4c4d-148">ポリシーは削除できません):</span><span class="sxs-lookup"><span data-stu-id="b4c4d-148">The policy cannot be deleted):</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    <span data-ttu-id="b4c4d-149">サイトポリシーを削除するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-149">To remove a site policy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    <span data-ttu-id="b4c4d-150">サイトポリシーレドモンドを削除します。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-150">Deletes the site policy Redmond.</span></span> <span data-ttu-id="b4c4d-151">UserEAPPolicy という名前のユーザーポリシーを削除するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b4c4d-151">To delete a user policy named UserEAPPolicy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a><span data-ttu-id="b4c4d-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4c4d-152">See Also</span></span>


[<span data-ttu-id="b4c4d-153">フェデレーションおよびパブリック IM 接続の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="b4c4d-153">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[<span data-ttu-id="b4c4d-154">外部ユーザー アクセス ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="b4c4d-154">Assign an external user access policy</span></span>](assign-an-external-user-access-policy.md)

[<span data-ttu-id="b4c4d-155">組織の SIP フェデレーション ドメインの管理</span><span class="sxs-lookup"><span data-stu-id="b4c4d-155">Manage SIP federated domains for your organization</span></span>](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[<span data-ttu-id="b4c4d-156">組織の SIP フェデレーション プロバイダーの管理</span><span class="sxs-lookup"><span data-stu-id="b4c4d-156">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[<span data-ttu-id="b4c4d-157">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="b4c4d-157">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="b4c4d-158">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="b4c4d-158">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="b4c4d-159">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="b4c4d-159">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="b4c4d-160">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="b4c4d-160">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="b4c4d-161">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="b4c4d-161">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

