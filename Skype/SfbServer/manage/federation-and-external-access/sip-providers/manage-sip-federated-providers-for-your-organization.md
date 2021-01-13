---
title: 組織の SIP フェデレーション プロバイダーの管理
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
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
description: SIP フェデレーション プロバイダーのユーザーのサポートを構成する方法について説明します。
ms.openlocfilehash: 8d4c6224a66454f8fb28bb4f991faf6ad672f596
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823567"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="13ce6-103">Skype for Business Server で組織の SIP フェデレーション プロバイダーを管理する</span><span class="sxs-lookup"><span data-stu-id="13ce6-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="13ce6-104">SIP フェデレーション プロバイダーのユーザーのサポートを構成するには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="13ce6-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="13ce6-105">1 つ以上の外部ユーザー アクセス ポリシーを構成して、SIP フェデレーション プロバイダーの連絡先との通信をサポートします。</span><span class="sxs-lookup"><span data-stu-id="13ce6-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="13ce6-106">サポートの対象となるホストされるプロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="13ce6-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="13ce6-107">サポートの対象となるパブリック IM プロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="13ce6-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="13ce6-108">Skype for Business Server でパブリック SIP フェデレーション プロバイダーを作成または編集する</span><span class="sxs-lookup"><span data-stu-id="13ce6-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="13ce6-109">パブリック インスタント メッセージング (IM) 接続を使用すると、組織内のユーザーは IM を使用して、パブリック プロバイダーが提供する IM サービスのユーザーと通信できます。</span><span class="sxs-lookup"><span data-stu-id="13ce6-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="13ce6-110">Skype for Business Server には、インスタント メッセージング用のパブリック プロバイダー構成があります。</span><span class="sxs-lookup"><span data-stu-id="13ce6-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="13ce6-111">各パブリック プロバイダーは、そのプロバイダーのエッジ サーバーの完全修飾ドメイン名と、既定の確認レベルである [**Allow users to communicate only with people on their Contacts list who use this provider**] を指定して構成されています。</span><span class="sxs-lookup"><span data-stu-id="13ce6-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="13ce6-112">既定の設定では、パブリック プロバイダーはいずれも無効になっています。</span><span class="sxs-lookup"><span data-stu-id="13ce6-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="13ce6-113">パブリック プロバイダーを有効にする前に、使用許諾契約とプロビジョニング作業を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13ce6-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="13ce6-114">ライセンスとプロビジョニングの作業を完了する前にプロバイダーを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="13ce6-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="13ce6-115">前提条件となる作業を完了するまで、ユーザーはそのプロバイダーで連絡先と通信することはできません。</span><span class="sxs-lookup"><span data-stu-id="13ce6-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="13ce6-116">パブリック プロバイダーのライセンスとプロビジョニングの詳細については、「ポリシーを構成してパブリック ユーザーのアクセスを制御する [」を参照してください](../external-access-policies/configure-policies-to-control-public-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="13ce6-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="13ce6-117">パブリック プロバイダーを作成または編集するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="13ce6-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="13ce6-118">パブリック プロバイダーを作成または編集するには</span><span class="sxs-lookup"><span data-stu-id="13ce6-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="13ce6-119">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="13ce6-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="13ce6-120">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="13ce6-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="13ce6-121">左側のナビゲーション バーで、[**フェデレーションと外部アクセス**] をクリックし、[**SIP フェデレーション プロバイダー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13ce6-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="13ce6-122">新しいパブリック プロバイダーを作成する必要がある場合は、[**新規作成**] をクリックし、[**パブリック プロバイダー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13ce6-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="13ce6-123">パブリック プロバイダーの一覧のエントリを編集する必要がある場合は、パブリック プロバイダーを選択し、[**編集**] をクリックして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13ce6-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="13ce6-124">[**編集 SIP フェデレーション プロバイダー**] ページでは、次の設定を入力または編集できます。</span><span class="sxs-lookup"><span data-stu-id="13ce6-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="13ce6-125">[**このプロバイダーとの通信を有効にする**]   この設定を選択すると、このプロバイダーのユーザーとの IM が有効になります。</span><span class="sxs-lookup"><span data-stu-id="13ce6-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="13ce6-126">[**プロバイダー名**]   必須プロパティ。プロバイダーの名前を入力します。この名前は SIP フェデレーション プロパティのリストに反映されます。</span><span class="sxs-lookup"><span data-stu-id="13ce6-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="13ce6-127">**アクセス エッジ サービス (FQDN):**   必須のプロパティで、構成するプロバイダーのアクセス エッジ サービスの完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="13ce6-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="13ce6-128">この情報は既定のアイテムとして提供され、パブリック プロバイダーがパブリック プロバイダーのアクセス エッジ サービスの FQDN を変更した場合にのみ変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13ce6-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="13ce6-129">[**Default verification level:**]   既定の設定である [**Allow users to communicate with people on their Contacts list who use this provider**] を使用すると、連絡先リストに含まれる承認済みの連絡先に通信が制限されます。</span><span class="sxs-lookup"><span data-stu-id="13ce6-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="13ce6-p104">[**Allow users to communicate with everyone using this provider**] を選択すると、連絡先からの招待を受け取って承認しておく必要があるという制限がなくなります。この設定では、パブリック プロバイダーのネットワークからユーザーに連絡できる相手先は制限されません。</span><span class="sxs-lookup"><span data-stu-id="13ce6-p104">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="13ce6-132">設定の構成が完了したら、[**コミット**] をクリックして保存するか、[**キャンセル**] をクリックして変更を破棄します。</span><span class="sxs-lookup"><span data-stu-id="13ce6-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="13ce6-133">Skype for Business Server でホスト SIP フェデレーション プロバイダーを作成または編集する</span><span class="sxs-lookup"><span data-stu-id="13ce6-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="13ce6-134">ホストされたプロバイダーのインスタント メッセージング (IM) 接続を使用すると、組織内のユーザーは IM を使用して、ホストされたプロバイダーが提供する IM サービスのユーザーと通信できます。</span><span class="sxs-lookup"><span data-stu-id="13ce6-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="13ce6-135">各ホストされるプロバイダーは、プロバイダーのエッジ サーバーの完全修飾ドメイン名と、既定の確認レベルである [**連絡先リストのユーザーのうち、このプロバイダーを使うユーザーとの通信のみを許可する**] によって構成されます。</span><span class="sxs-lookup"><span data-stu-id="13ce6-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="13ce6-136">ホストされたプロバイダーを作成または編集するには、以下の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="13ce6-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="13ce6-137">ホストされるプロバイダーを作成または編集するには</span><span class="sxs-lookup"><span data-stu-id="13ce6-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="13ce6-138">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="13ce6-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="13ce6-139">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="13ce6-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="13ce6-140">左側のナビゲーション バーで [**フェデレーションと外部アクセス**] をクリックし、[**SIP フェデレーション プロバイダー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13ce6-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="13ce6-141">新しいホストされるプロバイダーを作成するには、[**新規**] をクリックし、[**ホストされるプロバイダー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13ce6-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="13ce6-142">ホストされるプロバイダーの一覧に示されるプロバイダーを編集する必要がある場合は、編集するプロバイダーを選択し、[**編集**]、[**編集の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="13ce6-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="13ce6-143">[**編集 SIP フェデレーション プロバイダー**] ページで、次の設定を入力または編集できます。</span><span class="sxs-lookup"><span data-stu-id="13ce6-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="13ce6-144">[**このプロバイダーとの通信を有効にする**]   この設定を選択すると、このプロバイダーのユーザーと通信できます。</span><span class="sxs-lookup"><span data-stu-id="13ce6-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="13ce6-145">[**プロバイダー名**]   必須プロパティ。プロバイダーの名前を入力します。この名前は SIP フェデレーション プロパティのリストに反映されます。</span><span class="sxs-lookup"><span data-stu-id="13ce6-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="13ce6-146">**アクセス エッジ サービス (FQDN):**   必須のプロパティとして、構成するホストされたプロバイダーのアクセス エッジ サービスの完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="13ce6-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="13ce6-147">この情報は、ホストされたプロバイダーによって提供される必要があります。また、ホストされたプロバイダーが、ホストされているプロバイダーのアクセス エッジ サービスの FQDN を変更した場合にのみ変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13ce6-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="13ce6-148">[**既定の確認レベル**]   既定の設定である [**連絡先リストのユーザーのうち、このプロバイダーを使うユーザーとの通信のみを許可する**] を選択すると、既に受け入れ済みで連絡先リストに登録されている連絡先以外の連絡先とは通信できません。</span><span class="sxs-lookup"><span data-stu-id="13ce6-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="13ce6-p106">[**このプロバイダーを使うすべてのユーザーとの通信を許可する**] を選択すると、連絡先に対する制限が削除されます。この設定は、ホストされるプロバイダーのネットワークからの通信を制限しません。</span><span class="sxs-lookup"><span data-stu-id="13ce6-p106">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="13ce6-151">設定の構成が終了したら、[**コミット**] をクリックして保存するか、[**キャンセル**] をクリックして変更を破棄します。</span><span class="sxs-lookup"><span data-stu-id="13ce6-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="13ce6-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="13ce6-152">See Also</span></span>


[<span data-ttu-id="13ce6-153">パブリック ユーザーアクセスを制御するポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="13ce6-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="13ce6-154">フェデレーションおよびパブリック IM 接続の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="13ce6-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

