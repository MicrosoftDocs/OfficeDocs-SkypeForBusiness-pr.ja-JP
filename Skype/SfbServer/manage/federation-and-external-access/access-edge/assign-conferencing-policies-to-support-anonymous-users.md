---
title: 匿名ユーザーをサポートする会議ポリシーを割り当てる
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
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
description: 匿名ユーザーをサポートするよう会議ポリシーを構成し、この会議ポリシーを特定のユーザーに適用することで、匿名ユーザーを招待できるユーザーを制御します。
ms.openlocfilehash: 57d100569722cbe89811d15eb9fbe04e5d375711
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817457"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a><span data-ttu-id="4393c-103">Skype for Business Server で匿名ユーザーをサポートする会議ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4393c-103">Assign conferencing policies to support anonymous users in Skype for Business Server</span></span> 


<span data-ttu-id="4393c-104">既定では、どのユーザーも匿名ユーザーを会議に招待することはできません。</span><span class="sxs-lookup"><span data-stu-id="4393c-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="4393c-105">匿名ユーザーをサポートするよう会議ポリシーを構成し、この会議ポリシーを特定のユーザーに適用することで、匿名ユーザーを招待できるユーザーを制御します。</span><span class="sxs-lookup"><span data-stu-id="4393c-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="4393c-106">匿名ユーザーをサポートする会議ポリシーを構成する方法の詳細については [、「Skype for Business Server](../../conferencing/create-policies.md) での会議ポリシーの作成」および「Skype for Business [Server](../managing-federation-and-external-access.md)へのフェデレーションと外部アクセスの管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4393c-106">For details about how to configure a conferencing policies to support anonymous users, see [Create conferencing policies in Skype for Business Server](../../conferencing/create-policies.md) and [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>

<span data-ttu-id="4393c-107">このセクションの手順を使用して、既に作成した会議ポリシーを、1 人以上のユーザーまたは 1 つ以上のユーザー グループに適用します。</span><span class="sxs-lookup"><span data-stu-id="4393c-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

> [!NOTE]  
> <span data-ttu-id="4393c-108">ユーザーが匿名ユーザーを招待できるようにするポリシーを構成して適用するほかに、組織の匿名ユーザーのサポートを有効にする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="4393c-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="4393c-109">詳細については [、「Skype for Business Server でパブリック ユーザー アクセスを制御するポリシーを構成する」を参照してください](../external-access-policies/configure-policies-to-control-public-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="4393c-109">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="4393c-110">会議への匿名参加に対するユーザー ポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="4393c-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="4393c-111">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4393c-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4393c-112">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4393c-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4393c-113">左側のナビゲーション バーで [**会議**] をクリックし、次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4393c-113">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="4393c-p103">新しいユーザー ポリシーを作成するには、[**新規作成**] をクリックし、[**ユーザー ポリシー**] をクリックします。 [**名前**] フィールドに、ユーザー ポリシーの範囲を示す一意の名前を作成します (匿名ユーザーとの通信を有効にするユーザー ポリシーの場合は **EnableAnonymous** など)。</span><span class="sxs-lookup"><span data-stu-id="4393c-p103">To create a new user policy, click **New**, and then click **User policy**. Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="4393c-116">既存のユーザー ポリシーを編集する場合は、表の一覧にある適切なポリシーをクリックして [**編集**] をクリックし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4393c-116">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="4393c-117">[**会議ポリシー**] ダイアログ ボックスの [**参加者に匿名ユーザーの招待を許可する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="4393c-117">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="4393c-118">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4393c-118">Click **Commit**.</span></span>

6.  <span data-ttu-id="4393c-119">左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="4393c-119">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="4393c-120">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4393c-120">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="4393c-121">[**会議ポリシー] の [Skype for Business Server** ユーザーの編集] で、このユーザーに適用する匿名ユーザー アクセス構成を持つユーザー ポリシーを選択します。 </span><span class="sxs-lookup"><span data-stu-id="4393c-121">In **Edit Skype for Business Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>  

    > [!NOTE]  
    > <span data-ttu-id="4393c-122">自動<STRONG> &lt; 設定 &gt; </STRONG>は既定のサーバー インストール設定を適用し、サーバーによって自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="4393c-122">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>


<span data-ttu-id="4393c-123">ユーザーが匿名ユーザーを会議に招待できるようにするには、組織で匿名ユーザーのサポートも有効にしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="4393c-123">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="4393c-124">詳細については [、「Skype for Business Server でパブリック ユーザー アクセスを制御するポリシーを構成する」を参照してください](../external-access-policies/configure-policies-to-control-public-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="4393c-124">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

