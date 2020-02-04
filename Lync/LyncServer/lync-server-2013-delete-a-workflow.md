---
title: 'Lync Server 2013: ワークフローを削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ed32780e23cce82027271e74a89fb87e194cc4a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a><span data-ttu-id="25b92-102">Lync Server 2013 でワークフローを削除する</span><span class="sxs-lookup"><span data-stu-id="25b92-102">Delete a workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25b92-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="25b92-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="25b92-104">ワークフローを削除するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="25b92-104">Use one of the following procedures to delete a workflow.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a><span data-ttu-id="25b92-105">Lync Server コントロールパネルを使用するにはワークフローを削除する</span><span class="sxs-lookup"><span data-stu-id="25b92-105">To use Lync Server Control Panel delete a workflow</span></span>

1.  <span data-ttu-id="25b92-106">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="25b92-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="25b92-107">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="25b92-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="25b92-108">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="25b92-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="25b92-109">左側のナビゲーション バーで、[**応答グループ**] をクリックし、[**ワークフロー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="25b92-109">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="25b92-110">[**ワークフロー**] ページで、[**ワークフローの作成または編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="25b92-110">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="25b92-111">**[サービスの選択**] の検索フィールドに、削除するワークフローをホストしている**ApplicationServer**サービスの名前の一部またはすべてを入力します。</span><span class="sxs-lookup"><span data-stu-id="25b92-111">In the **Select a Service** search field, type part or all of the name of the **ApplicationServer** service that hosts the workflow that you want to delete.</span></span>

6.  <span data-ttu-id="25b92-112">サービスの一覧で、目的のサービスをクリックし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="25b92-112">In the list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="25b92-113">応答グループ構成ツールの web ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="25b92-113">The Response Group Configuration Tool webpage opens.</span></span> <span data-ttu-id="25b92-114"><STRONG>Https://&lt;webpoolfqdn&gt;/RgsConfig</STRONG>に接続して、Web ブラウザーから直接応答グループ構成ツールの web ページを開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="25b92-114">You can also open the Response Group Configuration Tool webpage directly from a web browser by connecting to <STRONG>https://&lt;webPoolFqdn&gt;/RgsConfig</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="25b92-115">[**既存のワークフローの管理**] で、削除するワークフローを見つけ、[**アクション**] の [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="25b92-115">Under **Manage an Existing Workflow**, locate the workflow you want to delete, and then under **Action**, click **Delete**.</span></span>

8.  <span data-ttu-id="25b92-116">[**はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="25b92-116">Click **Yes**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a><span data-ttu-id="25b92-117">Windows PowerShell を使用してワークフローを削除するには</span><span class="sxs-lookup"><span data-stu-id="25b92-117">To use Windows PowerShell to delete a workflow</span></span>

1.  <span data-ttu-id="25b92-118">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="25b92-118">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="25b92-119">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="25b92-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="25b92-120">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="25b92-120">At the command line, run:</span></span>
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    <span data-ttu-id="25b92-121">例:</span><span class="sxs-lookup"><span data-stu-id="25b92-121">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

