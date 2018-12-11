---
title: 組織の SIP フェデレーション ドメインの管理
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 管理し、フェデレーションを行うことができます SIP ドメインを構成する方法について説明します。
ms.openlocfilehash: 565971ccf5cd4cbf62f08acc91e15f9615d350f7
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223088"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="7fd88-103">ビジネス サーバー用の Skype で、組織のフェデレーションする SIP ドメインを管理します。</span><span class="sxs-lookup"><span data-stu-id="7fd88-103">Manage SIP federated domains for your organization in Skype for Business Server</span></span>


<span data-ttu-id="7fd88-104">管理し、構成の SIP ドメインとフェデレーションを行うことができますが、するには、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7fd88-104">To manage and configure SIP domains that you can federate with, you can do the following:</span></span>

  - <span data-ttu-id="7fd88-105">作成または SIP のフェデレーション パートナーのドメインのドメインが許可リストを編集します。</span><span class="sxs-lookup"><span data-stu-id="7fd88-105">Create or edit an allowed domain list of SIP federated partner domains.</span></span>

  - <span data-ttu-id="7fd88-106">作成またはフェデレーションする SIP ドメインのブロックされたドメインのリストを編集します。</span><span class="sxs-lookup"><span data-stu-id="7fd88-106">Create or edit a blocked domain list of SIP federated domains.</span></span>

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a><span data-ttu-id="7fd88-107">ビジネス サーバー用の Skype で許可された外部ドメインのサポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="7fd88-107">Configure support for allowed external domains in Skype for Business Server</span></span>

<span data-ttu-id="7fd88-108">フェデレーション パートナーのサポートを構成した場合は、組織とのフェデレーションがどの特定のドメインを管理できます。</span><span class="sxs-lookup"><span data-stu-id="7fd88-108">If you have configured support for federated partners, you can manage which specific domains can federate with your organization.</span></span> <span data-ttu-id="7fd88-109">1 つまたは複数の特定の外部ドメインを許可されたフェデレーション ドメインとして構成するとします。</span><span class="sxs-lookup"><span data-stu-id="7fd88-109">You configure one or more specific external domains as allowed federated domains.</span></span> <span data-ttu-id="7fd88-110">これを行うには、各ドメインを許可されるドメインの一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="7fd88-110">To do this, add each domain to the list of allowed domains.</span></span> <span data-ttu-id="7fd88-111">組織のパートナーの検出が有効な場合でも、ドメインが 1 秒あたり 20 のメッセージよりも、ユーザーの 1,000 を超えると通信する必要がありますまたは送信する必要がありますが、フェデレーション パートナーの場合は。</span><span class="sxs-lookup"><span data-stu-id="7fd88-111">Even if partner discovery is enabled for your organization, do this if the domain is a federated partner that might need to communicate with more than 1,000 of your users or might need to send more than 20 messages per second.</span></span> <span data-ttu-id="7fd88-112">パートナー検出が有効でない場合、組織の許可するドメイン] ボックスの一覧に追加した外部ドメインのユーザーだけが、組織内のユーザーと IM と会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="7fd88-112">If partner discovery is not enabled for your organization, only users of external domains that you add to the allowed domains list can participate in IM and conferencing with users in your organization.</span></span> <span data-ttu-id="7fd88-113">フェデレーション パートナーのアクセス エッジ サービスを実行して特定のサーバーにフェデレーション ドメインへのアクセスを制限する場合は、許可されるドメインの一覧でドメインごとに、アクセス エッジ サービスを実行するサーバーのドメイン名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7fd88-113">If you want to restrict access for a federated domain to a specific server running the Access Edge service of the federated partner, you can specify the domain name of the server running the Access Edge service for each domain in the list of allowed domains.</span></span>

> [!NOTE]  
> <span data-ttu-id="7fd88-114">この手順は、特定のドメインのサポートを構成する方法を説明していますが、フェデレーション ユーザーに対するサポートを実装することも、組織のフェデレーション ユーザーに対するサポートを有効にして設定しているユーザーがコントロールにポリシーを適用する必要があります。フェデレーション ユーザーと共同作業を行います。</span><span class="sxs-lookup"><span data-stu-id="7fd88-114">This procedure describes how to configure support for specific domains, but implementing support for federated users also requires that you enable support for federated users for your organization, and configure and apply policies to control which users can collaborate with federated users.</span></span> <span data-ttu-id="7fd88-115">フェデレーション ユーザーに対するサポートを有効にする方法の詳細[を有効にするかリモート ユーザー アクセスを無効にする](../access-edge/enable-or-disable-remote-user-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fd88-115">For details about enabling support for federated users, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span> <span data-ttu-id="7fd88-116">フェデレーションを制御するポリシーの構成に関する詳細については、[制御するポリシーを構成するユーザーのアクセスをフェデレーションする](../external-access-policies/configure-policies-to-control-federated-user-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fd88-116">For details about configuring policies to control federation, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a><span data-ttu-id="7fd88-117">外部ドメインを許可するドメインの一覧に追加するのには</span><span class="sxs-lookup"><span data-stu-id="7fd88-117">To add an external domain to the list of allowed domains</span></span>

1.  <span data-ttu-id="7fd88-118">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7fd88-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2.  <span data-ttu-id="7fd88-119">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="7fd88-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3.  <span data-ttu-id="7fd88-120">左側のナビゲーション ・ バーでは、**外部ユーザー アクセス**をクリックし、**フェデレーション ドメイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7fd88-120">In the left navigation bar, click **External User Access**, and then click **Federated Domains**.</span></span>
4.  <span data-ttu-id="7fd88-121">[**フェデレーション ドメイン**] ページで、[**新規**作成] をクリックし、**許可されたドメイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7fd88-121">On the **Federated Domains** page, click **New**, and then click **Allowed domain**.</span></span>
5.  <span data-ttu-id="7fd88-122">**新しいフェデレーション ドメイン**では、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7fd88-122">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="7fd88-123">**ドメイン名 (FQDN)** では、フェデレーション パートナーのドメインの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="7fd88-123">In **Domain name (or FQDN)**, type the name of the federated partner domain.</span></span>       

        > [!NOTE]  
        > <span data-ttu-id="7fd88-124">この名前は一意である必要があり、アクセス エッジ サービスを実行してこのサーバーで許可されているドメインとして存在できません。</span><span class="sxs-lookup"><span data-stu-id="7fd88-124">This name must be unique and cannot already exist as an allowed domain for this server running the Access Edge service.</span></span> <span data-ttu-id="7fd88-125">名前は、長さが 256 文字を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="7fd88-125">The name cannot exceed 256 characters in length.</span></span><BR><br><span data-ttu-id="7fd88-126">フェデレーション パートナーのドメイン名の検索では、サフィックスの一致を実行します。</span><span class="sxs-lookup"><span data-stu-id="7fd88-126">The search on the federated partner domain name performs a suffix match.</span></span> <span data-ttu-id="7fd88-127">たとえば、 **contoso.com**を入力する場合はも検索ドメイン**it.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="7fd88-127">For example, if you type **contoso.com**, the search will also return the domain **it.contoso.com**.</span></span><BR><br><span data-ttu-id="7fd88-128">フェデレーション パートナーのドメインのブロックおよび許可される同時にできません。</span><span class="sxs-lookup"><span data-stu-id="7fd88-128">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="7fd88-129">ビジネス サーバーの Skype できなくなりますこれがあるないように起こっているのか、リストを同期します。</span><span class="sxs-lookup"><span data-stu-id="7fd88-129">Skype for Business Server prevents this from happening so that you do not have to sync up your lists.</span></span>
    
      - <span data-ttu-id="7fd88-130">**アクセス エッジ サービス (FQDN)** で、アクセス エッジ サービスを実行している特定のサーバーのユーザーにこのフェデレーション ドメインへのアクセスを制限したい場合は、アクセス エッジ サービスを実行して、フェデレーション ドメインのサーバーの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="7fd88-130">If you want to restrict access for this federated domain to users of a specific server running the Access Edge service, in **Access Edge service (FQDN)**, type the FQDN of the federated domain’s server running the Access Edge service.</span></span>    
      - <span data-ttu-id="7fd88-131">追加情報を提供する場合は、**コメント**で、この構成については、他のシステム管理者と共有する情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="7fd88-131">If you want to provide additional information, in **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="7fd88-132">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7fd88-132">Click **Commit**.</span></span>
7.  <span data-ttu-id="7fd88-133">許可するフェデレーション パートナー ドメインごとに手順 4 ~ 6 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="7fd88-133">Repeat steps 4 through 6 for each federated partner domain that you want to allow.</span></span>

<span data-ttu-id="7fd88-134">フェデレーション ユーザー アクセスを有効にするも、組織でフェデレーション ユーザー アクセスのサポートを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fd88-134">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="7fd88-135">詳細については、[有効にするかリモート ユーザー アクセスを無効にする](../access-edge/enable-or-disable-remote-user-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fd88-135">For details, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="7fd88-136">さらに、構成し、フェデレーション ユーザーと共同作業を行うことができるようにするユーザーにポリシーを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fd88-136">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="7fd88-137">詳細については、[制御するポリシーを構成するユーザーのアクセスをフェデレーションする](../external-access-policies/configure-policies-to-control-federated-user-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fd88-137">For details, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a><span data-ttu-id="7fd88-138">ビジネス サーバー用の Skype でブロックされた外部ドメインのサポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="7fd88-138">Configure support for blocked external domains in Skype for Business Server</span></span> 

<span data-ttu-id="7fd88-139">フェデレーション パートナーのサポートを構成した場合は、組織とのフェデレーションを禁止するドメインがブロックされますを管理できます。</span><span class="sxs-lookup"><span data-stu-id="7fd88-139">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="7fd88-140">ブロックされたドメインの一覧は、ブロック リスト (リストの明示的なエントリを許可しないようにしている) として機能し、このオプションを有効にした場合に、フェデレーション ドメインの証拠開示に適用されます。</span><span class="sxs-lookup"><span data-stu-id="7fd88-140">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="7fd88-141">詳細については、[有効にするかフェデレーション パートナーの検出を無効にする](../access-edge/enable-or-disable-discovery-of-federation-partners.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fd88-141">For details, see [Enable or disable discovery of federation partners](../access-edge/enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="7fd88-142">組織への接続を 1 つまたは複数の外部ドメインをブロックします。</span><span class="sxs-lookup"><span data-stu-id="7fd88-142">Block one or more external domains from connecting to your organization.</span></span> <span data-ttu-id="7fd88-143">これを行うには、ブロックされたドメインの一覧にドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="7fd88-143">To do this, add the domain to the list of blocked domains.</span></span>


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="7fd88-144">外部ドメインを禁止するドメインの一覧に追加するのには</span><span class="sxs-lookup"><span data-stu-id="7fd88-144">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="7fd88-145">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7fd88-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2.  <span data-ttu-id="7fd88-146">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="7fd88-146">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3.  <span data-ttu-id="7fd88-147">左側のナビゲーション ・ バーで、 **[外部ユーザー アクセス**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7fd88-147">In the left navigation bar, click **External User Access**.</span></span>
4.  <span data-ttu-id="7fd88-148">**フェデレーション ドメイン**] をクリックして、[**新規**作成] をクリックし、[**禁止ドメイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7fd88-148">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>
5.  <span data-ttu-id="7fd88-149">**新しいフェデレーション ドメイン**では、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7fd88-149">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="7fd88-150">**ドメイン名 (FQDN)** では、禁止するフェデレーション パートナーのドメインの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="7fd88-150">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>

        > [!NOTE]  
        > <span data-ttu-id="7fd88-151">名前は、長さが 256 文字を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="7fd88-151">The name cannot exceed 256 characters in length.</span></span><BR><br><span data-ttu-id="7fd88-152">フェデレーション パートナーのドメイン名の検索では、サフィックスの一致を実行します。</span><span class="sxs-lookup"><span data-stu-id="7fd88-152">The search on the federated partner domain name performs a suffix match.</span></span> <span data-ttu-id="7fd88-153">たとえば、 **contoso.com**を入力する場合はも検索ドメイン**it.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="7fd88-153">For example, if you type **contoso.com**, the search will also return the domain **it.contoso.com**.</span></span><BR><br><span data-ttu-id="7fd88-154">フェデレーション パートナーのドメインのブロックおよび許可される同時にできません。</span><span class="sxs-lookup"><span data-stu-id="7fd88-154">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="7fd88-155">ビジネス サーバーの Skype できなくなりますこれがあるないように起こっているのか、リストを同期します。</span><span class="sxs-lookup"><span data-stu-id="7fd88-155">Skype for Business Server prevents this from happening so that you do not have to sync up your lists.</span></span>
   
      - <span data-ttu-id="7fd88-156">(省略可能)**コメント**] に、この構成については、他のシステム管理者と共有する情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="7fd88-156">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="7fd88-157">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7fd88-157">Click **Commit**.</span></span>
7.  <span data-ttu-id="7fd88-158">禁止するフェデレーション パートナーごとに手順 4 ~ 6 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="7fd88-158">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="7fd88-159">フェデレーション ユーザー アクセスを有効にするも、組織でフェデレーション ユーザー アクセスのサポートを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fd88-159">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="7fd88-160">詳細については、[有効にするかリモート ユーザー アクセスを無効にする](../access-edge/enable-or-disable-remote-user-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fd88-160">For details, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="7fd88-161">さらに、構成し、フェデレーション ユーザーと共同作業を行うことができるようにするユーザーにポリシーを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fd88-161">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="7fd88-162">詳細については、[制御するポリシーを構成するユーザーのアクセスをフェデレーションする](../external-access-policies/configure-policies-to-control-federated-user-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fd88-162">For details, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="7fd88-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="7fd88-163">See Also</span></span>

[<span data-ttu-id="7fd88-164">フェデレーション ユーザー アクセスを制御するポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="7fd88-164">Configure policies to control federated user access</span></span>](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[<span data-ttu-id="7fd88-165">フェデレーションおよびパブリック IM 接続の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="7fd88-165">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[<span data-ttu-id="7fd88-166">有効にするか、フェデレーション パートナーの検出を無効にします。</span><span class="sxs-lookup"><span data-stu-id="7fd88-166">Enable or disable discovery of federation partners</span></span>](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

