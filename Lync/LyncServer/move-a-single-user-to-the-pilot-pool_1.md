---
title: 1人のユーザーをパイロットプールに移動する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41d89241cdddd129ea5e7fad38e7a3d761fb220b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514974"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="1856a-102">1人のユーザーをパイロットプールに移動する</span><span class="sxs-lookup"><span data-stu-id="1856a-102">Move a single user to the pilot pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1856a-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="1856a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1856a-104">Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルを使用して、ユーザーを Office Communications Server 2007 R2 プールから Lync Server 2013 パイロットプールに移動することができます。</span><span class="sxs-lookup"><span data-stu-id="1856a-104">You can move a user from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="1856a-105">次の例では、レジストラープール列は、 **\<Office Communications Server\>** Office Communications Server 2007 R2 プールで、これらのユーザーの6つすべてがこのプールに接続されています。</span><span class="sxs-lookup"><span data-stu-id="1856a-105">In the example below, in the Registrar pool column, **\<Office Communications Server\>** is the Office Communications Server 2007 R2 pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="1856a-106">Lync Server 2013 コントロールパネルおよび Lync Server 管理シェルを使用して、ユーザーを Lync Server 2013 プールに移動するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="1856a-106">Use the following procedures to move a user to your Lync Server 2013 pool using Lync Server 2013 Control Panel and Lync Server Management Shell.</span></span>

<span data-ttu-id="1856a-107">![Lync Server コントロールパネルでの OCS ユーザーの検索](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Lync Server コントロールパネルでの OCS ユーザーの検索")</span><span class="sxs-lookup"><span data-stu-id="1856a-107">![Search for OCS users in Lync Server Control Panel](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="1856a-108">Lync Server 2013 コントロールパネルを使用してユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="1856a-108">To move a user by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="1856a-109">RTCUniversalServerAdmins グループのメンバーであるか、CsAdministrator または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1856a-109">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="1856a-110">[Lync Server コントロール パネル] を開きます。</span><span class="sxs-lookup"><span data-stu-id="1856a-110">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="1856a-111">[**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1856a-111">Click **Users**.</span></span>

4.  <span data-ttu-id="1856a-112">[**ユーザー検索**] タブで、[**検索**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1856a-112">From the **User Search** tab, click the **Search** button.</span></span>

5.  <span data-ttu-id="1856a-113">次に、[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1856a-113">Next, click **Add Filter**.</span></span>

6.  <span data-ttu-id="1856a-114">[**Office Communications Server ユーザー**] が [**True**] のフィルターを作成します。</span><span class="sxs-lookup"><span data-stu-id="1856a-114">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

7.  <span data-ttu-id="1856a-115">[ **検索** ] をクリックして、従来の Office Communications Server 2007 R2 ユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="1856a-115">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="1856a-116">![Lync Server コントロールパネルでの OCS ユーザーの検索](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Lync Server コントロールパネルでの OCS ユーザーの検索")</span><span class="sxs-lookup"><span data-stu-id="1856a-116">![Search for OCS users in Lync Server Control Panel](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>  

8.  <span data-ttu-id="1856a-117">Lync Server 2013 プールに移動するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="1856a-117">Select a user that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="1856a-118">この例では、Sara Davis というユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="1856a-118">In this example, we will move user Sara Davis.</span></span>

9.  <span data-ttu-id="1856a-119">[**アクション**]メニューの [**選択されたユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1856a-119">On the **Action** menu, select **Move selected users to pool**.</span></span>

10. <span data-ttu-id="1856a-120">ドロップダウンリストから、[Lync Server 2013] プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="1856a-120">From the drop-down list, select the Lync Server 2013 pool.</span></span>

11. <span data-ttu-id="1856a-121">[**アクション**] をクリックし、[**選択されたユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1856a-121">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="1856a-122">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1856a-122">Click **OK**.</span></span>
    
    <span data-ttu-id="1856a-123">![[ユーザーの移動] ダイアログでの転送先プールの設定](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "[ユーザーの移動] ダイアログでの転送先プールの設定")</span><span class="sxs-lookup"><span data-stu-id="1856a-123">![Setting the Destination pool in Move Users dialog](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Setting the Destination pool in Move Users dialog")</span></span>  

12. <span data-ttu-id="1856a-124">ユーザーの [ **レジストラー pool** ] 列に Lync Server 2013 プールが含まれるようになっていることを確認します。これは、ユーザーが正常に移動されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="1856a-124">Verify that the **Registrar pool** column for the user now contains the Lync Server 2013 pool, which indicates that the user has been successfully moved</span></span>

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="1856a-125">Lync Server 2013 管理シェルを使用してユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="1856a-125">To move a user by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="1856a-126">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1856a-126">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="1856a-127">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1856a-127">At the command line, type the following:</span></span>
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  <span data-ttu-id="1856a-128">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1856a-128">Next, at the command line, type the following:</span></span>
    
        Get-CsUser -Identity "David Pelton"

4.  <span data-ttu-id="1856a-129">**RegistrarPool** identity は、Lync Server 2013 プールを指すようになります。</span><span class="sxs-lookup"><span data-stu-id="1856a-129">The **RegistrarPool** identity now points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="1856a-130">この ID が存在していることにより、ユーザーが正常に移動されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1856a-130">The presence of this identity confirms that the user has been successfully moved.</span></span>
    
    <span data-ttu-id="1856a-131">![Id フィルターを使用した Get-CsUser コマンドレットからの出力](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Id フィルターを使用した Get-CsUser コマンドレットからの出力")</span><span class="sxs-lookup"><span data-stu-id="1856a-131">![Output from Get-CsUser cmdlet with Identity filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output from Get-CsUser cmdlet with Identity filter")</span></span>  
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1856a-132"><STRONG>Get-CsUser</STRONG> コマンドレットの詳細については、<STRONG>Get-Help Get-CsUser –Detailed</STRONG> を実行してください。</span><span class="sxs-lookup"><span data-stu-id="1856a-132">For details about the <STRONG>Get-CsUser</STRONG> cmdlet, run: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

