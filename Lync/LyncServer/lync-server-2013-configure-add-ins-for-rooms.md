---
title: 'Lync Server 2013: ルームのアドインの構成'
description: 'Lync Server 2013: ルームのアドインを構成します。'
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
ms.openlocfilehash: 803bff81fa76bf5a7d2d408c93ba9247ead72510
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546753"
---
# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a><span data-ttu-id="04f90-103">Lync Server 2013 でのルームのアドインの構成</span><span class="sxs-lookup"><span data-stu-id="04f90-103">Configure add-ins for rooms in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04f90-104">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="04f90-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="04f90-105">Lync Server 2013 コントロールパネルで、[**常設チャット**] ページの [**アドイン**] セクションを使用して、url を常設チャットルームに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="04f90-105">In Lync Server 2013 Control Panel, you can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="04f90-106">これらの Url は、会話機能拡張ウィンドウのチャットルームの Lync 2013 クライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="04f90-106">These URLs appear in the Lync 2013 client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="04f90-107">管理者は登録されたアドインの一覧にアドインを追加する必要があり、チャットルームマネージャー/作成者は、ユーザーが Lync 2013 クライアントでこのアップグレードを表示する前に、登録済みのアドインの1つにルームを関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="04f90-107">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators have to associate rooms with one of the registered add-ins before users can see this upgrade in their Lync 2013 client.</span></span>

<span data-ttu-id="04f90-108">アドインは、ルーム内でのエクスペリエンスを拡張するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="04f90-108">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="04f90-109">一般的なアドインには、株式相場がチャットルームに投稿されたときに受信する Silverlight アプリケーションを指す URL が含まれていることがあります。また、機能拡張ウィンドウで株価情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="04f90-109">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="04f90-110">チャット ルームに OneNote 2013 の URL をアドインとして埋め込んで、"優先事項" や "今日のトピック" などの共有コンテキストを組み込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="04f90-110">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="04f90-111">チャット ルームのアドインを構成するには</span><span class="sxs-lookup"><span data-stu-id="04f90-111">To configure Add-ins for chat rooms</span></span>

1.  <span data-ttu-id="04f90-112">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="04f90-112">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="04f90-113">[ **スタート** ] メニューから [Lync Server コントロールパネル] を選択するか、ブラウザーウィンドウを開いて管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="04f90-113">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="04f90-114">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04f90-114">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="04f90-115">Windows PowerShell コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="04f90-115">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="04f90-116">詳細については、「展開」のドキュメントの「 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell コマンドレットを使用して常設チャットサーバーを構成する</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04f90-116">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="04f90-117">左側のナビゲーション バーで [**常設チャット**] をクリックして、[**アドイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04f90-117">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="04f90-118">複数の常設チャットサーバープールを展開する場合は、ドロップダウンリストから適切なプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="04f90-118">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4.  <span data-ttu-id="04f90-119">[**アドイン**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04f90-119">On the **Add-in** page, click **New**.</span></span>

5.  <span data-ttu-id="04f90-120">**[サービスの選択**] で、アドインを作成する必要がある常設チャットサーバープールに対応するサービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="04f90-120">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="04f90-121">アドインをプール間で移動したり、複数のプールで共有したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="04f90-121">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6.  <span data-ttu-id="04f90-122">[**新規 アドイン**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="04f90-122">In **New Add-in**, do the following:</span></span>
    
      - <span data-ttu-id="04f90-123">[**名前**] に、新しいアドインの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="04f90-123">In **Name**, specify a name for the new add-in.</span></span>
    
      - <span data-ttu-id="04f90-p106">[**URL**] で、アドインに関連付ける URL を指定します。URL には http および https プロトコルのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="04f90-p106">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7.  <span data-ttu-id="04f90-126">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04f90-126">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="04f90-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="04f90-127">See Also</span></span>


[<span data-ttu-id="04f90-128">Lync Server 2013 管理ツールを開く</span><span class="sxs-lookup"><span data-stu-id="04f90-128">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)  


[<span data-ttu-id="04f90-129">Windows PowerShell コマンドレットを使用して常設チャットサーバーを構成する</span><span class="sxs-lookup"><span data-stu-id="04f90-129">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

