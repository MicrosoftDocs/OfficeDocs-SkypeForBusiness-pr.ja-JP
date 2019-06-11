---
title: 'Lync Server 2013: ワークフローを削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1aabb1b46d3f67408d586bada6db3d1efaf0538e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a><span data-ttu-id="f41cd-102">Lync Server 2013 でワークフローを削除する</span><span class="sxs-lookup"><span data-stu-id="f41cd-102">Delete a workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f41cd-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f41cd-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f41cd-104">ワークフローを削除するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="f41cd-104">Use one of the following procedures to delete a workflow.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a><span data-ttu-id="f41cd-105">Lync Server コントロールパネルを使用するにはワークフローを削除する</span><span class="sxs-lookup"><span data-stu-id="f41cd-105">To use Lync Server Control Panel delete a workflow</span></span>

1.  <span data-ttu-id="f41cd-106">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="f41cd-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="f41cd-107">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f41cd-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f41cd-108">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f41cd-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f41cd-109">左側のナビゲーション バーで、[**応答グループ**] をクリックし、[**ワークフロー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f41cd-109">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="f41cd-110">[**ワークフロー**] ページで、[**ワークフローの作成または編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f41cd-110">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="f41cd-111">**[サービスの選択**] の検索フィールドに、削除するワークフローをホストしている**ApplicationServer**サービスの名前の一部またはすべてを入力します。</span><span class="sxs-lookup"><span data-stu-id="f41cd-111">In the **Select a Service** search field, type part or all of the name of the **ApplicationServer** service that hosts the workflow that you want to delete.</span></span>

6.  <span data-ttu-id="f41cd-112">サービスの一覧で、目的のサービスをクリックし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f41cd-112">In the list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f41cd-113">応答グループ構成ツールの web ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="f41cd-113">The Response Group Configuration Tool webpage opens.</span></span> <span data-ttu-id="f41cd-114"><STRONG>Https://&lt;webpoolfqdn&gt;/RgsConfig</STRONG>に接続して、Web ブラウザーから直接応答グループ構成ツールの web ページを開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="f41cd-114">You can also open the Response Group Configuration Tool webpage directly from a web browser by connecting to <STRONG>https://&lt;webPoolFqdn&gt;/RgsConfig</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="f41cd-115">[**既存のワークフローの管理**] で、削除するワークフローを見つけ、[**アクション**] の [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f41cd-115">Under **Manage an Existing Workflow**, locate the workflow you want to delete, and then under **Action**, click **Delete**.</span></span>

8.  <span data-ttu-id="f41cd-116">[**はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f41cd-116">Click **Yes**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a><span data-ttu-id="f41cd-117">Windows PowerShell を使用してワークフローを削除するには</span><span class="sxs-lookup"><span data-stu-id="f41cd-117">To use Windows PowerShell to delete a workflow</span></span>

1.  <span data-ttu-id="f41cd-118">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="f41cd-118">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="f41cd-119">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f41cd-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f41cd-120">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f41cd-120">At the command line, run:</span></span>
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    <span data-ttu-id="f41cd-121">例:</span><span class="sxs-lookup"><span data-stu-id="f41cd-121">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

