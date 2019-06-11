---
title: 'Lync Server 2013: 場所のポリシーを削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting a location policy
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49733724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4766d2b05cef89ab29b9c303c5ba1ec456843669
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-location-policy-in-lync-server-2013"></a><span data-ttu-id="0f59b-102">Lync Server 2013 で位置情報ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="0f59b-102">Deleting a location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f59b-103">_**最終更新日:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="0f59b-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="0f59b-104">Lync Server 2013 では、位置情報ポリシーを使用して、強化された 9-1-1 (E9) 機能と、ユーザーまたは連絡先の位置設定に関連する設定を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="0f59b-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="0f59b-105">位置情報ポリシーは、ユーザーが E9 に対して有効になっているかどうかを決定し、場合によっては緊急通話の動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="0f59b-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="0f59b-106">たとえば、位置情報ポリシーを使用して、緊急通話 (米国の911など)、企業のセキュリティに自動的に通知するかどうか、および通話のルーティング方法を定義できます。</span><span class="sxs-lookup"><span data-stu-id="0f59b-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="0f59b-107">Lync Server 2013 コントロールパネルの [**ネットワーク構成**] グループから、場所のポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="0f59b-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="0f59b-108">Lync Server コントロールパネルから、場所のポリシーの表示、作成、変更、または削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0f59b-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="0f59b-109">次の手順を使用して、場所のポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="0f59b-109">Use the following procedures delete a location policy.</span></span> <span data-ttu-id="0f59b-110">場所のポリシーの作成または変更の詳細については、「 [Lync Server 2013 で位置情報ポリシーを作成または変更](lync-server-2013-creating-or-modifying-a-location-policy.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f59b-110">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-delete-a-location-policy"></a><span data-ttu-id="0f59b-111">場所のポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="0f59b-111">To delete a location policy</span></span>

1.  <span data-ttu-id="0f59b-112">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="0f59b-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0f59b-113">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0f59b-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0f59b-114">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0f59b-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0f59b-115">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**場所のポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0f59b-115">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="0f59b-116">[**場所のポリシー** ] ページで、削除する場所のポリシーを選びます。</span><span class="sxs-lookup"><span data-stu-id="0f59b-116">On the **Location Policy** page, select the location policy that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0f59b-117">複数の場所ポリシーは一度に削除できます。</span><span class="sxs-lookup"><span data-stu-id="0f59b-117">You can delete more than one location policy at a time.</span></span> <span data-ttu-id="0f59b-118">これを行うには、ctrl キーを押しながら、CTRL キーを押しながら複数のポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f59b-118">To do this, press CTRL and select multiple policies while holding down the CTRL key.</span></span> <span data-ttu-id="0f59b-119">または、すべてのポリシーを選択するには、[<STRONG>編集</STRONG>] メニューの [<STRONG>すべて選択</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0f59b-119">Or, to select all policies, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="0f59b-120">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0f59b-120">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="0f59b-121">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0f59b-121">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0f59b-122">グローバルな場所のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="0f59b-122">You cannot delete the Global location policy.</span></span> <span data-ttu-id="0f59b-123">グローバルポリシーを削除しようとすると、警告メッセージが表示され、そのポリシーは既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="0f59b-123">If you attempt to delete the Global policy you will receive a warning message and that policy will be reset to its default values.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0f59b-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f59b-124">See Also</span></span>


[<span data-ttu-id="0f59b-125">Lync Server 2013 で位置情報ポリシーを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="0f59b-125">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="0f59b-126">Lync Server 2013 で位置情報ポリシー情報を表示する</span><span class="sxs-lookup"><span data-stu-id="0f59b-126">Viewing location policy information in Lync Server 2013</span></span>](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

