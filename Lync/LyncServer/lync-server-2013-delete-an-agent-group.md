---
title: 'Lync Server 2013: エージェントグループを削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an agent group
ms:assetid: df385fd1-62f4-42b7-a349-4eb38dea50c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182597(v=OCS.15)
ms:contentKeyID: 48185670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adcdc0245f6fdd835492084fcae91389409f52c8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="b23ca-102">Lync Server 2013 でエージェントグループを削除する</span><span class="sxs-lookup"><span data-stu-id="b23ca-102">Delete an agent group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b23ca-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b23ca-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b23ca-104">エージェントグループを削除するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="b23ca-104">Use one of the following procedures to delete an agent group.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-agent-group"></a><span data-ttu-id="b23ca-105">Lync Server コントロールパネルを使用してエージェントグループを削除するには</span><span class="sxs-lookup"><span data-stu-id="b23ca-105">To use Lync Server Control Panel to delete an agent group</span></span>

1.  <span data-ttu-id="b23ca-106">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="b23ca-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="b23ca-107">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b23ca-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b23ca-108">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b23ca-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b23ca-109">左側のナビゲーション バーで、[**応答グループ**] をクリックし、[**グループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b23ca-109">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="b23ca-110">[**応答グループ**] ページで、削除するエージェントグループの名前のすべてまたは一部を検索フィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="b23ca-110">On the **Response Groups** page, type all or part of the name of the agent group that you want to delete in the search field.</span></span>

5.  <span data-ttu-id="b23ca-111">結果の一覧で、削除するグループをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b23ca-111">In the resulting list, click the group that you want to delete, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="b23ca-112">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b23ca-112">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-agent-group"></a><span data-ttu-id="b23ca-113">Windows PowerShell を使用してエージェントグループを削除するには</span><span class="sxs-lookup"><span data-stu-id="b23ca-113">To use Windows PowerShell to delete an agent group</span></span>

1.  <span data-ttu-id="b23ca-114">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="b23ca-114">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="b23ca-115">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b23ca-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b23ca-116">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b23ca-116">At the command line, run:</span></span>
    
        Get-CsRgsAgentGroup -Identity <Application Server service> -Name "<name of agent group>" | Remove-CsRgsAgentGroup
    
    <span data-ttu-id="b23ca-117">例:</span><span class="sxs-lookup"><span data-stu-id="b23ca-117">For example:</span></span>
    
        Get-CsRgsAgentGroup -Identity service:ApplicationServer:redmond.contoso.com -Name "Human Resources" | Remove-CsRgsAgentGroup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b23ca-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="b23ca-118">See Also</span></span>


[<span data-ttu-id="b23ca-119">Lync Server 2013 でエージェントグループを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="b23ca-119">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)  


[<span data-ttu-id="b23ca-120">削除-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="b23ca-120">Remove-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsAgentGroup)  
[<span data-ttu-id="b23ca-121">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="b23ca-121">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

