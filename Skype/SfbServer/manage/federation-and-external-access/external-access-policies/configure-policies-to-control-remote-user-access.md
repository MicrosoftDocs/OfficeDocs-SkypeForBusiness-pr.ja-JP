---
title: リモート ユーザー アクセスを制御するポリシーの構成
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: リモート ユーザーがビジネスのサーバーのユーザーの内部の Skype で共同作業を行うかどうかは、コントロールに 1 つまたは複数の外部ユーザー アクセス ポリシーを構成します。 リモート ユーザー アクセスを制御するには、グローバル ポリシー、サイト、およびユーザー レベルを構成できます。
ms.openlocfilehash: f6d316f022e671bc7f7e70ebbe2a801b0b3e312c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199892"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="3f1b2-104">ビジネス サーバーの Skype でのリモート ユーザー アクセスを制御するポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-104">Configure policies to control remote user access in Skype for Business Server</span></span>

<span data-ttu-id="3f1b2-105">リモート ユーザーがビジネスのサーバーのユーザーの内部の Skype で共同作業を行うかどうかは、コントロールに 1 つまたは複数の外部ユーザー アクセス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-105">You configure one or more external user access policies to control whether remote users can collaborate with internal Skype for Business Server users.</span></span> <span data-ttu-id="3f1b2-106">リモート ユーザー アクセスを制御するには、グローバル ポリシー、サイト、およびユーザー レベルを構成できます。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-106">To control remote user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="3f1b2-107">サイト ポリシーはグローバル ポリシーをオーバーライドし、ユーザー ポリシーは、サイトとグローバル ポリシーをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-107">Site policies override the global policy, and user policies override site and global policies.</span></span> <span data-ttu-id="3f1b2-108">詳細については、構成可能なポリシーの種類は、[フェデレーションの管理および業務サーバーの Skype への外部アクセス](../managing-federation-and-external-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-108">For details about the types of policies that you can configure, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span> <span data-ttu-id="3f1b2-109">Skype ビジネスのサーバーのポリシー設定が 1 つのポリシー レベルで適用されるは、別のポリシー レベルで適用される設定をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-109">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="3f1b2-110">ビジネス サーバー ポリシーの優先順位の Skype が: ユーザー ポリシー (ほとんどの影響) がサイト ポリシーを上書きし、[サイト ポリシーはグローバル ポリシー (最低限の影響) をよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-110">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="3f1b2-111">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-111">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

> [!NOTE]  
> <span data-ttu-id="3f1b2-112">組織のリモート ユーザー アクセスが有効にしない場合でも、リモート ユーザー アクセスを制御するポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-112">You can configure policies to control remote user access, even if you have not enabled remote user access for your organization.</span></span> <span data-ttu-id="3f1b2-113">ただし、ポリシーを構成することは、リモート ユーザー アクセスを有効に組織がある場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-113">However, the policies that you configure are in effect only when you have remote user access enabled for your organization.</span></span> <span data-ttu-id="3f1b2-114">さらに、リモート ユーザー アクセスを制御するユーザー ポリシーを指定する場合は、Skype のビジネス サーバー有効になって、ポリシーを使用するように構成されているユーザーにのみ、ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-114">Additionally, if you specify a user policy to control remote user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span> <span data-ttu-id="3f1b2-115">サインインできる Skype ビジネス サーバーのリモート ・ サイトからのユーザーを指定する方法の詳細は、[外部ユーザー アクセス ポリシーを割り当てる](assign-an-external-user-access-policy.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-115">For details about specifying users that can sign in to Skype for Business Server from remote locations, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

<span data-ttu-id="3f1b2-116">リモート ユーザー アクセスの制御に使用する各外部アクセス ポリシーを構成するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-116">Use the following procedure to configure each external access policy that you want to use to control remote user access.</span></span>


> [!NOTE]  
> <span data-ttu-id="3f1b2-117">この手順は、リモート ユーザーとの通信を有効にする場合にのみポリシーを構成する方法を説明しますが、リモート ユーザー アクセスをサポートするように構成する各ポリシーには、フェデレーション ユーザーのアクセスとパブリック ユーザー アクセスもを構成できます。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-117">This procedure describes how to configure a policy only to enable communications with remote users, but each policy that you configure to support remote user access can also configure federated user access and public user access.</span></span> <span data-ttu-id="3f1b2-118">フェデレーション ユーザーをサポートするためにポリシーの構成に関する詳細については、[制御するポリシーを構成する Skype のビジネス サーバーでユーザーのアクセスをフェデレーションする](configure-policies-to-control-federated-user-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-118">For details about configuring policies to support federated users, see [Configure policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md).</span></span> <span data-ttu-id="3f1b2-119">パブリック ユーザーをサポートするポリシーの構成に関する詳細については、[連合組織は、ビジネスのサーバー用の Skype でのプロバイダーの SIP の管理](../sip-providers/manage-sip-federated-providers-for-your-organization.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-119">For details about configuring policies to support public users, see [Manage SIP federated providers for your organization in Skype for Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a><span data-ttu-id="3f1b2-120">リモート ユーザー アクセスをサポートする外部アクセス ポリシーを構成するのには</span><span class="sxs-lookup"><span data-stu-id="3f1b2-120">To configure an external access policy to support remote user access</span></span>

1.  <span data-ttu-id="3f1b2-121">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-121">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3f1b2-122">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-122">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="3f1b2-123">左側のナビゲーション ・ バーでは、**外部ユーザー アクセス**をクリックし、**外部アクセス ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-123">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="3f1b2-124">[**外部アクセス ポリシー** ] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-124">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="3f1b2-125">リモート ユーザー アクセスをサポートするグローバル ポリシーを構成するには、グローバル ポリシーをクリックして**編集**を**の詳細を表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-125">To configure the global policy to support remote user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="3f1b2-126">新しいサイト ポリシーを作成、[**新規**作成] をクリックし、[**サイト ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-126">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="3f1b2-127">] で**サイトを選択して**、リストから適切なサイトをし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-127">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="3f1b2-128">新しいユーザー ポリシーを作成するには、[**新規**作成] をクリックし、[**ユーザー ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-128">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="3f1b2-129">**新しい外部アクセス ポリシー**では、どのユーザー ポリシーは (たとえば、リモート ユーザーの通信を有効にするユーザー ポリシーの**EnableRemoteUsers** ) を示す [**名**] フィールドに一意の名前を作成します。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-129">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableRemoteUsers** for a user policy that enables communications for remote users).</span></span>
    
      - <span data-ttu-id="3f1b2-130">既存のポリシーを変更するには、表に記載されている適切なポリシー] をクリック**を編集**するには、**の詳細を表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-130">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="3f1b2-131">(省略可能)追加または説明を編集する場合は、 **[説明**] にポリシーの情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-131">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="3f1b2-132">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-132">Do one of the following:</span></span>
    
      - <span data-ttu-id="3f1b2-133">ポリシーのリモート ユーザー アクセスを有効にするには、**リモート ユーザーとの通信を有効にする**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-133">To enable remote user access for the policy, select the **Enable communications with remote users** check box.</span></span>
    
      - <span data-ttu-id="3f1b2-134">ポリシーのリモート ユーザー アクセスを無効にするには、**リモート ユーザーとの通信を有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-134">To disable remote user access for the policy, clear the **Enable communications with remote users** check box.</span></span>

7.  <span data-ttu-id="3f1b2-135">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-135">Click **Commit**.</span></span>

<span data-ttu-id="3f1b2-136">リモート ユーザー アクセスを有効にするも、組織内のリモート ユーザー アクセスのサポートを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-136">To enable remote user access, you must also enable support for remote user access in your organization.</span></span> <span data-ttu-id="3f1b2-137">詳細については、[有効にするかフェデレーションとパブリック IM 接続を無効にする](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-137">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="3f1b2-138">ユーザー ポリシーの場合は、リモートで接続できるようにするユーザーにポリシーを適用する必要がありますもします。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-138">If this is a user policy, you must also apply the policy to users that you want to be able to connect remotely.</span></span> <span data-ttu-id="3f1b2-139">詳細については、[外部ユーザー アクセス ポリシーを割り当てる](assign-an-external-user-access-policy.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f1b2-139">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>
