---
title: ダイヤルイン アクセス番号の移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4f0f286450aeaaf747d4642bf8791695d16b603
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="a6fdf-102">ダイヤルイン アクセス番号の移行</span><span class="sxs-lookup"><span data-stu-id="a6fdf-102">Migrate dial-in access numbers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6fdf-103">_**最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="a6fdf-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="a6fdf-104">Lync Server 2010 から Lync Server 2013 にダイヤルインアクセス番号を移行するには、 **Move-CsApplicationEndpoint**コマンドレットを実行して、連絡先オブジェクトを移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-104">Migrating dial-in access numbers from Lync Server 2010 to Lync Server 2013 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="a6fdf-105">Lync server 2010 および Lync Server 2013 の共存期間中、Lync Server 2013 で作成したダイヤルインアクセス番号は、このセクションで説明するように、Lync Server 2010 で作成したダイヤルインアクセス番号と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-105">During the Lync Server 2010 and Lync Server 2013 coexistence period, dial-in access numbers that you created in Lync Server 2013 behave similarly to the dial-in access numbers that you create in Lync Server 2010, as described in this section.</span></span>

<span data-ttu-id="a6fdf-106">Lync server 2010 で作成したが、Lync Server 2013 に移動した、または Lync server 2013 で作成したダイヤルインアクセス番号は、移行中または移行後に次のような特性を持つことになります。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-106">Dial-in access numbers that you created in Lync Server 2010 but moved to Lync Server 2013 or that you created in Lync Server 2013 before, during or after migration have the following characteristics:</span></span>

  - <span data-ttu-id="a6fdf-107">Office Communications Server 2007 R2 会議の出席依頼とダイヤルインアクセス番号のページには表示されません。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-107">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="a6fdf-108">Lync Server 2010 会議の出席依頼とダイヤルインアクセス番号のページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-108">Appear on Lync Server 2010 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="a6fdf-109">Lync Server 2013 会議の出席依頼とダイヤルインアクセス番号のページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-109">Appear on Lync Server 2013 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="a6fdf-110">Office Communications Server 2007 R2 管理ツールでは、表示または変更できません。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-110">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

  - <span data-ttu-id="a6fdf-111">Lync Server 2010 コントロールパネルと Lync Server 2010 Management Shell で表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-111">Can be viewed and modified in the Lync Server 2010 Control Panel and in Lync Server 2010 Management Shell.</span></span>

  - <span data-ttu-id="a6fdf-112">Lync Server 2013 コントロールパネルと Lync Server 2013 Management Shell で表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-112">Can be viewed and modified in the Lync Server 2013 Control Panel and in Lync Server 2013 Management Shell.</span></span>

  - <span data-ttu-id="a6fdf-113">Priority パラメーターを指定して CsDialinConferencingAccessNumber コマンドレットを使用して、地域内で再シーケンスできます。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-113">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="a6fdf-114">Lync server 2010 プールを廃止する前に、Lync Server 2010 プールを参照するダイヤルインアクセス番号の移行を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-114">You must finish migrating dial-in access numbers that point to a Lync Server 2010 pool before you decommission the Lync Server 2010 pool.</span></span> <span data-ttu-id="a6fdf-115">次の手順で説明するように、ダイヤルインアクセス番号の移行が完了していない場合は、アクセス番号への着信通話が失敗します。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-115">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a6fdf-116">Lync Server 2010 プールの使用を停止する前に、この手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-116">You must perform this procedure prior to decommissioning the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a6fdf-117">短時間のサービス停止が発生した場合に備えて、ネットワーク使用量が少ない場合は、ダイヤルインアクセス番号を移動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-117">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span>



</div>

<span data-ttu-id="a6fdf-118">**ダイヤルインアクセス番号を特定して移動するには**</span><span class="sxs-lookup"><span data-stu-id="a6fdf-118">**To identify and move dial-in access numbers**</span></span>

1.  <span data-ttu-id="a6fdf-119">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a6fdf-120">Lync Server 2013 でホストされているプールにダイヤルインアクセス番号を移動するには、コマンドラインで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-120">To move each dial-in access number to a pool hosted on Lync Server 2013, from the command line run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  <span data-ttu-id="a6fdf-121">[Lync Server コントロール パネル] を開きます。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-121">Open Lync Server Control Panel.</span></span>

4.  <span data-ttu-id="a6fdf-122">左側のナビゲーション バーで [**会議**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-122">In the left navigation bar, click **Conferencing**.</span></span>

5.  <span data-ttu-id="a6fdf-123">[**ダイヤルインアクセス番号**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-123">Click the **Dial-in Access Number** tab.</span></span>

6.  <span data-ttu-id="a6fdf-124">移行元の Lync Server 2010 プールのダイヤルインアクセス番号が残っていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-124">Verify that no dial-in access numbers remain for the Lync Server 2010 pool from which you are migrating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a6fdf-125">すべてのダイヤルインアクセス番号が Lync Server 2013 プールをポイントしている場合は、Lync Server 2010 プールの使用を停止することができます。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-125">When all dial-in access numbers point to the Lync Server 2013 pool, you can then decommission the Lync Server 2010 pool.</span></span>

    
    </div>

<span data-ttu-id="a6fdf-126">**Lync Server コントロールパネルを使用して、ダイヤルインアクセス番号の移行を確認する**</span><span class="sxs-lookup"><span data-stu-id="a6fdf-126">**Verify the dial-in access number migration using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="a6fdf-127">**Csuseradministrator**ロールまたは**csadministrator**ロールに割り当てられているユーザーアカウントから、社内展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-127">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a6fdf-128">[Lync Server コントロール パネル] を開きます。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-128">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="a6fdf-129">左側のナビゲーション バーで [**会議**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-129">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="a6fdf-130">[**ダイヤルインアクセス番号**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-130">Click the **Dial-in Access Number** tab.</span></span>

5.  <span data-ttu-id="a6fdf-131">すべてのダイヤルインアクセス番号が、Lync Server 2013 でホストされているプールに移行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-131">Verify all the dial-in access number are migrated to the pool hosted on Lync Server 2013.</span></span>

<span data-ttu-id="a6fdf-132">**Lync Server 管理シェルを使用して、ダイヤルインアクセス番号の移行を確認する**</span><span class="sxs-lookup"><span data-stu-id="a6fdf-132">**Verify the dial-in access number migration using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="a6fdf-133">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-133">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="a6fdf-134">移行されたダイヤルイン会議アクセス番号をすべて返すには、コマンドラインで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-134">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  <span data-ttu-id="a6fdf-135">すべてのダイヤルインアクセス番号が、Lync Server 2013 でホストされているプールに移行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6fdf-135">Verify all the dial-in access numbers are migrated to the pool hosted on Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

