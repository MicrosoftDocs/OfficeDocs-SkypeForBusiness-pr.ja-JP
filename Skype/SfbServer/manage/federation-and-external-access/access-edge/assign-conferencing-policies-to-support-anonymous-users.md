---
title: 匿名ユーザー サポートのための会議ポリシーの割り当て
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ユーザーを制御、匿名ユーザーをサポートするための会議ポリシーを構成して、特定のユーザーにその会議のポリシーを適用することによって匿名ユーザーを招待することができます。
ms.openlocfilehash: 62ff84b19fadbeaf0f26fa3e5869026254d28d1f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881128"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a><span data-ttu-id="30bbd-103">Skype のビジネス サーバーの匿名ユーザーをサポートする会議ポリシーを割り当てください。</span><span class="sxs-lookup"><span data-stu-id="30bbd-103">Assign conferencing policies to support anonymous users in Skype for Business Server</span></span> 


<span data-ttu-id="30bbd-104">既定では、すべてのユーザーが会議に参加する匿名ユーザーの招待からできませんでした。</span><span class="sxs-lookup"><span data-stu-id="30bbd-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="30bbd-105">ユーザーを制御、匿名ユーザーをサポートするための会議ポリシーを構成して、特定のユーザーにその会議のポリシーを適用することによって匿名ユーザーを招待することができます。</span><span class="sxs-lookup"><span data-stu-id="30bbd-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="30bbd-106">匿名ユーザーをサポートするための会議ポリシーを構成する方法の詳細については、 [Skype ビジネス サーバー用の会議ポリシーを作成する](../../conferencing/create-policies.md)」および「[フェデレーションの管理および業務サーバー Skype への外部アクセス](../managing-federation-and-external-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30bbd-106">For details about how to configure a conferencing policies to support anonymous users, see [Create conferencing policies in Skype for Business Server](../../conferencing/create-policies.md) and [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>

<span data-ttu-id="30bbd-107">このセクションの 1 つまたは複数のユーザーまたはユーザー グループを既に作成した会議ポリシーを適用するのに手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="30bbd-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

> [!NOTE]  
> <span data-ttu-id="30bbd-108">構成して匿名ユーザーを招待するユーザーを有効にするポリシーを適用するだけでなくも、組織の匿名ユーザーのサポートを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="30bbd-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="30bbd-109">詳細については、 [Skype のビジネス サーバーのパブリック ユーザー アクセスを制御するポリシーを構成する](../external-access-policies/configure-policies-to-control-public-user-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30bbd-109">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="30bbd-110">会議への匿名参加に対するユーザー ポリシーを構成するのには</span><span class="sxs-lookup"><span data-stu-id="30bbd-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="30bbd-111">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="30bbd-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="30bbd-112">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="30bbd-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="30bbd-113">左側のナビゲーション ・ バーでは、**会議**をクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="30bbd-113">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="30bbd-114">新しいユーザー ポリシーを作成するには、[**新規**作成] をクリックし、[**ユーザー ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30bbd-114">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="30bbd-115">ユーザー ポリシーの説明 (たとえば、匿名ユーザーとの通信を有効にするユーザー ポリシーの**EnableAnonymous** ) を示す**名前**」フィールドに一意の名前を作成します。</span><span class="sxs-lookup"><span data-stu-id="30bbd-115">Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="30bbd-116">既存のユーザー ポリシーを構成するのには、表に記載されている適切なポリシー] をクリック**を編集**するには、**の詳細を表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30bbd-116">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="30bbd-117">**会議ポリシー** ] ダイアログ ボックスで、[**匿名ユーザーを招待する参加者を許可する**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="30bbd-117">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="30bbd-118">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30bbd-118">Click **Commit**.</span></span>

6.  <span data-ttu-id="30bbd-119">左側のナビゲーション バーで [**ユーザー**] をクリックしてを構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="30bbd-119">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="30bbd-120">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30bbd-120">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="30bbd-121">**ビジネス サーバー ユーザーの編集の Skype**の**会議**ポリシーでは、このユーザーに適用する匿名ユーザー アクセスの構成とユーザー ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="30bbd-121">In **Edit Skype for Business Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>  

    > [!NOTE]  
    > <span data-ttu-id="30bbd-122"><STRONG>&lt;自動&gt;</STRONG>の設定はサーバー インストールの既定の設定を適用し、サーバーによって自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="30bbd-122">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>


<span data-ttu-id="30bbd-123">会議への匿名ユーザーを招待するユーザーを有効にするも、組織で匿名ユーザーのサポートを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="30bbd-123">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="30bbd-124">詳細については、 [Skype のビジネス サーバーのパブリック ユーザー アクセスを制御するポリシーを構成する](../external-access-policies/configure-policies-to-control-public-user-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30bbd-124">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

