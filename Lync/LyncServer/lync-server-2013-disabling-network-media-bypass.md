---
title: 'Lync Server 2013: ネットワークメディアバイパスの無効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling network media bypass
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49733741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58bf551f94bc6b3ba919437730841f54dd01e291
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034839"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="a7b5d-102">Lync Server 2013 でのネットワークメディアバイパスの無効化</span><span class="sxs-lookup"><span data-stu-id="a7b5d-102">Disabling network media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7b5d-103">_**トピックの最終更新日:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="a7b5d-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="a7b5d-104">メディアバイパスの設定は、Microsoft Lync Server 2013 の展開全体でグローバルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a7b5d-104">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="a7b5d-105">メディアバイパスは、呼び出しが仲介サーバーをバイパスすることを許可します。</span><span class="sxs-lookup"><span data-stu-id="a7b5d-105">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="a7b5d-106">メディアバイパスを使用するタイミングの詳細については、「計画」セクションの「 [Lync Server 2013 でのメディアバイパスの計画](lync-server-2013-planning-for-media-bypass.md)」を参照してください。Lync Server コントロールパネルからメディアバイパスを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a7b5d-106">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.You can disable media bypass from the Lync Server Control Panel.</span></span> <span data-ttu-id="a7b5d-107">Medial バイパスの有効化と構成の詳細については、「 [Lync Server でのネットワークメディアバイパスの有効化 2013](lync-server-2013-enabling-network-media-bypass.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7b5d-107">For details on enabling and configuring medial bypass, see [Enabling network media bypass in Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)</span></span>

<div>

## <a name="to-disable-media-bypass"></a><span data-ttu-id="a7b5d-108">メディア バイパスを無効にするには</span><span class="sxs-lookup"><span data-stu-id="a7b5d-108">To disable media bypass</span></span>

1.  <span data-ttu-id="a7b5d-109">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a7b5d-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a7b5d-110">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a7b5d-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a7b5d-111">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7b5d-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a7b5d-112">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**グローバル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7b5d-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="a7b5d-p103">[**グローバル**] ページで [**グローバル**] 構成をクリックします。存在する構成は必ず 1 つのみで、必ずグローバルという名前です。</span><span class="sxs-lookup"><span data-stu-id="a7b5d-p103">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="a7b5d-115">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7b5d-115">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="a7b5d-116">[**グローバル設定の編集**] ページの [**メディア バイパスを有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a7b5d-116">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="a7b5d-117">[**確定**] をクリックして変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="a7b5d-117">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a7b5d-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7b5d-118">See Also</span></span>


[<span data-ttu-id="a7b5d-119">Lync Server 2013 でのネットワークメディアバイパスの有効化</span><span class="sxs-lookup"><span data-stu-id="a7b5d-119">Enabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-enabling-network-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

