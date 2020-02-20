---
title: 'Lync Server 2013: 匿名ユーザーをサポートするための会議ポリシーの割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign conferencing policies to support anonymous users
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4aaa2ee1f6734059983720ca9c3e228ab561a4d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a><span data-ttu-id="a709f-102">Lync Server 2013 で匿名ユーザーをサポートするための会議ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="a709f-102">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a709f-103">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="a709f-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="a709f-104">既定では、どのユーザーも匿名ユーザーを会議に招待することはできません。</span><span class="sxs-lookup"><span data-stu-id="a709f-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="a709f-105">匿名ユーザーをサポートするよう会議ポリシーを構成し、この会議ポリシーを特定のユーザーに適用することで、匿名ユーザーを招待できるユーザーを制御します。</span><span class="sxs-lookup"><span data-stu-id="a709f-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="a709f-106">匿名ユーザーをサポートするように会議ポリシーを構成する方法の詳細については、「 [Lync server 2013 で会議ポリシーを作成または変更](lync-server-2013-create-or-modify-a-conferencing-policy.md)する」および「 [lync server 2013 へのフェデレーションと外部アクセスを管理](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a709f-106">For details about how to configure a conferencing policies to support anonymous users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) and [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span>

<span data-ttu-id="a709f-107">このセクションの手順を使用して、既に作成した会議ポリシーを、1 人以上のユーザーまたは 1 つ以上のユーザー グループに適用します。</span><span class="sxs-lookup"><span data-stu-id="a709f-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a709f-108">ユーザーが匿名ユーザーを招待できるようにするポリシーを構成して適用するほかに、組織の匿名ユーザーのサポートを有効にする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="a709f-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="a709f-109">詳細については、「 <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to control public user access In Lync Server 2013</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a709f-109">For details, see <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to control public user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="a709f-110">会議への匿名参加に対するユーザー ポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="a709f-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="a709f-111">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a709f-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a709f-112">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a709f-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a709f-113">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a709f-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a709f-114">左側のナビゲーション バーで [**会議**] をクリックし、次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a709f-114">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="a709f-p104">新しいユーザー ポリシーを作成するには、[**新規作成**] をクリックし、[**ユーザー ポリシー**] をクリックします。 [**名前**] フィールドに、ユーザー ポリシーの範囲を示す一意の名前を作成します (匿名ユーザーとの通信を有効にするユーザー ポリシーの場合は **EnableAnonymous** など)。</span><span class="sxs-lookup"><span data-stu-id="a709f-p104">To create a new user policy, click **New**, and then click **User policy**. Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="a709f-117">既存のユーザー ポリシーを編集する場合は、表の一覧にある適切なポリシーをクリックして [**編集**] をクリックし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a709f-117">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="a709f-118">[**会議ポリシー**] ダイアログ ボックスの [**参加者に匿名ユーザーの招待を許可する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a709f-118">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="a709f-119">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a709f-119">Click **Commit**.</span></span>

6.  <span data-ttu-id="a709f-120">左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="a709f-120">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="a709f-121">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a709f-121">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="a709f-122">[**Lync Server ユーザーの編集**] の [**会議ポリシー**] で、このユーザーに適用する匿名ユーザー アクセス構成を含むユーザー ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="a709f-122">In **Edit Lync Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a709f-123">[ <STRONG> &lt;自動&gt; </STRONG> ] 設定は、既定のサーバーインストール設定を適用し、サーバーによって自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a709f-123">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>

    
    </div>

<span data-ttu-id="a709f-124">ユーザーが匿名ユーザーを会議に招待できるようにするには、組織で匿名ユーザーのサポートも有効にしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="a709f-124">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="a709f-125">詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 [Configure policies to control The Lync Server 2013」](lync-server-2013-configure-policies-to-control-public-user-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a709f-125">For details, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

