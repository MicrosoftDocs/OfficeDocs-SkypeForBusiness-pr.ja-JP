---
title: 'Lync Server 2013: ネットワークサブネットの削除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network subnets
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49733806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05e47875007bd9fb7893ad952bea6772d2d9df9b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-network-subnets-in-lync-server-2013"></a><span data-ttu-id="c8e27-102">Lync Server 2013 でのネットワークサブネットの削除</span><span class="sxs-lookup"><span data-stu-id="c8e27-102">Deleting network subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8e27-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="c8e27-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c8e27-104">次の手順を使用して、サブネットを削除できます。</span><span class="sxs-lookup"><span data-stu-id="c8e27-104">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="c8e27-105">Lync Server コントロールパネルから、ネットワークサブネットを作成、変更、または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="c8e27-105">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="c8e27-106">ネットワークサブネットの作成または変更の詳細については、「 [Lync Server 2013 でネットワークサブネットを作成または変更](lync-server-2013-create-or-modify-network-subnets.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8e27-106">For details on creating or modifying network subnets, see [Create or modify network subnets in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span></span>

<span data-ttu-id="c8e27-107">通話受付管理 (CAC) が実装されている Microsoft Lync Server 2013 のほとんどの展開では、通常、多くのサブネットがあります。</span><span class="sxs-lookup"><span data-stu-id="c8e27-107">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="c8e27-108">このため、多くの場合、Lync Server 管理シェルからサブネットを構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c8e27-108">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="c8e27-109">そこから、Windows PowerShell コマンドレットの**Import-CSV**と共に、**新しい-csnetworksubnet**を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="c8e27-109">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="c8e27-110">これらのコマンドレットを使用すると、コンマ区切り値 (.csv) ファイルからサブネット設定を読み込み、同時に複数のサブネットを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="c8e27-110">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="c8e27-111">.csv ファイルからサブネットを作成する方法の例は、「[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8e27-111">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-delete-a-network-subnet"></a><span data-ttu-id="c8e27-112">ネットワーク サブネットを削除するには</span><span class="sxs-lookup"><span data-stu-id="c8e27-112">To delete a network subnet</span></span>

1.  <span data-ttu-id="c8e27-113">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c8e27-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c8e27-114">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c8e27-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c8e27-115">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8e27-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c8e27-116">左側のナビゲーション バーで [**ネットワーク構成**]、[**サブネット**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8e27-116">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="c8e27-117">[**サブネット**] ページで、削除するサブネットをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8e27-117">On the **Subnet** page, click the subnet that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c8e27-p104">1 つ以上のサブネットを一度に削除できます。これを実行するには、Ctrl キーを押しながら、複数のサブネットを選択します。または、すべてのサブネットを選択するには、[<STRONG>編集</STRONG>] メニューの [<STRONG>すべて選択</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8e27-p104">You can delete more than one subnet at a time. To do this, press CTRL and select multiple subnets while holding down the CTRL key. Or, to select all subnets, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="c8e27-121">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8e27-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="c8e27-122">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8e27-122">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c8e27-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8e27-123">See Also</span></span>


[<span data-ttu-id="c8e27-124">Lync Server 2013 でのネットワークサブネットの作成または変更</span><span class="sxs-lookup"><span data-stu-id="c8e27-124">Create or modify network subnets in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

