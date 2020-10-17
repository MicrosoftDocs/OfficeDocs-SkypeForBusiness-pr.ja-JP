---
title: 'Lync Server 2013: 発信通話用のボイスルートの構成'
description: 'Lync Server 2013: 発信通話用のボイスルートの構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice routes for outbound calls
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48183875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dd0d712295ecdd0e9a517330abcff36021e996d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542213"
---
# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a><span data-ttu-id="f551d-103">Lync Server 2013 での発信通話の音声ルートの構成</span><span class="sxs-lookup"><span data-stu-id="f551d-103">Configuring voice routes for outbound calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f551d-104">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f551d-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f551d-105">Lync Server 2013 voice route は、宛先の電話番号を1つまたは複数の公衆交換電話網 (PSTN) ゲートウェイまたは SIP トランクおよび1つ以上の PSTN 使用法レコードに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="f551d-105">A Lync Server 2013 voice route associates destination phone numbers with one or more public switched telephone network (PSTN) gateways or SIP trunks and one or more PSTN usage records.</span></span>

<span data-ttu-id="f551d-106">**Lync Server コントロールパネルを使用して音声ルートを表示するには**</span><span class="sxs-lookup"><span data-stu-id="f551d-106">**To view voice routes by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="f551d-107">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f551d-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f551d-108">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f551d-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="f551d-109">[**音声のルーティング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f551d-109">Click **Voice Routing**.</span></span>

3.  <span data-ttu-id="f551d-110">[**ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f551d-110">Click **Route**.</span></span>

4.  <span data-ttu-id="f551d-p102">音声ルートをダブルクリックし、音声ルートの一覧から追加のプロパティを表示するか、ルートを選択し、[**編集**] をクリックします。次に、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f551d-p102">Double-click a voice route to view additional properties from the list of voice routes, or select the route and click **Edit**. Then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f551d-113">一度に 1 つのルートの詳細情報しか表示できません。</span><span class="sxs-lookup"><span data-stu-id="f551d-113">You can only view detailed information for a single route at a time.</span></span>

    
    </div>

<span data-ttu-id="f551d-114">**Windows PowerShell を使用して音声ルートを表示するには**</span><span class="sxs-lookup"><span data-stu-id="f551d-114">**To view voice routes by using Windows PowerShell**</span></span>

  - <span data-ttu-id="f551d-115">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f551d-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="f551d-116">音声ルートは、Windows PowerShell と **get-csvoiceroute** コマンドレットを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="f551d-116">Voice routes can be viewed by using Windows PowerShell and the **Get-CsVoiceRoute** cmdlet.</span></span> <span data-ttu-id="f551d-117">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="f551d-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f551d-118">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="f551d-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="f551d-119">すべての音声ルートに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f551d-119">To view information about all of your voice routes, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsVoiceRoute
    
    <span data-ttu-id="f551d-120">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f551d-120">That will return information similar to this:</span></span>
    
        Identity          : global
        Priority          : -1
        Description       :
        NumberPattern     : ^(\+1[0-9]{10})$
        PstnUsages        : {}
        PstnGatewayList   : {}
        Name              : global
        SuppressCallerId  :
        AlternateCallerId :

<div>


> [!NOTE]  
> <span data-ttu-id="f551d-121">詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-voice-routes.md">Voice 回送 In Lync Server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f551d-121">For details, see <A href="lync-server-2013-voice-routes.md">Voice routes in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f551d-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f551d-122">In This Section</span></span>

  - [<span data-ttu-id="f551d-123">Lync Server 2013 での音声ルートの作成</span><span class="sxs-lookup"><span data-stu-id="f551d-123">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)

  - [<span data-ttu-id="f551d-124">Lync Server 2013 での音声ルートの変更</span><span class="sxs-lookup"><span data-stu-id="f551d-124">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f551d-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="f551d-125">See Also</span></span>


[<span data-ttu-id="f551d-126">Lync Server 2013 での音声ルーティングの管理</span><span class="sxs-lookup"><span data-stu-id="f551d-126">Managing voice routing in Lync Server 2013</span></span>](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

