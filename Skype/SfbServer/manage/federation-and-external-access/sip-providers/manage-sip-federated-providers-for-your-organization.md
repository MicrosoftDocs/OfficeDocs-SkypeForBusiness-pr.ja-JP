---
title: 組織の SIP フェデレーション プロバイダーの管理
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
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
description: SIP フェデレーションプロバイダーのユーザー向けのサポートを構成する方法について説明します。
ms.openlocfilehash: 42845bfd39c65e60765ee8d3fd2f1e3a58a08aae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818368"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="43da4-103">Skype for Business Server で組織の SIP フェデレーションプロバイダーを管理する</span><span class="sxs-lookup"><span data-stu-id="43da4-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="43da4-104">SIP フェデレーションプロバイダーのユーザー向けのサポートを構成するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43da4-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="43da4-105">SIP フェデレーションプロバイダの連絡先との通信をサポートするように1つ以上の外部ユーザーアクセスポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="43da4-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="43da4-106">サポートするホストされているプロバイダーを指定する</span><span class="sxs-lookup"><span data-stu-id="43da4-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="43da4-107">サポートするパブリック IM プロバイダーを指定する</span><span class="sxs-lookup"><span data-stu-id="43da4-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="43da4-108">Skype for Business Server でパブリック SIP フェデレーションプロバイダーを作成または編集する</span><span class="sxs-lookup"><span data-stu-id="43da4-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="43da4-109">パブリックインスタントメッセージング (IM) 接続を使うと、組織内のユーザーは IM を使用して、パブリックプロバイダーによって提供される IM サービスのユーザーと通信することができます。</span><span class="sxs-lookup"><span data-stu-id="43da4-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="43da4-110">Skype for Business Server には、インスタントメッセージ用のパブリックプロバイダー構成があります。</span><span class="sxs-lookup"><span data-stu-id="43da4-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="43da4-111">各パブリックプロバイダーは、プロバイダーのエッジサーバーの完全修飾ドメイン名で構成され、既定の認証レベルでは、**このプロバイダーを使用する連絡先リストのユーザーのみとの通信を許可**します。</span><span class="sxs-lookup"><span data-stu-id="43da4-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="43da4-112">既定の設定では、どのパブリックプロバイダーも有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="43da4-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="43da4-113">パブリックプロバイダーを有効にする前に、ライセンス契約とプロビジョニング作業を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43da4-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="43da4-114">ライセンスとプロビジョニングの作業を完了する前に、プロバイダーを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="43da4-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="43da4-115">ユーザーは、前提条件となる作業が完了するまで、これらのプロバイダーの連絡先と通信できません。</span><span class="sxs-lookup"><span data-stu-id="43da4-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="43da4-116">パブリックプロバイダーのライセンスとプロビジョニングの詳細については、「[パブリックユーザーのアクセスを制御するためのポリシーを構成する](../external-access-policies/configure-policies-to-control-public-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43da4-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="43da4-117">パブリックプロバイダーを作成または編集するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="43da4-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="43da4-118">パブリックプロバイダーを作成または編集するには</span><span class="sxs-lookup"><span data-stu-id="43da4-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="43da4-119">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="43da4-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="43da4-120">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="43da4-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="43da4-121">左側のナビゲーションバーで、[**フェデレーションと外部アクセス**] をクリックし、[ **SIP フェデレーションプロバイダー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43da4-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="43da4-122">新しいパブリックプロバイダーを作成する必要がある場合は、[**新規**] をクリックし、[**パブリックプロバイダー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43da4-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="43da4-123">パブリックプロバイダーの一覧からエントリを編集する必要がある場合は、パブリックプロバイダーを選択し、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43da4-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="43da4-124">[ **SIP フェデレーションプロバイダーの編集**] ページでは、次の設定を入力または編集できます。</span><span class="sxs-lookup"><span data-stu-id="43da4-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="43da4-125">**このプロバイダー**   との通信を有効にするこの設定をオンにすると、このプロバイダーのユーザーとの IM が有効になります。</span><span class="sxs-lookup"><span data-stu-id="43da4-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="43da4-126">**[Provider name]:**   必要なプロパティは、SIP フェデレーションプロバイダーの一覧に反映されるプロバイダーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="43da4-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="43da4-127">**Access edge サービス (FQDN):**   必要なプロパティで、構成しているプロバイダーのアクセスエッジサービスの完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="43da4-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="43da4-128">この情報は既定の項目として提供され、パブリックプロバイダーがアクセスエッジサービスの FQDN に変更を加えた場合にのみ変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43da4-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="43da4-129">**既定の確認レベル:**   既定の設定では、ユーザーが連絡先リストに登録されているユーザー**との通信を許可**します。このプロバイダーを使用すると、承諾した連絡先と連絡先リストに含まれている連絡先への通信が制限されます。</span><span class="sxs-lookup"><span data-stu-id="43da4-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="43da4-130">[**このプロバイダーを使用するすべてのユーザーとの通信を許可する**] を選択すると、連絡先への招待を受信して受け付けるために必要な制限が解除されます。</span><span class="sxs-lookup"><span data-stu-id="43da4-130">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="43da4-131">この設定では、パブリックプロバイダーのネットワークから連絡できるユーザーを制限することはできません。</span><span class="sxs-lookup"><span data-stu-id="43da4-131">This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="43da4-132">設定の構成が完了したら、[**確定**] をクリックするか、[**キャンセル**] をクリックして変更を破棄します。</span><span class="sxs-lookup"><span data-stu-id="43da4-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="43da4-133">Skype for Business Server でホストされている SIP フェデレーションプロバイダーを作成または編集する</span><span class="sxs-lookup"><span data-stu-id="43da4-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="43da4-134">ホストされているプロバイダーのインスタントメッセージング (IM) 接続により、組織内のユーザーは IM を使って、ホストされているプロバイダーによって提供される IM サービスのユーザーと通信することができます。</span><span class="sxs-lookup"><span data-stu-id="43da4-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="43da4-135">ホストされる各プロバイダーは、プロバイダーのエッジサーバーの完全修飾ドメイン名で構成され、既定の認証レベルでは、**このプロバイダーを使用する連絡先リストのユーザーのみとの通信を許可**します。</span><span class="sxs-lookup"><span data-stu-id="43da4-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="43da4-136">ホストされるプロバイダーを作成または編集するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="43da4-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="43da4-137">ホストされているプロバイダーを作成または編集するには</span><span class="sxs-lookup"><span data-stu-id="43da4-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="43da4-138">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="43da4-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="43da4-139">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="43da4-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="43da4-140">左側のナビゲーションバーで、[**フェデレーションと外部アクセス**] をクリックし、[ **SIP フェデレーションプロバイダー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43da4-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="43da4-141">新しいホスティングプロバイダーを作成する必要がある場合は、[**新規**] をクリックし、[ホストされる**プロバイダー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43da4-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="43da4-142">ホストされているプロバイダーの一覧からエントリを編集する必要がある場合は、ホストされているプロバイダーを選択し、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43da4-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="43da4-143">[ **SIP フェデレーションプロバイダーの編集**] ページでは、次の設定を入力または編集できます。</span><span class="sxs-lookup"><span data-stu-id="43da4-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="43da4-144">**このプロバイダー**   との通信を有効にするこの設定をオンにすると、このプロバイダーのユーザーとの通信が有効になります。</span><span class="sxs-lookup"><span data-stu-id="43da4-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="43da4-145">**[Provider name]:**   必要なプロパティは、SIP フェデレーションプロバイダーの一覧に反映されるプロバイダーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="43da4-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="43da4-146">**Access edge サービス (FQDN):**   必須プロパティ。構成するホストされているプロバイダーのアクセスエッジサービスの完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="43da4-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="43da4-147">この情報は、ホストされたプロバイダーによって提供される必要があります。また、ホストされているプロバイダーが、ホストされているプロバイダーでアクセスエッジサービスの FQDN に変更を加えた場合にのみ変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43da4-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="43da4-148">**既定の確認レベル:**   既定の設定では、ユーザーが連絡先リストに登録されているユーザー**との通信を許可**します。このプロバイダーを使用すると、承諾した連絡先と連絡先リストに含まれている連絡先への通信が制限されます。</span><span class="sxs-lookup"><span data-stu-id="43da4-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="43da4-149">[**このプロバイダーを使用するすべてのユーザーとの通信を許可する**] を選択すると、連絡先への招待を受信して受け付けるために必要な制限が解除されます。</span><span class="sxs-lookup"><span data-stu-id="43da4-149">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="43da4-150">この設定では、ホストされているプロバイダーのネットワークから連絡できるユーザーを制限することはできません。</span><span class="sxs-lookup"><span data-stu-id="43da4-150">This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="43da4-151">設定の構成が完了したら、[**確定**] をクリックするか、[**キャンセル**] をクリックして変更を破棄します。</span><span class="sxs-lookup"><span data-stu-id="43da4-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="43da4-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="43da4-152">See Also</span></span>


[<span data-ttu-id="43da4-153">パブリックユーザーのアクセスを制御するためのポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="43da4-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="43da4-154">フェデレーションおよびパブリック IM 接続の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="43da4-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

