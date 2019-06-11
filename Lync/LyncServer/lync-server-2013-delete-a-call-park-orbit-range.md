---
title: 'Lync Server 2013: コールパークの範囲を削除する範囲'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a Call Park orbit range
ms:assetid: 85e9f916-062d-450d-ac0a-aeaefc0f7cdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182546(v=OCS.15)
ms:contentKeyID: 48184713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69144e6552f9c3688c904c8522689abc8da7add2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-call-park-orbit-range-in-lync-server-2013"></a><span data-ttu-id="66abd-102">Lync Server 2013 でのコールパークの範囲の削除</span><span class="sxs-lookup"><span data-stu-id="66abd-102">Delete a Call Park orbit range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66abd-103">_**最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="66abd-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="66abd-104">次のいずれかの手順を使用して、コールパーク軌道範囲を削除します。</span><span class="sxs-lookup"><span data-stu-id="66abd-104">Use one of the following procedures to delete a Call Park orbit range.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-a-call-park-orbit-range"></a><span data-ttu-id="66abd-105">Lync Server コントロールパネルを使用して、通話パークの範囲を削除するには</span><span class="sxs-lookup"><span data-stu-id="66abd-105">To use Lync Server Control Panel to delete a Call Park orbit range</span></span>

1.  <span data-ttu-id="66abd-106">RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="66abd-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="66abd-107">詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66abd-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="66abd-108">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="66abd-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="66abd-109">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="66abd-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="66abd-110">左側のナビゲーション バーで [**音声機能**] をクリックし、[**コール パーク**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66abd-110">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4.  <span data-ttu-id="66abd-111">[ **Call パーク**] ページの [検索] フィールドで、削除する範囲の名前のすべてまたは一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="66abd-111">On the **Call Park** page, in the search field, type all or part of the name of the orbit range that you want to delete.</span></span>

5.  <span data-ttu-id="66abd-112">Orbits の結果の一覧で、軌道をクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66abd-112">In the resulting list of orbits, click the orbit, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="66abd-113">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66abd-113">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-call-park-orbit-range"></a><span data-ttu-id="66abd-114">Windows PowerShell を使用してコールパークを削除するには範囲</span><span class="sxs-lookup"><span data-stu-id="66abd-114">To use Windows PowerShell to delete a Call Park orbit range</span></span>

1.  <span data-ttu-id="66abd-115">Lync Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 の委任セットアップの権限](lync-server-2013-delegate-setup-permissions.md)」で説明されているように、必要なユーザー権限を持つコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="66abd-115">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="66abd-116">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="66abd-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="66abd-117">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="66abd-117">At the command line, type:</span></span>
    
        Remove-CsCallParkOrbit -Identity "<orbit range name>" 
    
    <span data-ttu-id="66abd-118">例:</span><span class="sxs-lookup"><span data-stu-id="66abd-118">For example:</span></span>
    
        Remove-CsCallParkOrbit -Identity "Redmond orbit 1"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66abd-119">その他のオプションの詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66abd-119">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="66abd-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="66abd-120">See Also</span></span>


[<span data-ttu-id="66abd-121">通話パークの作成または変更 Lync Server 2013 の範囲の軌道</span><span class="sxs-lookup"><span data-stu-id="66abd-121">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  


[<span data-ttu-id="66abd-122">Remove-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="66abd-122">Remove-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit)  
[<span data-ttu-id="66abd-123">Get-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="66abd-123">Get-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

