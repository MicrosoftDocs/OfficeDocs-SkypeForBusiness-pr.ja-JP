---
title: 'Lync Server 2013: ネットワークサブネットの削除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting network subnets
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49733806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93806d3e9d5f0cb7f004a90d6f461b363aff65f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-subnets-in-lync-server-2013"></a><span data-ttu-id="ff0fc-102">Lync Server 2013 でのネットワークサブネットの削除</span><span class="sxs-lookup"><span data-stu-id="ff0fc-102">Deleting network subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff0fc-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ff0fc-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ff0fc-104">次の手順を使用して、サブネットを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="ff0fc-104">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="ff0fc-105">Lync Server コントロールパネルから、ネットワークサブネットの作成、変更、または削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ff0fc-105">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="ff0fc-106">ネットワークサブネットの作成または変更の詳細については、「 [Lync Server 2013 でネットワークサブネットを作成または変更](lync-server-2013-create-or-modify-network-subnets.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff0fc-106">For details on creating or modifying network subnets, see [Create or modify network subnets in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span></span>

<span data-ttu-id="ff0fc-107">通話受付制御 (CAC) が実装されている Microsoft Lync Server 2013 の大半の展開では、通常、多数のサブネットが存在します。</span><span class="sxs-lookup"><span data-stu-id="ff0fc-107">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="ff0fc-108">このため、多くの場合、Lync Server 管理シェルからサブネットを構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ff0fc-108">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="ff0fc-109">そこから、Windows PowerShell コマンドレットの**Import-CSV**と組み合わせて、**新しい csnetworksubnet**を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="ff0fc-109">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="ff0fc-110">これらのコマンドレットを一緒に使用することで、サブネットの設定をコンマ区切り値 (.csv) ファイルから読み取り、複数のサブネットを同時に作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ff0fc-110">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="ff0fc-111">.Csv ファイルからサブネットを作成する方法の例については、「[新しい-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff0fc-111">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-delete-a-network-subnet"></a><span data-ttu-id="ff0fc-112">ネットワークサブネットを削除するには</span><span class="sxs-lookup"><span data-stu-id="ff0fc-112">To delete a network subnet</span></span>

1.  <span data-ttu-id="ff0fc-113">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ff0fc-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ff0fc-114">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ff0fc-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ff0fc-115">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ff0fc-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ff0fc-116">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サブネット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff0fc-116">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="ff0fc-117">[ **Subnet** ] ページで、削除するサブネットをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff0fc-117">On the **Subnet** page, click the subnet that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ff0fc-118">一度に複数のサブネットを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="ff0fc-118">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="ff0fc-119">これを行うには、ctrl キーを押しながら、CTRL キーを押しながら複数のサブネットを選択します。</span><span class="sxs-lookup"><span data-stu-id="ff0fc-119">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="ff0fc-120">または、すべてのサブネットを選択するには、[<STRONG>編集</STRONG>] メニューの [<STRONG>すべて選択</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff0fc-120">Or, to select all subnets, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="ff0fc-121">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff0fc-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="ff0fc-122">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff0fc-122">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ff0fc-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff0fc-123">See Also</span></span>


[<span data-ttu-id="ff0fc-124">Lync Server 2013 でネットワークサブネットを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="ff0fc-124">Create or modify network subnets in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

