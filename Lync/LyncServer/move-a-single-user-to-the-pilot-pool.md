---
title: 1人のユーザーをパイロットプールに移動する
description: 1人のユーザーをパイロットプールに移動します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5f7396ed2d92c7015f01ff6cd6e90fd3998219d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574733"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="48c6c-103">1人のユーザーをパイロットプールに移動する</span><span class="sxs-lookup"><span data-stu-id="48c6c-103">Move a single user to the pilot pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48c6c-104">_**トピックの最終更新日:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="48c6c-104">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="48c6c-105">Lync server 2013 コントロールパネルまたは Lync Server 2013 管理シェルを使用して、ユーザーを lync server 2010 プールから Lync Server 2013 パイロットプールに移動することができます。</span><span class="sxs-lookup"><span data-stu-id="48c6c-105">You can move a user from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="48c6c-106">次の例では、レジストラープール列の **pool01.contoso.net** は Lync Server 2010 プールで、これらのユーザーの6つすべてがこのプールに接続されています。</span><span class="sxs-lookup"><span data-stu-id="48c6c-106">In the example below, in the Registrar pool column, **pool01.contoso.net** is the Lync Server 2010 pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="48c6c-107">Lync Server 2013 コントロールパネルおよび Lync Server 管理シェルを使用して、ユーザーを Lync Server 2013 プールに移動するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="48c6c-107">Use the following procedures to move a user to your Lync Server 2013 pool using Lync Server 2013 Control Panel and Lync Server Management Shell.</span></span>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="48c6c-108">Lync Server 2013 コントロールパネルを使用してユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="48c6c-108">To move a user by using the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="48c6c-109">**Lync Server 2013 コントロール パネル内のユーザー一覧**</span><span class="sxs-lookup"><span data-stu-id="48c6c-109">**List of users in the Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="48c6c-110">![Lync Server コントロールパネル、[ユーザーの移動] ダイアログ](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server コントロールパネル、[ユーザーの移動] ダイアログ")</span><span class="sxs-lookup"><span data-stu-id="48c6c-110">![Lync Server Control Panel, Move User dialog](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server Control Panel, Move User dialog")</span></span>

1.  <span data-ttu-id="48c6c-111">RTCUniversalServerAdmins グループ、CsAdministrator 管理者ロール、または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="48c6c-111">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="48c6c-112">[**Lync Server コントロール パネル**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="48c6c-112">Open **Lync Server Control Panel**.</span></span>

3.  <span data-ttu-id="48c6c-113">[**ユーザー**]、[検索]、[**ユーザー検索**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="48c6c-113">Click **Users**, click Search, and then click **Find**.</span></span>

4.  <span data-ttu-id="48c6c-114">Lync Server 2013 プールに移動するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="48c6c-114">Select a user that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="48c6c-115">この例では、Sara Davis というユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="48c6c-115">In this example, we will move user Sara Davis.</span></span>

5.  <span data-ttu-id="48c6c-116">[**アクション**]メニューの [**選択されたユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48c6c-116">On the **Action** menu, select **Move selected users to pool**.</span></span>

6.  <span data-ttu-id="48c6c-117">ドロップダウンリストから、[Lync Server 2013] プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="48c6c-117">From the drop-down list, select the Lync Server 2013 pool.</span></span>

7.  <span data-ttu-id="48c6c-118">[**アクション**] をクリックし、[**選択されたユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48c6c-118">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="48c6c-119">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48c6c-119">Click **OK**.</span></span>
    
    <span data-ttu-id="48c6c-120">![[ユーザーの移動]、[宛先レジストラープール] ダイアログボックス](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "[ユーザーの移動]、[宛先レジストラープール] ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="48c6c-120">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

8.  <span data-ttu-id="48c6c-121">ユーザーの [ **レジストラープール** ] 列に Lync Server 2013 プールが含まれるようになっていることを確認します。これは、ユーザーが正常に移動されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="48c6c-121">Verify that the **Registrar pool** column for the user now contains the Lync Server 2013 pool, which indicates that the user has been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="48c6c-122">Lync Server 2013 管理シェルを使用してユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="48c6c-122">To move a user by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="48c6c-123">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="48c6c-123">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="48c6c-124">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="48c6c-124">At the command line, type the following:</span></span>
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  <span data-ttu-id="48c6c-125">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="48c6c-125">Next, at the command line, type the following:</span></span>
    
        Get-CsUser -Identity "David Pelton"

4.  <span data-ttu-id="48c6c-126">**RegistrarPool** identity は、Lync Server 2013 プールを指すようになります。</span><span class="sxs-lookup"><span data-stu-id="48c6c-126">The **RegistrarPool** identity now points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="48c6c-127">この ID が存在していることにより、ユーザーが正常に移動されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="48c6c-127">The presence of this identity confirms that the user has been successfully moved.</span></span>
    
    <span data-ttu-id="48c6c-128">![Id フィルターを使用した Get-CsUser コマンドレットからの出力](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Id フィルターを使用した Get-CsUser コマンドレットからの出力")</span><span class="sxs-lookup"><span data-stu-id="48c6c-128">![Output from Get-CsUser cmdlet with Identity filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output from Get-CsUser cmdlet with Identity filter")</span></span>  
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="48c6c-129"><STRONG>Get-CsUser</STRONG> コマンドレットの詳細については、<STRONG>Get-Help Get-CsUser –Detailed</STRONG> を実行してください。</span><span class="sxs-lookup"><span data-stu-id="48c6c-129">For details about the <STRONG>Get-CsUser</STRONG> cmdlet, run: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

