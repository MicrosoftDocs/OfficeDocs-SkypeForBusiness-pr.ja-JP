---
title: 'Lync Server 2013: ネットワーク地域の作成または変更'
description: 'Lync Server 2013: ネットワーク地域を作成または変更しています。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network regions
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182579(v=OCS.15)
ms:contentKeyID: 48185266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b02a041272f0df27d2133ca26096caeb01816c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544033"
---
# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a><span data-ttu-id="4bb60-103">Lync Server 2013 でのネットワーク地域の作成または変更</span><span class="sxs-lookup"><span data-stu-id="4bb60-103">Creating or modifying network regions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4bb60-104">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4bb60-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4bb60-105">ネットワーク地域は、複数の地理的な領域にまたがるネットワークのさまざまな部分を相互接続します。</span><span class="sxs-lookup"><span data-stu-id="4bb60-105">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="4bb60-106">すべてのネットワーク地域は、セントラル サイトと関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bb60-106">Every network region must be associated with a central site.</span></span> <span data-ttu-id="4bb60-107">このセントラル サイトは、通話受付管理 (CAC) 帯域幅ポリシー サービスが実行されているデータ センター サイトです。</span><span class="sxs-lookup"><span data-stu-id="4bb60-107">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="4bb60-108">Lync Server コントロールパネルを使用して、ネットワーク地域を構成できます。</span><span class="sxs-lookup"><span data-stu-id="4bb60-108">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="4bb60-109">ネットワーク地域には、オーディオとビデオの接続でインターネット経由の代替パスを許可するかどうかを決定する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4bb60-109">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="4bb60-110">Lync Server コントロールパネルから、ネットワーク地域を作成、変更、または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="4bb60-110">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="4bb60-111">ネットワーク地域を作成および変更するには、このトピックを参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="4bb60-111">Use this topic to create and modify network regions.</span></span> <span data-ttu-id="4bb60-112">既存のネットワーク領域の削除の詳細については、「 [Lync Server 2013 の既存のネットワーク地域の削除](lync-server-2013-deleting-existing-network-regions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bb60-112">For details about deleting existing network regions, see [Deleting existing network regions in Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span></span>

<div>

## <a name="to-create-a-network-region"></a><span data-ttu-id="4bb60-113">ネットワーク地域を作成するには</span><span class="sxs-lookup"><span data-stu-id="4bb60-113">To create a network region</span></span>

1.  <span data-ttu-id="4bb60-114">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4bb60-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4bb60-115">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4bb60-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4bb60-116">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bb60-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4bb60-117">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**地域**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bb60-117">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="4bb60-118">[**地域**] ページで [**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bb60-118">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="4bb60-119">[**新しい地域**] ページで、[**名前**] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="4bb60-119">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="4bb60-120">この値は、Microsoft Lync Server 2013 展開内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bb60-120">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

6.  <span data-ttu-id="4bb60-121">[**セントラル サイト**] ドロップダウン リストで、このネットワーク地域に対応するセントラル サイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="4bb60-121">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="4bb60-p104">既定では、[**オーディオ代替パスを有効にする**] チェック ボックスはオンになっています。このフィールドで、プライマリ パスに適当な帯域幅がない場合に音声通話を代替パスにルーティングするかどうかを設定します。インターネットへの負荷分散を無効する必要がある場合にのみ、このチェック ボックスをオフにします。いずれかの通話をインターネット通話にする場合は、帯域幅設定に関係なく、このチェック ボックスをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bb60-p104">The **Enable audio alternate path** check box is checked by default. This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="4bb60-p105">既定では、[**ビデオ代替パスを有効にする**] チェック ボックスはオンになっています。このフィールドで、プライマリ パスに適当な帯域幅がない場合にビデオ通話を代替パスにルーティングするかどうかを設定します。インターネットへの負荷分散を無効する必要がある場合にのみ、このチェック ボックスをオフにします。いずれかの通話をインターネット通話にする場合は、帯域幅設定に関係なく、このチェック ボックスをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bb60-p105">The **Enable video alternate path** check box is checked by default. This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="4bb60-130">(オプション) [**説明**] フィールドに値を入力して、名前だけでは表現できないこの地域に関する詳細を設定します。</span><span class="sxs-lookup"><span data-stu-id="4bb60-130">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="4bb60-131">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bb60-131">Click **Commit**.</span></span>

<span data-ttu-id="4bb60-132">[**関連付けられているサイト**] テーブルは、ネットワーク地域の作成では使用しません。</span><span class="sxs-lookup"><span data-stu-id="4bb60-132">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="4bb60-133">サイトを作成または変更するときに、サイトと地域を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="4bb60-133">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="4bb60-134">詳細については、「 [Lync Server 2013 でのネットワークサイトの作成または変更](lync-server-2013-creating-or-modifying-network-sites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bb60-134">For details, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

</div>

<div>

## <a name="to-modify-a-network-region"></a><span data-ttu-id="4bb60-135">ネットワーク地域を変更するには</span><span class="sxs-lookup"><span data-stu-id="4bb60-135">To modify a network region</span></span>

1.  <span data-ttu-id="4bb60-136">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4bb60-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4bb60-137">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4bb60-137">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4bb60-138">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bb60-138">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4bb60-139">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**地域**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bb60-139">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="4bb60-140">[**地域**] ページで、変更する地域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bb60-140">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="4bb60-141">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bb60-141">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="4bb60-142">[**編集 地域**] ページで、オーディオとビデオの代替パスを有効または無効に切り替えたり、説明を変更したりできます。詳細については、このトピック前半の「ネットワーク地域を作成するには」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bb60-142">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="4bb60-143">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bb60-143">Click **Commit**.</span></span>

<span data-ttu-id="4bb60-p108">このページでは [**関連付けられているサイト**] を変更できません。関連付けられているサイトの一覧は参考のために表示されています。これにより、地域設定を変更するとどのサイトが影響を受けるか確認することができます。</span><span class="sxs-lookup"><span data-stu-id="4bb60-p108">You cannot modify the **Associated sites** on this page. The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4bb60-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="4bb60-146">See Also</span></span>


[<span data-ttu-id="4bb60-147">Lync Server 2013 の既存のネットワーク領域の削除</span><span class="sxs-lookup"><span data-stu-id="4bb60-147">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
[<span data-ttu-id="4bb60-148">Lync Server 2013 で CAC のネットワーク地域を構成する</span><span class="sxs-lookup"><span data-stu-id="4bb60-148">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)  


[<span data-ttu-id="4bb60-149">新しい-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="4bb60-149">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[<span data-ttu-id="4bb60-150">設定-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="4bb60-150">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[<span data-ttu-id="4bb60-151">-CsNetworkRegion の削除</span><span class="sxs-lookup"><span data-stu-id="4bb60-151">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[<span data-ttu-id="4bb60-152">取得-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="4bb60-152">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

