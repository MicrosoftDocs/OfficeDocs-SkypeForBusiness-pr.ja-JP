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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'フェデレーション パートナーとの通信をサポートするためにポリシーを構成する場合は、フェデレーション ドメインのユーザーに、ポリシーが適用されます。 '
ms.openlocfilehash: 81eced8db10c9ffd017b5b79a54980b773b300bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920659"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a><span data-ttu-id="c3d54-103">ビジネス サーバーの Skype でフェデレーション ユーザー アクセスを制御するポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="c3d54-103">Configure policies to control federated user access in Skype for Business Server</span></span>

<span data-ttu-id="c3d54-104">フェデレーション パートナーとの通信をサポートするためにポリシーを構成する場合は、フェデレーション ドメインのユーザーに、ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="c3d54-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="c3d54-105">フェデレーション ドメインのユーザーがビジネス サーバーのユーザーは、Skype で共同作業を行うかどうかは、コントロールに 1 つまたは複数の外部ユーザー アクセス ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c3d54-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Skype for Business Server users.</span></span> <span data-ttu-id="c3d54-106">フェデレーション ユーザー アクセスを制御するには、グローバル ポリシー、サイト、およびユーザー レベルを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c3d54-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="c3d54-107">Skype ビジネスのサーバーのポリシー設定が 1 つのポリシー レベルで適用されるは、別のポリシー レベルで適用される設定をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="c3d54-107">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="c3d54-108">ビジネス サーバー ポリシーの優先順位の Skype が: ユーザー ポリシー (ほとんどの影響) がサイト ポリシーを上書きし、[サイト ポリシーはグローバル ポリシー (最低限の影響) をよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="c3d54-108">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="c3d54-109">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="c3d54-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


> [!NOTE]  
> <span data-ttu-id="c3d54-110">組織のフェデレーションが有効にしない場合でも、フェデレーション ユーザー アクセスを制御するポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c3d54-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="c3d54-111">ただし、構成したポリシーは、フェデレーションの組織に対して有効である場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="c3d54-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="c3d54-112">フェデレーションを有効にする方法の詳細[を有効にするかリモート ユーザー アクセスを無効にする](../access-edge/enable-or-disable-remote-user-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3d54-112">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>  <span data-ttu-id="c3d54-113">さらに、フェデレーション ユーザー アクセスを制御するユーザー ポリシーを指定する場合は、Skype のビジネス サーバー有効になって、ポリシーを使用するように構成されているユーザーにのみ、ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="c3d54-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span>


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="c3d54-114">フェデレーション ドメインのユーザーによるアクセスをサポートするためにポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="c3d54-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="c3d54-115">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c3d54-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c3d54-116">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="c3d54-116">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="c3d54-117">左側のナビゲーション ・ バーでは、**外部ユーザー アクセス**をクリックし、**外部アクセス ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3d54-117">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="c3d54-118">[**外部アクセス ポリシー** ] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c3d54-118">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="c3d54-119">フェデレーション ユーザー アクセスをサポートするグローバル ポリシーを構成するには、グローバル ポリシーをクリックして**編集**を**の詳細を表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3d54-119">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="c3d54-120">新しいサイト ポリシーを作成、[**新規**作成] をクリックし、[**サイト ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3d54-120">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="c3d54-121">] で**サイトを選択して**、リストから適切なサイトをし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3d54-121">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="c3d54-122">新しいユーザー ポリシーを作成するには、[**新規**作成] をクリックし、[**ユーザー ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3d54-122">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="c3d54-123">**新しい外部アクセス ポリシー**では、どのユーザー ポリシーは (たとえば、フェデレーション ドメインのユーザーの通信を有効にするユーザー ポリシーの**EnableFederatedUsers** ) を示す [**名**] フィールドに一意の名前を作成します。</span><span class="sxs-lookup"><span data-stu-id="c3d54-123">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="c3d54-124">既存のポリシーを変更するには、表に記載されている適切なポリシー] をクリック**を編集**するには、**の詳細を表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3d54-124">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="c3d54-125">(省略可能)追加または説明を編集する場合は、 **[説明**] にポリシーの情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="c3d54-125">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="c3d54-126">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c3d54-126">Do one of the following:</span></span>
    
      - <span data-ttu-id="c3d54-127">ポリシーのフェデレーション ユーザー アクセスを有効にするには、**フェデレーション ユーザーとの通信を有効にする**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="c3d54-127">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="c3d54-128">ポリシーのフェデレーション ユーザー アクセスを無効にするには、**フェデレーション ユーザーとの通信を有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="c3d54-128">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="c3d54-129">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3d54-129">Click **Commit**.</span></span>

<span data-ttu-id="c3d54-130">フェデレーション ユーザー アクセスを有効にするには、また組織でフェデレーションのサポートを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3d54-130">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="c3d54-131">詳細については、[有効にするかフェデレーションとパブリック IM 接続を無効にする](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3d54-131">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="c3d54-132">ユーザー ポリシーの場合は、フェデレーション ユーザーと共同作業を行うことができるようにするユーザーにポリシーを適用する必要がありますもします。</span><span class="sxs-lookup"><span data-stu-id="c3d54-132">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="c3d54-133">詳細については、[外部ユーザー アクセス ポリシーを割り当てる](assign-an-external-user-access-policy.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3d54-133">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="c3d54-134">Windows PowerShell を使用して、フェデレーション ドメインのユーザーによるアクセスをサポートする既存のポリシーを構成するのには</span><span class="sxs-lookup"><span data-stu-id="c3d54-134">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="c3d54-135">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c3d54-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c3d54-136">ビジネス用サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、 **Skype**ビジネス サーバーをクリック**ビジネス サーバー管理シェルの Skype**です。</span><span class="sxs-lookup"><span data-stu-id="c3d54-136">Start the Skype for Busines Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="c3d54-137">ビジネス サーバー管理シェルには、Skype で次を入力します。</span><span class="sxs-lookup"><span data-stu-id="c3d54-137">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > <span data-ttu-id="c3d54-138">"EnablePublicCloudAudioVideoAccess"のパラメーターが対応する選択、Skype のビジネス サーバーのコントロール パネルの</span><span class="sxs-lookup"><span data-stu-id="c3d54-138">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Skype for Business Server Control Panel</span></span>


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="c3d54-139">Windows PowerShell を使用して、フェデレーション ドメインのユーザーによるアクセスをサポートする新しいポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="c3d54-139">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="c3d54-140">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c3d54-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c3d54-141">ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、**ビジネスのサーバーの Microsoft の Skype**をクリック**ビジネス サーバー管理シェルの Skype**です。</span><span class="sxs-lookup"><span data-stu-id="c3d54-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="c3d54-142">ビジネス サーバー管理シェルには、Skype で次を入力します。</span><span class="sxs-lookup"><span data-stu-id="c3d54-142">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    <span data-ttu-id="c3d54-143">新しいサイト ポリシーを作成する例です。</span><span class="sxs-lookup"><span data-stu-id="c3d54-143">An example of creating a new site policy:</span></span>
    
    ```
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="c3d54-144">削除するか、フェデレーション ドメインのユーザーによるアクセスをサポートするために Windows PowerShell を使用してポリシーをリセットするには</span><span class="sxs-lookup"><span data-stu-id="c3d54-144">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="c3d54-145">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c3d54-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c3d54-146">ビジネス サーバー管理シェルには、Skype で以下を入力します。</span><span class="sxs-lookup"><span data-stu-id="c3d54-146">Type the following in the Skype for Business Server Management Shell</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    <span data-ttu-id="c3d54-147">(グローバル ポリシーだけが削除の設定グローバル ポリシーをリセットする際の例します。</span><span class="sxs-lookup"><span data-stu-id="c3d54-147">An example of resetting the global policy (The global policy can only have its setting removed.</span></span> <span data-ttu-id="c3d54-148">ポリシーは削除できません)。</span><span class="sxs-lookup"><span data-stu-id="c3d54-148">The policy cannot be deleted):</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    <span data-ttu-id="c3d54-149">サイト ポリシーを削除するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c3d54-149">To remove a site policy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    <span data-ttu-id="c3d54-150">レドモンド サイトのポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c3d54-150">Deletes the site policy Redmond.</span></span> <span data-ttu-id="c3d54-151">UserEAPPolicy をという名前のユーザー ポリシーを削除するのには次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c3d54-151">To delete a user policy named UserEAPPolicy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a><span data-ttu-id="c3d54-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3d54-152">See Also</span></span>


[<span data-ttu-id="c3d54-153">フェデレーションおよびパブリック IM 接続の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="c3d54-153">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[<span data-ttu-id="c3d54-154">外部ユーザー アクセス ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="c3d54-154">Assign an external user access policy</span></span>](assign-an-external-user-access-policy.md)

[<span data-ttu-id="c3d54-155">組織の SIP フェデレーション ドメインの管理</span><span class="sxs-lookup"><span data-stu-id="c3d54-155">Manage SIP federated domains for your organization</span></span>](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[<span data-ttu-id="c3d54-156">組織の SIP フェデレーション プロバイダーの管理</span><span class="sxs-lookup"><span data-stu-id="c3d54-156">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[<span data-ttu-id="c3d54-157">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="c3d54-157">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="c3d54-158">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="c3d54-158">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="c3d54-159">Get CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="c3d54-159">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="c3d54-160">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="c3d54-160">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="c3d54-161">許可 CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="c3d54-161">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

