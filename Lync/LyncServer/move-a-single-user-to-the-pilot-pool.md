---
title: 1人のユーザーをパイロットプールに移動する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9ee58a49afaa9c1e57689b6a3a87fac1a6a4502
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="419c7-102">1人のユーザーをパイロットプールに移動する</span><span class="sxs-lookup"><span data-stu-id="419c7-102">Move a single user to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="419c7-103">_**最終更新日:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="419c7-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="419c7-104">Lync server 2013 コントロールパネルまたは Lync Server 2013 Management Shell を使って、ユーザーを Lync Server 2010 プールから Lync Server 2013 パイロットプールに移動することができます。</span><span class="sxs-lookup"><span data-stu-id="419c7-104">You can move a user from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="419c7-105">次の例では、[レジストラー pool] 列では、 **pool01.contoso.net**は Lync Server 2010 プールであり、これらの6人のユーザーはこのプールに接続されています。</span><span class="sxs-lookup"><span data-stu-id="419c7-105">In the example below, in the Registrar pool column, **pool01.contoso.net** is the Lync Server 2010 pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="419c7-106">Lync Server 2013 コントロールパネルと Lync Server 管理シェルを使用して、ユーザーを Lync Server 2013 プールに移動するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="419c7-106">Use the following procedures to move a user to your Lync Server 2013 pool using Lync Server 2013 Control Panel and Lync Server Management Shell.</span></span>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="419c7-107">Lync Server 2013 コントロールパネルを使用してユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="419c7-107">To move a user by using the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="419c7-108">**Lync Server 2013 コントロールパネルに表示されたユーザーのリスト**</span><span class="sxs-lookup"><span data-stu-id="419c7-108">**List of users in the Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="419c7-109">![Lync Server コントロールパネルの [ユーザーの移動] ダイアログ](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server コントロールパネルの [ユーザーの移動] ダイアログ")</span><span class="sxs-lookup"><span data-stu-id="419c7-109">![Lync Server Control Panel, Move User dialog](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server Control Panel, Move User dialog")</span></span>

1.  <span data-ttu-id="419c7-110">RTCUniversalServerAdmins グループ、CsAdministrator 管理者ロール、または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="419c7-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="419c7-111">[**Lync Server コントロール パネル**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="419c7-111">Open **Lync Server Control Panel**.</span></span>

3.  <span data-ttu-id="419c7-112">[**ユーザー**]、[検索] の順にクリックして、[**ユーザー検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="419c7-112">Click **Users**, click Search, and then click **Find**.</span></span>

4.  <span data-ttu-id="419c7-113">Lync Server 2013 プールに移動するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="419c7-113">Select a user that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="419c7-114">この例では、Sara Davis というユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="419c7-114">In this example, we will move user Sara Davis.</span></span>

5.  <span data-ttu-id="419c7-115">[**アクション**] メニューの [**選択されたユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="419c7-115">On the **Action** menu, select **Move selected users to pool**.</span></span>

6.  <span data-ttu-id="419c7-116">ドロップダウンリストから、Lync Server 2013 プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="419c7-116">From the drop-down list, select the Lync Server 2013 pool.</span></span>

7.  <span data-ttu-id="419c7-117">[**アクション**] をクリックし、[**選択されたユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="419c7-117">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="419c7-118">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="419c7-118">Click **OK**.</span></span>
    
    <span data-ttu-id="419c7-119">![[ユーザーの移動]、[宛先レジストラー pool] ダイアログボックス](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "[ユーザーの移動]、[宛先レジストラー pool] ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="419c7-119">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

8.  <span data-ttu-id="419c7-120">ユーザーの**レジストラー pool**列に Lync Server 2013 プールが含まれていることを確認します。これは、ユーザーが正常に移動されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="419c7-120">Verify that the **Registrar pool** column for the user now contains the Lync Server 2013 pool, which indicates that the user has been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="419c7-121">Lync Server 2013 管理シェルを使用してユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="419c7-121">To move a user by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="419c7-122">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="419c7-122">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="419c7-123">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="419c7-123">At the command line, type the following:</span></span>
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  <span data-ttu-id="419c7-124">次に、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="419c7-124">Next, at the command line, type the following:</span></span>
    
        Get-CsUser -Identity "David Pelton"

4.  <span data-ttu-id="419c7-125">**RegistrarPool** Id が Lync Server 2013 プールを指すようになりました。</span><span class="sxs-lookup"><span data-stu-id="419c7-125">The **RegistrarPool** identity now points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="419c7-126">この id の存在は、ユーザーが正常に移動されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="419c7-126">The presence of this identity confirms that the user has been successfully moved.</span></span>
    
    <span data-ttu-id="419c7-127">![Id フィルターを使用したユーザーのアクセスコマンドレットの出力](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Id フィルターを使用したユーザーのアクセスコマンドレットの出力")</span><span class="sxs-lookup"><span data-stu-id="419c7-127">![Output from Get-CsUser cmdlet with Identity filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output from Get-CsUser cmdlet with Identity filter")</span></span>  
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="419c7-128"><STRONG>ユーザーの取得</STRONG>コマンドレットの詳細については、次を実行してください: <STRONG>get-ヘルプの取得-Csuser –詳細</STRONG></span><span class="sxs-lookup"><span data-stu-id="419c7-128">For details about the <STRONG>Get-CsUser</STRONG> cmdlet, run: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

