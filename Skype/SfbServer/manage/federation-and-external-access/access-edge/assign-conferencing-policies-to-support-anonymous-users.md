---
title: 匿名ユーザー サポートのための会議ポリシーの割り当て
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 匿名ユーザーをサポートする会議ポリシーを構成し、その会議ポリシーを特定のユーザーに適用することによって、匿名ユーザーを招待できるユーザーを制御します。
ms.openlocfilehash: d7956e68db3330f0804e6161e0eeaf52958bc588
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280286"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a><span data-ttu-id="b02fd-103">Skype for Business Server で匿名ユーザーをサポートする会議ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b02fd-103">Assign conferencing policies to support anonymous users in Skype for Business Server</span></span> 


<span data-ttu-id="b02fd-104">既定では、すべてのユーザーが匿名ユーザーを招待して会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="b02fd-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="b02fd-105">匿名ユーザーをサポートする会議ポリシーを構成し、その会議ポリシーを特定のユーザーに適用することによって、匿名ユーザーを招待できるユーザーを制御します。</span><span class="sxs-lookup"><span data-stu-id="b02fd-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="b02fd-106">匿名ユーザーをサポートするように会議ポリシーを構成する方法について詳しくは、「 [skype For Business server で会議ポリシーを作成](../../conferencing/create-policies.md)する」と「 [Skype for business server へのフェデレーションと外部アクセスを管理](../managing-federation-and-external-access.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b02fd-106">For details about how to configure a conferencing policies to support anonymous users, see [Create conferencing policies in Skype for Business Server](../../conferencing/create-policies.md) and [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>

<span data-ttu-id="b02fd-107">このセクションの手順を使用して、既に作成済みの会議ポリシーを1人または複数のユーザーまたはユーザーグループに適用します。</span><span class="sxs-lookup"><span data-stu-id="b02fd-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

> [!NOTE]  
> <span data-ttu-id="b02fd-108">ユーザーが匿名ユーザーを招待できるようにポリシーを構成して適用することに加えて、組織の匿名ユーザーのサポートも有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b02fd-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="b02fd-109">詳細については、「 [Skype For Business Server でパブリックユーザーアクセスを制御するためのポリシーを構成する](../external-access-policies/configure-policies-to-control-public-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b02fd-109">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="b02fd-110">会議への匿名参加用のユーザーポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="b02fd-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="b02fd-111">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b02fd-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b02fd-112">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b02fd-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b02fd-113">左側のナビゲーションバーで、[**会議**] をクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b02fd-113">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="b02fd-114">新しいユーザーポリシーを作成するには、[**新規**作成] をクリックし、[**ユーザーポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b02fd-114">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="b02fd-115">[**名前**] フィールドに、ユーザーポリシーがどのようなものであるかを示す一意の名前を作成します (たとえば、匿名ユーザーとの通信を可能にする、ユーザーポリシーに対して**anonymous**を有効にします)。</span><span class="sxs-lookup"><span data-stu-id="b02fd-115">Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="b02fd-116">既存のユーザーポリシーを構成するには、表に記載されている適切なポリシーをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b02fd-116">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="b02fd-117">[**会議ポリシー** ] ダイアログボックスで、[**参加者に匿名ユーザーの招待を許可する**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b02fd-117">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="b02fd-118">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b02fd-118">Click **Commit**.</span></span>

6.  <span data-ttu-id="b02fd-119">左側のナビゲーションバーで [**ユーザー**] をクリックし、構成するユーザーアカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="b02fd-119">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="b02fd-120">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b02fd-120">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="b02fd-121">[**会議ポリシー**] の [ **Skype For business Server ユーザーの編集**] で、このユーザーに適用する匿名ユーザーアクセス構成を持つユーザーポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b02fd-121">In **Edit Skype for Business Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>  

    > [!NOTE]  
    > <span data-ttu-id="b02fd-122"><STRONG> &lt;自動&gt; </STRONG>設定では、既定のサーバーインストール設定が適用され、サーバーによって自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b02fd-122">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>


<span data-ttu-id="b02fd-123">ユーザーが会議に匿名ユーザーを招待できるようにするには、組織内の匿名ユーザーのサポートも有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b02fd-123">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="b02fd-124">詳細については、「 [Skype For Business Server でパブリックユーザーアクセスを制御するためのポリシーを構成する](../external-access-policies/configure-policies-to-control-public-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b02fd-124">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

