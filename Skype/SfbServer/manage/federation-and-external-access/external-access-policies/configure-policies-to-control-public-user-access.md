---
title: パブリック ユーザー アクセスを制御するポリシーの構成
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
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
description: インスタント メッセージング (IM) 接続を使用すると、組織内のユーザーは IM を使用して、パブリック IM サービス プロバイダーが提供する IM サービスのユーザーと通信できます。
ms.openlocfilehash: 28bb1c94cb42068fe99f07a6608a3ac1c50991ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823593"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a><span data-ttu-id="79507-103">Skype for Business Server でパブリック ユーザー アクセスを制御するポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="79507-103">Configure policies to control public user access in Skype for Business Server</span></span>

<span data-ttu-id="79507-104">パブリック インスタント メッセージング (IM) 接続により、組織内のユーザーは IM を使用して、パブリック IM サービス プロバイダーが提供する IM サービスのユーザーと通信できます。</span><span class="sxs-lookup"><span data-stu-id="79507-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers.</span></span> <span data-ttu-id="79507-105">パブリック ユーザーが内部の Skype for Business Server ユーザーと共同作業できるかどうかを制御するために、1 つ以上の外部ユーザー アクセス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="79507-105">You configure one or more external user access policies to control whether public users can collaborate with internal Skype for Business Server users.</span></span> <span data-ttu-id="79507-106">パブリック インスタント メッセージング接続は、展開およびユーザーの構成に依存する追加機能です。</span><span class="sxs-lookup"><span data-stu-id="79507-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="79507-107">この機能は、パブリック IM プロバイダーでのサービスのプロビジョニングにも依存します。</span><span class="sxs-lookup"><span data-stu-id="79507-107">It also depends on the provisioning of the service at the public IM provider.</span></span> 

<span data-ttu-id="79507-108">パブリック ユーザー アクセスを制御するには、グローバル レベル、サイト レベル、およびユーザー レベルでポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="79507-108">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="79507-109">1 つのポリシー レベルで適用される Skype for Business Server ポリシー設定は、別のポリシー レベルで適用される設定を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="79507-109">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="79507-110">Skype for Business Server ポリシーの優先順位: ユーザー ポリシー (最も高い) はサイト ポリシーをオーバーライドし、サイト ポリシーはグローバル ポリシーをオーバーライド (最も低い) します。</span><span class="sxs-lookup"><span data-stu-id="79507-110">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="79507-111">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="79507-111">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="79507-p103">IM の招待の場合は、クライアント ソフトウェアによって応答が異なります。 ユーザーが構成したルール (ユーザーのクライアントの [**許可**] および [**禁止**] リストの設定) によって、外部の送信者が明示的に禁止されている場合以外は、要求が受け入れられます。 また、[**許可**] リストに含まれていないユーザーからの IM はすべて禁止することを選択すると、IM の招待をブロックできます。</span><span class="sxs-lookup"><span data-stu-id="79507-p103">In the case of IM invitations, the response depends on the client software. The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists). Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>



> [!NOTE]  
> <span data-ttu-id="79507-115">組織でフェデレーションを有効にしていなくても、パブリック ユーザー アクセスを制御するポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="79507-115">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="79507-116">ただし構成するポリシーは、組織でフェデレーションを有効にした場合にのみ有効となります。</span><span class="sxs-lookup"><span data-stu-id="79507-116">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="79507-117">フェデレーションを有効にする方法の詳細については、「リモート ユーザー アクセスを [有効または無効にする」を参照してください](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="79507-117">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span> <span data-ttu-id="79507-118">さらに、パブリック ユーザー アクセスを制御するユーザー ポリシーを指定した場合、このポリシーは、Skype for Business Server が有効で、ポリシーを使用するように構成されているユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="79507-118">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span> <span data-ttu-id="79507-119">Skype for Business Server にサインインできるパブリック ユーザーの指定の詳細については、「外部ユーザー アクセス ポリシーを割り当てる [」を参照してください](assign-an-external-user-access-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="79507-119">For details about specifying public users that can sign in to Skype for Business Server, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>


<span data-ttu-id="79507-120">以下の手順を使用して、1 つ以上のパブリック IM プロバイダーのユーザーによるアクセスをサポートするポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="79507-120">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="79507-121">パブリック ユーザー アクセスをサポートするように外部アクセス ポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="79507-121">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="79507-122">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="79507-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="79507-123">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="79507-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="79507-124">左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79507-124">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="79507-125">[**外部アクセス ポリシー**] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="79507-125">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="79507-126">パブリック ユーザー アクセスをサポートするようにグローバル ポリシーを構成するには、グローバル ポリシーをクリックし、[**編集**]、[**詳細の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="79507-126">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="79507-p105">新しいサイト ポリシーを作成するには、[**新規作成**] をクリックし、[**サイト ポリシー**] をクリックします。 [**サイトの選択**] で一覧から適切なサイトをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79507-p105">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="79507-p106">新しいユーザー ポリシーを作成するには、[**新規作成**] をクリックし、[**ユーザー ポリシー**] をクリックします。 [**新しい外部アクセス ポリシー**] の [**名前**] フィールドで、ユーザー ポリシーの適用範囲を示す一意の名前を作成します (たとえば、パブリック ユーザーの通信を有効にするユーザー ポリシーの場合、**EnablePublicUsers** という名前を作成します)。</span><span class="sxs-lookup"><span data-stu-id="79507-p106">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="79507-131">既存のポリシーを変更するには、表に表示されている適切なポリシーをクリックし、[**編集**]、[**詳細の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="79507-131">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="79507-132">(オプション) 説明を追加または編集する場合は、[**説明**] でポリシーの情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="79507-132">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="79507-133">次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="79507-133">Do one of the following:</span></span>
    
      - <span data-ttu-id="79507-134">ポリシーのパブリック ユーザー アクセスを有効にするには、[**パブリック ユーザーとの通信を有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="79507-134">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="79507-135">ポリシーのパブリック ユーザー アクセスを無効にするには、[**パブリック ユーザーとの通信を有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="79507-135">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="79507-136">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79507-136">Click **Commit**.</span></span>

<span data-ttu-id="79507-137">パブリック ユーザー アクセスを有効にするには、組織でフェデレーションのサポートも有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="79507-137">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="79507-138">詳細については [、「Configure policies to control federated user access in Skype for Business Server 」を参照してください](configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="79507-138">For details, see [Configure policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="79507-139">これがユーザー ポリシーの場合、パブリック ユーザーと共同作業できるようにするパブリック ユーザーに対してもポリシーを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79507-139">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> 


## <a name="see-also"></a><span data-ttu-id="79507-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="79507-140">See Also</span></span>

[<span data-ttu-id="79507-141">組織の SIP フェデレーション プロバイダーの管理</span><span class="sxs-lookup"><span data-stu-id="79507-141">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
