---
title: 'Lync Server 2013: ルームのアドインの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure add-ins for rooms
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204878(v=OCS.15)
ms:contentKeyID: 48184090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8389f72394be26057eb12560c054bd5292b528f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757861"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a><span data-ttu-id="db8d8-102">Lync Server 2013 でのルームのアドインの構成</span><span class="sxs-lookup"><span data-stu-id="db8d8-102">Configure add-ins for rooms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db8d8-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="db8d8-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="db8d8-104">Lync Server 2013 コントロールパネルでは、**常設チャット**ページの [**アドイン**] セクションを使用して、url を常設チャットルームに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="db8d8-104">In Lync Server 2013 Control Panel, you can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="db8d8-105">これらの Url は、会話機能拡張ウィンドウのチャットルームの Lync 2013 クライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="db8d8-105">These URLs appear in the Lync 2013 client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="db8d8-106">管理者が、登録されたアドインの一覧にアドインを追加する必要があります。チャットルームマネージャー/作成者は、ユーザーが Lync 2013 クライアントでこのアップグレードを表示する前に、登録されているアドインのいずれかにルームを関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="db8d8-106">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators have to associate rooms with one of the registered add-ins before users can see this upgrade in their Lync 2013 client.</span></span>

<span data-ttu-id="db8d8-107">アドインは、ルーム内でのエクスペリエンスを拡張するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="db8d8-107">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="db8d8-108">一般的なアドインには、株式のティッカーがチャットルームに投稿されたときに受信する Silverlight アプリケーションを指す URL が含まれている場合があります。また、拡張機能ウィンドウには、株式履歴が表示されます。</span><span class="sxs-lookup"><span data-stu-id="db8d8-108">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="db8d8-109">チャット ルームに OneNote 2013 の URL をアドインとして埋め込んで、"優先事項" や "今日のトピック" などの共有コンテキストを組み込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="db8d8-109">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="db8d8-110">チャット ルームのアドインを構成するには</span><span class="sxs-lookup"><span data-stu-id="db8d8-110">To configure Add-ins for chat rooms</span></span>

1.  <span data-ttu-id="db8d8-111">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="db8d8-111">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="db8d8-112">[**スタート**] メニューから [Lync Server コントロールパネル] を選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="db8d8-112">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="db8d8-113">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="db8d8-113">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="db8d8-114">Windows PowerShell コマンドレットを使うこともできます。</span><span class="sxs-lookup"><span data-stu-id="db8d8-114">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="db8d8-115">詳細については、展開ドキュメントの「 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell コマンドレットを使用して常設チャットサーバーを構成</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db8d8-115">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="db8d8-116">左側のナビゲーション バーで [**常設チャット**] をクリックして、[**アドイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db8d8-116">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="db8d8-117">複数の常設チャットサーバープールの展開の場合、ドロップダウンリストから適切なプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="db8d8-117">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4.  <span data-ttu-id="db8d8-118">[**アドイン**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db8d8-118">On the **Add-in** page, click **New**.</span></span>

5.  <span data-ttu-id="db8d8-119">[**サービスの選択**] で、アドインを作成する必要がある常設チャットサーバープールに対応するサービスを選びます。</span><span class="sxs-lookup"><span data-stu-id="db8d8-119">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="db8d8-120">アドインは、プール間で移動したり、異なるプール間で共有したりできません。</span><span class="sxs-lookup"><span data-stu-id="db8d8-120">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6.  <span data-ttu-id="db8d8-121">[**新しいアドイン**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="db8d8-121">In **New Add-in**, do the following:</span></span>
    
      - <span data-ttu-id="db8d8-122">[**名前**] に、新しいアドインの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="db8d8-122">In **Name**, specify a name for the new add-in.</span></span>
    
      - <span data-ttu-id="db8d8-p106">[**URL**] に、アドインに関連付ける URL を指定します。URL には、http および https プロトコルのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="db8d8-p106">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7.  <span data-ttu-id="db8d8-125">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db8d8-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="db8d8-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="db8d8-126">See Also</span></span>


[<span data-ttu-id="db8d8-127">Lync Server 2013 管理ツールを開く</span><span class="sxs-lookup"><span data-stu-id="db8d8-127">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)  


[<span data-ttu-id="db8d8-128">Windows PowerShell コマンドレットを使用した常設チャット サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="db8d8-128">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

