---
title: 'Lync Server 2013: 応答グループキューを削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a Response Group queue
ms:assetid: 67c7a489-8c5f-4c6b-9387-9d4c11d43695
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521008(v=OCS.15)
ms:contentKeyID: 48184356
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14f713407756863e1976be536cf16e9557c93a56
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-response-group-queue-in-lync-server-2013"></a><span data-ttu-id="477e3-102">Lync Server 2013 で応答グループキューを削除する</span><span class="sxs-lookup"><span data-stu-id="477e3-102">Delete a Response Group queue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="477e3-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="477e3-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="477e3-104">キューを削除するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="477e3-104">Use one of the following procedures to delete a queue.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-a-queue"></a><span data-ttu-id="477e3-105">Lync Server コントロールパネルを使用してキューを削除するには</span><span class="sxs-lookup"><span data-stu-id="477e3-105">To use Lync Server Control Panel to delete a queue</span></span>

1.  <span data-ttu-id="477e3-106">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="477e3-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="477e3-107">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="477e3-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="477e3-108">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="477e3-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="477e3-109">左側のナビゲーション バーで [**応答グループ**] をクリックし、[**キュー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="477e3-109">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>

4.  <span data-ttu-id="477e3-110">検索フィールドに、削除するキューの名前の一部またはすべてを入力します。</span><span class="sxs-lookup"><span data-stu-id="477e3-110">In the search field, type part or all of the name of the queue you want to delete.</span></span>

5.  <span data-ttu-id="477e3-111">キューの一覧で、目的のキューをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="477e3-111">In the list of queues, click the queue that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="477e3-112">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="477e3-112">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-queue"></a><span data-ttu-id="477e3-113">Windows PowerShell を使用してキューを削除するには</span><span class="sxs-lookup"><span data-stu-id="477e3-113">To use Windows PowerShell to delete a queue</span></span>

1.  <span data-ttu-id="477e3-114">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="477e3-114">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="477e3-115">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="477e3-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="477e3-116">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="477e3-116">At the command line, run:</span></span>
    
        Get-CsRgsQueue -Identity <Application Server service> -Name "<name of queue>" | Remove-CsRgsQueue
    
    <span data-ttu-id="477e3-117">例:</span><span class="sxs-lookup"><span data-stu-id="477e3-117">For example:</span></span>
    
        Get-CsRgsQueue -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsQueue

</div>

</div>

<span> </span>

</div>

</div>

</div>

