---
title: 'Lync Server 2013: 発信通話用のボイス ルートの構成'
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
ms.openlocfilehash: f8b425ce1e0627645f84223f36f6fc0de18b5af8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a><span data-ttu-id="c1be5-102">Lync Server 2013 での発信通話用のボイス ルートの構成</span><span class="sxs-lookup"><span data-stu-id="c1be5-102">Configuring voice routes for outbound calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1be5-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c1be5-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c1be5-104">Lync Server 2013 のボイスルーティングは、1つ以上の公衆交換電話網 (PSTN) ゲートウェイまたは SIP trunks と1つ以上の PSTN 使用状況レコードとの接続先電話番号を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="c1be5-104">A Lync Server 2013 voice route associates destination phone numbers with one or more public switched telephone network (PSTN) gateways or SIP trunks and one or more PSTN usage records.</span></span>

<span data-ttu-id="c1be5-105">**Lync Server コントロールパネルを使用して音声ルートを表示するには**</span><span class="sxs-lookup"><span data-stu-id="c1be5-105">**To view voice routes by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="c1be5-106">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c1be5-106">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c1be5-107">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c1be5-107">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="c1be5-108">[**音声ルーティング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1be5-108">Click **Voice Routing**.</span></span>

3.  <span data-ttu-id="c1be5-109">[**ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1be5-109">Click **Route**.</span></span>

4.  <span data-ttu-id="c1be5-110">ボイスルートをダブルクリックして、音声ルートの一覧からその他のプロパティを表示するか、ルートを選んで [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1be5-110">Double-click a voice route to view additional properties from the list of voice routes, or select the route and click **Edit**.</span></span> <span data-ttu-id="c1be5-111">次に、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1be5-111">Then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1be5-112">一度に1つのルートの詳細情報のみを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="c1be5-112">You can only view detailed information for a single route at a time.</span></span>

    
    </div>

<span data-ttu-id="c1be5-113">**Windows PowerShell を使用して音声ルートを表示するには**</span><span class="sxs-lookup"><span data-stu-id="c1be5-113">**To view voice routes by using Windows PowerShell**</span></span>

  - <span data-ttu-id="c1be5-114">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1be5-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="c1be5-115">音声ルートを表示するには、Windows PowerShell と**CsVoiceRoute**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c1be5-115">Voice routes can be viewed by using Windows PowerShell and the **Get-CsVoiceRoute** cmdlet.</span></span> <span data-ttu-id="c1be5-116">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="c1be5-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c1be5-117">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1be5-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="c1be5-118">すべての音声ルートに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c1be5-118">To view information about all of your voice routes, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsVoiceRoute
    
    <span data-ttu-id="c1be5-119">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1be5-119">That will return information similar to this:</span></span>
    
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
> <span data-ttu-id="c1be5-120">詳細については、計画ドキュメントの「 <A href="lync-server-2013-voice-routes.md">Lync Server 2013 の音声ルート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1be5-120">For details, see <A href="lync-server-2013-voice-routes.md">Voice routes in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c1be5-121">このセクション中</span><span class="sxs-lookup"><span data-stu-id="c1be5-121">In This Section</span></span>

  - [<span data-ttu-id="c1be5-122">Lync Server 2013 での音声ルートの作成</span><span class="sxs-lookup"><span data-stu-id="c1be5-122">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)

  - [<span data-ttu-id="c1be5-123">Lync Server 2013 での音声ルートの変更</span><span class="sxs-lookup"><span data-stu-id="c1be5-123">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c1be5-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1be5-124">See Also</span></span>


[<span data-ttu-id="c1be5-125">Lync Server 2013 での音声ルーティングの管理</span><span class="sxs-lookup"><span data-stu-id="c1be5-125">Managing voice routing in Lync Server 2013</span></span>](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

