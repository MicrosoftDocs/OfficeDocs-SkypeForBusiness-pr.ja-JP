---
title: リモート ユーザー アクセスを制御するポリシーの構成
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
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
description: リモートユーザーが社内の Skype for Business Server ユーザーと共同作業できるかどうかを制御するために、1つ以上の外部ユーザーアクセスポリシーを構成します。 リモートユーザーアクセスを制御するには、グローバル、サイト、ユーザーレベルでポリシーを構成することができます。
ms.openlocfilehash: 7735f15e61654f55a70f18ca032cd6b1613fec58
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818298"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="9fbc3-104">Skype for Business Server でリモートユーザーのアクセスを制御するためのポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="9fbc3-104">Configure policies to control remote user access in Skype for Business Server</span></span>

<span data-ttu-id="9fbc3-105">リモートユーザーが社内の Skype for Business Server ユーザーと共同作業できるかどうかを制御するために、1つ以上の外部ユーザーアクセスポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-105">You configure one or more external user access policies to control whether remote users can collaborate with internal Skype for Business Server users.</span></span> <span data-ttu-id="9fbc3-106">リモートユーザーアクセスを制御するには、グローバル、サイト、ユーザーレベルでポリシーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-106">To control remote user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="9fbc3-107">サイトポリシーはグローバルポリシーを上書きし、ユーザーポリシーはサイトとグローバルポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-107">Site policies override the global policy, and user policies override site and global policies.</span></span> <span data-ttu-id="9fbc3-108">構成できるポリシーの種類の詳細については、「 [Skype For Business Server のフェデレーションと外部アクセスを管理](../managing-federation-and-external-access.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-108">For details about the types of policies that you can configure, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span> <span data-ttu-id="9fbc3-109">1つのポリシーレベルで適用される Skype for Business Server のポリシー設定は、別のポリシーレベルで適用されている設定を上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-109">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="9fbc3-110">Skype for Business Server のポリシーの優先順位: ユーザーポリシー (ほとんどの影響) でサイトポリシーが上書きされ、サイトポリシーがグローバルポリシーを上書きします (最も影響が少なくなります)。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-110">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="9fbc3-111">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-111">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

> [!NOTE]  
> <span data-ttu-id="9fbc3-112">組織のリモートユーザーアクセスを有効にしていない場合でも、リモートユーザーアクセスを制御するポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-112">You can configure policies to control remote user access, even if you have not enabled remote user access for your organization.</span></span> <span data-ttu-id="9fbc3-113">ただし、構成したポリシーは、組織のリモートユーザーアクセスが有効になっている場合にのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-113">However, the policies that you configure are in effect only when you have remote user access enabled for your organization.</span></span> <span data-ttu-id="9fbc3-114">さらに、リモートユーザーアクセスを制御するユーザーポリシーを指定した場合、このポリシーは、Skype for Business Server が有効になっていて、ポリシーを使用するように構成されているユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-114">Additionally, if you specify a user policy to control remote user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span> <span data-ttu-id="9fbc3-115">リモートの場所から Skype for Business Server にサインインできるユーザーを指定する方法について詳しくは、「[外部ユーザーアクセスポリシーを割り当てる](assign-an-external-user-access-policy.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-115">For details about specifying users that can sign in to Skype for Business Server from remote locations, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

<span data-ttu-id="9fbc3-116">リモートユーザーアクセスを制御するために使用する外部アクセスポリシーをそれぞれ構成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-116">Use the following procedure to configure each external access policy that you want to use to control remote user access.</span></span>


> [!NOTE]  
> <span data-ttu-id="9fbc3-117">この手順では、リモートユーザーとの通信を可能にするようにポリシーを構成する方法について説明します。ただし、リモートユーザーアクセスをサポートするように構成した各ポリシーでは、フェデレーションされたユーザーアクセスとパブリックユーザーアクセスを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-117">This procedure describes how to configure a policy only to enable communications with remote users, but each policy that you configure to support remote user access can also configure federated user access and public user access.</span></span> <span data-ttu-id="9fbc3-118">フェデレーションユーザーをサポートするためのポリシーの構成の詳細については、「 [Skype For Business Server でフェデレーションされたユーザーアクセスを制御するためのポリシーを構成する](configure-policies-to-control-federated-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-118">For details about configuring policies to support federated users, see [Configure policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md).</span></span> <span data-ttu-id="9fbc3-119">パブリックユーザーをサポートするためのポリシーの構成の詳細については、「 [Skype For Business Server で組織の SIP フェデレーションプロバイダーを管理](../sip-providers/manage-sip-federated-providers-for-your-organization.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-119">For details about configuring policies to support public users, see [Manage SIP federated providers for your organization in Skype for Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a><span data-ttu-id="9fbc3-120">外部アクセスポリシーを構成してリモートユーザーのアクセスをサポートするには</span><span class="sxs-lookup"><span data-stu-id="9fbc3-120">To configure an external access policy to support remote user access</span></span>

1.  <span data-ttu-id="9fbc3-121">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-121">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9fbc3-122">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-122">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9fbc3-123">左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**外部アクセスポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-123">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="9fbc3-124">[**外部アクセスポリシー** ] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-124">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="9fbc3-125">リモートユーザーアクセスをサポートするようにグローバルポリシーを構成するには、グローバルポリシーをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-125">To configure the global policy to support remote user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="9fbc3-126">新しいサイトポリシーを作成するには、[**新規**作成] をクリックし、[**サイトポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-126">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="9fbc3-127">[**サイトの選択**] で、一覧から該当するサイトをクリックし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-127">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="9fbc3-128">新しいユーザーポリシーを作成するには、[**新規**作成] をクリックし、[**ユーザーポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-128">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="9fbc3-129">[**新しい外部アクセスポリシー**] で、[**名前**] フィールドに、ユーザーポリシーがどのようなものであるかを示す一意の名前を作成します (たとえば、リモートユーザーの通信を有効にするユーザーポリシーの**EnableRemoteUsers** )。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-129">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableRemoteUsers** for a user policy that enables communications for remote users).</span></span>
    
      - <span data-ttu-id="9fbc3-130">既存のポリシーを変更するには、表に記載されている適切なポリシーをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-130">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="9fbc3-131">省略説明を追加または編集する場合は、ポリシーの情報を [**説明**] で指定します。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-131">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="9fbc3-132">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-132">Do one of the following:</span></span>
    
      - <span data-ttu-id="9fbc3-133">ポリシーのリモートユーザーアクセスを有効にするには、[**リモートユーザーとの通信を有効**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-133">To enable remote user access for the policy, select the **Enable communications with remote users** check box.</span></span>
    
      - <span data-ttu-id="9fbc3-134">ポリシーのリモートユーザーアクセスを無効にするには、[**リモートユーザーとの通信を有効に**する] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-134">To disable remote user access for the policy, clear the **Enable communications with remote users** check box.</span></span>

7.  <span data-ttu-id="9fbc3-135">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-135">Click **Commit**.</span></span>

<span data-ttu-id="9fbc3-136">リモートユーザーアクセスを有効にするには、組織内のリモートユーザーアクセスのサポートも有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-136">To enable remote user access, you must also enable support for remote user access in your organization.</span></span> <span data-ttu-id="9fbc3-137">詳細について[は、「フェデレーションとパブリック IM 接続を有効または無効](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-137">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="9fbc3-138">ユーザーポリシーの場合は、リモートで接続できるようにするユーザーにもポリシーを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-138">If this is a user policy, you must also apply the policy to users that you want to be able to connect remotely.</span></span> <span data-ttu-id="9fbc3-139">詳細については、「[外部ユーザーアクセスポリシーを割り当てる](assign-an-external-user-access-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fbc3-139">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>
