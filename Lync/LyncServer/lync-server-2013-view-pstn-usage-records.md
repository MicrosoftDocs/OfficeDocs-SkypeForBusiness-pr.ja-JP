---
title: 'Lync Server 2013: PSTN 使用法レコードの表示'
description: 'Lync Server 2013: PSTN 使用法レコードを表示します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PSTN usage records
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398458(v=OCS.15)
ms:contentKeyID: 48184361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 924ea74a4bb19b36da91bf97f51fbf4af54835a5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579623"
---
# <a name="view-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="ecccf-103">Lync Server 2013 での PSTN 使用法レコードの表示</span><span class="sxs-lookup"><span data-stu-id="ecccf-103">View PSTN usage records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ecccf-104">_**トピックの最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="ecccf-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="ecccf-105">公衆交換電話網 (PSTN) 使用法レコードは、組織内のさまざまなユーザーまたはグループが利用できる通話のクラス (内部、市内、長距離など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="ecccf-105">A public switched telephone network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="ecccf-106">詳細については、「計画」のドキュメントの「 [Lync Server 2013 の PSTN 使用法レコード](lync-server-2013-pstn-usage-records.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecccf-106">For details, see [PSTN usage records in Lync Server 2013](lync-server-2013-pstn-usage-records.md) in the Planning documentation.</span></span>

<div>

## <a name="to-view-a-pstn-usage-record-by-using-lync-server-control-panel"></a><span data-ttu-id="ecccf-107">Lync Server コントロールパネルを使用して PSTN 使用法レコードを表示するには</span><span class="sxs-lookup"><span data-stu-id="ecccf-107">To view a PSTN usage record by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="ecccf-108">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ecccf-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="ecccf-109">詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecccf-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ecccf-110">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ecccf-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ecccf-111">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecccf-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ecccf-112">左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**PSTN 使用法**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecccf-112">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

4.  <span data-ttu-id="ecccf-113">[**PSTN 使用法**] ページで、表示する PSTN 使用法レコードを選択状態にし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecccf-113">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ecccf-114">選択した PSTN 使用法レコードの読み取り専用ページに、関連付けられたルートと関連付けられた音声ポリシーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ecccf-114">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

    
    </div>

</div>

<div>

## <a name="viewing-pstn-usage-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ecccf-115">Windows PowerShell コマンドレットを使用して PSTN 使用法情報を表示する</span><span class="sxs-lookup"><span data-stu-id="ecccf-115">Viewing PSTN Usage Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ecccf-116">Windows PowerShell および **Get-CsPstnUsage** コマンドレットを使用して、PSTN 使用法を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="ecccf-116">You can also view PSTN usages by using Windows PowerShell and the **Get-CsPstnUsage** cmdlet.</span></span> <span data-ttu-id="ecccf-117">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="ecccf-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ecccf-118">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecccf-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-pstn-usage-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ecccf-119">Windows PowerShell コマンドレットを使用して PSTN 使用状況の情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="ecccf-119">To view PSTN usage information by using Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="ecccf-120">すべての PSTN 使用法に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ecccf-120">To view information about all of your PSTN usages, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsPstnUsage
    
    <span data-ttu-id="ecccf-121">このコマンドは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="ecccf-121">This command returns information similar to the following:</span></span>
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

</div>

<span data-ttu-id="ecccf-122">詳細については、「[Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecccf-122">For details, see [Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ecccf-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="ecccf-123">See Also</span></span>


[<span data-ttu-id="ecccf-124">Lync Server 2013 で音声ポリシーを作成し、PSTN 使用法レコードを構成する</span><span class="sxs-lookup"><span data-stu-id="ecccf-124">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="ecccf-125">Lync Server 2013 での音声ポリシーの変更と PSTN 使用法レコードの構成</span><span class="sxs-lookup"><span data-stu-id="ecccf-125">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

