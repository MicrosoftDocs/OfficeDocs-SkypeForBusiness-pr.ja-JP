---
title: 'Lync Server 2013: 割り当てられていない番号範囲を削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an unassigned number range
ms:assetid: a8141bfb-b94d-4d0f-a7a9-2e60d10b103a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182565(v=OCS.15)
ms:contentKeyID: 48185090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1a27598af0185dcccac211f89ea7d7a88060fea
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501534"
---
# <a name="delete-an-unassigned-number-range-in-lync-server-2013"></a><span data-ttu-id="f16b8-102">Lync Server 2013 で割り当てられていない番号範囲を削除する</span><span class="sxs-lookup"><span data-stu-id="f16b8-102">Delete an unassigned number range in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f16b8-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f16b8-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f16b8-104">アナウンスの割り当てられていない番号範囲を削除するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="f16b8-104">Use one of the following procedures to delete an unassigned number range for Announcements.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-unassigned-number-range"></a><span data-ttu-id="f16b8-105">Lync Server コントロールパネルを使用して割り当てられていない番号範囲を削除するには</span><span class="sxs-lookup"><span data-stu-id="f16b8-105">To use Lync Server Control Panel to delete an unassigned number range</span></span>

1.  <span data-ttu-id="f16b8-106">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f16b8-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="f16b8-107">詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f16b8-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f16b8-108">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f16b8-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f16b8-109">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f16b8-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f16b8-110">左側のナビゲーション バーで [**音声機能**] をクリックし、[**割り当てられていない番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f16b8-110">In the left navigation bar, click **Voice Features** and then click **Unassigned Number**.</span></span>

4.  <span data-ttu-id="f16b8-111">[**割り当てられていない番号**] ページの検索フィールドで、削除する割り当てられていない番号範囲の名前または名前の一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="f16b8-111">On the **Unassigned Number** page, in the search field, type all or part of the name of the unassigned number range you want to delete.</span></span>

5.  <span data-ttu-id="f16b8-112">結果の番号範囲の一覧で、名前をクリックして、[**編集**] をクリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f16b8-112">In the resulting list of number ranges, click the name, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="f16b8-113">[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f16b8-113">Click **Commit all**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-unassigned-number-range"></a><span data-ttu-id="f16b8-114">Windows PowerShell を使用して割り当てられていない番号範囲を削除するには</span><span class="sxs-lookup"><span data-stu-id="f16b8-114">To use Windows PowerShell to delete an unassigned number range</span></span>

1.  <span data-ttu-id="f16b8-115">Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 のセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="f16b8-115">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f16b8-116">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f16b8-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f16b8-117">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f16b8-117">At the command line, type:</span></span>
    
        Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
    
    <span data-ttu-id="f16b8-118">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f16b8-118">For example:</span></span>
    
        Remove-CsUnassignedNumber -Identity "Unassigned range 1"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f16b8-119">その他のオプションの詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">get-cscallparkorbit</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f16b8-119">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f16b8-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="f16b8-120">See Also</span></span>


[<span data-ttu-id="f16b8-121">Lync Server 2013 で割り当てられていない番号範囲を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="f16b8-121">Create or modify an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-unassigned-number-range.md)  


[<span data-ttu-id="f16b8-122">Remove-csunassignednumber</span><span class="sxs-lookup"><span data-stu-id="f16b8-122">Remove-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUnassignedNumber)  
[<span data-ttu-id="f16b8-123">Remove-csunassignednumber</span><span class="sxs-lookup"><span data-stu-id="f16b8-123">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

