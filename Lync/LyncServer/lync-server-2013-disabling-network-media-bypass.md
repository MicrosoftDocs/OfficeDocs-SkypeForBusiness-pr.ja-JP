---
title: 'Lync Server 2013: ネットワークメディアのバイパスを無効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disabling network media bypass
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49733741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9bfab9fbf8174a1124a45681098196c84ac5444
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="25567-102">Lync Server 2013 でネットワークメディアのバイパスを無効にする</span><span class="sxs-lookup"><span data-stu-id="25567-102">Disabling network media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25567-103">_**最終更新日:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="25567-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="25567-104">メディアバイパスの設定は、Microsoft Lync Server 2013 の展開でグローバルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="25567-104">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="25567-105">メディアのバイパスでは、仲介サーバーを経由せずに通話を発信できます。</span><span class="sxs-lookup"><span data-stu-id="25567-105">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="25567-106">メディアのバイパスを使用する場合の詳細については、「計画」セクションの「 [Lync Server 2013 でのメディアのバイパスの計画](lync-server-2013-planning-for-media-bypass.md)」を参照してください。Lync Server コントロールパネルからメディアのバイパスを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="25567-106">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.You can disable media bypass from the Lync Server Control Panel.</span></span> <span data-ttu-id="25567-107">Medial バイパスの有効化と構成の詳細については、「 [Lync Server 2013 でネットワークメディアのバイパスを有効にする](lync-server-2013-enabling-network-media-bypass.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25567-107">For details on enabling and configuring medial bypass, see [Enabling network media bypass in Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)</span></span>

<div>

## <a name="to-disable-media-bypass"></a><span data-ttu-id="25567-108">メディアのバイパスを無効にするには</span><span class="sxs-lookup"><span data-stu-id="25567-108">To disable media bypass</span></span>

1.  <span data-ttu-id="25567-109">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="25567-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="25567-110">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="25567-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="25567-111">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="25567-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="25567-112">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**グローバル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="25567-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="25567-113">[**グローバル**] ページで、[**グローバル**構成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="25567-113">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="25567-114">構成は常に1つだけであり、常に Global という名前が付いています。</span><span class="sxs-lookup"><span data-stu-id="25567-114">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="25567-115">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="25567-115">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="25567-116">[**グローバル設定の編集**] ページで、[**メディアバイパスを有効にする**] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="25567-116">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="25567-117">[**コミット**] をクリックして変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="25567-117">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="25567-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="25567-118">See Also</span></span>


[<span data-ttu-id="25567-119">Lync Server 2013 でネットワークメディアのバイパスを有効にする</span><span class="sxs-lookup"><span data-stu-id="25567-119">Enabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-enabling-network-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

