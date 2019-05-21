---
title: 組織の SIP フェデレーション ドメインの管理
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: フェデレーションできる SIP ドメインを管理し、構成する方法について説明します。
ms.openlocfilehash: 1a2f76f7f465401bae04b4defa2e0a1f5300ab0f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303971"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="54c56-103">Skype for Business Server で組織の SIP フェデレーションドメインを管理する</span><span class="sxs-lookup"><span data-stu-id="54c56-103">Manage SIP federated domains for your organization in Skype for Business Server</span></span>


<span data-ttu-id="54c56-104">フェデレーションできる SIP ドメインを管理して構成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="54c56-104">To manage and configure SIP domains that you can federate with, you can do the following:</span></span>

  - <span data-ttu-id="54c56-105">SIP フェデレーションパートナードメインの許可ドメインリストを作成または編集します。</span><span class="sxs-lookup"><span data-stu-id="54c56-105">Create or edit an allowed domain list of SIP federated partner domains.</span></span>

  - <span data-ttu-id="54c56-106">SIP フェデレーションドメインのブロックドメインリストを作成または編集します。</span><span class="sxs-lookup"><span data-stu-id="54c56-106">Create or edit a blocked domain list of SIP federated domains.</span></span>

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a><span data-ttu-id="54c56-107">Skype for Business Server で許可されている外部ドメインのサポートを構成する</span><span class="sxs-lookup"><span data-stu-id="54c56-107">Configure support for allowed external domains in Skype for Business Server</span></span>

<span data-ttu-id="54c56-108">フェデレーションパートナーのサポートを構成している場合、組織とフェデレーションできる特定のドメインを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="54c56-108">If you have configured support for federated partners, you can manage which specific domains can federate with your organization.</span></span> <span data-ttu-id="54c56-109">1つ以上の特定の外部ドメインを、許可されたフェデレーションドメインとして構成します。</span><span class="sxs-lookup"><span data-stu-id="54c56-109">You configure one or more specific external domains as allowed federated domains.</span></span> <span data-ttu-id="54c56-110">そのためには、許可ドメインの一覧に各ドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="54c56-110">To do this, add each domain to the list of allowed domains.</span></span> <span data-ttu-id="54c56-111">組織でパートナーの検出が有効になっている場合でも、ドメインが1000以上のユーザーと通信する必要がある、または1秒あたり20件を超えるメッセージを送信する必要があるフェデレーションパートナーである場合に、この操作を行います。</span><span class="sxs-lookup"><span data-stu-id="54c56-111">Even if partner discovery is enabled for your organization, do this if the domain is a federated partner that might need to communicate with more than 1,000 of your users or might need to send more than 20 messages per second.</span></span> <span data-ttu-id="54c56-112">組織でパートナー検出が有効になっていない場合、許可されたドメインリストに追加した外部ドメインのユーザーのみが、組織内のユーザーと IM および会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="54c56-112">If partner discovery is not enabled for your organization, only users of external domains that you add to the allowed domains list can participate in IM and conferencing with users in your organization.</span></span> <span data-ttu-id="54c56-113">フェデレーションドメインへのアクセスをフェデレーションパートナーのアクセスエッジサービスを実行している特定のサーバーに制限する場合は、許可ドメインの一覧で、各ドメインのアクセスエッジサービスを実行しているサーバーのドメイン名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="54c56-113">If you want to restrict access for a federated domain to a specific server running the Access Edge service of the federated partner, you can specify the domain name of the server running the Access Edge service for each domain in the list of allowed domains.</span></span>

> [!NOTE]  
> <span data-ttu-id="54c56-114">この手順では、特定のドメインのサポートを構成する方法について説明します。フェデレーションユーザー向けのサポートを実装するには、組織のフェデレーションユーザーのサポートを有効にする必要があります。また、ポリシーを構成して適用して、ユーザーを管理することもできます。フェデレーションされたユーザーとの共同作業</span><span class="sxs-lookup"><span data-stu-id="54c56-114">This procedure describes how to configure support for specific domains, but implementing support for federated users also requires that you enable support for federated users for your organization, and configure and apply policies to control which users can collaborate with federated users.</span></span> <span data-ttu-id="54c56-115">フェデレーションユーザーのサポートを有効にする方法について詳しくは、「[リモートユーザーアクセスを有効または無効](../access-edge/enable-or-disable-remote-user-access.md)にする」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="54c56-115">For details about enabling support for federated users, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span> <span data-ttu-id="54c56-116">フェデレーションを制御するポリシーの構成の詳細については、「フェデレーションされた[ユーザーアクセスを制御するためのポリシーの構成](../external-access-policies/configure-policies-to-control-federated-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54c56-116">For details about configuring policies to control federation, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a><span data-ttu-id="54c56-117">許可ドメインの一覧に外部ドメインを追加するには</span><span class="sxs-lookup"><span data-stu-id="54c56-117">To add an external domain to the list of allowed domains</span></span>

1.  <span data-ttu-id="54c56-118">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="54c56-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2.  <span data-ttu-id="54c56-119">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="54c56-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3.  <span data-ttu-id="54c56-120">左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**フェデレーションドメイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c56-120">In the left navigation bar, click **External User Access**, and then click **Federated Domains**.</span></span>
4.  <span data-ttu-id="54c56-121">[**フェデレーションドメイン**] ページで、[**新規作成**] をクリックし、[許可した**ドメイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c56-121">On the **Federated Domains** page, click **New**, and then click **Allowed domain**.</span></span>
5.  <span data-ttu-id="54c56-122">**新しいフェデレーションドメイン**で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="54c56-122">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="54c56-123">[ **Domain name (または FQDN)**] に、フェデレーションパートナードメインの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="54c56-123">In **Domain name (or FQDN)**, type the name of the federated partner domain.</span></span>       

        > [!NOTE]  
        > <span data-ttu-id="54c56-124">この名前は一意であり、アクセスエッジサービスを実行しているこのサーバーで許可されているドメインとして既に存在することはできません。</span><span class="sxs-lookup"><span data-stu-id="54c56-124">This name must be unique and cannot already exist as an allowed domain for this server running the Access Edge service.</span></span> <span data-ttu-id="54c56-125">名前の長さは、256文字以下にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="54c56-125">The name cannot exceed 256 characters in length.</span></span><BR><br><span data-ttu-id="54c56-126">フェデレーションパートナーのドメイン名での検索では、サフィックス一致が実行されます。</span><span class="sxs-lookup"><span data-stu-id="54c56-126">The search on the federated partner domain name performs a suffix match.</span></span> <span data-ttu-id="54c56-127">たとえば、 **contoso.com**と入力すると、検索によってドメイン**it.contoso.com**も返されます。</span><span class="sxs-lookup"><span data-stu-id="54c56-127">For example, if you type **contoso.com**, the search will also return the domain **it.contoso.com**.</span></span><BR><br><span data-ttu-id="54c56-128">フェデレーションパートナードメインは、同時にブロックおよび許可することはできません。</span><span class="sxs-lookup"><span data-stu-id="54c56-128">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="54c56-129">Skype for Business Server では、リストを同期する必要がないように、この問題を回避することができます。</span><span class="sxs-lookup"><span data-stu-id="54c56-129">Skype for Business Server prevents this from happening so that you do not have to sync up your lists.</span></span>
    
      - <span data-ttu-id="54c56-130">このフェデレーションドメインへのアクセスを、アクセスエッジサービス **(FQDN)** で実行されている特定のサーバーのユーザーに制限する場合は、アクセスエッジサービスを実行しているフェデレーションドメインのサーバーの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="54c56-130">If you want to restrict access for this federated domain to users of a specific server running the Access Edge service, in **Access Edge service (FQDN)**, type the FQDN of the federated domain’s server running the Access Edge service.</span></span>    
      - <span data-ttu-id="54c56-131">追加情報を提供する場合は、[**コメント**] に、この構成について他のシステム管理者と共有する情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="54c56-131">If you want to provide additional information, in **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="54c56-132">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c56-132">Click **Commit**.</span></span>
7.  <span data-ttu-id="54c56-133">許可するフェデレーションパートナードメインごとに、手順 4 ~ 6 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="54c56-133">Repeat steps 4 through 6 for each federated partner domain that you want to allow.</span></span>

<span data-ttu-id="54c56-134">フェデレーションされたユーザーアクセスを有効にするには、組織でフェデレーションされたユーザーアクセスのサポートを有効にする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="54c56-134">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="54c56-135">詳細について[は、「リモートユーザーアクセスを有効または無効](../access-edge/enable-or-disable-remote-user-access.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54c56-135">For details, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="54c56-136">さらに、フェデレーションされたユーザーと共同作業できるようにするユーザーにポリシーを構成して適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54c56-136">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="54c56-137">詳しくは、「フェデレーションされた[ユーザーアクセスを制御するためのポリシーを構成する](../external-access-policies/configure-policies-to-control-federated-user-access.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="54c56-137">For details, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a><span data-ttu-id="54c56-138">Skype for Business Server でブロックされた外部ドメインのサポートを構成する</span><span class="sxs-lookup"><span data-stu-id="54c56-138">Configure support for blocked external domains in Skype for Business Server</span></span> 

<span data-ttu-id="54c56-139">フェデレーションパートナーのサポートを構成している場合は、どのドメインを組織とのフェデレーションからブロックするかを管理できます。</span><span class="sxs-lookup"><span data-stu-id="54c56-139">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="54c56-140">ブロックされたドメインの一覧はブロックリスト (許可されていない明示的なエントリの一覧) として機能し、このオプションを有効にしている場合はフェデレーションドメインの検出に適用されます。</span><span class="sxs-lookup"><span data-stu-id="54c56-140">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="54c56-141">詳細について[は、「フェデレーションパートナーの検出を有効または無効](../access-edge/enable-or-disable-discovery-of-federation-partners.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54c56-141">For details, see [Enable or disable discovery of federation partners](../access-edge/enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="54c56-142">1つ以上の外部ドメインをブロックして組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="54c56-142">Block one or more external domains from connecting to your organization.</span></span> <span data-ttu-id="54c56-143">そのためには、ブロックされたドメインの一覧にドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="54c56-143">To do this, add the domain to the list of blocked domains.</span></span>


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="54c56-144">ブロックされたドメインの一覧に外部ドメインを追加するには</span><span class="sxs-lookup"><span data-stu-id="54c56-144">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="54c56-145">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="54c56-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2.  <span data-ttu-id="54c56-146">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="54c56-146">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3.  <span data-ttu-id="54c56-147">左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c56-147">In the left navigation bar, click **External User Access**.</span></span>
4.  <span data-ttu-id="54c56-148">[**フェデレーションドメイン**] をクリックし、[**新規作成**] をクリックして、[**禁止ドメイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c56-148">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>
5.  <span data-ttu-id="54c56-149">**新しいフェデレーションドメイン**で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="54c56-149">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="54c56-150">[ **Domain name (または FQDN)**] に、ブロックするフェデレーションパートナードメインの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="54c56-150">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>

        > [!NOTE]  
        > <span data-ttu-id="54c56-151">名前の長さは、256文字以下にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="54c56-151">The name cannot exceed 256 characters in length.</span></span><BR><br><span data-ttu-id="54c56-152">フェデレーションパートナーのドメイン名での検索では、サフィックス一致が実行されます。</span><span class="sxs-lookup"><span data-stu-id="54c56-152">The search on the federated partner domain name performs a suffix match.</span></span> <span data-ttu-id="54c56-153">たとえば、 **contoso.com**と入力すると、検索によってドメイン**it.contoso.com**も返されます。</span><span class="sxs-lookup"><span data-stu-id="54c56-153">For example, if you type **contoso.com**, the search will also return the domain **it.contoso.com**.</span></span><BR><br><span data-ttu-id="54c56-154">フェデレーションパートナードメインは、同時にブロックおよび許可することはできません。</span><span class="sxs-lookup"><span data-stu-id="54c56-154">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="54c56-155">Skype for Business Server では、リストを同期する必要がないように、この問題を回避することができます。</span><span class="sxs-lookup"><span data-stu-id="54c56-155">Skype for Business Server prevents this from happening so that you do not have to sync up your lists.</span></span>
   
      - <span data-ttu-id="54c56-156">省略[**コメント**] に、この構成について他のシステム管理者と共有する情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="54c56-156">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="54c56-157">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c56-157">Click **Commit**.</span></span>
7.  <span data-ttu-id="54c56-158">ブロックするフェデレーションパートナーごとに、手順 4 ~ 6 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="54c56-158">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="54c56-159">フェデレーションされたユーザーアクセスを有効にするには、組織でフェデレーションされたユーザーアクセスのサポートを有効にする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="54c56-159">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="54c56-160">詳細について[は、「リモートユーザーアクセスを有効または無効](../access-edge/enable-or-disable-remote-user-access.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54c56-160">For details, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="54c56-161">さらに、フェデレーションされたユーザーと共同作業できるようにするユーザーにポリシーを構成して適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54c56-161">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="54c56-162">詳しくは、「フェデレーションされた[ユーザーアクセスを制御するためのポリシーを構成する](../external-access-policies/configure-policies-to-control-federated-user-access.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="54c56-162">For details, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="54c56-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="54c56-163">See Also</span></span>

[<span data-ttu-id="54c56-164">フェデレーション ユーザー アクセスを制御するポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="54c56-164">Configure policies to control federated user access</span></span>](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[<span data-ttu-id="54c56-165">フェデレーションおよびパブリック IM 接続の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="54c56-165">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[<span data-ttu-id="54c56-166">フェデレーション パートナーの検出の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="54c56-166">Enable or disable discovery of federation partners</span></span>](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

