---
title: 'Lync Server 2013: 位置情報ポリシー情報の表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing location policy information
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520954(v=OCS.15)
ms:contentKeyID: 48183489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f68ad38ffbc8bb1b4abdfbf8119add7d9f965e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-location-policy-information-in-lync-server-2013"></a><span data-ttu-id="f3a64-102">Lync Server 2013 で位置情報ポリシー情報を表示する</span><span class="sxs-lookup"><span data-stu-id="f3a64-102">Viewing location policy information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3a64-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f3a64-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f3a64-104">Lync Server 2013 では、位置情報ポリシーを使用して、強化された 9-1-1 (E9) 機能と、ユーザーまたは連絡先の位置設定に関連する設定を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="f3a64-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="f3a64-105">位置情報ポリシーは、ユーザーが E9 に対して有効になっているかどうかを決定し、場合によっては緊急通話の動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="f3a64-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="f3a64-106">たとえば、位置情報ポリシーを使用して、緊急通話 (米国の911など)、企業のセキュリティに自動的に通知するかどうか、および通話のルーティング方法を定義できます。</span><span class="sxs-lookup"><span data-stu-id="f3a64-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="f3a64-107">Lync Server 2013 コントロールパネルの [**ネットワーク構成**] グループから、場所のポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="f3a64-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="f3a64-108">Lync Server コントロールパネルから、場所のポリシーの表示、作成、変更、または削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f3a64-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="f3a64-109">場所のポリシーに関する情報を表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="f3a64-109">Use the following procedure to view information about location policies.</span></span> <span data-ttu-id="f3a64-110">場所のポリシーの作成または変更の詳細については、「 [Lync Server 2013 で位置情報ポリシーを作成または変更](lync-server-2013-creating-or-modifying-a-location-policy.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3a64-110">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-view-information-about-a-location-policy"></a><span data-ttu-id="f3a64-111">場所のポリシーに関する情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="f3a64-111">To view information about a location policy</span></span>

1.  <span data-ttu-id="f3a64-112">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f3a64-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f3a64-113">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f3a64-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f3a64-114">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f3a64-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f3a64-115">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**場所のポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3a64-115">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="f3a64-116">[**場所のポリシー** ] ページで、変更する場所のポリシーを選びます。</span><span class="sxs-lookup"><span data-stu-id="f3a64-116">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="f3a64-117">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3a64-117">On the **Edit** menu, click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f3a64-118">表示できるのは、一度に1つの場所ポリシーに関する情報だけです。</span><span class="sxs-lookup"><span data-stu-id="f3a64-118">You can only view information about one location policy at a time.</span></span>

    
    </div>

<span data-ttu-id="f3a64-119">グローバルと呼ばれる単一のポリシーは既定で存在するため、削除したり名前を変更したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f3a64-119">A single policy, called Global, exists by default and cannot be deleted or renamed.</span></span> <span data-ttu-id="f3a64-120">ただし、グローバルポリシーは変更できます。</span><span class="sxs-lookup"><span data-stu-id="f3a64-120">However, you can modify the Global policy.</span></span> <span data-ttu-id="f3a64-121">このポリシーは、サイトポリシーまたはユーザーごとのポリシーを作成しない限り、すべてのユーザーと連絡先に適用されます。</span><span class="sxs-lookup"><span data-stu-id="f3a64-121">This policy will apply to all users and contacts, unless you create site policies or per-user policies.</span></span> <span data-ttu-id="f3a64-122">ユーザーごとのポリシーは、特定のユーザーに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3a64-122">Per-user policies must be applied to specific users.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f3a64-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3a64-123">See Also</span></span>


[<span data-ttu-id="f3a64-124">Lync Server 2013 で位置情報ポリシーを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="f3a64-124">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="f3a64-125">Lync Server 2013 で位置情報のポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="f3a64-125">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)  
[<span data-ttu-id="f3a64-126">Lync Server 2013 でのネットワーク サイトの作成または変更</span><span class="sxs-lookup"><span data-stu-id="f3a64-126">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)  


[<span data-ttu-id="f3a64-127">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="f3a64-127">New-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[<span data-ttu-id="f3a64-128">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="f3a64-128">Set-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[<span data-ttu-id="f3a64-129">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="f3a64-129">Remove-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[<span data-ttu-id="f3a64-130">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="f3a64-130">Get-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

