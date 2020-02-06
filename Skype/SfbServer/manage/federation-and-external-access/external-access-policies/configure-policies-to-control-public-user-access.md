---
title: パブリック ユーザー アクセスを制御するポリシーの構成
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
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
description: ublic インスタントメッセージング (IM) 接続を使うと、組織内のユーザーは IM を使用して、パブリック IM サービスプロバイダーによって提供される IM サービスのユーザーと通信することができます。
ms.openlocfilehash: d661ca9a4ef7840cbc955d0c999ae5a1490a63cb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818308"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a><span data-ttu-id="7c5b0-103">Skype for Business Server でのパブリックユーザーアクセスを制御するためのポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="7c5b0-103">Configure policies to control public user access in Skype for Business Server</span></span>

<span data-ttu-id="7c5b0-104">パブリックインスタントメッセージング (IM) 接続を使うと、組織内のユーザーは IM を使用して、パブリック IM サービスプロバイダーによって提供される IM サービスのユーザーと通信できます。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers.</span></span> <span data-ttu-id="7c5b0-105">パブリックユーザーが社内の Skype for Business Server ユーザーと共同作業できるかどうかを制御するために、1つ以上の外部ユーザーアクセスポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-105">You configure one or more external user access policies to control whether public users can collaborate with internal Skype for Business Server users.</span></span> <span data-ttu-id="7c5b0-106">パブリックインスタントメッセージング接続は、展開とユーザーの構成に依存する追加機能です。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="7c5b0-107">また、パブリック IM プロバイダーでのサービスのプロビジョニングにも依存します。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-107">It also depends on the provisioning of the service at the public IM provider.</span></span> 

<span data-ttu-id="7c5b0-108">パブリックユーザーアクセスを制御するために、グローバル、サイト、ユーザーレベルでポリシーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-108">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="7c5b0-109">1つのポリシーレベルで適用される Skype for Business Server のポリシー設定は、別のポリシーレベルで適用されている設定を上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-109">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="7c5b0-110">Skype for Business Server のポリシーの優先順位: ユーザーポリシー (ほとんどの影響) でサイトポリシーが上書きされ、サイトポリシーがグローバルポリシーを上書きします (最も影響が少なくなります)。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-110">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="7c5b0-111">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-111">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="7c5b0-112">IM 招待の場合、応答はクライアントソフトウェアによって異なります。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-112">In the case of IM invitations, the response depends on the client software.</span></span> <span data-ttu-id="7c5b0-113">外部の送信者が、ユーザーによって構成されたルールによって明示的にブロックされていない限り、要求は承認されます (つまり、ユーザーのクライアントの**許可**リストと**ブロック**リスト内の設定)。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-113">The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists).</span></span> <span data-ttu-id="7c5b0-114">さらに、ユーザーが**許可**リストにないユーザーからのすべての im をブロックすることにした場合、im 招待をブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-114">Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>



> [!NOTE]  
> <span data-ttu-id="7c5b0-115">組織のフェデレーションを有効にしていない場合でも、パブリックユーザーアクセスを制御するためのポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-115">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="7c5b0-116">ただし、構成したポリシーは、組織でフェデレーションが有効になっている場合にのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-116">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="7c5b0-117">フェデレーションを有効にする方法について詳しくは、「[リモートユーザーアクセスを有効または無効](../access-edge/enable-or-disable-remote-user-access.md)にする」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-117">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span> <span data-ttu-id="7c5b0-118">さらに、公開ユーザーアクセスを制御するユーザーポリシーを指定した場合、このポリシーは、Skype for Business Server が有効になっていて、ポリシーを使用するように構成されているユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-118">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span> <span data-ttu-id="7c5b0-119">Skype for Business Server にサインインできるパブリックユーザーの指定の詳細については、「[外部ユーザーアクセスポリシーの割り当て](assign-an-external-user-access-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-119">For details about specifying public users that can sign in to Skype for Business Server, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>


<span data-ttu-id="7c5b0-120">次の手順を使用して、1つ以上のパブリック IM プロバイダーのユーザーによるアクセスをサポートするポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-120">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="7c5b0-121">パブリックユーザーのアクセスをサポートするように外部アクセスポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="7c5b0-121">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="7c5b0-122">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7c5b0-123">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="7c5b0-124">左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**外部アクセスポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-124">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="7c5b0-125">[**外部アクセスポリシー** ] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-125">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="7c5b0-126">パブリックユーザーアクセスをサポートするようにグローバルポリシーを構成するには、グローバルポリシーをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-126">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="7c5b0-127">新しいサイトポリシーを作成するには、[**新規**作成] をクリックし、[**サイトポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-127">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="7c5b0-128">[**サイトの選択**] で、一覧から該当するサイトをクリックし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-128">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="7c5b0-129">新しいユーザーポリシーを作成するには、[**新規**作成] をクリックし、[**ユーザーポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-129">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="7c5b0-130">[**新しい外部アクセスポリシー**] で、[**名前**] フィールドに、ユーザーポリシーがどのようなものであるかを示す一意の名前を作成します (たとえば、パブリックユーザーの通信を可能にするユーザーポリシーの**enablepublicusers** )。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-130">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="7c5b0-131">既存のポリシーを変更するには、表に記載されている適切なポリシーをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-131">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7c5b0-132">省略説明を追加または編集する場合は、ポリシーの情報を [**説明**] で指定します。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-132">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="7c5b0-133">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-133">Do one of the following:</span></span>
    
      - <span data-ttu-id="7c5b0-134">ポリシーのパブリックユーザーアクセスを有効にするには、[**パブリックユーザーとの通信を有効**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-134">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="7c5b0-135">ポリシーのパブリックユーザーアクセスを無効にするには、[**パブリックユーザーとの通信を有効に**する] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-135">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="7c5b0-136">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-136">Click **Commit**.</span></span>

<span data-ttu-id="7c5b0-137">パブリックユーザーアクセスを有効にするには、組織のフェデレーションのサポートも有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-137">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="7c5b0-138">詳細については、「 [Skype For Business Server でフェデレーションされたユーザーアクセスを制御するためのポリシーを構成する](configure-policies-to-control-federated-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-138">For details, see [Configure policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="7c5b0-139">ユーザーポリシーの場合は、パブリックユーザーとの共同作業を可能にするパブリックユーザーにもポリシーを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c5b0-139">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> 


## <a name="see-also"></a><span data-ttu-id="7c5b0-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c5b0-140">See Also</span></span>

[<span data-ttu-id="7c5b0-141">組織の SIP フェデレーション プロバイダーの管理</span><span class="sxs-lookup"><span data-stu-id="7c5b0-141">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
