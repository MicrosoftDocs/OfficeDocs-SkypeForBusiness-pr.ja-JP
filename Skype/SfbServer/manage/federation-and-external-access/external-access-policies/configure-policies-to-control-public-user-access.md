---
title: パブリック ユーザー アクセスを制御するポリシーの構成
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ublic のインスタント メッセージング (IM) 接続では、パブリック IM サービス プロバイダーが提供する IM サービスのユーザーと通信するために IM を使用する、組織内のユーザーを使用できます。
ms.openlocfilehash: 8ad406957d50f44bd8cee9465549ff86af9a3e6b
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222871"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a><span data-ttu-id="2fbe7-103">ビジネス サーバーの Skype のパブリック ユーザー アクセスを制御するポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-103">Configure policies to control public user access in Skype for Business Server</span></span>

<span data-ttu-id="2fbe7-104">パブリック インスタント メッセージング (IM) の接続は、パブリック IM サービス プロバイダーが提供する IM サービスのユーザーと通信するために IM を使用する、組織内のユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers.</span></span> <span data-ttu-id="2fbe7-105">パブリックのユーザーがビジネスのサーバーのユーザーの内部の Skype で共同作業を行うかどうかは、コントロールに 1 つまたは複数の外部ユーザー アクセス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-105">You configure one or more external user access policies to control whether public users can collaborate with internal Skype for Business Server users.</span></span> <span data-ttu-id="2fbe7-106">パブリック インスタント メッセージング接続は、展開およびユーザーの構成に依存する追加機能です。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="2fbe7-107">パブリック IM プロバイダーのサービスの提供によっても異なります。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-107">It also depends on the provisioning of the service at the public IM provider.</span></span> 

<span data-ttu-id="2fbe7-108">パブリック ユーザー アクセスを制御するには、グローバル ポリシー、サイト、およびユーザー レベルを構成できます。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-108">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="2fbe7-109">Skype ビジネスのサーバーのポリシー設定が 1 つのポリシー レベルで適用されるは、別のポリシー レベルで適用される設定をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-109">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="2fbe7-110">ビジネス サーバー ポリシーの優先順位の Skype が: ユーザー ポリシー (ほとんどの影響) がサイト ポリシーを上書きし、[サイト ポリシーはグローバル ポリシー (最低限の影響) をよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-110">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="2fbe7-111">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-111">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="2fbe7-112">IM の招待の場合は、応答は、クライアント ・ ソフトウェアに依存します。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-112">In the case of IM invitations, the response depends on the client software.</span></span> <span data-ttu-id="2fbe7-113">(つまり、ユーザーのクライアントの**許可**の設定、**ブロック**リスト) は、ユーザーが設定したルールで、外部の送信者が明示的にブロックされている場合を除き、要求を承諾します。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-113">The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists).</span></span> <span data-ttu-id="2fbe7-114">また、ユーザー本人の**許可**リストに登録されていないユーザーからのすべての IM をブロックする場合は、IM 招待をブロックできます。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-114">Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>



> [!NOTE]  
> <span data-ttu-id="2fbe7-115">組織のフェデレーションが有効にしない場合でも、パブリック ユーザー アクセスを制御するポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-115">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="2fbe7-116">ただし、構成したポリシーは、フェデレーションの組織に対して有効である場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-116">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="2fbe7-117">フェデレーションを有効にする方法の詳細[を有効にするかリモート ユーザー アクセスを無効にする](../access-edge/enable-or-disable-remote-user-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-117">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span> <span data-ttu-id="2fbe7-118">また、パブリック ユーザー アクセスを制御するユーザー ポリシーを指定する場合は、Business Server の Skype を有効にしてポリシーを使用するように構成されているユーザーにのみ、ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-118">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span> <span data-ttu-id="2fbe7-119">ビジネス サーバーの Skype にサインインできるパブリック ユーザーの指定の詳細については、[外部ユーザー アクセス ポリシーを割り当てる](assign-an-external-user-access-policy.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-119">For details about specifying public users that can sign in to Skype for Business Server, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>


<span data-ttu-id="2fbe7-120">1 つまたは複数のパブリック IM プロバイダーのユーザーによるアクセスをサポートするためにポリシーを構成するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-120">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="2fbe7-121">パブリック ユーザー アクセスをサポートする外部アクセス ポリシーを構成するのには</span><span class="sxs-lookup"><span data-stu-id="2fbe7-121">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="2fbe7-122">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2fbe7-123">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2fbe7-124">左側のナビゲーション ・ バーでは、**外部ユーザー アクセス**をクリックし、**外部アクセス ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-124">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="2fbe7-125">[**外部アクセス ポリシー** ] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-125">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="2fbe7-126">パブリック ユーザー アクセスをサポートするグローバル ポリシーを構成するには、グローバル ポリシーをクリックして**編集**を**の詳細を表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-126">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="2fbe7-127">新しいサイト ポリシーを作成、[**新規**作成] をクリックし、[**サイト ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-127">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="2fbe7-128">] で**サイトを選択して**、リストから適切なサイトをし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-128">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="2fbe7-129">新しいユーザー ポリシーを作成するには、[**新規**作成] をクリックし、[**ユーザー ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-129">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="2fbe7-130">**新しい外部アクセス ポリシー**では、どのユーザー ポリシーは (たとえば、パブリック ユーザーの通信を有効にするユーザー ポリシーの**EnablePublicUsers** ) を示す [**名**] フィールドに一意の名前を作成します。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-130">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="2fbe7-131">既存のポリシーを変更するには、表に記載されている適切なポリシー] をクリック**を編集**するには、**の詳細を表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-131">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="2fbe7-132">(省略可能)追加または説明を編集する場合は、 **[説明**] にポリシーの情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-132">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="2fbe7-133">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-133">Do one of the following:</span></span>
    
      - <span data-ttu-id="2fbe7-134">ポリシーのパブリック ユーザー アクセスを有効にするには、**パブリック ユーザーとの通信を有効にする**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-134">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="2fbe7-135">ポリシーのパブリック ユーザー アクセスを無効にするには、**パブリック ユーザーとの通信を有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-135">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="2fbe7-136">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-136">Click **Commit**.</span></span>

<span data-ttu-id="2fbe7-137">パブリック ユーザー アクセスを有効にするには、また組織でフェデレーションのサポートを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-137">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="2fbe7-138">詳細については、[制御するポリシーを構成する Skype のビジネス サーバーでユーザーのアクセスをフェデレーションする](configure-policies-to-control-federated-user-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-138">For details, see [Configure policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="2fbe7-139">ユーザー ポリシーの場合は、パブリック ユーザーと共同作業を行うことができるパブリックのユーザーにポリシーを適用する必要がありますもします。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-139">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> 


## <a name="see-also"></a><span data-ttu-id="2fbe7-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="2fbe7-140">See Also</span></span>

[<span data-ttu-id="2fbe7-141">組織のフェデレーションの SIP プロバイダーを管理します。</span><span class="sxs-lookup"><span data-stu-id="2fbe7-141">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
