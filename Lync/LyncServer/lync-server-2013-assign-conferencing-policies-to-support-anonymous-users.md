---
title: 'Lync Server 2013: 匿名ユーザー サポートのための会議ポリシーの割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign conferencing policies to support anonymous users
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94ff3fe520b776d6f6043abb66f9926da5acaa22
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a><span data-ttu-id="8fc45-102">Lync Server 2013 での匿名ユーザー サポートのための会議ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="8fc45-102">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fc45-103">_**最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="8fc45-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="8fc45-104">既定では、すべてのユーザーが匿名ユーザーを招待して会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="8fc45-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="8fc45-105">匿名ユーザーをサポートする会議ポリシーを構成し、その会議ポリシーを特定のユーザーに適用することによって、匿名ユーザーを招待できるユーザーを制御します。</span><span class="sxs-lookup"><span data-stu-id="8fc45-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="8fc45-106">匿名ユーザーをサポートするように会議ポリシーを構成する方法の詳細については、「 [Lync server 2013 で会議ポリシーを作成または変更](lync-server-2013-create-or-modify-a-conferencing-policy.md)する」および「 [lync server 2013 のフェデレーションと外部アクセスを管理](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fc45-106">For details about how to configure a conferencing policies to support anonymous users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) and [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span>

<span data-ttu-id="8fc45-107">このセクションの手順を使用して、既に作成済みの会議ポリシーを1人または複数のユーザーまたはユーザーグループに適用します。</span><span class="sxs-lookup"><span data-stu-id="8fc45-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8fc45-108">ユーザーが匿名ユーザーを招待できるようにポリシーを構成して適用することに加えて、組織の匿名ユーザーのサポートも有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fc45-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="8fc45-109">詳細については、「 <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Lync Server 2013 でパブリックユーザーアクセスを制御するためのポリシーを構成する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fc45-109">For details, see <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to control public user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="8fc45-110">会議への匿名参加用のユーザーポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="8fc45-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="8fc45-111">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8fc45-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8fc45-112">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="8fc45-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8fc45-113">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8fc45-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8fc45-114">左側のナビゲーションバーで、[**会議**] をクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8fc45-114">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="8fc45-115">新しいユーザーポリシーを作成するには、[**新規**作成] をクリックし、[**ユーザーポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fc45-115">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="8fc45-116">[**名前**] フィールドに、ユーザーポリシーがどのようなものであるかを示す一意の名前を作成します (たとえば、匿名ユーザーとの通信を可能にする、ユーザーポリシーに対して**anonymous**を有効にします)。</span><span class="sxs-lookup"><span data-stu-id="8fc45-116">Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="8fc45-117">既存のユーザーポリシーを構成するには、表に記載されている適切なポリシーをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fc45-117">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="8fc45-118">[**会議ポリシー** ] ダイアログボックスで、[**参加者に匿名ユーザーの招待を許可する**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8fc45-118">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="8fc45-119">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fc45-119">Click **Commit**.</span></span>

6.  <span data-ttu-id="8fc45-120">左側のナビゲーションバーで [**ユーザー**] をクリックし、構成するユーザーアカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="8fc45-120">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="8fc45-121">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fc45-121">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="8fc45-122">[**会議ポリシー**] の [ **Lync Server ユーザーの編集**] で、このユーザーに適用する匿名ユーザーアクセス構成が設定されているユーザーポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="8fc45-122">In **Edit Lync Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8fc45-123"><STRONG> &lt;自動&gt; </STRONG>設定では、既定のサーバーインストール設定が適用され、サーバーによって自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8fc45-123">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>

    
    </div>

<span data-ttu-id="8fc45-124">ユーザーが会議に匿名ユーザーを招待できるようにするには、組織内の匿名ユーザーのサポートも有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fc45-124">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="8fc45-125">詳細については、「展開ドキュメントまたは運用ドキュメントの「 [Lync Server 2013 でのパブリックユーザーアクセスを制御するためのポリシーを構成する](lync-server-2013-configure-policies-to-control-public-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fc45-125">For details, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

