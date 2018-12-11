---
title: 組織の SIP フェデレーション プロバイダーの管理
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ユーザーの SIP プロバイダーのフェデレーションのサポートを構成する方法について説明します。
ms.openlocfilehash: 111a71f95f3ae6a6c9dec90f5c0b29df07266fd2
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222962"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="97246-103">ビジネス サーバー用の Skype で、組織のフェデレーションの SIP プロバイダーを管理します。</span><span class="sxs-lookup"><span data-stu-id="97246-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="97246-104">SIP のユーザーのフェデレーション プロバイダーのサポートを構成するのには、次の操作をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="97246-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="97246-105">フェデレーションの SIP プロバイダーの連絡先との通信をサポートするために 1 つまたは複数の外部ユーザー アクセス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="97246-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="97246-106">サポートするホストされるプロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="97246-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="97246-107">サポートするパブリック IM プロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="97246-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="97246-108">作成または編集公開のフェデレーションの SIP プロバイダー Skype のビジネス サーバー</span><span class="sxs-lookup"><span data-stu-id="97246-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="97246-109">パブリック インスタント メッセージング (IM) の接続は、IM を使用してパブリック プロバイダーが提供する IM サービスのユーザーと通信するのには、組織内のユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="97246-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="97246-110">ビジネス サーバー用の Skype は、インスタント メッセージング用のパブリック プロバイダー構成を持ちます。</span><span class="sxs-lookup"><span data-stu-id="97246-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="97246-111">各パブリック プロバイダーには、プロバイダーのエッジ サーバーの完全修飾ドメイン名、および**ユーザーがこのプロバイダーを使用している自分の連絡先リストのメンバーのみと通信できるようにする**既定の検証レベルを構成します。</span><span class="sxs-lookup"><span data-stu-id="97246-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="97246-112">既定の設定としてパブリック プロバイダーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="97246-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="97246-113">使用許諾契約書とパブリック プロバイダーを有効にする前に作業の準備を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97246-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="97246-114">ライセンス取得が完了し、作業の準備をする前にプロバイダーを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="97246-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="97246-115">ユーザーは前提の作業が完了するまでに、これらのプロバイダーの連絡先と通信することができません。</span><span class="sxs-lookup"><span data-stu-id="97246-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="97246-116">ライセンスとプロビジョニングのパブリック プロバイダーの詳細については、[パブリック ユーザー アクセスを制御するポリシーを構成する](../external-access-policies/configure-policies-to-control-public-user-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97246-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="97246-117">パブリック プロバイダーを作成または更新するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="97246-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="97246-118">パブリック プロバイダーを作成または更新</span><span class="sxs-lookup"><span data-stu-id="97246-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="97246-119">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="97246-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="97246-120">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="97246-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="97246-121">左側のナビゲーション ・ バーで [**フェデレーションと外部アクセス**、および**SIP フェデレーション プロバイダーの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97246-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="97246-122">新しい公開プロバイダーを作成する場合は、[**新規**] をクリックし、**パブリック プロバイダー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97246-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="97246-123">パブリック プロバイダーの一覧からエントリを編集する場合は、パブリック プロバイダーを選択し、[**編集**] メニュー**の詳細を表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97246-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="97246-124">**SIP フェデレーション プロバイダーの編集**] ページで、入力するか、次の設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="97246-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="97246-125">**このプロバイダーとの通信を有効にする**   このプロバイダーのユーザーと IM を使用するこの設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="97246-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="97246-126">**プロバイダー名:**   、必要なプロパティ、型のようにプロバイダーの名前は、フェデレーションの SIP プロバイダーの一覧に反映されます。</span><span class="sxs-lookup"><span data-stu-id="97246-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="97246-127">**エッジ サービス (FQDN) へのアクセス:**   、必要なプロパティを構成しているプロバイダーのアクセス エッジ サービスの完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="97246-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="97246-128">この情報は、既定の項目として用意されているが、パブリック プロバイダーは、公開プロバイダーのアクセス エッジ サービスの FQDN に変更を加える場合にのみ変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97246-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="97246-129">**検証レベルを既定値:**   既定の設定、**ユーザーがこのプロバイダーを使用している自分の連絡先リストのユーザーと通信できるようにする**には、承諾し、連絡先リストに登録されている取引先担当者との通信が制限されます。</span><span class="sxs-lookup"><span data-stu-id="97246-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="97246-130">**このプロバイダーを使用してすべてのユーザーとの通信を許可するユーザー**を選択する必要がありますが受信している取引先担当者への招待を承諾の制限を削除します。</span><span class="sxs-lookup"><span data-stu-id="97246-130">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="97246-131">この設定では、ユーザーが連絡できるパブリック プロバイダーのネットワークからは制限されません。</span><span class="sxs-lookup"><span data-stu-id="97246-131">This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="97246-132">実行、設定を構成する**コミット**を保存する] をクリックするか**キャンセル**変更を破棄する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97246-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="97246-133">作成または編集では、ビジネスのサーバーの Skype でのフェデレーションの SIP プロバイダーがホストされています。</span><span class="sxs-lookup"><span data-stu-id="97246-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="97246-134">インスタント メッセージング (IM) 接続ユーザーができる、組織でホストされるプロバイダーが提供する IM サービスのユーザーと通信するために IM を使用してプロバイダーをホストします。</span><span class="sxs-lookup"><span data-stu-id="97246-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="97246-135">各ホスト プロバイダーには、プロバイダーのエッジ サーバーの完全修飾ドメイン名、および**ユーザーがこのプロバイダーを使用している自分の連絡先リストのメンバーのみと通信できるようにする**既定の検証レベルを構成します。</span><span class="sxs-lookup"><span data-stu-id="97246-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="97246-136">使用の作成または編集するには、次の手順には、プロバイダーがホストされています。</span><span class="sxs-lookup"><span data-stu-id="97246-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="97246-137">プロバイダーのホストの作成または編集するには</span><span class="sxs-lookup"><span data-stu-id="97246-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="97246-138">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="97246-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="97246-139">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="97246-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="97246-140">左側のナビゲーション ・ バーで [**フェデレーションと外部アクセス**、および**SIP フェデレーション プロバイダーの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97246-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="97246-141">新しいホスト プロバイダーを作成する場合は、[**新規**] をクリックし、**ホスト プロバイダー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97246-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="97246-142">ホスト プロバイダーの一覧からエントリを編集する場合は、ホストされるプロバイダーを選択して**編集**] をクリックし、**詳細を表示**します。</span><span class="sxs-lookup"><span data-stu-id="97246-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="97246-143">**SIP フェデレーション プロバイダーの編集**] ページで、入力するか、次の設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="97246-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="97246-144">**このプロバイダーとの通信を有効にする**   このプロバイダーのユーザーとの通信は、この設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="97246-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="97246-145">**プロバイダー名:**   、必要なプロパティ、型のようにプロバイダーの名前は、フェデレーションの SIP プロバイダーの一覧に反映されます。</span><span class="sxs-lookup"><span data-stu-id="97246-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="97246-146">**エッジ サービス (FQDN) へのアクセス:**   、必要なプロパティを構成しているホストされるプロバイダーのアクセス エッジ サービスの完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="97246-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="97246-147">この情報は、ホストされるプロバイダーによって提供される必要があり、ホストされるプロバイダーは、ホストされるプロバイダーのアクセス エッジ サービスの FQDN に変更を加える場合にのみ変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97246-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="97246-148">**検証レベルを既定値:**   既定の設定、**ユーザーがこのプロバイダーを使用している自分の連絡先リストのユーザーと通信できるようにする**には、承諾し、連絡先リストに登録されている取引先担当者との通信が制限されます。</span><span class="sxs-lookup"><span data-stu-id="97246-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="97246-149">**このプロバイダーを使用してすべてのユーザーとの通信を許可するユーザー**を選択する必要がありますが受信している取引先担当者への招待を承諾の制限を削除します。</span><span class="sxs-lookup"><span data-stu-id="97246-149">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="97246-150">この設定では、ホストされるプロバイダーのネットワークからご連絡することができますが制限されません。</span><span class="sxs-lookup"><span data-stu-id="97246-150">This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="97246-151">実行、設定を構成する**コミット**を保存する] をクリックするか**キャンセル**変更を破棄する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97246-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="97246-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="97246-152">See Also</span></span>


[<span data-ttu-id="97246-153">パブリック ユーザー アクセスを制御するポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="97246-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="97246-154">フェデレーションおよびパブリック IM 接続の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="97246-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

