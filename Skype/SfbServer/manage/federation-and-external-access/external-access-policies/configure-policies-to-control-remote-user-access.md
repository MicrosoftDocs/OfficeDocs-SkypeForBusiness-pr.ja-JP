---
title: リモート ユーザー アクセスを制御するポリシーの構成
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
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
description: 1 つ以上の外部ユーザー アクセス ポリシーを構成して、リモート ユーザーが内部の Skype for Business Server ユーザーと共同作業できるかどうかを制御します。 リモート ユーザー アクセスを管理するため、グローバル、サイト、およびユーザー レベルでポリシーを構成できます。
ms.openlocfilehash: 0fd24f7c57cfaa4a131bcd1648cb1b6e6eb5f05a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817302"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="5118b-104">Skype for Business Server でリモート ユーザー アクセスを制御するポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="5118b-104">Configure policies to control remote user access in Skype for Business Server</span></span>

<span data-ttu-id="5118b-105">1 つ以上の外部ユーザー アクセス ポリシーを構成して、リモート ユーザーが内部の Skype for Business Server ユーザーと共同作業できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="5118b-105">You configure one or more external user access policies to control whether remote users can collaborate with internal Skype for Business Server users.</span></span> <span data-ttu-id="5118b-106">リモート ユーザー アクセスを管理するため、グローバル、サイト、およびユーザー レベルでポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="5118b-106">To control remote user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="5118b-107">サイト ポリシーはグローバル ポリシーより優先され、ユーザー ポリシーはサイト ポリシーとグローバル ポリシーより優先されます。</span><span class="sxs-lookup"><span data-stu-id="5118b-107">Site policies override the global policy, and user policies override site and global policies.</span></span> <span data-ttu-id="5118b-108">構成できるポリシーの種類の詳細については、「Skype for Business Server へのフェデレーションと外部アクセスの管理」 [を参照してください](../managing-federation-and-external-access.md)。</span><span class="sxs-lookup"><span data-stu-id="5118b-108">For details about the types of policies that you can configure, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span> <span data-ttu-id="5118b-109">あるポリシー レベルで適用される Skype for Business Server ポリシー設定は、別のポリシー レベルで適用される設定を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="5118b-109">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="5118b-110">Skype for Business Server ポリシーの優先順位: ユーザー ポリシー (最も高い) はサイト ポリシーをオーバーライドし、サイト ポリシーはグローバル ポリシーをオーバーライド (最も低い) します。</span><span class="sxs-lookup"><span data-stu-id="5118b-110">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="5118b-111">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="5118b-111">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

> [!NOTE]  
> <span data-ttu-id="5118b-112">組織のリモート ユーザー アクセスを有効にしていない場合でも、リモート ユーザー アクセスを制御するポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="5118b-112">You can configure policies to control remote user access, even if you have not enabled remote user access for your organization.</span></span> <span data-ttu-id="5118b-113">ただし、構成したポリシーは、組織のリモート ユーザー アクセスを有効にしているときのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="5118b-113">However, the policies that you configure are in effect only when you have remote user access enabled for your organization.</span></span> <span data-ttu-id="5118b-114">さらに、リモート ユーザー アクセスを制御するユーザー ポリシーを指定した場合、このポリシーは、Skype for Business Server が有効で、ポリシーを使用するように構成されているユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="5118b-114">Additionally, if you specify a user policy to control remote user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span> <span data-ttu-id="5118b-115">リモートの場所から Skype for Business Server にサインインできるユーザーの指定の詳細については、「外部ユーザー アクセス ポリシーを割り当てる [」を参照してください](assign-an-external-user-access-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="5118b-115">For details about specifying users that can sign in to Skype for Business Server from remote locations, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

<span data-ttu-id="5118b-116">リモート ユーザー アクセスの制御に使用する各外部アクセス ポリシーを構成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="5118b-116">Use the following procedure to configure each external access policy that you want to use to control remote user access.</span></span>


> [!NOTE]  
> <span data-ttu-id="5118b-117">この手順で説明するのは、リモート ユーザーとの通信を有効にするだけのポリシーを構成する方法ですが、リモート ユーザー アクセスをサポートするため構成する各ポリシーで、フェデレーション ユーザー アクセスやパブリック ユーザー アクセスも構成できます。</span><span class="sxs-lookup"><span data-stu-id="5118b-117">This procedure describes how to configure a policy only to enable communications with remote users, but each policy that you configure to support remote user access can also configure federated user access and public user access.</span></span> <span data-ttu-id="5118b-118">フェデレーション ユーザーをサポートするポリシーの構成の詳細については [、「Configure policies to control federated user access in Skype for Business Server 」を参照してください](configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="5118b-118">For details about configuring policies to support federated users, see [Configure policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md).</span></span> <span data-ttu-id="5118b-119">パブリック ユーザーをサポートするポリシーの構成の詳細については、「Skype for Business Server で組織の SIP フェデレーション プロバイダーを管理する [」を参照してください](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="5118b-119">For details about configuring policies to support public users, see [Manage SIP federated providers for your organization in Skype for Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a><span data-ttu-id="5118b-120">リモート ユーザー アクセスをサポートする外部アクセス ポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="5118b-120">To configure an external access policy to support remote user access</span></span>

1.  <span data-ttu-id="5118b-121">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5118b-121">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5118b-122">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5118b-122">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5118b-123">左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5118b-123">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="5118b-124">[**外部アクセス ポリシー**] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5118b-124">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="5118b-125">リモート ユーザー アクセスをサポートするグローバル ポリシーを構成するには、グローバル ポリシーをクリックして [**編集**] をクリックし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5118b-125">To configure the global policy to support remote user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="5118b-p105">新しいサイト ポリシーを作成するには、[**新規作成**] をクリックし、[**サイト ポリシー**] をクリックします。 [**サイトの選択**] で一覧から適切なサイトをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5118b-p105">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="5118b-p106">新しいユーザー ポリシーを作成するには、[**新規作成**] をクリックし、[**ユーザー ポリシー**] をクリックします。 [**新しい外部アクセス ポリシー**] の [**名前**] フィールドに、ユーザー ポリシーの範囲を示す一意の名前を作成します (リモート ユーザーの通信を有効にするユーザー ポリシーの場合は **EnableRemoteUsers** など)。</span><span class="sxs-lookup"><span data-stu-id="5118b-p106">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableRemoteUsers** for a user policy that enables communications for remote users).</span></span>
    
      - <span data-ttu-id="5118b-130">既存のポリシーを変更するには、表に表示されている適切なポリシーをクリックし、[**編集**] に続いて [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5118b-130">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="5118b-131">(オプション) 説明を追加または編集する場合は、[**説明**] でポリシーの情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="5118b-131">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="5118b-132">次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5118b-132">Do one of the following:</span></span>
    
      - <span data-ttu-id="5118b-133">ポリシーのリモート ユーザー アクセスを有効にするには、[**リモート ユーザーとの通信を有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="5118b-133">To enable remote user access for the policy, select the **Enable communications with remote users** check box.</span></span>
    
      - <span data-ttu-id="5118b-134">ポリシーのリモート ユーザー アクセスを無効にするには、[**リモート ユーザーとの通信を有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="5118b-134">To disable remote user access for the policy, clear the **Enable communications with remote users** check box.</span></span>

7.  <span data-ttu-id="5118b-135">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5118b-135">Click **Commit**.</span></span>

<span data-ttu-id="5118b-136">リモート ユーザー アクセスを有効にするには、組織のリモート ユーザー アクセスのサポートも有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5118b-136">To enable remote user access, you must also enable support for remote user access in your organization.</span></span> <span data-ttu-id="5118b-137">詳細については、「フェデレーションと [パブリック IM 接続を有効または無効にする」を参照してください](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="5118b-137">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="5118b-138">これがユーザー ポリシーである場合は、リモート接続を許可するユーザーにポリシーを適用する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="5118b-138">If this is a user policy, you must also apply the policy to users that you want to be able to connect remotely.</span></span> <span data-ttu-id="5118b-139">詳細については、「外部ユーザー アクセス [ポリシーの割り当て」を参照してください](assign-an-external-user-access-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="5118b-139">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>
