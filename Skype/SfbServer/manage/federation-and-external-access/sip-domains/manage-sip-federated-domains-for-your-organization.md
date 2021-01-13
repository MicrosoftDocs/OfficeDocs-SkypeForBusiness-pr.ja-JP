---
title: 組織の SIP フェデレーション ドメインの管理
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
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
description: フェデレーションを行える SIP ドメインを管理および構成する方法について学習します。
ms.openlocfilehash: 7b04225542387d52a36533c9639b02f773731e9f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817217"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="a607b-103">Skype for Business Server で組織の SIP フェデレーション ドメインを管理する</span><span class="sxs-lookup"><span data-stu-id="a607b-103">Manage SIP federated domains for your organization in Skype for Business Server</span></span>


<span data-ttu-id="a607b-104">フェデレーションを行うことができる SIP ドメインを管理および構成する場合、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="a607b-104">To manage and configure SIP domains that you can federate with, you can do the following:</span></span>

  - <span data-ttu-id="a607b-105">SIP フェデレーション パートナー ドメインの許可されたドメイン リストを作成または編集する</span><span class="sxs-lookup"><span data-stu-id="a607b-105">Create or edit an allowed domain list of SIP federated partner domains.</span></span>

  - <span data-ttu-id="a607b-106">SIP フェデレーション ドメインの禁止ドメイン リストを作成または編集する</span><span class="sxs-lookup"><span data-stu-id="a607b-106">Create or edit a blocked domain list of SIP federated domains.</span></span>

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a><span data-ttu-id="a607b-107">Skype for Business Server で許可された外部ドメインのサポートを構成する</span><span class="sxs-lookup"><span data-stu-id="a607b-107">Configure support for allowed external domains in Skype for Business Server</span></span>

<span data-ttu-id="a607b-108">フェデレーション パートナーのサポートを構成している場合は、組織とフェデレーションできる特定のドメインを管理できます。</span><span class="sxs-lookup"><span data-stu-id="a607b-108">If you have configured support for federated partners, you can manage which specific domains can federate with your organization.</span></span> <span data-ttu-id="a607b-109">1 つ以上の特定の外部ドメインを許可されたフェデレーション ドメインとして構成します。</span><span class="sxs-lookup"><span data-stu-id="a607b-109">You configure one or more specific external domains as allowed federated domains.</span></span> <span data-ttu-id="a607b-110">これを行うには、許可されたドメインの一覧に各ドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="a607b-110">To do this, add each domain to the list of allowed domains.</span></span> <span data-ttu-id="a607b-111">組織でパートナー検出が有効になっている場合でも、ドメインが 1,000 を超えるユーザーと通信する必要があるフェデレーション パートナーである場合や、1 秒あたり 20 件を超えるメッセージを送信する必要がある場合は、この操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a607b-111">Even if partner discovery is enabled for your organization, do this if the domain is a federated partner that might need to communicate with more than 1,000 of your users or might need to send more than 20 messages per second.</span></span> <span data-ttu-id="a607b-112">組織でパートナーの検出が有効になっていない場合、許可されたドメインの一覧に追加した外部ドメインのユーザーだけが、組織内のユーザーとの IM および会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="a607b-112">If partner discovery is not enabled for your organization, only users of external domains that you add to the allowed domains list can participate in IM and conferencing with users in your organization.</span></span> <span data-ttu-id="a607b-113">フェデレーション ドメインのアクセスを、フェデレーション パートナーのアクセス エッジ サービスを実行している特定のサーバーに制限する場合は、許可されたドメインの一覧で、各ドメインのアクセス エッジ サービスを実行しているサーバーのドメイン名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a607b-113">If you want to restrict access for a federated domain to a specific server running the Access Edge service of the federated partner, you can specify the domain name of the server running the Access Edge service for each domain in the list of allowed domains.</span></span>

> [!NOTE]  
> <span data-ttu-id="a607b-114">この手順では、特定のドメインのサポートを構成する方法について説明しますが、フェデレーション ユーザーのサポートを実装するには、組織のフェデレーション ユーザーのサポートを有効にし、フェデレーション ユーザーと共同作業できるユーザーを制御するポリシーを構成および適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a607b-114">This procedure describes how to configure support for specific domains, but implementing support for federated users also requires that you enable support for federated users for your organization, and configure and apply policies to control which users can collaborate with federated users.</span></span> <span data-ttu-id="a607b-115">フェデレーション ユーザーのサポートを有効にする方法の詳細については、「リモート ユーザー アクセスを有効または無効にする」 [を参照してください](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="a607b-115">For details about enabling support for federated users, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span> <span data-ttu-id="a607b-116">フェデレーションを制御するポリシーの構成の詳細については、「フェデレーション ユーザー アクセスを制御するポリシーを構成 [する」を参照してください](../external-access-policies/configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="a607b-116">For details about configuring policies to control federation, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a><span data-ttu-id="a607b-117">許可されたドメインの一覧に外部ドメインを追加するには</span><span class="sxs-lookup"><span data-stu-id="a607b-117">To add an external domain to the list of allowed domains</span></span>

1.  <span data-ttu-id="a607b-118">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a607b-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2.  <span data-ttu-id="a607b-119">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a607b-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3.  <span data-ttu-id="a607b-120">左側のナビゲーション バーで、[外部ユーザー アクセス **] を** クリックし、[フェデレーション ドメイン] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="a607b-120">In the left navigation bar, click **External User Access**, and then click **Federated Domains**.</span></span>
4.  <span data-ttu-id="a607b-121">[フェデレーション **ドメイン] ページで、[** 新規] **をクリックし**、[許可されたドメイン] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="a607b-121">On the **Federated Domains** page, click **New**, and then click **Allowed domain**.</span></span>
5.  <span data-ttu-id="a607b-122">[**新規フェデレーション ドメイン**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a607b-122">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="a607b-123">[ **ドメイン名 ( FQDN) ]** に、フェデレーション パートナー ドメインの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a607b-123">In **Domain name (or FQDN)**, type the name of the federated partner domain.</span></span>       

        > [!NOTE]  
        > <span data-ttu-id="a607b-124">この名前は一意である必要があります。また、アクセス エッジ サービスを実行しているこのサーバーの許可ドメインとして存在することはできません。</span><span class="sxs-lookup"><span data-stu-id="a607b-124">This name must be unique and cannot already exist as an allowed domain for this server running the Access Edge service.</span></span> <span data-ttu-id="a607b-125">名前の長さは、最大 256 文字です。</span><span class="sxs-lookup"><span data-stu-id="a607b-125">The name cannot exceed 256 characters in length.</span></span><BR><br><span data-ttu-id="a607b-p104">フェデレーション パートナー ドメインの名前についての検索では、サフィックスの一致が実行されます。たとえば、**contoso.com** と入力すると、検索によりドメイン **it.contoso.com** も戻されます。</span><span class="sxs-lookup"><span data-stu-id="a607b-p104">The search on the federated partner domain name performs a suffix match. For example, if you type **contoso.com**, the search will also return the domain **it.contoso.com**.</span></span><BR><br><span data-ttu-id="a607b-128">フェデレーション パートナー ドメインを同時に禁止および許可することはできません。</span><span class="sxs-lookup"><span data-stu-id="a607b-128">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="a607b-129">Skype for Business Server では、この問題が発生しないので、リストを同期する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a607b-129">Skype for Business Server prevents this from happening so that you do not have to sync up your lists.</span></span>
    
      - <span data-ttu-id="a607b-130">このフェデレーション ドメインのアクセスを、アクセス エッジ サービスを実行している特定のサーバーのユーザーに制限する場合は、アクセス エッジ サービス **(FQDN)** で、アクセス エッジ サービスを実行しているフェデレーション ドメインのサーバーの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="a607b-130">If you want to restrict access for this federated domain to users of a specific server running the Access Edge service, in **Access Edge service (FQDN)**, type the FQDN of the federated domain’s server running the Access Edge service.</span></span>    
      - <span data-ttu-id="a607b-131">追加情報を提供する場合は **、Comment** に、この構成に関して他のシステム管理者と共有する情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="a607b-131">If you want to provide additional information, in **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="a607b-132">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a607b-132">Click **Commit**.</span></span>
7.  <span data-ttu-id="a607b-133">許可するフェデレーション パートナー ドメインごとに、手順 4. ~ 6. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a607b-133">Repeat steps 4 through 6 for each federated partner domain that you want to allow.</span></span>

<span data-ttu-id="a607b-134">フェデレーション ユーザー アクセスを有効にするには、組織でフェデレーション ユーザー アクセスのサポートも有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a607b-134">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="a607b-135">詳細については、「リモート ユーザー [アクセスを有効または無効にする」を参照してください](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="a607b-135">For details, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="a607b-136">また、ポリシーを構成して、フェデレーション ユーザーと共同作業できるようにするユーザーに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a607b-136">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="a607b-137">詳細については、「フェデレーション ユーザー [アクセスを制御するポリシーを構成する」を参照してください](../external-access-policies/configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="a607b-137">For details, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a><span data-ttu-id="a607b-138">Skype for Business Server でブロックされた外部ドメインのサポートを構成する</span><span class="sxs-lookup"><span data-stu-id="a607b-138">Configure support for blocked external domains in Skype for Business Server</span></span> 

<span data-ttu-id="a607b-139">フェデレーション パートナーに対するサポートが構成されている場合、組織とのフェデレーションを禁止するドメインを管理できます。</span><span class="sxs-lookup"><span data-stu-id="a607b-139">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="a607b-140">このオプションが有効な場合は、禁止されているドメインの一覧は禁止リスト (許可されていない明示的なエントリの一覧) として機能し、フェデレーション ドメインの検出時に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a607b-140">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="a607b-141">詳細については、「フェデレーション パートナー [の検出を有効または無効にする」を参照してください](../access-edge/enable-or-disable-discovery-of-federation-partners.md)。</span><span class="sxs-lookup"><span data-stu-id="a607b-141">For details, see [Enable or disable discovery of federation partners](../access-edge/enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="a607b-p109">1 つまたは複数の外部ドメインの組織への接続を禁止します。この構成を実行するには、ドメインを禁止ドメインの一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="a607b-p109">Block one or more external domains from connecting to your organization. To do this, add the domain to the list of blocked domains.</span></span>


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="a607b-144">外部ドメインを禁止ドメインの一覧に追加するには</span><span class="sxs-lookup"><span data-stu-id="a607b-144">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="a607b-145">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a607b-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2.  <span data-ttu-id="a607b-146">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a607b-146">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3.  <span data-ttu-id="a607b-147">左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a607b-147">In the left navigation bar, click **External User Access**.</span></span>
4.  <span data-ttu-id="a607b-148">[**フェデレーション ドメイン**] をクリックし、[**新規**] をクリックし、[**禁止ドメイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a607b-148">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>
5.  <span data-ttu-id="a607b-149">[**新規フェデレーション ドメイン**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a607b-149">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="a607b-150">[**ドメイン名 (または FQDN)**] で、禁止するフェデレーション パートナー ドメインの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a607b-150">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>

        > [!NOTE]  
        > <span data-ttu-id="a607b-151">名前の長さは、最大 256 文字です。</span><span class="sxs-lookup"><span data-stu-id="a607b-151">The name cannot exceed 256 characters in length.</span></span><BR><br><span data-ttu-id="a607b-p110">フェデレーション パートナー ドメインの名前についての検索では、サフィックスの一致が実行されます。たとえば、**contoso.com** と入力すると、検索によりドメイン **it.contoso.com** も戻されます。</span><span class="sxs-lookup"><span data-stu-id="a607b-p110">The search on the federated partner domain name performs a suffix match. For example, if you type **contoso.com**, the search will also return the domain **it.contoso.com**.</span></span><BR><br><span data-ttu-id="a607b-154">フェデレーション パートナー ドメインを同時に禁止および許可することはできません。</span><span class="sxs-lookup"><span data-stu-id="a607b-154">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="a607b-155">Skype for Business Server では、この問題が発生しないので、リストを同期する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a607b-155">Skype for Business Server prevents this from happening so that you do not have to sync up your lists.</span></span>
   
      - <span data-ttu-id="a607b-156">(オプション) [**コメント**] で、この構成について他のシステム管理者と共有する必要のある情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="a607b-156">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="a607b-157">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a607b-157">Click **Commit**.</span></span>
7.  <span data-ttu-id="a607b-158">禁止するフェデレーション パートナーごとに、ステップ 4 ～ 6 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a607b-158">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="a607b-159">フェデレーション ユーザー アクセスを有効にするには、組織でフェデレーション ユーザー アクセスのサポートも有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a607b-159">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="a607b-160">詳細については、「リモート ユーザー [アクセスを有効または無効にする」を参照してください](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="a607b-160">For details, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="a607b-161">また、ポリシーを構成して、フェデレーション ユーザーと共同作業できるようにするユーザーに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a607b-161">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="a607b-162">詳細については、「フェデレーション ユーザー [アクセスを制御するポリシーを構成する」を参照してください](../external-access-policies/configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="a607b-162">For details, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="a607b-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="a607b-163">See Also</span></span>

[<span data-ttu-id="a607b-164">フェデレーション ユーザー アクセスを制御するポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="a607b-164">Configure policies to control federated user access</span></span>](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[<span data-ttu-id="a607b-165">フェデレーションおよびパブリック IM 接続の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="a607b-165">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[<span data-ttu-id="a607b-166">フェデレーション パートナーの検出の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="a607b-166">Enable or disable discovery of federation partners</span></span>](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

